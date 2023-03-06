JavaScript變數與資料型別
=================

變數
--

*   變數名稱的第一個字母必須為英文字母、底線或是錢字號，後面可以是英文字母、底線或錢字號以及數字。例如：`_name`、`$price`、`firstName`。
*   變數名稱不可以是保留字(Reserved Words)和關鍵字(keyword)。例如：`var`、`let`、`const`、`if`、`else`等等。
*   JavaScript語法有分大小寫，所以`app`和`APP`會被認為是不同的變數。
*   ES6開始之後，宣告變數分成了變數和常數，除了`var`之外還有`let`和`const`。其中`let`和`const`都是區塊作用域。
*   變數在宣告的時候無需指定型別，如果沒有宣告變數的情況就直接使用，就會出現`ReferenceError`的錯誤。
*   如果沒有宣告變數，而直接給值的話是可以的，但是強烈不建議這麼做，因為會自動轉成全域變數。
*   `var`宣告過後依然可以再次宣告，但是`let`卻不行，會觸發`SyntaxError`。

資料型別
----

*   JavaScript支援的型別主要可以分成基本型別(Primitives)和物件型別(Object)兩大類。
*   基本型別有`string`、`number`、`bool`、`null`、`undefined`，而ES6後又新增了一個`Symbol`。
*   除了上述幾種型別，其他都可以歸類至物件型別(Object)。
*   判斷型別的方法可以用`typeof`來進行判斷。例如：`typeof "Hello"`會返回`string`。
*   JavaScript沒有char的概念，只有字串的概念。
*   字串使用雙引號和單引號包夾住，兩者不可混用，意思就是用單引號開頭就必須要用單引號結尾，JavaScript中單引號和雙引號作用也相同。例如：`'Hello'`、`"World"`。
*   ES6開始後又新增一種特殊字串樣板字面值(template literal)，這種新特性在字串使用上提供了很大的靈活性，例如可以支援多行字串，允許變數直接嵌入字串，甚至可以嵌入運算式。例如：
javascript

```javascript
const name = "Alice";
const age = 18;
console.log(`My name is ${name}, and I'm ${age} years old.`);
// My name is Alice, and I'm 18 years old.
```

*   數字型別有整數和小數點兩種，另外還有幾種特殊的數字`Infinity`(無限大)、`-Infinity`(負無限大)和NaN(不是數值 "Not a Number")。例如：`10`、`3.14`、`Infinity`。
*   NaN代表的是不是一個數字，但是用`typeof`運算子判斷型態會告訴我們是一個數字(number)。例如：`typeof NaN`會返回`number`。
*   NaN和任何數字做數學運算結果都會是NaN，甚至不等於他自己。例如：`NaN + 1`會返回`NaN`、`NaN === NaN`會返回`false`。
*   要檢查一個變數是否是NaN可以使用`isNaN`來判斷。例如：`isNaN(NaN)`會返回`true`。
*   JavaScript是基於IEEE754二進位浮點數算數標準，所以在使用`0.1+0.2===0.3`時會返回`false`，因為十進位的小數無法完美的用二進位的方式表示，所以會存在精度問題。
*   如果要比較浮點數，可以利用ES6提供的最小精度值(Number.EPSILON)來進行比較。例如：

javascript

```javascript
const a = 0.1;
const b = 0.2;
const c = 0.3;
if (Math.abs((a + b) - c) < Number.EPSILON) {
  console.log("a + b = c");
}
```

*   undefined代表的是變數還沒有給值，所以不知道是什麼。例如：`let x;`，此時變數`x`的值就是`undefined`。
*   null代表的是變數可能曾經有值，可能沒有值，現在也沒有值。例如：`let x = null;`。
*   在非全域作用範圍下，undefined允許被當作變數名稱使用，而且這個變數的值是『可以』被更改的，甚至做為參數使用也是可以的。例如：

javascript

```javascript
function test(undefined) {
  console.log(undefined); // "Hello"
}
test("Hello");
```

在上面的範例中，`test`函式的參數名稱是`undefined`，但是在呼叫函式的時候，傳入的是`"Hello"`，所以會印出`"Hello"`。這是因為在函式作用域中，變數名稱會優先使用函式參數中的名稱，而不是全域作用範圍中的`undefined`值。如果在全域作用範圍中定義了一個變數或函式名稱為`undefined`，那麼在這個作用範圍中就無法使用`undefined\`來當作變數名稱或函式名稱使用。
