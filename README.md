# 目次

<!-- TOC -->

- [目次](#目次)
- [参考記事](#参考記事)
- [概要](#概要)
- [サンプルコード](#サンプルコード)

<!-- /TOC -->

# 参考記事

https://qiita.com/n0bisuke/items/66abf6ca1c12f495aa04

# 概要

- 6 段階あって左から秒,分,時間,日,月,曜日
- 秒はオプショナル

# サンプルコード

ここにないものは参考記事を見ながら、  
実際の機能を使う前に文字列出力で都度テストする。

```js
// strictモード
"use strict";

// node-cronを呼び出して変数cronから実行可能に
const cron = require("node-cron");

//// node app.jsで実行する
// 毎秒実行
// cron.schedule("* * * * * *", () =>
//   console.log(
//     // 現在時刻
//     new Date().getHours().toString() +
//       new Date().getMinutes().toString() +
//       new Date().getSeconds().toString()
//   )
// );

// 毎分1秒,10秒,30秒,55秒に実行
// cron.schedule("1,10,30,55 * * * * *", () =>
//   console.log(
//     // 現在時刻
//     new Date().getHours().toString() +
//       new Date().getMinutes().toString() +
//       new Date().getSeconds().toString()
//   )
// );

// 毎分1秒~10秒に実行
// cron.schedule("1-10 * * * * *", () =>
//   console.log(
//     // 現在時刻
//     new Date().getHours().toString() +
//       new Date().getMinutes().toString() +
//       new Date().getSeconds().toString()
//   )
// );

// 3秒ごとに実行
// cron.schedule("*/3 * * * * *", () =>
//   console.log(
//     // 現在時刻
//     new Date().getHours().toString() +
//       new Date().getMinutes().toString() +
//       new Date().getSeconds().toString()
//   )
// );

// 2分ごとに実行
cron.schedule("0 */3 * * * *", () =>
  console.log(
    // 現在時刻
    new Date().getHours().toString() +
      new Date().getMinutes().toString() +
      new Date().getSeconds().toString()
  )
);

// これだと毎秒実行されてしまう
// cron.schedule("* */3 * * * *", () =>
//   console.log(
//     // 現在時刻
//     new Date().getHours().toString() +
//       new Date().getMinutes().toString() +
//       new Date().getSeconds().toString()
//   )
// );
```
