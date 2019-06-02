---
documentclass : ltjsarticle
title : |
	第15回輪講補講資料  
	「コンピュータ・ネットワーク」  
	第4.3節 イーサネット(pp.272-282)
author : |
	岡崎 雅大 <Masahiro Okazaki>  
	okazaki@nile.cse.kyutech.ac.jp
date : 2019年5月28日（火）
papersize : a4
header-includes:
	-	\usepackage[deluxe,noto-otf,no-math]{luatexja-preset}
	-	\usepackage{luatexja-otf}
	-	\usepackage{graphicx}
	-	\usepackage{listings}
	-	\usepackage{amssymb,amsmath}
	-	\usepackage[margin=0.8in]{geometry}
	-	\usepackage{siunitx}
	-	\usepackage{here}
	-	\setmainfont[BoldFont=Noto Serif CJK JP Bold]{Noto Serif CJK JP Regular}
	-	\setsansfont[BoldFont=Noto Sans CJK JP Bold]{Noto Sans CJK JP Regular}
---
# 最大ケーブル長
最大ケーブル長は伝送媒体の物理的性質に影響を受ける．
シック・イーサネットで用いられたケーブルは，直径約\SI{10}{mm}，インピーダンスが\SI{50}{\ohm}の太い同軸ケーブルであった．
このケーブルは太くて取り回しが面倒であった上に，接続なども不便であった．
よって，シン・イーサネットでは，直径約\SI{5}{mm}，インピーダンスが\SI{50}{\ohm}の同軸ケーブルを使用した．
それぞれにおいて最大ケーブル長が異なるのは，ケーブルの太さが違うことで耐ノイズ性やケーブルの抵抗成分による信号の減衰量が異なるためである．
一般的に，ケーブルは太く，シールドの多いほうがノイズの影響を受けにくく，減衰量も小さくなる．
よってシック・イーサネットがより長い最大ケーブル長となっている．より対線を用いたイーサネットでは，ノイズの影響をより受けるため最大ケーブル長はさらに短く，\SI{100}{m}と規定されているものが多い．

また，ケーブルの周波数特性により低周波に比べて高周波の信号がより減衰されてしまう．
よって，信号の伝達速度を上げるために周波数を上げると減衰量が多くなってしまう．

# トランシーバーの間隔
シック・イーサネットでは\SI{2.5}{m}ごとに接続する場所を示す印が印刷されている．
接続する際にはこの印ごとに行うため，隣接するトランシーバーの間隔は\SI{2.5}{m}の整数倍となる．
これは，隣接するトランシーバー間において信号干渉が起こらないようにするためのものである．
しかし，厳密に間隔を守らなかったとしても全体に致命的な影響を及ぼすわけではない．

# チェックサム
イーサネットで用いられる誤り検出手法は，32ビットCRCである．
チェックサムフィールドにはCRC値が代入される．
送信側は宛先アドレスフィールドからデータフィールドまでを対象としてCRC値を計算し，その計算結果をチェックサムフィールドに記録する．
受信側でも同様にCRC値を計算し，その値とチェックサムフィールドに記録された値を比較する．
もし値が異なった場合は誤りが発生したものとしてそのフレームを破棄し，同じ場合は誤りがないものとしてフレームを上位層へ受け渡す．
このようにフレームの中身をもとにCRC値の計算を行って誤り検出に利用するため，その結果はフレームの最後に付加する必要がある．