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
シック・イーサネットで用いられたケーブルは，直径約\SI{10}{mm}，インピーダンスが\SI{50}{\omega}の太い同軸ケーブルであった．
このケーブルは太くて取り回しが面倒であった上に，接続なども不便であった．
よって，シン・イーサネットでは，直径直径約\SI{5}{mm}，インピーダンスが\SI{50}{\omega}の同軸ケーブルを使用した．
それぞれにおいて最大ケーブル長が異なるのは，ケーブルの太さが違うことで耐ノイズ性や減衰量が異なるためである．
一般的に，ケーブルは太く，シールドの多いほうがノイズの影響を受けにくく，減衰量も小さくなる．
よってシック・イーサネットがより長い最大ケーブル長となっている．

# トランシーバーの間隔