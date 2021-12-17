FROM golang:1.14

# go moduleを使用
ENV GO111MODULE=on 

# アプリケーションを実行するディレクトリを指定
WORKDIR /go/src/github.com/Le0tk0k/go-rest-api

# 上記のディレクトリにgo.modとgo.sumをコピー
COPY go.mod go.sum ./
# 上記のファイルに変更がなければキャッシュ利用できる
RUN go mod download

COPY . .
RUN go build .

RUN go get github.com/pilu/fresh

EXPOSE 8080

# freshコマンドでサーバーを起動
CMD ["fresh"]