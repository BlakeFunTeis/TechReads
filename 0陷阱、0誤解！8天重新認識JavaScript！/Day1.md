# JavaScript變數和型別筆記

- JavaScript變數的規則：
  - 第一個字母必須為英文字母、底線或是錢字號
  - 後面可以是英文字母、底線、錢字號或數字
  - 變數名稱不可以是保留字(Reserved Words)和關鍵字(keyword)
  - JavaScript的語法有分大小寫，app 和 APP 會被認為是不同的變數
  - 從1.3開始可以支援中文變數命名，但是不建議使用，因為其他語言的系統開啟可能會是亂碼

- 變數的宣告：
  - ES6以前使用var，ES6之後也可以使用let和const
  - var和let最大的差異就是作用範圍不同
  - 變數在宣告的時候無需指定型別
  - 如果沒有宣告變數的情況就直接使用，會出現ReferenceError的錯誤
  - 如果沒有宣告變數而直接給值的話是可以的，但是不建議這麼做，因為會自動轉成全域變數
  - var宣告過後依然可以再次宣告，但是let卻不行，會觸發SyntaxError

- JavaScript的型別：
  - 分成基本型別(Primitives)和物件型別(Object)兩大類
  - 基本型別有string、number、bool、null、undefined，ES6後又新增了Symbol
  - 除了上面這幾種之外，其他都可以歸類至物件型別(Obejct)
  - 判斷型別的方法可以用typeof來進行判斷
  - JavaScript沒有char的概念，只有字串的概念
  - 字串使用雙引號和單引號包夾住，兩者不可混用，用單引號開頭就必須用單引號結尾
  - ES6開始後又新增一種特殊字串樣板字面值(template literal)，支援多行字串和變數直接嵌入字串甚至運算式也可以

