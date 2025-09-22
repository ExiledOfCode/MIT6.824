```sh
# 安装 go
curl -L -O https://go.dev/dl/go1.13.6.linux-amd64.tar.gz
tar xzf go1.13.6.linux-amd64.tar.gz -C /usr/local

# Config Go ENV
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export GOPROXY=https://goproxy.cn
export GO111MODULE=on
# Merge PATH
export PATH=$PATH:$GOROOT/bin:$GOPATH/bin

# 运行程序
cd src/main
go build -buildmode=plugin ../mrapps/wc.go
rm mr-out*
go run mrsequential.go wc.so pg*.txt
more mr-out-0


```