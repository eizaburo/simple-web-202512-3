GAS側のコード

```js
function doPost(e){

  //パラメータ取得
  const title = e.parameter.title;
  const email = e.parameter.email;
  const message = e.parameter.message;

  //スプレッドシート用意
  const ss = SpreadsheetApp.getActiveSpreadsheet();
  const sheet = ss.getSheetByName("シート1");

  //書き込み
  sheet.appendRow([title, email, message, new Date()]);

  //レスポンス
  return ContentService.createTextOutput("受け付けました。");

}
```