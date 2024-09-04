# 使用适合ARM架构的基础镜像
FROM balenalib/generic-aarch64-alpine:edge-build
 
# 设置Node.js和Yarn的版本
ENV NODE_VERSION 16.15.1
ENV YARN_VERSION 1.22.4
 
# 安装Node.js和Yarn
RUN apk add --no-cache libgcc libstdc++ libuv && \
    curl -SLO "http://resin-packages.s3.amazonaws.com/node/v$NODE_VERSION/node-v$NODE_VERSION-linux-alpine-aarch64.tar.gz" && \
    echo "19e6916df79781c440e4949bb8b3714c7f8a26ed34ec5cd6f32e6871223ec0c53  node-v$NODE_VERSION-linux-alpine-aarch64.tar.gz" | sha256sum -c - && \
    tar -xzf "node-v$NODE_VERSION-linux-alpine-aarch64.tar.gz" -C /usr/local && \
    rm "node-v$NODE_VERSION-linux-alpine-aarch64.tar.gz" && \
    cd /usr/local/node-v$NODE_VERSION-linux-alpine-aarch64 && \
    ln -s /usr/local/node-v$NODE_VERSION-linux-alpine-aarch64/bin/* /usr/local/bin
 
# 设置环境变量
ENV NODE_ENV=production
 
# 复制你的应用文件到容器中
COPY . /home/node/app
 
# 切换工作目录
WORKDIR /home/node/app
 
# 安装依赖
RUN yarn install
 
# 设置启动命令
CMD ["node", "index.js"]
