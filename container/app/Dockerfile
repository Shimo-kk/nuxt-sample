FROM node:lts-alpine

# ワークディレクトリを指定
WORKDIR /usr/src

# 環境変数を設定
ENV WATCHPACK_POLLING=true

# 必要なパッケージをインストール
RUN apk update && \
apk upgrade && \
apk add git && \
npm install -g npm@latest nuxi nuxt3

# ソースコードをコンテナにコピー
COPY ./src /usr/src

# 依存関係をインストール
RUN npm install

# TypeScript をビルド
RUN npm run build

# 3000番を公開
EXPOSE 3000

# CMD ["npm", "start"]
