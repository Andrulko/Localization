---
title: Presenceクラス
description: すべてのPreMIDのプレゼンスのメインクラス
published: true
date: 2020-04-07T18:55:34.585Z
tags:
---

# Presenceクラス

## 説明

`Presence`クラスにはプレゼンスを作成するのに必要なメソッドがあるので、とても便利です。

 クラスを作成する時は、`clientId`プロパティを指定してください。

```typescript
let presence = new Presence({
    clientId: "514271496134389561" // clientIdの例
});
```

`Presence`クラスには、2つの利用可能なプロパティがあります。

#### `clientId`

`clientId`プロパティは、IDを使用してアセットやロゴを表示するので、プレゼンスを動作させるのに必要です。

あなたのプレゼンスのID等はDiscordの[アプリケーションページ](https://discordapp.com/developers/applications)から取得できます。

## メソッド

### `setActivity(presenceData, Boolean)`

提供されたデータに基づいて、プロフィールのアクティビティをセットします。

1つ目のパラメーターには、プロフィールに表示させたい情報を取得するために `presenceData` インターフェースが必須です。

2つ目のパラメーターではプレゼンスが何かをプレイ中かどうかを定義します。 `presenceData` に時刻を提供する場合は、常に `true` を使用してください。

### `clearActivity()`

現在のアクティビティ、キー割り当てとトレーのタイトルを削除します。

### `setTrayTitle(String)`

> このメソッドはmacOSのみで動作します。 
> 
> {.is-warning}

メニューバー上のトレーのタイトルを設定します。

### `getStrings(Object)`

拡張機能から、翻訳された文字列を取得できます。 文字列のキー(`keyValue`が文字列の値)を含んだ`Object`を提供する必要があります。 このエンドポイントを使用していくつかの文字列を見つけることができます: `https://api.premid.app/v2/langFIle/extension/en`

```typescript
// '再生中' と '一時停止中' の文字列を
// 拡張機能から取得する
strings = await presence.getStrings({
    play: "presence.playback.playing",
    pause: "presence.playback.paused"
});
```

### `getSetting(String)`
Returns value of setting.
```typescript
var setting = await presence.getSetting("pdexID"); //Replace pdexID with the id of the setting
console.log(setting); // This will log the value of the setting
```

### `hideSetting(String)`
Hides given setting.
```typescript
presence.hideSetting("pdexID"); //Replace pdexID with the id of the setting
```

### `showSetting(String)`
Shows given setting (Only works if the setting was already hidden).
```typescript
presence.showSetting("pdexID"); //Replace pdexID with the id of the setting
```

### `getPageLetiable(String)`

Returns a variable from the website if it exists.

```typescript
var pageVar = getPageLetiable('.pageVar');
console.log(pageVar); // This will log the "Variable content"
```

## `presenceData` インターフェース

The `presenceData` interface is recommended to use when you are using the `setActivity()` method.

This interface has following variables, all of them are optional.

<table>
  <thead>
    <tr>
      <th style="text-align:left">変数</th>
      <th style="text-align:left">概要</th>
      <th style="text-align:left">Type</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">details</td>
      <td style="text-align:left">プレゼンス内の最初の行, 一般にヘッダーとして使用されています</td>
      <td style="text-align:left"><code>String</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">state</td>
      <td style="text-align:left">プレゼンス内の2行目の文字列</td>
      <td style="text-align:left"><code>String</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">startTimestamp</td>
      <td style="text-align:left">現在の時刻を指定します<br>
        <code>hours:minutes:seconds</code> の形式で残り時間を表示するのに使用します
          <br>時間を <code>timestamp</code> に変換しなければ、誤った時間が表示されます
      </td>
      <td style="text-align:left"><code>Number</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">endTimestamp</td>
      <td style="text-align:left">全体の長さを指定します
        <br><code>hours:minutes:seconds</code> の形式で残り時間を表示するのに使用します
          <br>時間を <code>timestamp</code> に変換しなければ、誤った時間が表示されます
      </td>
      <td style="text-align:left"><code>Number</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">largeImageKey</td>
      <td style="text-align:left">プレゼンスのロゴを指定します</td>
      <td style="text-align:left"><code>String</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">smallImageKey</td>
      <td style="text-align:left">プレゼンス内の、ロゴの横の小さいアイコンを指定します</td>
      <td style="text-align:left"><code>String</code>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">smallImageText</td>
      <td style="text-align:left">小さいアイコンにカーソルを合わせたときに表示する内容を指定します</td>
      <td style="text-align:left"><code>String</code>
      </td>
    </tr>
  </tbody>
</table>

```typescript
var presenceData: presenceData = {
    details: "My title",
    state: "My description",
    largeImageKey: "service_logo",
    smallImageKey: "small_service_icon",
    smallImageText: "You hovered me, and what now?",
    startTimestamp: 1564444631188,
    endTimestamp: 1564444634734
};
```

## イベント

Events allow you to detect and handle some changes or calls that were made. You can subscribe to events using the `on` method.

```typescript
presence.on("UpdateData", async () => {
    // Do something when data gets updated.
});
```

There are few events available:

#### `UpdateData`

This event is fired every time the presence is being updated.

#### `iFrameData`

Fired when data is received from iFrame script.
