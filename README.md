# 0829 

# Unlucky 7  diff 131

解答遷移  AC

問題把握 00:13  発想 00:00   base 04:30  デバック&提出 02:05

備考

➀ 8進数

整数Nの8進数文字列は f"{N:o}"で出力可能




# 185C Duodecim Ferra diff 374　

解答遷移 WA 諦め(再解答の必要はなし)

問題把握 01:42  発想 + base 08:18  計 21:14 諦め


備考

➀ scipy.special 整数型

![image](https://user-images.githubusercontent.com/109026838/187097939-c96a938b-fa12-4ad8-8ab6-90d48c2a0c79.png)

int(comb((L-1),11))としたためにL=200などの大きな値の処理が正確出来なかった。

3つだけWAが発生してコーナーケースを考えたが存在しないと結論付けた。そこで上限値でなにか問題が発生しているのかなと考えたはしたのだが、その場合はどうせ解けないなとcombの仕様を調べようともせずににすぐ諦めてしまった。仕様を知らなかったことは仕方ないが、この努力をできなかったことを大きく反省する。


# ABC171D Replacing    diff 498

解答遷移 AC

問題把握 01:13  発想 01:31  base 04:48  デバック&提出 05:12  計 12:46

備考

なし



# 258C Rotation  2回目   diff 419    類題 199C

解答遷移 AC

問題把握 01:22  発想 11:08  base 03:16  デバック&提出 01:04　計 16:52


備考

➀ 思考

クエリ1で本当に入替を行うのは無理だから疑似いれかえをしたいな →  最初のindex番号をキーに、要素をvalueにした辞書を作ることを考えたが、キーを変化させるにはループが必要になるからこれじゃだめだな。→ 結構時間をかけて考えた後、クエリ２で取り出す場所の方をいれかえを反映させた数字にすればよいこと気付いてACできた





# 187C 1-SAT   diff 207

解答遷移 AC

問題把握 02:01  発想 09:15  base 06:02  デバック&提出 12:24  計 29:43


備考

➀ 速度ボトルネック

題意読み取りミスが原因。Sを揃えてから存在確認の判定を必要があることになかなか気づかなかった。

また解法もナンセンス

そもそも調べる文字列が"!"つきか否か分類する必要がない。例えば red は red , !red を調べるのに対して、!red なら !red , !!red であるため、なにか特別な処理を施さなくても自然に異っていて条件で区別する必要がないことを読み取れななかった。



* この読み取りミスの原因は部分的な処理に頭を使ってしまうこと？

今回では!をうまく処理するためにpopがいけるかどうかみたいなことに9割思考を割いてしまうせいで、やらなければいけないことが曖昧なまま方針を進めたり、コードを書いてしまうことが原因かもしれない。速度ガ大切なため完全に整理してから進めるのは不可能だが、全体を俯瞰する姿勢をとる必要がありそう。



# 265C  Comma   diff 265

解答遷移 AC

問題把握 00:40  発想 05:44  base 05:44  デバック&提出 02:57  計 15:07  

備考

➀ 速度ボトルネック

N < 10^s における探索時の個数処理の正確さが不安で確認を慎重に行ったために作成時に時間がかかってしまった。N+1<=10^sなのだからどんなNであってもmin処理の結果が同じことが時間をかけないとわからなかった。


➁　別解(模範解答)

その数に何個のカンマがあるのかに注目する自分の解答とは異なり、その数に特定の位置のカンマが存在するかに注目することもできる。例えばN=7,777,777の場合、3-4桁目,6-7桁目のカンマは存在するが、9-10桁目,12-15桁目,18-19桁目のカンマは存在しない。よって+2のように考えることも可能。





# 0831 

# 176C Step  diff  72

解答遷移 AC

問題把握 00:21  base 04:21  デバック&提出 01:35  計 06:18

備考

なし


# 209C  Not Equal  diff 285 

解答遷移 AC

発想まで?  11:44   baseから提出まで? 05:23   計 17:07  (境界が曖昧)

備考

➀ 思考

素直に実装すると、Cの要素を前から探索して、その要素の値以下の数値を探索していくことになるがそれは無理だな。　→ 逆にどんな数値かを探索して、setで重複処理すればいけるか？ でも、Aが数値ではないので探索ができない  

Cの制約的に探索するのかと思ったが、思いつく限りの探索方法を講じても制約を突破できないので何か直接答え出力する方法がないか探してみる。 → sortして前から順に、i番目に(要素-i)の値をかけていく処理をすればよいことに気づいてAC


とても速い提出とはいえないが、プロセス自体は良いと思うので、あとは自分自身の思考処理がはやくなれば完璧





# 189C Mandarin Orange  diff 565

解答遷移  AC

問題把握 02:38  発想 18:44  base 03:30  デバック&提出 00:52  計 25:46

備考

➀思考

前から探索しても、区間を探索できないから組み合わえ使うか？ でも5.0 * 10^7で無理ではないが他のより高速な処理を探そう　→ 探索開始位置と終了位置を二重ループで操作するのはどうか？　これも結局同じか　

setならmin処理が速いか調べたりしながら、ここでようやく区間の始点終点を決めても取り出すのにO(l)かかるからこれじゃだめなことに気づく。

発想を変えてAの要素で探索しようとしたところ 5.0 * 10^7にはなるがこれで解答は一応できることがわかったので、ほかに案もないしダメもとで出したらACできた。


➁模範解答

よく考えたら区間をとりだす必要はなく、その区間での最小値さえわかればよいので自分が捨てた方針でACできる。ただしmin処理に注意

➁ pypy 

➀でも記述したが、5.0 * 10^7 ならpypyで通る






#  0901  

# 176B Multiple of 9     diff  51

解答遷移 AC

問題把握 00:45  base 01:06  デバック&提出 00:41  計 02:33

備考

なし


# 177B Substring     diff  193

解答遷移 AC

備考　

なし



# 166C Peak   diff 263

解答遷移 AC

計 24:21

備考

➀　思考と計算量

各展望台について隣接する展望台のリストを作ってその最大値をmaxで取得する場合、O(N^2)になるためこれではだめだなと思って、熟考し最大値のみを保有することでO(N)の解答を導くことができた。

しかし、却下した方針でも普通にACできた。これは、ある展望台については他全ての展望台と隣接することはあっても、隣接候補が2M個しかないために探索回数はO(N^2)ではなくO(2M)になるからだと思われる。




#  Alter Altar     diff  486

解答遷移 AC

問題把握  04:07  発想 24:27   提出まで 02:32  計  31:56


備考

➀ 思考

1,アルゴリズム理解 09:49  + 2,コードでどう実装するかの思考 15:27  の計24:27を発想段階で費やした。(少しコードも書いてはいるがほぼ思考時間)


とりあえずシミレーション。入替と色変えの効率を比べたりしながら、石の入れ替え位置候補が多すぎてこれを探索することは不可能だと感じ、操作完了時の石の状態に注目してみた。すると最も右の位置にある赤石と最も左の位置にある白石が...w...R...のように白 < 赤になっている場合にはまだ操作が必要で、そうでないなら操作完了になるなと気が付く　 1  → 白石と赤石の位置を調べあげ、初めて白 > 赤　になるindex回操作が必要である処理でAC 2




# 196B  Round Down   diff 39

解答遷移 AC

問題把握 00:13    提出まで 03:31   計 03:45   

備考

➀ 思考

floatで受け取って、math.floorすればいいや。→ sample3で、入力を受け取った時点で小数16桁付近から情報が落ちていることを確認。仕方なく文字列として受け取り前から "." まで探索し出力する方針でAC

割算演算の結果のみでなく、入力時点でも情報が落ちてしまうことに気を付ける




# 0902

# uNrEaDaBlE sTrInG   diff  23

解答遷移 AC

計 04:18

備考

➀ 小文字 / 大文字判定

文字列.islower() /  .isupper()にて文字列が全て小文字か大文字かを判定できる



# Unexpressed   diff 379

解答遷移 WA  WA  AC

問題把握 00:49   発想  02:49   base  03:40   初提出までのデバック  12:36   AC 08:17   計 28:12 +10:00


備考

➀　注意点

1, 重複処理

たとえば 16　のような 2^4　とも 4^2 とも表現できる数字のカウントを正確に行わなくてはいけない

2, break処理

a^2 > N となった場合、(a+1) ^2 >Nなので処理をうち切りたい。b=2のまま処理が終了したことを表すflagを使ってprintする処理を実装した場合、ループ回数が十分に大きくないと10^10の場合にprintされないことになる。詳しくはコード参照




# ☆ 226D Teleportation     diff 706

平行な場合にも同じ魔法であることを処理できず諦め

問題把握 04:14  発想 29:13  base 11:55  　計 1:04:32


備考

➀ 傾きと最大公約数

2点間の変化量を表す傾き dy/dxを素直に実装すると割算になって不便であることは　226C(0820) でも学んだが、dxとdyの最大公約数gによって(dx/g,dy/g)により、その傾きを代表するベクトルを表現できる。

なお、a,bの最大公約数はmath.gcd(a,b)にて O(log(max(a,b))で出力可能


➁ hash化　タプルとリスト

辞書のキーやsetの要素にリストは渡せないが、タプルなら可能


③ 解答補足

combinationsを使っ探索し結果を2倍する処理では正解できない。なぜなら傾きの絶対値が同じ2点であってもベクトルが違えば傾きが変化しsetにどちらも格納されることになってしまうからである



#  148C  Snack

解答遷移 AC

計 05:35

備考

➀　最小公倍数

a,bの最小公倍数は　a * b // gcd(a,b)  で求められる





# 224C Triangle? 2回目

解答遷移  RE ➁ / TLE ③ / AC ➀

計 27:15 + 10:00

備考

➀　最大公約数解法

226Dで傾きを最大公約数で解釈できるようになったので練習がてらこの問題を最大公約数を利用して解いてみた。この問題では選んだ3点において、同一直線状にあっても始点の決め方でベクトルの向きが変ってしまうこと、にさえ気を付ければこの解法でもACすることができた。

ただし模範解答の、傾き分母払い解法であれば逆ベクトルを考える必要がないためこちらの方が楽である。


➁scipy と pypy

pypypではnumpy 同様にscipyも扱えない。そのためこの問題をpypyで通したいなら、N* (N-1)* (N-2)//6とするしかない

③ 計算量

NC3 * log(max(dx,dy)) はx,y <= 10^9　により 10^8近くなる。そのためpythonで最大公約数解法は使えない



# 0903

# 048A Atcoder ** Contest   diff 54

解答遷移  AC

計 01:59

備考

なし


# 053B A to Z String  diff 164

解答遷移  AC

計 07:33

備考

➀　解法

読み違えたままACしてしまったが、この問題ではZが来ても数をリセットするのではなく、最左のAの位置と最右のZの位置が分かればよい問題である




# 連結リスト Linked List 勉強

ノードのつながりを記憶するデータ構造。インスタンスにその前後のインスタンスを記憶させて、挿入をくりかえすことで一つの連結リストを作成する

・ LikedList インスタンス式

https://www.delftstack.com/ja/howto/python/linked-list-in-python/

ノードの挿入などの関数を持つ全体のクラスを作成し、これを操作してノードインスタンスを連結させる方法

・アルゴ式

https://algo-method.com/tasks/844/editorial

最初と最後のノードnilを作り、nilを目印にして連結する方法


・欠点

abc225(後述) に顕著であるが、特定の位置にアクセスすることができない。前から辿って見つける必要がある。

https://www.momoyama-usagi.com/entry/info-algo-list#i-2





# ☆ abc225D  Play Train   diff  778

方針がたたず諦め

備考

➀ 双方向連結リスト

上述した連結リストの考えで解答可能。ただし生成される連結リストが一つではない点、アクセスが不便な点からTrainクラスの連結でこの問題を解くことは難しい。

そこでリストのtrain番号に対応した場所にその電車の前にある電車と後ろにある電車の情報を格納したリストを格納することで操作1,2をO(1)で処理することができる。もしくは前の電車の情報と後ろの電車の情報をそれぞれ別のリストにわけて記憶することでも解答可能




# ☆ 181D Hachi    diff  600

解法がわからず諦め

備考

➀　思考

並び替えの探索は不可能なのでそれ以外の方針をとるべきだとは思ったものの、8進数や他の方針を考え始めて、しまいには8の倍数の判定方法を調べることもせずあきらめてしまった。

８の倍数を列挙して4の倍数の様に下2桁に注目して8の倍数以外もあるなと最初に気づき、そこでこの方針はだめだと打ち切ったことを引き釣り判定方法わからないと結論付けて調べようともしないこの姿勢がダメ


➁ 8の倍数

1000 = 125 * 8 であることに注目すると、例えば 5424 → 5* 1000^1  + 424 * 1000^0 より 424 が8の倍数であることと、5424が8の倍数であることの真偽は一致する




#  180A  box  

解答遷移 AC

備考

なし


#  180B Various distances   diff 129

解答遷移 AC

備考

なし



# ☆　211C  chokudai  diff 559

解答遷移 TLE 諦め

備考

➀ 思考

chokudaiを構成する8文字のそえぞれがSに出てくる場所さえわかれば、cから順に次の文字を二分探索すれば、例えば8文字すべてに10^5 /8 個登場するとしても 10^5 / 8 * 10g(10^5 / 8)^8 で間に合うと思った。

しかし実際に実装してみると次の文字の中でもある文字を動かす必要があり結局これではループが8重になりTLEすることに気づいた。

かなり時間を使ってようやくdpっぽく処理できるなと気づき導入。chokudaiリストと同じ形状のdpを作って、dp[n][m]を文字nの中のm番目のものを使ってchokudaiのnの文字までの組み方の数を表して、nのm番目とn+1のm`番目を比較してm<m`ならばdp[i+1][m`]+=dp[i][m]とすればよいと考えた。　→ しかしこれでは8つの文字それぞれにおいて前から順に探索が必要な点が解消されていないのでACできずTLEしてしまった


➁　模範解答

dp

Sに出てくるn番目の文字でchokudaiのある場所までを表現することができる総数に注目する。例えばn番目がkならn-1番目までで作ったoまでの文字列が新たにkまで構成できるようになるのでdp[n][kを表すindexl+=dp[n-1][kを表すindex]+dp[n-1][oを表すindex]  * が成り立つ

またcにおいては前の文字がなく、dp[n][cを表すindex]=dp[n-1][cを表すindex]+1となるが、すべての要素が1の-1列目をdpに追加すれば他の処理と同じく * 式で済む

また、実はdpでは直前の情報以外使用しないので、すべての情報を記憶する意味はない。よって9列の一次元リストを作成し、S[i]がchokudaiを構成するならばdp[S[i]の表すindex+1] = dp[S[i]を表すindex]として古い情報を更新してしまうことも可能




# 0905

# Changing Jewels   diff  413　　2回目

解答遷移  AC

計 09:47

備考

➀ dpで解答



# アルゴ式 dp基礎編

# 3-2 部分和問題

解答遷移 AC

計 25:00

備考

➀ 思考

2^100は探索できない。M以下の最大値を保存していてもW1+WN=Mだった場合などでMにならなくなるので途中の重さの情報を保存する必要があると気づく。→ そのためには0からM+1までの列を作ってdp[i][j]にはWiまでで重さjにできるかの真偽を格納すればよい


#  データ損失 ===================

# 3-5  部分和問題応用

解答遷移 WA AC

計 59:04

備考

配るdpでも貰うdpでもどちらでもよいが、min処理で更新していくため初期値はありえないくらい大きな値であるほうが都合がよい。初期値-1などにしてしまうと初期値か否かで余計な条件分岐が発生してしまう


# 3-6 部分和問題(応用２)

備考

dpするだけ

# 3-7 ボールと2つの箱

備考

➀　思考

bit全探索は無理。そのボールを左の箱に入れるかいれないかでdpできないか　→ すべての場合を表現すること自体は可能だが差の情報が得られないので差の情報に注目　→ そのボールを入れることでその分だけ差が増えるか減ることに注目してAC

なお、dpの列の大きさとしては、すべてのボールを片側に入れる時が差の最大値なためsum(W)分の大きさを設定すれば良い


#  189A Slot 

備考

なし

# ☆ 189B  Alcoholic   diff   274

ACできず諦め

備考

➀ 小数演算

215B(0726) , 224C Triangle(0820) などで小数16桁付近で情報が落ちると学んだが、実はそうではなくとも小数を扱う場合には正確な演算を行えない可能性が高い

例えば 0.07 + 0.07 + 0.07 は0.21000000000000002(0の数は適当)となってしまう。これは以下のように、そもそも小数は近似値で保存されてしまうことがほとんどであるからだ

![image](https://user-images.githubusercontent.com/109026838/189067746-85ff7968-08e2-436b-8332-039c31222b5c.png)

このような理由で小数演算の結果は誤差を孕む。したがって桁数によらず誤差を生じていることをかんがえなくてはいけない

➁　模範解答

➀の理由で小数演算を回避すべく、Xを100倍した値と、%の値をそのまま乗じたアルコール量を比較すれば整数の範囲での演算が行えるようになる



# ☆ 183D WaterHeater  diff 662

諦め

備考

➀ 逐次計算(シミレーション)

時刻で全探索。何人目であるかの情報を持ったSとTをソートしたSSi,TTiを作成し、そこから何人目かの情報を落して一次元化したSS,TTを時刻で二部探索。SSに挿入する位置leftが更新されればその分だけ使用量tmpを追加、TTに挿入する位置rightが更新されればその分だけtmpを減少させる。tmpがWを超えるか否かを判定することで目的の処理を行える

➁ imos method

時間ごとの使用量リストを作成し、使用開始時要素をP増加させ、終了時要素をP減少させ、累積和をとることで時間ごとの使用量を得ることができる。



③　itertools.accumulate(イテラブル)

イテラブルの累積和イテレータを生成できる



# 226C Marial artist   diff 539

解答遷移 AC

備考

dfs


# 207C Many Segments  diff 397

解答遷移 AC

備考

➀　思考

閉区間か開区間か考えなかった場合、左端点が小さい方の右端点right1ともう一方の左端点left2を比較して、right1>=left2であれば区間が重なる。そのうえでright1=left2だった場合に端点の情報で条件分岐すればよいとわかる。また2点a,bの組み合わせは全探索すればよいが、左端の大きさが大切なので、L,T,Rの順で情報を格納したリストを作成しsortすることで左端点の小さな方がどちらなのか決定させる。

➁　別解

開区間の場合端点を+0.5すれば条件分岐なしで皮革が行える。さらに全体を2倍すれば整数の範囲ですべての処理を行える

また、このとa,bの左端点のうち大きい方と、右端点のうち小さな方を比較すればよいのでmax,min処理を利用すればよい(ただしmax,min処理ではa,bどちらの端点であるかの情報が落ちるため、あらかじめ区間の変換を行っていない自分の案のような場合には扱えない)

③　余事象

模範解答では直接重複区間を求めるのが難しいため、区間が被らない条件を考えている。このように余事象を考えることは大切である　後述 178C



# 162B  Fizz Buzz Sum  diff 42

解答遷移 AC

備考

なし


================================================================================


# 0908

# 197A Rotate  diff 6

解答遷移 AC

計 01:03

備考

なし


# 197B Visibility  diff 96

解答遷移 AC

計 13:32

備考


# ☆ 179C A x B + C  diff 283

解答遷移 AC

発想　06：03　　AC  03:04  計 09:08

備考

➀ 解法

A * B + = N - C よりN以下の整数の約数を求める問題に見えるが、 約数列挙は工夫してもO(√N)なので全体でO(10^9)かかってしまう。したがってこの解法では解くことができない

次にAを全探索することを考える。C = N - A * B より 1<=N-A * B　これを変形して 1<=B<=(N-1)//A となるため、このAの場合の条件を満たすBの数は(N-1)//A　となる。この方法はO(10^6)なので間に合う。


# 177C Sum of product of pairs  diff 386

解答遷移 AC

発想 01:44   base 02:21  AC 01:28  計 05:34

備考

➀ 掛け算の和をまとめることで累積和を使えるようになるパターンのやつ


# ☆ 178C Ubiquity   diff　653 

解答遷移  方針がたたず諦め

備考

➀　思考

09と90に文字を挿入することを繰り返してカウントしようと考えたが、重複を排除する方法がわからない　→　setで処理しようにも挿入位置を全探索してその数字を求める必要がありそれは制約が許さず、setに10^9を超える要素を格納するのも難しい。　→　方針を変えてあり得る数字を全探索しようとしたが、10^(10^6)を探索できるわけもない　→　ここで策が尽きて諦め


➁　模範解答

余事象を考える。207Cでもあったが、何かを直接求めることが難しい場合に有力な方法になる。


③　pow(x,y,z)

x^yをzで割った余りを出力できる。(x^y)%Zとするよりも途中で随時あまりをとる処理のために高速で行えるらしい。pypyでも使用可能



# 0909

# 175B Making Triangle   diff 130

解答遷移 AC

問題把握&発想 00:49  AC 03:36  計 04:26

備考

なし

# 175C Walking Takahashi  diff 417

解答遷移 AC

base 作成 23:04   AC 01:05  計 24:09

備考

➀ 思考

探索はできないから計算で最小値を求めるのかな？　→  正なら負に、負なら正にとりあえず進むことが最適であること、Kの偶奇で止まれる場所が異なることを発見　→　行ったり来たりが可能なので、場合分けしなくてもKが奇数なら初期値をずらし、その後偶奇によらずKを半分に、Dを倍にすればすべての場合が同じ条件で扱えることを発見　→　さらにXは絶対値をとっても問題ないことも発見

あとはどうやって0に接近させるかだが、X//D が正側の最小値 X%D に接近するための最小回数であることに気づいたことでACできた。あとはX//DとKの大小関係に注意すれば完璧である。

スピードは速くはないが思考プロセスとしては十分なので満足



# 149C Replacing Integer diff 149

解答遷移 AC

発想 01:18  AC 01:35  計 02:53

備考

175Cの簡単ver




# 173D Chat in a Circle   diff 720

解答遷移 AC

発想 30:34  base 08:21  AC 01:50  計 40:47

備考

➀ 思考

座る順番はAの大きい順として、割り込み位置の前後要素[left,right]リストを作成して要素ごとの最小値の最大値が得られる心地良さであり、割り込み位置を示すことに気づくが、maxmin処理の後に挿入する値で更新するとなるとO(ΣN(N-1))でだいたいO(N^3)なので実装できない。

例) A[8 6 6 5 4]の場合 8 6 8をの挿入位置を[[8,6],[6,8]で表し、最大最小値は6なので[8,6]を[6,6]に変換して[8,6]をリストに追加する感じ。なおこの際6が含まれているものであればどれを変換しても結果に変化を与えないことを発見

この発見により現在の最大最小値の個数を管理すればよいのではないかと考える。新たな要素の追加で現在の最大最小値の個数を-1して0になるまではその心地よさが得られるという処理ができないか？　→ counterで管理して現在の最大最小値が0になればAを昇順でソートしたリストを二分探索し次の最大最小値に更新させる処理を考え無事ACできた



➁　模範解答

心地よさはA[0]+A[1]+A[1]+A[2]+A[2]+・・・を挿入回数のN-1回繰り返すことで最大値をとる。これは追加した値の左右の挿入位置を消費するまでその心地よさが得られ、次の最大値に移ることをくりかえす処理を最も簡潔に表している


# 166B Trick or Treat  diff 84

解答遷移 AC

計 05:12

備考

なし



# 0910 

# 262B Triangel(Easier)  2回目 diff 220

解答遷移 AC

計09:49

備考

0731のデータがなぜかないうえに記憶もまったくないのだが、当日の処理は今見ると意図が読めない。成長を感じる

# 262C Max Min Pair  2回目  diff 362

解答遷移 AC

計 11:00

備考

➀　思考

nC3で全探索はできない。Ai != i の場合はAi番目の要素にアクセスすればよいのでO(1)。Ai==iの場合にi番目以降のj番目がjであるかの処理を高速に行う方法を考える →　探索前にAi==iである全ての要素の数を数えてAi==i番目の探索時にその分だけansに追加する処理ならばO(N)で済むことに気づいてAC

➁ 0731時

Ai=iを満たす要素がX個だった場合、総数がXC2になることに注目して探索時に数え上げる処理を行っていた。nC2にわざわscipyを使っていたり、面倒なflag処理をしていたりと綺麗ではないが処理内容自体は〇


# 259B Counterclockwise Rotation　　2回目    diff 180  

解答遷移 AC

計 07:37

備考

複素数で計算するだけ。度数とラジアンの変換をでバックするまで勘違いしていて遅れた

0709時はわけのわからん条件分岐で解いている。煩雑すぎて読みかえす気も起きない




# 259C  XX to XXX  2回目  diff 451  

解答遷移 WA AC

計 21:28 +05:00

備考

➀ 思考

S,とTを前から探索すると、index番号がずれてしまうのでどの文字が何個続いているかのリスト作るか　→ WAを2つ出したので条件の見落としやコーナーケースを探す　→  Sのほうが文字の数が多いときもダメなことに気づいてAC

0709時も同じ思考でできている。



# 0910

# abc 268 記録

# 268A Five Integers

解答遷移 AC

計 01:18 

備考

なし

# 268B Prefix?

解答遷移 AC

計 02:30

備考

なし

# 268C Chinese Restaurant    diff 676

解答遷移 AC

計 40:34

備考

➀　思考

料理のならびを全探索するTLE確実な方針しか思いつかず、実験してみることに　→　たとえば 3,6と料理が並んでいた時 3が4の位置にいる時6は5の位置にいて両方条件を満たすことが判明　→ つまりi番目の料理は1場目の料理が　pi-1-i,pi-i,pi+1-i のいづれかに存在する場合に条件を満たすことを理解。　したがって料理を前から全探索し、条件を満たす1番目の料理の位置を+1する処理をし最も条件を満たした位置を出力する処理で完了できるはず　→ AC


方針がたたずdpを試したり、それでもうまくいかなかったりして緑diffなのかなと諦めかけたが、順位表を見てもDが先に解かれている様子もなかったためいろんな視点で実験してみたところうまくいった。最終的なパフォーマンスから見ても十分健闘できた


# 268D  Unique Username  diff 1309

解答遷移 無数のWA

終了時まで思考しACできず

備考

➀ 思考と解答例

permurationで順番を探索し、各位置に _ を何個挿入するかをproductで探索する方針をとった。方針自体は全く問題なかったがこの方針でbaseを完成させたのが終了まじかだったこともあって十分デバックして確認することができなかった。


挿入する位置の数で挿入できる _ の最大値が変化することなど productで作るpoints タプルの要素および要素数を精査することで同じ方針でACすることができる。しかしpointsの要素をN-1,Nのどちらで作ろうが,また要素の最大値をありえる範囲で作ろうが作らまいが、生成する文字列の長さで最終的にありえないものを排除できるはずなのだが 入力 01-one_04でのみ結果が異なるようである。

一日使ってあらゆる実験をためしてみてもなぜ結果が異なるのかつきとめることができなかった。サンプルが公開され次第確認すること(ssssに実験の記録を残す。内容はランダムに作成したサンプルに対してAC処理とWA処理の出力をテキストに出力するもの。ソフトに投げれば差がわかるはずだった。。。)



➁ 入力データ生成

https://timesaving.hatenablog.com/entry/2022/04/29/150000

上サイトやssssのようにして文字列を作成できる。これを使えばなぜWAなのかわかるケースが将来あるはず

③ a^b

a や b が 1異なるだけで一桁変わるほどなのでproductの引数は十分精査する必要がある。この問題でも _ の挿入位置数、挿入可能最大値を正確に与えればACできる処理でもこれを怠るとTLEしてしまった



# 154C Distinct or Not  diff 64

解答遷移 WA AC

発想 00:56  base 00:48  AC 03:24  計 04:59 + 05:00

備考

➀ 出力文字が大文字であることに気づかずWAを出す。方針を再考察し間違っていると思えなかったので問題をもう一度読み返したところ出力がいつもと違う文字を要求していることに気づいてAC


# 139C Lower    diff  152

解答遷移 AC

計 08:25

備考

➀　思考

前から順に探索し、つぎの高さより低い位置になるまでcountしていき、その条件を満たす位置で現在の最大カウントと比較することその位置までの区間における最大値を求められる。カウントをリセットして探索を続ければ全区間の最大値を求められる。更新途中でループが修了した場合のためにループを抜けたあとで追加の比較を行うことでAC




# 0912  

# 151A Next Alphabet  diff 13

解答遷移 AC

計 01:40

備考

なし


# 151B Achieve the Goal  diff 40

解答遷移 AC

計 03:10

備考

サンプルが親切でなければ、既にN * K を超えている場合に負数を出力していた。注意


# 151C  Welcome to AtCoder diff 333

解答遷移 WA AC

計 12:36 + 05:00

備考

ACをとっているかのリストを用意してFalseの間処理すればよいと考えて提出したがWA → ACしていない問題はいくらWAをカウントしていようが集計しないことを見落としていたのでWAの数もリストで管理して、ACしている問題だけそこからWAの数を取り出す処理を加えてACできた


# 240C Jumping Takahashi  diff 464

解答遷移 AC

計 08:38

備考

なし


# 240A Edge Checker 2回目  diff 7

解答遷移 AC

計 03:07

備考

循環型の性質をいかして余りで処理すれば 1 →  2　などと 10 → 1 を同列に扱うことはできるが逆方向の 1 → 10は同列に扱えない。進行方向が異なるからである(2 → 1などとは差が1などで同列に扱える)。したがってふつうに10の場合のみ特別に処理するべきである



# 227C ABC conjecture    diff 692

解答遷移 AC

計 32:26

読み取りミス 有


備考

➀ 思考

約数列挙で間に合うわけがなく 、10分ぐらい探索対象を考えたがわからないままだったので実験開始。ここでようやくN以下の数なことに気が付く。また勘違いしていたがa,bが定まっているならば、N以下だろうがちょうどNだろうがO(1)で求められることに気づく。したがってa,bの探索が間に合うのかについて考察すると、aの最小値1のときbの探索のために √N 回必要で、かつaの探索は合計で 3√N 回必要だから10^8を超えることはないと思って試しに10^11でテストしてみたところ通ったので提出してAC

読み取りミス + 計算量勘違い + 計算量見積もりの遅さ　で必要以上に時間がかかってしまった




➁　計算量

https://atcoder.jp/contests/abc227/editorial/2906

実際に積分してみるとたしかにN^(2/3)の項が最大の項だった。



# 255B Lights It Up   2回目    diff　351

解答遷移　AC

発想 02:45  base 11:53  AC 03:37 　計 18:17

備考

➀ 思考

あるライトを持っている人とライトをそもそももっていない全ての人の距離の最大値が、そのライトで全ての人を照らすための最小値だから、これを全てのライトで求めてどのライトで照らすのがもっとも効率的かminで求めればいいと思った　→ サンプル3で間違いに気づく。

ライトを持っていないある人を照らすための最小値を求める。すべての人を照らすにはもっとも照らすのに距離が必要な人を照らすことができればよいのでこれらの最大値を求めればよい。

➁ numpy演算

最大最小演算をnumpyで行えばループなしの高速な実装が実現するのでは？　→ (K,N,2)の1次元方向にすべての人の位置を格納した配列をK個3次元方向に格納した配列1 と 1次元方向にN個の同じライトの位置を格納した配列を3次元方向にすべてのライトK個格納した配列2を作る。　→ (1-2)^2 の和を2次元方向にとることでライトと人の距離の(K,N)配列ができる。求めたいのはある人を照らすための最小値の最大値だから、1次元方向の最小値をとればすべて人の最小値が格納された(K,)配列が生成され、これの最大値が解となる。

確かに処理の中にループは含まれてはいないのだが、(K,N,2)の配列を生成する際に時間がかかってとても遅い処理になっている

![image](https://user-images.githubusercontent.com/109026838/189896500-e25cc944-bfe9-46e3-ba11-6d76dc1e7e01.png)

test_21 サンプルでのコードテスト。出力1が配列正整部。出力2が最小最大値計算処理部。

これであればライトごとの計算はループで行う実装(昔作成したコード)のほうが何倍も速い。


* また、numpyは内部でC++が組み込まれている関係でpythonのように無限に整数を扱えない。例えば1000^2+1000^2はオーバーフローしてしまう。dtypeをint型にすれば回避できるが速度が遅くなる？らしい。numpyを使うときは注意



# 0913

# 254B Practical Computing   2回目 diff 45

解答遷移 AC

発想 01:23  base 02:10  AC 01:27  計 05:00

備考

なし


# 251B At Most3(Jude ver)  2回目   diff  181

解答遷移 AC

発想 01:01  AC 10:05  計 11:06

読み取りミス　有

備考

➀ 注意点

同じ数字でカウントするのは一回だけ

またあらかじめ0の重りを2つ追加で用意すれば、任意の3個を選ぶ処理だけで、疑似的に3つ以下の重りを選ぶ操作を実現できる


# 182C To 3  2回目  diff 292 

計 18:35

備考

➀　思考

N%3 に注目。0なら消す必要なし。1ならNを構成するいづれかの数字のうち余りが1のものを削除するか2のものを2つ削除すればよいことに気づく。(2の場合は2を1か1を２つ消せばよい)  → collectionsを用いて削除する数が最大で桁数-1個であることに気を付けてAC


➁ bit

計算量に気を付けているなら➀の解答が先に思いつくが、18の数字を消すか消さないかの問題なのでbit全探索も可能




# 247B Unique NIcknames   2回目  diff 202

解答遷移 WA AC

問題把握 01:55   発想 01:04  AC 08:59   計 11:59 + 05:00

備考

自分自身の姓名は被ってもいい点に注意




# 245B Mex  2回目  diff  40

解答遷移 AC

計 15:32

備考

➀　思考

ソートしリストを前から探索し、次の数字が一つ大きければそのまま進み、そうでなければ出力する処理を思いついた。　→  連続数や同じ数字が続く場合にうまく処理できないので条件分岐を考える。　→　うまくいきそうにないので見た数字を記憶して出現していない最小値を出力することでAC

➁ 別解

1, 差集合

2, setで重複をなくしsort。前から探索し、インデックス番号と異なればインデックス番号を出力する



# 242B Minimize Ordering    2回目   diff  45

解答遷移 AC

計 04:07  

備考

文字列もソートできる


# 246B Get Closer   2回目   diff  79

解答遷移 AC

計 03:06

備考

実部虚部の出力はZ.real,Z.imagで可能



# 243B Hit and Blow  2回目  diff 26

解答遷移 AC

備考

➀　解法

1, 積集合で共通要素を調べ、Aを前から探索。同じインデックス番号でA=Bなものを数え、それを共通要素から引けば位置の異なる数もわかる

2,共通要素があるときAの要素でその共通要素がBのどこに存在するのかアクセスできたらうれしい。→ Bの要素をkeyにindexを要素にした辞書を作ればいい


# 243 Shampoo  2回目   diff 18

解答遷移 AC

発想　01:48   AC 02:37   計 04:25

備考



# 0914

# 260B Better Students Are Needed!  2回目   diff 195

解答遷移 AC

計 17:54

備考

➀ 思考

not in で処理したいが、回数で制御できないくなるからwhileするか。でもこれって間に合うのか？　→ 英語の合格者を選出するためのループ回数が最高でX+Yなことに気づたことで、ループ合計回数が 6 * 10^3　であること、またX+Y回ループして合格者が合計X+Y人になればbreakする処理ｍならforで制御できることに気づいてAC



# 250B Enlarged Checker Board   diff 109

解答遷移 AC

計  10分未満(計測ミスで消してしまったが8～9分くらいだったのを見た)

備考

なし


# 252C Slot Strategy    2回目  diff 441

解答遷移 AC

計 26:59

備考

➀ 解法

どの数字で止めるか全探索。Counterでどの列にあるか管理し、最頻値を求める。


# 232B  Caesar Cipher  2回目   diff 82

解答遷移 WA  AC

計測ミス

備考

➀ a→b とz→a を同列に扱うために余りを利用する



# 241C connect6    2回目   diff  664 

解答遷移 AC

計 17:27

備考

➀　思考

マスを全探索。特定の方向に向かって6マス進み黒マスをカウントして4以上かどうか判断する処理でいいな。6マス済めない場合を条件処理してAC


➁　別解

進行方向ごとに、黒マスの数を累積させた新しいデータを作成し6マス先のマスが3か4増加しているかどうか判定する(始点のマスの色で区別)。この処理はマスを進む際にループを発生させないため、どんな連続マスであってもO(4* N^2)で処理できる




# 233C Product   2回目  diff 604

解答遷移 AC

計22:23

備考

➀　思考

制約がよくわからないけど、方針をたててからそれがいけるのか判断するときに制約の考察をしよう。　→  無難に再帰関数で袋ごとにループしたい。ここでボールの総積 =  ループ回数に気が付いて実装できることがわかる。なお袋には最低でも2つボールが含まれることから袋の数も16以下とわかり上限をあげる必要もないとか考えた・・・☆　→ あとは掛け算をくり返し行うため、最後まで行って戻ってきたときにその先の情報を忘れて次へ進むことができたら便利だなと考えた。これは掛け算を途中で一切更新せず、引数の中で掛け算を行えば値が記憶されないことを利用して処理した。

➁ 再帰関数上限

sys.setcursionlimit()で制御できる再帰関数の上限であるが、☆で既述したようにループ宣言の個数だと思っていたのだが、どうやらループの回数みたい

![image](https://user-images.githubusercontent.com/109026838/190244593-0fb9e62c-381d-4536-b95f-1c6f67fc7975.png)

しかしながら提出コードでは上限を上げなかったのにもかかわらず、10^5回程度ループする処理も問題なく実行されACできた。よく調べたが結局何の回数なのかわからないままであるので、とりあえずループ回数を賄えるくらいの上限を設定することにしよう


③　別解

どのボールを使うか、itertools.productで直接求めてることが可能




# 0916

# 228B  Takahashi's Secret    2回目  diff  83

解答遷移 RE  AC

計 06:33 + 05:00

備考

➀　RE

昨日学んだばかりなのに再帰関数の上限設定を忘れてREしてしまった。


# 253A Median?    2回目   diff 17

解答遷移 AC

計 02:56

備考

A,B,Cは大きさの順に並んでいるわけではない。


# 229B Hard Calculation  2回目   diff 42

解答遷移 AC

計 03:50

備考

➀　解法

1,桁数の少ない方にあわせて前から探索。

2,両者20桁程度になるまで0埋めして前から探索



# 226A Round decimals   2回目  diff 14

解答遷移 AC

計測せず実装

備考

➀ 整数部と小数部の分割

input.split(".")が便利

➁ round + epsillon

なぜかroundは微小数を加えることで正しく四捨五入できるようになる


# 245C Choose Elements  2回目   diff  403

解答遷移 WA  AC

計 24:27 + 05:00

備考

➀　思考

どの数字を使うか2^Nするのは不可能。ABを前から順に探索し、両方つかえなかったらNoな処理で良さそうと考え WA → 条件を満たす次の数がABどちらのものだったかの情報が伝わらず捨てられてしまっていたことに気づいて逐次情報を更新していく処理を増やしたところACできた



# 165D  Floor Function  diff 600

解答遷移 AC

計 33:07

備考

➀　思考

簡単な実験でどうやらXがB未満かそうでないかで結果が変りそうだと考察。よくわからないB以上の方を詰めていく。→  実験に実験を重ね、A * f(x/B)の情報の落ちが最大となるのが X=B-1の時で、落ちた A*(B-1)//Bを超えない最大の整数が差になってこれが答えになることが分かった。　→　XがB未満の場合はf(A* X/B)のみ考えればよく、この値はXが最大値をとるときに最大となりそれはX=B-1のときなので実はすべての場合でf(A*(B-1)/B)が答えになることが分かった　→　あとはNとB-1のうち小さい方を使いACすることができた。



# 225C Calender Validator   2回目  diff  326

解答遷移 WA  AC

計 32:08 + 05:00

備考

➀　思考

B1[0][0]で全体を引けば探索しやすくなるが、例えば 7 8 みたいな並びと1 2の並びを同列に扱うことは不都合。順序の情報を落したくない。　→  余りと商の情報で順序の情報を保ったまま探索を簡単に行えると判断。余りと商は0始まりが都合がいいので入力から-1を引いた値に対して同じ行の商の値は等しく、余りは1増え、行が変化すると商の値が1増え、余りは同じ行が続いているかを判断すればよいと考えた。　→ WA → 余りの方で忘れていた、行が変る際の処理を追加してAC



# 0916

# 257A A to Z String 2  2回目　 diff 22

解答遷移 AC

計 03:15

備考

なし


#  227B KEYENCE building   2回目  diff 30

解答遷移 AC

計 11:04

備考 

a,b　は正整部(0でない)ことに注意



# 226B Counting Array  2回目  diff 192

解答遷移 AC

計 3分くらい

備考

tupleはハッシュ化可能なことを利用する


# 165B  1%  diff 89

解答遷移 AC

計 08:46

備考

➀　解法

整数の範囲だけで扱えるように初期値は10000からスタートさせる。小数以下切り捨てを疑似的に実現させるために10^4で割ったものを100倍していき、100* Xと比較する。



# 223C Dokasen  2回目 diff 354  

解答遷移 AC

計 25:35

備考

➀　思考

左から進んだ距離 L_left と右から進んだ距離 L_right の和がN本の長さの合計値になること、進んだ時間 T_lert = T_right になることを利用しそうだなと考えた。　→ しかしこれだけではうまく処理できそうになくさらに考えたところ、N本すべてを燃やし尽す時間の半分と T_left,T_rightが一致することに気づき、N本がそれぞれ燃える時間のリストの累積和リストを二部探索して燃える場所を特定し、そこまで前から探索して距離を累積し、時間を減らしていって、最後の位置で残った時間 * 速度分の長さを足せばよいと判断。


➁　初見(0819)での反省を踏まえて

今回も初めはどこで止まるかを探索の結果として求めようとしていた。しかし処理が煩雑になりそうな点から視点を変えて考察してみることにした。すると前回の記憶が少し残っていたことが助けになって方程式をたてることを思いつき、解答できた。

競プロをしていると探索することが多くその考えが先行しがちになるが、逆に全体を俯瞰して骨組みをとらえることで問題の本質をとらえ、方針がたつ可能性があることを忘れない。



# 224B Mongeness   2回目　 diff 81

解答遷移 AC

計 09:19

備考

➀　思考

(i1,i2,j1,j2)をproductで全探索しようとしたが50^4はTLEするので無理。別の探索できる方法を探したところ(i1,i2) と (j1,j2)を別々にcombinationsで探索すれば　(50C2)^2 = 1.5 * 10^6なので通せると判断して解答した




# 214B How many?   diff 53

解答遷移 AC

計 11:33

備考

➀ 解法

1, a,bを探索し、cを一意に定めてcが2つの条件を満たすかどうか判定する

2, a,b,cすべてを探索し、2つの条件を満たすか判定する

a+b+c <= S <= 100 の条件から a,b,cそれぞれSを超えることなく、最大でも100なので解法2の様に3重ループが可能である。

1の解法で解いた場合、a* b * c <=Tを判定する際にa,bが0か0以外かで場合分けが必要になることに注意




# 0917

# 208B Factorial Yen Coin  2回目  diff 51

解答遷移 AC

計 10:37

備考

➀　階乗

mat.factorial(x) で x!を出力できる



# 241A T-shirt   2回目   diff 37

解答遷移 AC

計　03:58

備考

なし


# ☆ 249 Jogging   2回目  diff  103

解答遷移 WA * 4  AC

計 13:15 + 20:00

備考

歩いた回数　* 時間 * 速度で距離が求まるのだが、回数だけだったり、時間をかけ忘れたりと不備のある状態を完璧と判断してしまった。





# Union Find 勉強

![image](https://user-images.githubusercontent.com/109026838/190854213-d9630190-7d4a-4a8d-aeed-38eb550b09e1.png)

atcoder/class/union_find に保存済

親がなにかをfindで出力、二つの親が同じかどうかの判定を sameで行う。

また、unionで併合することが可能だが、例えば [0,1] と[2,3]を併合させるとき、0の下にもともとの子である1と新しい子になる2がつながるが、3の親は0でなく2のままである。findして更新するか、3を用いて新たにunionすればfindが実行されるので更新される。



参考 : https://note.nkmk.me/python-union-find/

       https://atcoder.jp/contests/atc001/tasks/unionfind_a



# ATC 001 B  Union Find

解答遷移 RE AC

備考

UnionFindのクラスを定義しているファイルをインポートしてコードを作成しても、そのまま提出はできない。atcoder側はそのファイルを知らないからだ。必ず提出するコードにクラスの定義をコピーする必要があることに気を付ける



# 0918

# 190C  Bowls and Dishes   2回目  diff 472

解答遷移 AC

発想 02:11  AC 10:52  計 13:03

備考

➀ 思考とボトルネック

K<=16 人の人がどちらの皿を選ぶか全探索した後、条件を一つずつ確認すればよいと判断　→ AC

ボールの乗った皿を示すdishesリストを、ループ毎に初期化する必要があることをでバックしてから気がつき遅くなった。



# 167C Skill Up   2回目  diff  595

解答遷移 AC

発想 01:36   AC 08:54   計 10:30

備考

➀　思考

N<=12 の制約からどの本を購入するかbit探索できると考えてAC


# 128C Switches  2回目    diff 805

解答遷移 AC

計 15:04

備考

なし



# ☆ 177D Friends  diff 732

初見時あきらめ　→ Union Find 勉強して解答

備考

➀　解法

UnionFindでともだちグループを管理する。A,Bを逐次unionしていき、最終的なグループのサイズの最大値を求めることになる。グループのサイズはuf.parentesの要素の-1倍であることを利用すればこの問題は完了できる



# 181D Choose Me  diff 650

解答遷移　WA  AC

計　27:01

備考

➀　思考

どの町にいくか探索して最適化するのは制約が許さないな　→ AOKIの初期値はAの合計値,TAKAHASiは0であり、町に行くとその町の A+B がTAKAHASHIに加わり AOKIからAが減る処理を行い。逐次比較して初めてAOKIを超えるまの回数が答えになると考えた。→ あとは、いく街の順番だが、Aがでかい順にいけばいいかと根拠もなく考えて提出して WA  → たとえば A,B=10000,1 の町があれば絶対にここに行くべき。Aだけの大小関係ではなくBも含めて得点差を大きくできる町に行くべきだと考察し、その町にいくと得点差がどう変化するかに注目してみた。 → すると 2* A + B だけ得点が動くことがわかったので、この順に行くべきだと判断した。コードを修正してAC



# 205D Kth Excluded   diff 713

解答遷移 AC

計 28:10

備考

➀　思考

探索はできないので K を見ただけで直接数字を出力できる仕組みを作りたい →  Aの各要素の前に何個条件を満たす数字があるか数えることができれば、kでAを二分探索することでk番目の数を求められるのではないかと考えた。例えば A=[2,5,7,12] , k=6 の場合、条件を満たす数字の個数は[1,2,4,8]なので 二部探索してkが示す数字は 7-12の間のいづれかだとわかる。あとは7から k-4 = 2個進めて答えは9となる。

条件を満たす数字の数に関しては、まずAの要素間の中で条件を満たす数字の数が Aを前から順にみたときの直前の数との差であるので、これをリストにして累積和をとればよいと考えた  *** ☆
　
 なお、二部探索の結果でAへアクセスする必要があるためnumpyで一気に求めても結局for ループの探索が追加で必要になりそうだと感じたため素直にbisectの方で処理した。


* ☆ 条件を満たす数字の数

ある要素までの数字の中で条件を満たすものは その要素までに出現したAの要素以外のすべてとなる。したがって要素間を一度考えてから累積和をとるようなことをしなくても A[i] - (i+1) で求められる




# 0919

# 215C One More aab aba baa    diff 178

解答遷移 AC

発想 05:23   AC 03:19   計 08:42

備考

➀ 思考

たかだか8文字なので 並び替えても最大 8! 通り。したがって全探索してsetに格納できると判断してAC

➁ itertools.permurations

順列を列挙

③ sortedの引数と返り値

リストだけでなく辞書やsetの要素を並び替えて並び替えたリストを作成できる。わざわざリストに変換する必要はない



# 222C  Swiss-System Tournament   2回目   diff 367

解答遷移 AC

発想 03:46  Ac 15:33   計 18:49

備考

➀　思考 と 注意したいポイント

ソートできるならシミレーションで解けるな。M * N * 2N * log(2* n) なので行けると判断。勝負する二人が誰なのかアクセスできるように [ 得点 , - index] でソートする。あとは前から順に勝負させる際に、index番号から　何の手を出すかAにアクセスして得点を加算する処理を繰り返せばいいと思った。 → デバックして得点を加算する場所が間違っていることに気づき、これを修正してAC


注意したいポイント

シミレーションはソート済みorderの前から順に行われているので、得点を加算するには今前から何番目なのかの情報が必要になる。勝負している人間がなんの手を出すのかを知るために利用したindexは勝負している人間のもともとの場所であって、ソート済みのorderにはアクセスできなくなっていることに注意



 
# ☆ 180D Takahashi Unevolved  diff 752

解答遷移 WA 諦め

発想 07:46  計 30:40

原因 ：  不十分な条件設定

備考

➀　思考

dpでやりたいけどYがでかすぎて無理だな。→ サンプル1で実験しながら、強さは単調増加するからA倍するか+Bするかの結果が小さい方を随時選択するのが最適だと考えた。また一度でもA倍する方がより大きくなると+BがA倍を追い越すことはないので・・➁ その時点までA倍してそれ以降は+Bする処理をすればよいことに気が付いた。ループ回数は 2* 2^ N < 10^18 を満たす最大のNなのだがこれは約60程度なので間に合うと考えwhileループでXがYを超えるま上記の処理を繰り返すことにした。

しかしサンプル2でTLE。+Bする処理をループさせるべきでないと考え、AX<X+Bでなくなった時点でのXにおいて、Y-1を超えない値までXを+Bする回数は (Y-1-X)//B回であることに気が付き、これを修正して提出したところWAになった。

処理自体の誤りやコーナーケースを見つけようとしたが見つからずここで終了した


➁ 照明

ある値の時にA倍したAXと+BしたX+Bを比較して AX > X+Bならば A^2* X - (AX+B) (XをA倍した値に関してA倍したものと+Bしたものの比較) = A(AX-X) -B > A* B -B =B(A-1)>0 。　A(X+B) - (X+ 2* B) (Xを+Bした値についてA倍と+Bの比較) =  AX-X-B > 0 。したがってある値時点でA倍した場合が+Bを上回るならばそれ以降も必ずA倍するほうが大きくなることがわかる。


③　解法

A倍できるのは、AX<X+B かつ、AX < Y を満たす範囲である。例えば 4 5 2 63 などは一回も経験値を得ることができないはずが、4* 2 < 63 なのでA倍されてしまう。



④　反省

不幸にも(Y-1-X)//Bが負の値を出力してしまうことで、4 5 4 10 などがAX<Yの条件を加えなくても0を出力してしまい誤りに気付けなかった。

この問題から考える、自分自身の改善点は3つ

1, 範囲の設定が十分か気を付ける

2, サンプルをうまく作る

3, // の仕様でマイナスが出力されることを覚えておく


2に関しては実際に0回の場合のケアもできているために十分できていると感じる。

1に関しては確かに不幸なケースではあったものの、サンプルでテストして初めて条件設定が不十分なことに気が付くことはとても多いので改善すべきである。

3がしっかりできていれば負の場合をケアできたかもしれない( + max(0,Y-1-X) の検証ができたかも?)



3は覚えるとしてどうやって2を改善していくかだが、確実にできることはデバックをより正確に行う方法で、今回も 4 5 4 10 の場合を一行ずつデバックしていればansに負値が加算される現象に気が付けたかもしれない。この方法は時間がかかるので最終手段にはなるが、解けないよりは十分まし。




# アルゴ式 グラフアルゴリズム

# 4-3 深さ優探索

備考

なし



# 4-4 辿り着けない頂点

備考

なし



# 4-5 　連結性判定

備考

なし



# 4-6 連結成分の個数

解答遷移 AC

備考

➀ 解法

・UnionFind

Ｎ個の親リストを作成し、Gの各要素をunionしていく。最終的に親になっている根の個数を数える


・dfs

全ての非探索済み頂点を探索する。一度探索できた頂点は新たに連結成分を作ることはないので再び探索する
必要はない。


# 4-7　塊の個数

備考

➀　解法

・ UnionFind

要素 HW個 の一次元 親リストを作成し、UnionFindで連結成分の個数を求める。マスを全探索して、そのマスが黒マスであったときに4方向のいづれかのマスも黒であればその2マスをunionすることでグループ化できる。実際にはマスは2次元なので探索自体はそれに準ずる形で行う。具体的には2重ループで縦方向と横方向の場所i,jを探索して W* i+ j がそのマスに対応する親であるとする。もし一次元に探索を行い4方向を [-1,1,-W,W]としてしまうと、行がずれる境界を無視してつながりを作る可能性が生まれてしまうので注意。



・ dfs

黒マスでかつ非探索済のますを全探索して連結成分をカウント。前問 4-6をグリッドverにするだけ



# 0920

# アルゴ式　データ構造

# 10-1 Union Find

備考

なし



# 10-2 連結成分

備考

なし

# 10-3 連結成分の最小値

備考

➀ union()の修正

サイズの大小ではなく、常にindex番号が最小のものを根にしていけば、parentsを前から出力すればこの問題に解答できる。したがって、unnion関数内部の結合ルールをそのように修正すればよい


# 10-5 グループ分け問題

備考

➀ 解法

Mが最大10^5なので、結合するたびにroots関数を利用してグループの数を求める処理ができない(O(M2))。ここでグループの遷移を考えると、別々のグループが結合すると全体のグループ数は１だけ減少し、一度に2以上変化することはない。したがって現在のグループ数を管理して、結合が発生すれば１減らした数値を、そうでなければそのまま出力することでこの問題をO(M)で解答できる


# 10-6 粘土の重さ

備考

➀ 解法

10-3同様、クエリごとに重さを計算するとTLEするので工夫を考える。 → 今回重要なのはグループごとの重さの総和であってグループのサイズは重要ではない。したがってparentsの初期値をサイズを示す -1 ではなく -Wiにすることでこの問題を解凍できる


# 234 Happy New Year diff 　2回目　155

解答遷移 AC

備考

➀　思考

小さい方から列挙すると2進数を2倍した数字であることがわかったので、int(bin(K)[2:]) を求めて2倍してAC



# 232C Graph Isomorphism  diff 682

解答遷移　AC

発想 06:24  AC 15:34  計 21:55

備考

➀　思考

ボールの並び方を全探索したうえで、すべてのボールの組みにおいて条件を満たすか探索できればこの問題は解答できると考え、この処理はO(8! * 8C2)　と十分高速なので行けると判断しAC

➁ NOR演算

![image](https://user-images.githubusercontent.com/109026838/191290745-6820492e-87fb-4a96-b729-db1b200bb927.png)

A^BでA,Bのはいたてき論理和が出力可能




# 213D  Takahashi Tour   diff 710

解答遷移 AC

発想　02：30  AC 07:58  計 10:29

備考

➀ 思考

dfsで探索して、都市に行ったときと、根に向う探索を終えて帰ってきたときの両方でその都市に訪れたことを記憶すればこの問題を解答できると考えた。そのためにはdfsで呼ばれた時にその呼ばれた都市を、またその都市から行ける全ての都市をdfsで呼んだ後にその都市を、記憶リストorderに格納すればよいと判断しAC


# 201C Serect Number  2回目  diff 439

解答遷移 RE RE AC

計 36:21 +10:00

備考

➀　思考

あり得るものを探すのはめんどくさそうだと考えて、ありえないものをカウントする方針をとることにした。oが4以下の場合において、使うo の数を0 ～ oの数-1 の範囲で探索し、組み合わせを考えてパスワードの候補を列挙し、それを全てのパスワードの数 10^4から引いていけば最終的にありえる数を求められると考えた。 → しかし例えば [2,3,4,5]　と　[2,3,4,6] の組み合わせにおいて 2222 や 3333を重複して数え上げてしまっている点に気づき、一度見たものをカウントしない処理を追加しようかとも考えたが、もうパスワードの方を全探索して、記憶と照らし合わせてそのパスワードがありえるか直接判定する処理にした方が楽そうだ思い方針を変更した。→ oとxを集合で管理し、パスワードを構成する要素の集合との差集合、積集合で条件を満たすか判定する処理でAC


➁ RE

scipyインポート文が残っているにもかかわらずpypyで提出したため。



# 0921 

# BFS 幅優先探索　勉強


# 211

簡易メモ



# 211

下院イメも

なぜdfsでtLE?

帰りがけで行ったことを忘れることで目的地に向かうすべての経路を求められると考えたが、0:[1,3,4],  1:[0,2,3] . 2:[1,3] . 3:[0,1,2] , 4[0,3] のグラフを例にして考察してみる。01234 で最短距離 4 →　0134で最短距離3  → 0312 失敗, 0321 失敗  034 で 最短距離 2 → 04 最短距離 1 となる。DFSはO(N+M)らしいが、少なく見積もってもこの処理はN+Mを超過する。より複雑なグラフなサンプルに対してはより爆発的に探索対象となる経路が増えて「TLEするに至ったと考えられる。


# 181D Hachi  n回目  diff

解答遷移














# 2分探索 勉強➁ 二分法

# アルゴ式 2分法

# Q2-1 方程式を解く

備考

➀ 二分法

リスト内の挿入位置を調べるにはnp.searchsortedなどの二分探索が役立つが、対象がリストでない場合には使えない。

したがってこの問題では、方程式の近似解を求めるためのアルゴリズム二分法を使って解を求める




