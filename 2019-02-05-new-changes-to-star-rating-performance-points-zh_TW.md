---
layout: post
title: "Changes to osu! Star Rating / Performance Points"
date: 2019-02-07 03:00:00 +0000
---

在好幾年的停滯之後，星數與表現分數(PP)的計算終於有了些改變，讓我們看看有啥變化吧。

![](/resources/star-rating.jpg)
這次的變動是由Xexxar帶頭與社群以及團隊的許多人合作，幾個月來在[osu! development discord server](https://discord.gg/ppy)中提出修訂。最終的目標是要去更新已經許多年沒有大改動的osu!競爭發展的核心。從難度計算方法最後一次被動到現在，高端的技術已經快速成長，這些更新就是希望能重新找回評等與排名的公平性與合理性。

雖然說我們這次的更新並無法去修正*所有*的目前的問題，我們希望這些變動可以讓玩家更能去接觸不同於舊算法所針對的技巧與能力。

此外，這次的更新只針對osu!標準模式(std)，其他遊戲模式也有其他正在進行的工作且將會在接下來幾個月實裝。

比較能接受影片的話，讓Doomsday用20分鐘帶你看過所有改動:

<iframe width="100%" height="420" src="https://www.youtube.com/embed/5rSaXWr_VUM" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

# 更新進度

- ☑ 在這篇文章公開後，一個穩定版更新將會重新計算所有本機的圖譜。這或許會花上數分鐘的時間（依圖譜數量而定），計算將會在選歌時背景運行。 **[完成]**
- ☑ 接下來的幾個小時，伺服器端的星數也會更新。 **[完成]**
- ☑ 接下來的24小時， 玩家的總PP數將會更新。這段期間內，排名與個人資料的PP曲線將會暫停更新。 **[完成]**
- ☑ 接下來的4到6小時，所有玩家的排名將會重新計算，會一併將不活躍的玩家過濾**基本上會提升大家的排名** **[完成]**
- 接下來的幾天，所有現存的遊戲成績將會重新計算，並更新個人資料與圖譜紀錄。這段時間內，部分個人資料內的"最佳成績"可能會暫時不可視或順序錯亂 **[進行中]**

所有新建立的成績將會使用最新的演算法

# 調整大略

## 大角度跳

圈圈的排列角度現在會計算到移動的難度(SR)中

![](/resources/wide-angle-chart.png)

舉例：
- [MAX COVERI - RUNNING IN THE 90'S](https://osu.ppy.sh/beatmapsets/739262#osu/1559974) - 6.25* -> 6.34*
- [FELT - Puppet in the Dark (Part I & II)](https://osu.ppy.sh/beatmapsets/829511#osu/1737885) - 6.04* -> 6.63*
- [Momoi Haruko - Luka Luka Night Fever](https://osu.ppy.sh/beatmapsets/21724#osu/83925) - 4.38* -> 4.88*

View on GitHub: [#3839](https://github.com/ppy/osu/pull/3839)

## 高BPM串

200BPM到350BPM的高速的連打(串燒)，難度(SR)將會倍增

![](/resources/high-bpm-chart.png)

舉例：
- [UNDEAD CORPORATION - Everything will freeze](https://osu.ppy.sh/beatmapsets/158023#osu/555797) - 7.65* -> 8.03*

View on GitHub: [#3839](https://github.com/ppy/osu/pull/3839)

## 大間隔連打

間隔很大的連打(串燒)，難度將會稍微減少。這種技巧仍然很強而且很賺，只是沒有以前那麼賺

![](/resources/high-spacing-chart.png)

舉例：
- [GYZE - HONESTY](https://osu.ppy.sh/beatmapsets/586121#osu/1241370) - 7.11* -> 7.03*
- [VINXIS - Sidetracked Day](https://osu.ppy.sh/beatmapsets/728276#osu/1537566) - 7.11* -> 7.04*

View on GitHub: [#3839](https://github.com/ppy/osu/pull/3839)

## 長的滑條

長滑條的難度(SR)已經被顯著提升

![](/resources/long-slider-chart.png)

這項改動也會依照物件與滑條間的距離增加以及間隔時間之縮短而提升難度(SR)

舉例：
- [Fractal - Collide (feat. Danyka Nadeau)](https://osu.ppy.sh/beatmapsets/753365#osu/1586083) - 5.08* -> 5.71*

View on GitHub: [#3839](https://github.com/ppy/osu/pull/3839)

## 高速準度

在高速的圖譜中，低ACC將會拿到更少的PP

![](/resources/speed-accuracy-chart.png)

舉例：
- [DragonForce - Cry Thunder](https://osu.ppy.sh/beatmapsets/871946#osu/1822108) - [idke](https://osu.ppy.sh/users/4650315)的S成績從980pp上升到990pp
- [ClariS](https://osu.ppy.sh/beatmapsets/661919#osu/1401254) - [FGSky](https://osu.ppy.sh/users/2094566)的B成績從819pp減少成808pp

View on GitHub: [#74](https://github.com/ppy/osu-performance/pull/74)

## 手電筒(Flashlight/FL)調整

在短圖中FL能拿到的pp減少，長圖中增加

![](/resources/flashlight-chart.png)

舉例：
- [Aoi Eir - IGNITE](https://osu.ppy.sh/beatmapsets/209170#osu/492285) - [Ekoro](https://osu.ppy.sh/users/284905)的成績從435pp增加為490pp
- [Harumachi Clover (Swing Arrangement) [Dictate Edit]](https://osu.ppy.sh/beatmapsets/859783#osu/1893461) - [fieryrage](https://osu.ppy.sh/users/3533958)的成績從832pp減少為733pp

View on GitHub: [#48](https://github.com/ppy/osu-performance/pull/48), [#71](https://github.com/ppy/osu-performance/pull/71)

## 隱藏(Hidden/HD)調整

HD的移動和準度難度增加，速度難度在高縮圈速度(AR)時減少，慢速時增加

| ![](/resources/hidden-chart-1.png) | ![](/resources/hidden-chart-2.png) | ![](/resources/hidden-chart-3.png) |
| - | - | - |

舉例：
- [GYZE - Honesty](https://osu.ppy.sh/beatmapsets/586121#osu/1241370) - [OPSwimmyJimmy](https://osu.ppy.sh/users/4196808)的成績從941pp減少為926pp
- [Linkin Park - Guilty All The Same (feat. Rakim)](https://osu.ppy.sh/beatmapsets/518596#osu/1187302) - [nathan on osu](https://osu.ppy.sh/users/124493)的成績從695pp增加為705pp

View on GitHub: [#72](https://github.com/ppy/osu-performance/pull/72)

## 小改動

這些是一些技術上的小更動，用來解決先前的問題並保持平衡

- 多種滑條長度計算修正。 ([#4099](https://github.com/ppy/osu/pull/4099), [#4193](https://github.com/ppy/osu/pull/4193))
- 若滑條的下一個物件為圈圈，滑條長度將會加入計算。 ([#3608](https://github.com/ppy/osu/pull/3608))
- 同時的物件的排序有些微更動並只會對部分圖帶來些微影響，但會方便未來的改動。
- 圖最後400ms的物件加入難度計算。 ([#4074](https://github.com/ppy/osu/pull/4074))
- AR10.33以上的圖獲得的移動pp稍微減少。 ([#76](https://github.com/ppy/osu-performance/pull/76))
- AR10.33以上的圖獲得的速度pp稍微增加。 ([#76](https://github.com/ppy/osu-performance/pull/76))

----------

我們希望這項更新能變動排行榜使玩家感到更有趣與刺激。持續關注以獲得更多訊息，祝你點圈圈愉快~

—osu!team, Xexxar and others
