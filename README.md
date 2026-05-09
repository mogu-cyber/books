[hon-uranai.html](https://github.com/user-attachments/files/27545976/hon-uranai.html)
<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>本の紙さま占い</title>
    <style>
        /* 全体のデザイン（小学生向けに少し明るく） */
        body { text-align: center; font-family: 'Hiragino Maru Gothic ProN', 'Yu Gothic', sans-serif; background-color: #fdfaf4; color: #443322; padding: 40px 20px; }
        .container { background: #ffffff; padding: 30px; border-radius: 30px; box-shadow: 0 8px 15px rgba(0,0,0,0.1); display: inline-block; max-width: 450px; border: 3px solid #e0d0b0; transition: all 0.4s; }
        
        /* 紙さまイラストのスタイル */
        .kami-image { 
            max-width: 100%; 
            height: auto; 
            border-radius: 10px; 
            margin-bottom: 20px; 
            display: block; 
            margin-left: auto; 
            margin-right: auto;
        }

        /* 結果表示エリア */
        #result-area { font-size: 80px; margin: 20px 0; line-height: 1.2; }

        /* ボタンのデザイン */
        .start-button { background: #8bbc9f; color: white; border: none; padding: 15px 40px; border-radius: 30px; cursor: pointer; font-size: 20px; font-weight: bold; margin-top: 20px; transition: background 0.3s; box-shadow: 0 4px 0 #6a8e78; outline: none; }
        .start-button:hover { background: #6a8e78; }
        .start-button:active { position: relative; top: 3px; box-shadow: 0 1px 0 #6a8e78; }

        h1 { font-size: 24px; color: #5d4a37; border-bottom: 2px dashed #e0d0b0; padding-bottom: 10px; }
        #message { line-height: 1.6; font-size: 17px; }
    </style>
</head>
<body>

    <div class="container" id="main-container">
        <!-- 本の紙さまイラスト（同じフォルダに paperkami.png を置いてね！） -->
        <img src="paperkami.png" alt="本の紙さま" class="kami-image" id="main-image">
        
        <h1 id="title">本の紙さま占い</h1>
        
        <!-- お告げのシンボルが出る場所 -->
        <div id="result-area"></div>

        <p id="message">
            読みたい本が見つからない？<br>
            そんな時は「本の紙さま」に聞いてみよう。<br>
            今のキミにぴったりのページを開いてくれるぞ！
        </p>
        
        <button class="start-button" id="main-button" onclick="uranai()">お告げを聞く</button>
    </div>

    <script>
        function uranai() {
            // 10種類のジャンルデータ
            const genreList = [
                { symbol: "🔍", name: "ドキドキ・ミステリー", msg: "おっと、このページには『謎』が挟まっていたぞ。キミならこの事件、解決できるかな？" },
                { symbol: "👻", name: "ゾクゾク・ホラー", msg: "パラパラ…ピタッ！背筋が凍るようなお話が呼んでおるぞ。今夜はトイレに行けるかな？" },
                { symbol: "🐉", name: "ワクワク・ファンタジー", msg: "冒険のにおいがするのう。魔法と勇者の世界へ、いざ出発じゃ！" },
                { symbol: "⚽", name: "胸アツ・スポーツ", msg: "一生懸命な姿は、紙の目から見てもまぶしいものじゃ。熱い友情に触れてみるのじゃ！" },
                { symbol: "🦕", name: "なるほど・図鑑", msg: "「なんで？」の数だけ、世界は広がるぞ。物知り博士への第一歩じゃな。" },
                { symbol: "🤣", name: "くすっと・ユーモア", msg: "笑う門には福来る！お腹をかかえて笑えば、悩みも吹き飛んでしまうぞ。" },
                { symbol: "🌟", name: "あこがれ・伝記", msg: "昔のすごい人も、キミと同じ子供だったんじゃ。人生の宝物を見つけに行こう。" },
                { symbol: "🎨", name: "うっとり・絵本", msg: "言葉を超えた魔法がここにあるぞ。絵の中に吸い込まれないようにな！" },
                { symbol: "🎎", name: "しんみり・昔ばなし", msg: "むかしむかしから伝わるお話には、大事な知恵が隠れておる。宝探し気分で読んでみるのじゃ。" },
                { symbol: "🧪", name: "はてな？・科学", msg: "世界の『ふしぎ』を解き明かすカギを見つけたぞ！実験や観察の準備はいいかな？" }
            ];
            
            const randomIndex = Math.floor(Math.random() * genreList.length);
            const result = genreList[randomIndex];

            // 演出：画像を表示したままにするか消すかはお好みで！今回はヤドカリさん流で隠します
            document.getElementById("main-image").style.display = "none";

            // 画面を書き換える
            document.getElementById("title").innerText = "紙さまのお告げ";
            document.getElementById("result-area").innerText = result.symbol;
            document.getElementById("message").innerHTML = `キミへのおすすめは…<br><strong>【${result.name}】</strong><br><br>${result.msg}`;
            
            // ボタンをリセット用に
            const button = document.getElementById("main-button");
            button.innerText = "もう一度聞く";
            button.onclick = function() { location.reload(); };
            
            // 少しだけ背景を変える
            document.getElementById("main-container").style.backgroundColor = "#fffef0";
        }
    </script>

</body>
</html>
