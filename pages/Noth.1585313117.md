---
title: [Android / Kotlin] ノッチ（ディスプレイカット / 切り欠き）の部分も表示する方法
tags: Android Kotlin
author: takusan_23
slide: false
---
ノッチを付けずに戦ってるメーカーはかっこいいと思います。

# ノッチ、ディスプレイカット、切り欠きとは
iPhone X（嘘ですEssential Phoneです）から始まった上のかけている部分。この部分にはカメラや顔認証に必要な部品があったりする（顔認証対応端末のみ）。
中華系が真似したせいで流行ってしまった？

Pixel 3 XLに関しては他端末よりも大きめのノッチがついてたりする。（カメラが自撮り側のみ２つついているため。広角だよ←使ったことないけど）

基本的にはこの部分にはステータスバー（🔋や📶や📳等があるバーのこと）があってアプリは侵略できない。

# ノッチがない端末でノッチを出す方法

開発者向けオプション→ディスプレイカット→縦長のカットアウト
を選択することでノッチを表示できます。
ステータスバーが広くなって違和感あると思うよ。

# ノッチがある端末でノッチを隠す（利用しない）方法
Pixel 3 XLでの場合です。
開発者向けオプション→ディスプレイカット→非表示　
を選択することでノッチを利用しない設定にできます。

その他サードパーティのアプリでノッチ領域の背景を黒くするアプリなどもあるのでどうしても気になる人は入れてみては？。

# 侵略するには
![Screenshot_1578906820.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/409918/7b9cf20d-ad5b-a631-bcaf-531a970da9ab.png)

こんなふうに上にも表示させたい場合は、

```kotlin
//ステータスバー透明化＋タイトルバー非表示＋ノッチ領域にも侵略
window.addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS)
supportActionBar?.hide()
if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.P) {
    val attrib = window.attributes
    attrib.layoutInDisplayCutoutMode =
        WindowManager.LayoutParams.LAYOUT_IN_DISPLAY_CUTOUT_MODE_SHORT_EDGES
}
```

これで動きます。
ActionBarを非表示にしてますが、どっかでそもそも表示しない設定にしている場合は
二行目を消したほうがいいと思います。


これでノッチ領域に侵略することに成功しました。

![Screenshot_1578906694.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/409918/38701a36-6bfe-969e-1b62-013a5bcfd64c.png)

以上です。お疲れさまでした。８８８８８８８８８

# 参考にしました
https://stackoverflow.com/questions/49190381/fullscreen-app-with-displaycutout

android display cutout full screen って検索したんですけどGoogle先生すごい。
