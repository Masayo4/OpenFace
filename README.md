# OpenFace
***
## Overview  
OpenFaceについての調査および実装計画  
日本語の記事がほとんどなく説明も英語なので必要な部分を日本語に訳していく  
***  
## MEMO
***  
### OpenFaceの主な機能  

1. 顔の特徴点の抽出
2. 顔の特徴点および顔の向きのトラッキング
3. Facial Action Unit Recognition (ユニットを組み合わせた表情の判定)
4. 視線のトラッキング
5. 顔の特徴点抽出

### FAU(Facial Action Unit)の詳細
実際にどのような値が取れるのか? 組み合わせはどのように考えるのかをまとめる  
(特に重要とされるものはボールドで記載する)
#### 判断基準  
筋肉の動きを生物学的に判断をしている
#### 各用語の解説   
AU: Action Unit 基盤となる筋肉や筋肉群  
ADs: Action descriptions AUまでの判断基準とはいかないまでも判断基準となる筋肉や筋肉群  
各バーツにおいてA~Eの強度が付いている  
A(弱い)~E(強い) で表情の筋肉の動きの強さを示している  
RとL: Rは右側,Lは左側のパーツを表す  
UとA: Uは片側だけに起こるが左や右の指定がない, Aは片側だけでより強く表出するもの  

#### 各ユニットが示すパーツ
[イメージ画像](https://www.cs.cmu.edu/~face/facs.htm)  
| Unit number | English | 日本語 |
|:-----------|:------------|:------------|
|0	|Neutral face|	中立顔 |
|1	|Inner brow raiser|	内側の眉毛が上がる |
|2	|Outer brow raiser|	外側の眉毛が上がる |
|4	|Brow lowerer|	眉毛が下がる |
|5	|Upper lid raiser|	瞼が上がる |
|6	|Cheek raiser|	ほほが上がる |
|7	|Lid tightener|	瞼が細くなる |
|8	|Lips toward each other|	唇が前に尖る |
|9	|Nose wrinkler|	 鼻にシワがよる |
|10	|Upper lip raiser|	上唇が上がる |
|11	|Nasolabial deepener|	ほうれい線が深くなる |
|12	|Lip corner puller|	口角が上がる |
|13	|Sharp lip puller|	プクーっとする |
|14	|Dimpler|	えくぼ |
|15	|Lip corner depressor|	口角が下がる |
|16	|Lower lip depressor|	下唇が下向き |
|17	|Chin raiser|	顎が上がる |
|18	|Lip pucker| 唇を尖らせる	 |
|19	|Tongue show|	　下が出る |
|20	|Lip stretcher|	横に唇が伸びる |
|21	|Neck tightener|	首？ |
|22	|Lip funneler|	歯が出るように口をすぼめる |
|23	|Lip tightener|	口をすぼめる |
|24	|Lip pressor|	唇を潰す |
|25	|Lips part|	口を開く（唇がはなれる） |
|26	|Jaw drop|	大きく口が開く |
|27	|Mouth stretch|	顎がうごくくらい大きく口が開く |
|28	|Lip suck|	お口チャック |


#### 組み合わせ  
幸福: 6 + 12  
悲しみ: 1 + 4 +15  
驚き: 1 + 2 + 5B + 26  
恐怖: 1 + 2 + 4 + 5 + 7 + 20 + 26  
怒り: 4 + 5 + 7 + 23
嫌悪: 9 + 15 + 16  
軽蔑: R12A + r14A  



## REFERENCE  
[公式wiki](https://github.com/TadasBaltrusaitis/OpenFace/wiki)  
[日本語でのOpenFace紹介](https://medium.com/@NegativeMind/%E3%82%AA%E3%83%BC%E3%83%97%E3%83%B3%E3%82%BD%E3%83%BC%E3%82%B9%E3%81%AE%E9%A1%94%E3%81%AE%E5%8B%95%E4%BD%9C%E8%A7%A3%E6%9E%90%E3%83%84%E3%83%BC%E3%83%AB%E3%82%AD%E3%83%83%E3%83%88-openface-2383cbb56823)  


## Author
Masayoshi Tsuruoka  
[HP](https://www.ht.sfc.keio.ac.jp/~massaman/)  
[GIT](https://github.com/Masayo4)   
