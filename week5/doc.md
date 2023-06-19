## week5
1. 最小二乗法を用いてデータを分割してから半分ずつでgreedy
2. 2opt
- 初期解を生成する。
- 2つの辺を選び、それらを交換する。交換によって得られる新たな経路が既存の経路よりも短くなる場合、経路を更新する。
- 全ての組み合わせについて2つの辺を交換する操作を繰り返す。
- 改善が見られなくなるまでステップ2とステップ3を繰り返す。
- 最終的な巡回路が得られたら終了。


|challenge|random|greedy|sa|1|2|
|---|---|---|---|---|---|
|0| 3862.2| 3418.1| 3291.62| 3418.1| 3418.1|
|1| 6101.57| 3832.29| 3778.72| 3832.29| 3832.29|
|2| 13479.25| 5449.44| 4494.42| 6011.44| 5124.85|
|3| 47521.08| 10519.16| 8150.91| 10845.1| 8989.62|
|4| 92719.14| 12684.06| 10675.29| 12764.17| 11596.28|
|5| 347392.97| 25331.84| 21119.55| 26265.63| 22504.95|
|6| 1374393.14| 49892.05| 44393.89| 52517.46| 44309.61|