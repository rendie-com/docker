# 使用适合ARM64架构的基础镜像
FROM node:20
 
# 设置环境变量以确认我们正在ARM64上运行
ENV RUNTIME_ARCH=arm64
 
# 设置工作目录
WORKDIR /app
 
# 复制项目文件到工作目录
COPY . /app
 
# 安装项目依赖
RUN apt-get update && npm install
 
# 对外暴露的端口
EXPOSE 8080
 
# 启动node应用
CMD ["node", "index.js"]
