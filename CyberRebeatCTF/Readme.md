# CyberRebeatCTF  Writeup by 氷影
  in 2018/09/08 15:00 - 2018/09/09 15:00
* ## Exercise
    * ### [Exercise](https://cyberrebeat.adctf.online/ja/contests/2/problems/16)  
        問題文に表示されている文字列をFlagとしてsubmitするだけ。  
        Flagの形式を知ることは後の問題を解くうえでも大事。  
        Flag:`CRCTF{CyberRebeatCTF}`
 
* ## Misc
    * ### [Readme](https://cyberrebeat.adctf.online/ja/contests/2/problems/5/problem_attachments/10)
        画像が渡される。英文をカタカナなどを加工した形で表しているので何となくで推測をする。すると、
        >CAN YOU READ JAPANESE?  
        >IF SO, THIS QUESTION MAY BE DIFFICULT.  
        >CRCTF{YOUCANPLAYCYBERREBEATINBOTHLANGUAGES}   
  
        と読めるので三行目がFlag。  
        Flag:`CRCTF{YOUCANPLAYCYBERREBEATINBOTHLANGUAGES}`
  
* ## Recon
    * ### [Tweet](https://cyberrebeat.adctf.online/ja/contests/2/problems/18)
        公式twitterアカウントを見ろと言われたので[これがそのアカウント](https://cyberrebeat.adctf.online/ja/contests/2/problems/18)。  
        [こんなツイート](https://twitter.com/CyberRebeat/status/1038306822602416128)があったのでこのままsubmit。　　
        Flag:`CRCTF{CyberRebeatCTF_has_started!}`
  
    * ### [CyberRebeatScripts](https://cyberrebeat.adctf.online/ja/contests/2/problems/19)  
        GitHubを知ってるかと言われた。CyberRebeatは同人ゲームである。GitHubにソースコードかなにか上がっているかなと思ってググる。  
        あった。<https://github.com/ennach/CyberRebeatScripts>   
        上がっているファイルにはFlagが見当たらなかったのでいろいろ探したら、コミットログにdelete Flagとあったのでそこを覗く。  
        ありました。<https://github.com/ennach/CyberRebeatScripts/commit/86cc1779522ad0708ad0b829935b08ac42b2588d>  
        Flag:`CRCTF{I cut down her gag in a single strike}`
  
    * ### [ChangeHistory](https://cyberrebeat.adctf.online/ja/contests/2/problems/21)
        これもGitHubを見る問題。同じアカウントのChangeHistoryのコミットログを見ると、TODO mistake云々書いてある。  
        <https://github.com/ennach/ChangeHistory/issues/1>   
        Hashを間違えたらしいのでそのハッシュで#1 commit againのURLを書き換えるとplain textsが復元できる。  
        <https://github.com/ennach/ChangeHistory/commit/c476614bc439fe1910e494422b3aa207b776d486>  
        Flag:`CRCTF{the timer is set to 120 seconds}`
  
* ## Stegano
    * ### [Secret.pdf](https://cyberrebeat.adctf.online/ja/contests/2/problems/6)
        pdfが渡されるがFlagの部分は黒で塗りつぶされていて読めない。その部分をコピペして適当なところに貼り付けたら読めるのでそのまま提出。  
        Flag:`CRCTF{I don't know of a time without the internet}`
  
    * ### [Alpha](https://cyberrebeat.adctf.online/ja/contests/2/problems/7)
        pngが渡される。いたって普通の画像なので解析ソフトにかけた。(以下に記載)  
        色々とbit抽出などしていたらアルファチャンネル　ビット0の抽出でFlagが見えた。  
        Flag:`CRCTF{ALPHA_IS_THE_NAME_OF_A_HACKER_IN_CYBERREBEAT}`  
        使用ソフト:[青い空を見上げればいつもそこに白い猫](https://digitaltravesia.jp/usamimihurricane/webhelp/_RESOURCE/MenuItem/another/anotherAoZoraSiroNeko.html)(ステガノグラフィ―解析)
* ## Trivia
    * ### [Crossword](https://cyberrebeat.adctf.online/ja/contests/2/problems/17)
        クロスワードを解いていく。答えだけすべて小文字で乗せる。 
        
        |横|縦|
        |---|---|
        |1.karma|2.aurora|  
        |5.botnet|3.unity|  
        |8.misa|4.manose|  
        |10.re:lief|6.spectre|  
        |11.hackers|7.titan|  
        |15.wannacry|9.tecchin(てっちん　綴りわからず)|  
        |16.earu または ealu(えある　綴りわからず)|12.sekaiproject|  
        |18.e.n.nach|13.cyberrebeat|  
        |19.acrivedefense|14.steampowered|  
        |20.poodle|17.heartbleed|  
        |21.shellshock||  
  
        当てはまる文字を抜き出して並べて、  
        Flag:`CRCTF{submarine}`  
          
        以上8完でした。次はやるだけ以外の問題も解きたい。
