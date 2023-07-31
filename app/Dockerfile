# ベースイメージとしてPython公式イメージを使用します
FROM python:3.9-slim

# コンテナ内に/appディレクトリを作成します
WORKDIR /app

# 必要なパッケージをインストールします
RUN apt-get update && apt-get install -y gcc

# Pythonの依存パッケージをコピーしてインストールします
COPY ./app/requirements.txt /app/
RUN pip install --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

# カレントディレクトリのコードをコンテナ内の/appにコピーします
COPY ./app/ /app/

# # マイグレーションを実行します
# RUN flask db upgrade

# Flaskアプリを起動するコマンドを指定します
CMD [ "python", "app.py" ]