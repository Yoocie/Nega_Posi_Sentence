# Nega_Posi_Sentence

# 目的
日本語の短文を入力し、それがどれだけポジティブな文章かを定量してみること。

# 方法
1. 単語感情極性対応表（東京工業大学 高村先生）の読み込み
2. 文章の手入力
3. 入力した文章をMeCabによって形態素に分けた。

  例：
  -入力した文章：優れた作品だと認められたね。めでたいなあ。

  -出力
  優れ	スグレ	優れる	動詞-自立	一段	連用形
  た	タ	た	助動詞	特殊・タ	基本形
  作品	サクヒン	作品	名詞-一般		
  だ	ダ	だ	助動詞	特殊・ダ	基本形
  と	ト	と	助詞-格助詞-引用		
  認め	ミトメ	認める	動詞-自立	一段	未然形
  られ	ラレ	られる	動詞-接尾	一段	連用形
  た	タ	た	助動詞	特殊・タ	基本形
  ね	ネ	ね	助詞-終助詞		
  。	。	。	記号-句点		
  めでたい	メデタイ	めでたい	形容詞-自立	形容詞・アウオ段	基本形
  なあ	ナア	なあ	助詞-終助詞		
  。	。	。	記号-句点	

4. 形態素の原型を取り出し(例：認め→認める),それが単語感情極性表に含まれる場合、ネガポジの値を取り出した。(-1.0が最もネガティブ、1.0が最もポジティブ)
5. 短文に含まれる形態素のネガポジの値の平均値を出力した。

# 感想
単語ごとの感情極性値の平均を取るだけだと、直感に反した出来がかなり多かったです。
単語ごとの関連を調べる係受け解析などの必要性を痛感しました。
  例：
    入力：「昨日はいい天気だったので、テラスで昼食を食べました。とても美味しかったです。」
    出力：-0.2597057777777778　（ややネガティブ）
    
