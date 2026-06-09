import os
from flask import Flask

# 初始化 Flask 應用程式
app = Flask(__name__)

# 定義首頁路由
@app.route('/')
def home():
    return '''
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="UTF-8">
        <title>Python 期末專題</title>
        <style>
            body { font-family: Arial, sans-serif; text-align: center; margin-top: 50px; background-color: #f4f7f6; }
            .container { background-color: white; padding: 30px; border-radius: 10px; display: inline-block; box-shadow: 0px 0px 10px rgba(0,0,0,0.1); }
            h1 { color: #333; }
            a { color: #1b75bb; text-decoration: none; font-weight: bold; }
            a:hover { text-decoration: underline; }
        </style>
    </head>
    <body>
        <div class="container">
            <h1>歡迎來到我的 Python 期末成果網站！</h1>
            <p>班級：資管系 2A</p>
            <p>姓名：李紹圻</p>
            <hr>
            <p>這是一個使用 Flask 框架開發並部署於雲端的動態網頁。</p>
            <a href="/about">👉 點擊這裡進入「關於我」頁面</a>
        </div>
    </body>
    </html>
    '''

# 定義關於我路由
@app.route('/about')
def about():
    return '''
    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="UTF-8">
        <title>關於我</title>
        <style>
            body { font-family: Arial, sans-serif; text-align: center; margin-top: 50px; background-color: #f4f7f6; }
            .container { background-color: white; padding: 30px; border-radius: 10px; display: inline-block; box-shadow: 0px 0px 10px rgba(0,0,0,0.1); }
            h1 { color: #333; }
            a { color: #1b75bb; text-decoration: none; font-weight: bold; }
        </style>
    </head>
    <body>
        <div class="container">
            <h1>關於我 (About Me)</h1>
            <p>大家好，我是林靖淏。這是我的 Python 網頁開發初體驗。</p>
            <p>本專案展示了如何將後端 Python 程式碼與前端 HTML 結合，並透過 Git 實現自動化雲端部署。</p>
            <hr>
            <a href="/">⬅️ 返回首頁</a>
        </div>
    </body>
    </html>
    '''

# 啟動伺服器並綁定雲端環境變數 Port
if __name__ == '__main__':
    port = int(os.environ.get('PORT', 5000))
    app.run(host='0.0.0.0', port=port)
