# Python & Visual Studio Code 簡易教學
***對於初學者來說，這是一款<font color=#FF6600>簡易</font>上手的<u>程式語言</u>。<br>本文稍後會介紹關於 Windows環境，python 的<u>安裝及設定</u>和<u>編輯工具</u>軟體***

---
# Getting Started
+ [Python](https://www.python.org/downloads/)(語言)
+ [Visual Studio Code](https://code.visualstudio.com/)(編輯工具)
+ 學習目錄
  + [1. Python](#1)
    + [1.1 安裝](#1-1)
    + [1.2 環境設定](#1-2)
    + [1.3 PIP 軟體包管理系統](#1-3)
      + [1.3.1 pip 套件進階相關指令](#1-3-1)
      + [1.3.2 pipenv 套件管理工具](#1-3-2)
    + [1.4 資料參考](#1-4)
  + [2. Visual Studio Code](#2)
    + [2.1 安裝](#2-1)
    + [2.2 安裝外掛](#2-2)
    + [2.3 Code Runner 外掛和 Python 設定](#2-3)
      + [2.3.1 Code Runner 亂碼問題](#2-3-1)
    + [2.4 資料參考](#2-4)

# <h1 id="1">Python</h1>
## <h2 id="1-1">1. 安裝(圖庫搬運以下參考)</h2>
+ 參考 [Python 安裝教學及說明](https://medium.com/ai-for-k12/python-%E5%AE%89%E8%A3%9D%E6%95%99%E5%AD%B8%E5%8F%8A%E8%AA%AA%E6%98%8E-a07de2463d98)<br>
參考 [Python 官方下載網址](https://www.python.org/downloads/)<br>
![安裝-1](https://miro.medium.com/max/700/1*l2pQI0R7v31rYBGwEWiIbQ.png)
![安裝-2](https://miro.medium.com/max/700/1*NQ-aacv7QDgPm2onK6dfvg.png)
![安裝-3](https://miro.medium.com/max/700/1*kh1Ofi6Vh-BSFj-vHkAqRQ.png)
![安裝-4](https://miro.medium.com/max/700/1*p6tuAbybi19wAb7OWsVNqQ.png)

+ 確認 Python 是否已安裝成功，開啟 `CMD` 輸入下列訊息。
```cmd
python --version
```

---
## <h2 id="1-2">2. 環境設定</h2>
+ [電腦] → [內容] → [進階環境設定] → [進階] → [環境變數]
  + 編輯 [Path] 加入 <u><font color=#FF6600>Python目錄</font></u> 和 <u><font color=#FF6600>Python Scripts目錄</font></u>
![環境設定-1](https://miro.medium.com/max/700/1*99NsvhOdPY9GSONfGmCebA.png)
![環境設定-2](https://miro.medium.com/max/1000/1*koLBo9rLFhxlgVc9FxNqig.png)

---
## <h2 id="1-3">3. PIP (軟體包管理系統)</h2>
+ 參考 [Windows 安裝Python套件管理工具pip](https://matthung0807.blogspot.com/2019/08/windows-pythonpip.html)

+ pip `未安裝`，請先行下載 [get-pip.py](https://bootstrap.pypa.io/get-pip.py)。<br>下載完成後，切換至用戶下載放置檔案 (`get-pip.py`)的位置，並在資料夾空白處，同時按住`鍵盤shift`和`滑鼠右鍵`，點選`在此處開啟命令視窗(w)`，開啟 `CMD` 輸入下列訊息。
```cmd
python get-pip.py
```

+ `確認`是否已安裝 pip，開啟 `CMD` 輸入下列訊息。
```cmd
python -m pip --version
```

+ 部分套件需要最新的 pip 版本，所以，`更新` pip 版本是必要的，開啟 `CMD` 輸入下列訊息。
```cmd
python -m pip install -U pip
```

+ 用 pip `安裝` python 套件，使用 [`物件名稱`]，開啟 `CMD` 輸入下列訊息。
```cmd
python -m pip install requests             # latest version
python -m pip install requests==1.0.4      # specific version
python -m pip install 'requests>=1.0.4'    # minimum version
```

+ 用 pip `移除`已下載 python 套件，開啟 `CMD` 輸入下列訊息。
```cmd
python -m pip uninstall requests
```

+ `列出`已下載的套件，開啟 `CMD` 輸入下列訊息。
```cmd
python -m pip list
```

---
### <h2 id="1-3-1">※ ***pip 套件進階相關指令***</h2>
+ 用 pip `安裝` python 套件，使用 [`列表檔案.txt`]，開啟 `CMD` 輸入下列訊息。
```cmd
python -m pip install -r requirements.txt
```

+ `導出`已下載的套件至 [`列表檔案.txt`]，開啟 `CMD` 輸入下列訊息。
```cmd
python -m pip freeze > requirements.txt
```

+ `複製`現有套件至其他系統環境，開啟 `CMD` 輸入下列訊息。
```cmd
python -m pip freeze > requirements.txt
python -m pip install -r requirements.txt
```

---
### <h2 id="1-3-2">※ ***pipenv 套件管理工具***</h2>
+ 參考 [Pipenv 更簡單、更快速的 Python 套件管理工具](https://medium.com/@chihsuan/pipenv-%E6%9B%B4%E7%B0%A1%E5%96%AE-%E6%9B%B4%E5%BF%AB%E9%80%9F%E7%9A%84-python-%E5%A5%97%E4%BB%B6%E7%AE%A1%E7%90%86%E5%B7%A5%E5%85%B7-135a47e504f4)<br>
參考 [[Python] 讓Pipenv 幫你做套件管理](https://medium.com/tsungs-blog/python-%E8%AE%93pipenv-%E5%B9%AB%E4%BD%A0%E5%81%9A%E5%A5%97%E4%BB%B6%E7%AE%A1%E7%90%86-bb284e865dc1)<br>
參考 [有效管理Python套件(Package)的工具及概念](https://www.learncodewithmike.com/2020/02/python-pip-and-pipenv.html)<br>
參考 [Pipenv指令大全](https://medium.com/@hiimdoublej/pipenv%E6%8C%87%E4%BB%A4%E5%A4%A7%E5%85%A8-6e4415cc8a15)<br>


+ 用 pip 安裝 Pipenv，開啟 `CMD` 輸入下列訊息。
```cmd
python -m pip install pipenv
```

+ 用 Pipenv 在專案目錄下，建立 `python2` or `python3` `虛擬環境`，開啟 `CMD` 輸入下列訊息。
```cmd
pipenv install --two          # 產生 Python 2 虛擬環境
pipenv install --three        # 產生 Python 3 虛擬環境
pipenv install --python 3.6.5 # 產生 Python 3.6.5 虛擬環境，更精確的指定版本
```

+ 用 Pipenv `安裝`套件，開啟 `CMD` 輸入下列訊息。
```cmd
pipenv install requests
pipenv install requests --dev  # development 環境
```

+ 用 Pipenv `移除`套件，開啟 `CMD` 輸入下列訊息。
```cmd
pipenv uninstall request
```

+ 用 Pipenv `檢查`，開啟 `CMD` 輸入下列訊息。
```cmd
pipenv check
```

+ 用 Pipenv `列出`套件的相依圖，開啟 `CMD` 輸入下列訊息。
```cmd
pipenv graph
```

---
## <h2 id="1-4">4. 資料參考</h2>
+ python
  + [Python 安裝教學及說明](https://medium.com/ai-for-k12/python-%E5%AE%89%E8%A3%9D%E6%95%99%E5%AD%B8%E5%8F%8A%E8%AA%AA%E6%98%8E-a07de2463d98)
  + [Python 官方下載網址](https://www.python.org/downloads/)
+ PIP 套件管理工具
  + [pip 文件](https://pip.pypa.io/en/stable/user_guide/)
  + [pip freeze 文件](https://pip.pypa.io/en/stable/reference/pip_freeze/#pip-freeze)
  + [Windows 安裝Python套件管理工具pip](https://matthung0807.blogspot.com/2019/08/windows-pythonpip.html)
+ PIPENV 套件
  + [pipenv 文件](https://docs.pipenv.org/install/#homebrew-installation-of-pipenv)
  + [Pipenv 更簡單、更快速的 Python 套件管理工具](https://medium.com/@chihsuan/pipenv-%E6%9B%B4%E7%B0%A1%E5%96%AE-%E6%9B%B4%E5%BF%AB%E9%80%9F%E7%9A%84-python-%E5%A5%97%E4%BB%B6%E7%AE%A1%E7%90%86%E5%B7%A5%E5%85%B7-135a47e504f4)
  + [[Python] 讓Pipenv 幫你做套件管理](https://medium.com/tsungs-blog/python-%E8%AE%93pipenv-%E5%B9%AB%E4%BD%A0%E5%81%9A%E5%A5%97%E4%BB%B6%E7%AE%A1%E7%90%86-bb284e865dc1)
  + [有效管理Python套件(Package)的工具及概念](https://www.learncodewithmike.com/2020/02/python-pip-and-pipenv.html)
  + [Pipenv指令大全](https://medium.com/@hiimdoublej/pipenv%E6%8C%87%E4%BB%A4%E5%A4%A7%E5%85%A8-6e4415cc8a15)


# <h1 id="2">Visual Studio Code</h1>
## <h2 id="2-1">1. 安裝(圖庫搬運以下參考)</h2>
+ 參考[Visual Studio Code 下載安裝筆記](https://clay-atlas.com/blog/2020/09/03/visual-studio-code-%E4%B8%8B%E8%BC%89%E5%AE%89%E8%A3%9D%E7%AD%86%E8%A8%98/)<br>
參考[VSCode快速安裝教學，推薦常用外掛擴充套件](https://tw.alphacamp.co/blog/visual-studio-code-editor-tutorial-and-extensions)<br>
參考[使用VS code建置環境並執行python程式](https://ithelp.ithome.com.tw/articles/10212365)<br>
參考 [Visual Studio Code 官方下載網址](https://code.visualstudio.com/)<br>
![安裝-1](https://i0.wp.com/clay-atlas.com/wp-content/uploads/2020/09/image-1.png?resize=768%2C437&ssl=1)
![安裝-2](https://uploads-ssl.webflow.com/5d3a7aed4e11720246d46f49/5e3ccf43c849bf36ef854b77_ExportedContentImage_00.png)

---
## <h2 id="2-2">2. 安裝外掛(圖庫搬運以下參考)</h2>
+ 參考[Visual Studio Code 環境設定](https://medium.com/icguanyu/visual-studio-code-%E5%9F%BA%E7%A4%8E%E7%92%B0%E5%A2%83%E8%A8%AD%E5%AE%9A-%E5%89%8D%E7%AB%AF-14756e7a2424)<br>
![外掛安裝-1](https://miro.medium.com/max/467/0*B2KREvDqOj9leBy1.png)<br>
+ Chinese (Traditional) Language Pack for Visual Studio Code
  + 中文版套件
+ cdnjs
  + 未來引入外掛的好幫手
+ Live Server
  + 在本地端啟用伺服器預覽網站使用
+ Live Sass Compiler
  + 編譯Sass/Scss
+ Prettier — Code formatter
  + 協助將你的程式碼排整齊。
    + Window : Shift + Alt + F
    + Mac : Shift + Commend + F
+ Code Spell Checker
  + 檢查有沒有拼錯字，超級推薦
+ AutoFileName
  + 自動填入檔案路徑，在引入檔案時很方便
+ indent-rainbow
  + 顯示縮排顏色的小工具
+ vscode-icons
  + 讓資料夾和檔案有漂亮的 icons
+ One Dark (Sublime Babel) or One Dark Pro
  + 主題顏色，還有很多外掛可自由選擇。
  + 變更方式：[檔案]→[喜好設定]→[色彩佈景主題]，即可選擇主題。
+ GlassIt-VSC
  + 整個VSCode視窗透明度 Ctrl + Alt + ZorC
+ Code Runner
  + 程式 Compiler

---
## <h2 id="2-3">3. Code Runner 外掛和 Python 設定(圖庫搬運以下參考)</h2>
+ 參考[Visual Studio Code Python環境建置](https://www.learncodewithmike.com/2019/11/python2-visual-studio-code-python.html)<br>
+ 參考[Visual Studio Code 環境設定](https://medium.com/icguanyu/visual-studio-code-%E5%9F%BA%E7%A4%8E%E7%92%B0%E5%A2%83%E8%A8%AD%E5%AE%9A-%E5%89%8D%E7%AB%AF-14756e7a2424)<br>
+ 參考[使用VS code建置環境並執行python程式](https://ithelp.ithome.com.tw/articles/10212365)<br>
+ 開啟使用者喜好設定
  + 按下 [Ctrl + Shift + P] → 輸入 [settings]

![設定-1](https://1.bp.blogspot.com/-GyNgB2gd6i4/Xc-g_XIu2JI/AAAAAAAAALM/YAEvPQAK-ug0fySJUt9x_91NeWzl7h7KgCLcBGAsYHQ/s640/v9.PNG)
  + 圖形點選[設定] → [Settings Ctrl+,]

![設定-2](https://1.bp.blogspot.com/-Vq4BuJXC4YE/Xc-g8LbueOI/AAAAAAAAALI/B7mleTQsA_cs5-vipYE5vGilOsXiZBkogCLcBGAsYHQ/s640/v8.PNG)

+ `編輯` settings.json
```json
{
    "python.pythonPath": "C:\\Users\\user\\AppData\\Local\\Programs\\Python\\Python37\\python.exe", //依個人安裝路徑作調整
    "python.linting.enabled": true,
    "python.linting.pylintEnabled": true,
    "files.trimTrailingWhitespace": true, // 儲存的時候，會幫你自動過濾多餘的空格
    "files.autoSave": "onFocusChange", // 是否自動儲存檔案
    "[python]":{  // 加入這幾行
        "editor.formatOnType": true,
        "editor.formatOnSave": true,
        "editor.renderIndentGuides": true,
        "editor.insertSpaces": true,
        "editor.detectIndentation": true,
        "editor.tabSize": 4
    },
}
```

---
### <h2 id="2-3-1">※ ***Code Runner 亂碼問題***</h2>
+ 參考[Code Runner 亂碼問題](https://zh-tw.coderbridge.com/@iiiplay/bd123619f9af451481639f50f62c3619)<br>
參考[VS Code採用Code Runner遇到的 Output中文亂碼問題 (Python)
](https://umin27.medium.com/vs-code%E6%8E%A1%E7%94%A8code-runner%E9%81%87%E5%88%B0%E7%9A%84-output%E4%B8%AD%E6%96%87%E4%BA%82%E7%A2%BC%E5%95%8F%E9%A1%8C-python-55e73edf9d0b)<br>
參考[解决VS Code使用code runner开发Python乱码问题](https://www.cnblogs.com/zhaoshizi/p/9050768.html)<br>

+ <方法一> `編輯` settings.json
```json
{
  "code-runner.executorMap": {
          "java": "cd $dir && javac -encoding utf8 $fileName && java -Dfile.encoding=UTF-8 $fileNameWithoutExt",
          "python": "set PYTHONIOENCODING=utf8 && python -u"
  },
}
```

+ <方法二>`編輯` settings.json
  + 更改 "code-runner.runInTerminal": true
![設定-2](https://miro.medium.com/max/700/1*4_2bPrXDbrmbBXc5KVNOzw.gif)

## <h2 id="2-4">4. 資料參考</h2>
+ Visual Studio Code 安裝
  + [Visual Studio Code 下載安裝筆記](https://clay-atlas.com/blog/2020/09/03/visual-studio-code-%E4%B8%8B%E8%BC%89%E5%AE%89%E8%A3%9D%E7%AD%86%E8%A8%98/)
  + [VSCode快速安裝教學，推薦常用外掛擴充套件](https://tw.alphacamp.co/blog/visual-studio-code-editor-tutorial-and-extensions)
  + [使用VS code建置環境並執行python程式](https://ithelp.ithome.com.tw/articles/10212365)
  + [Visual Studio Code 官方下載網址](https://code.visualstudio.com/)
+ Visual Studio Code 環境設定
  + [Visual Studio Code 環境設定](https://medium.com/icguanyu/visual-studio-code-%E5%9F%BA%E7%A4%8E%E7%92%B0%E5%A2%83%E8%A8%AD%E5%AE%9A-%E5%89%8D%E7%AB%AF-14756e7a2424)
+ Code Runner
  + [Visual Studio Code Python環境建置](https://www.learncodewithmike.com/2019/11/python2-visual-studio-code-python.html)
  + [使用VS code建置環境並執行python程式](https://ithelp.ithome.com.tw/articles/10212365)
  + [Code Runner 亂碼問題](https://zh-tw.coderbridge.com/@iiiplay/bd123619f9af451481639f50f62c3619)
  + [VS Code採用Code Runner遇到的 Output中文亂碼問題 (Python)
](https://umin27.medium.com/vs-code%E6%8E%A1%E7%94%A8code-runner%E9%81%87%E5%88%B0%E7%9A%84-output%E4%B8%AD%E6%96%87%E4%BA%82%E7%A2%BC%E5%95%8F%E9%A1%8C-python-55e73edf9d0b)
  + [解决VS Code使用code runner开发Python乱码问题](https://www.cnblogs.com/zhaoshizi/p/9050768.html)
