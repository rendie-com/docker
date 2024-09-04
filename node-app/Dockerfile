# 使用适合ARM架构的基础镜像
FROM balenalib/generic-aarch64-alpine:edge-build
 
# 复制你的应用文件到容器中
COPY . /home/node/app
 
# 切换工作目录
WORKDIR /home/node/app
 
# 安装依赖
RUN npm install
 
# 设置启动命令
CMD ["node", "index.js"]
