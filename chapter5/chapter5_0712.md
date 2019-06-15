---
documentclass : ltjsarticle
title : |
	第15回輪講資料  
	「コンピュータ・ネットワーク」  
	第5.6.2項 IPアドレス(pp.429-442)
author : |
	岡崎 雅大 <Masahiro Okazaki>  
	okazaki@nile.cse.kyutech.ac.jp
date : 2019年7月12日（金）
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

# はじめに
本稿では，教科書「コンピュータネットワーク」より，第5.6.2項の内容についてまとめたものである．

# IPアドレス
IPv4の特徴を定義するのは32ビットのアドレスである．
インターネット上のすべてのホストとルーターはIPアドレスを持っており，IPパケット上で送信元アドレスと宛先アドレス・フィールドの指定に使用される．
重要な点として，IPアドレスはホストではなく，ネットワーク・インタフェースを指す．
このため，あるホストが2つのネットワーク上にある場合，2つのIPアドレスを持たなければならない．
多くの場合，ホストは1つのネットワーク上にあり，IPアドレスも1つである．
一方，ルーターは複数のインタフェースを持っているため，複数のIPアドレスを持っている．

## プレフィックス