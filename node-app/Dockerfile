# 使用针对ARM的Node基础镜像
FROM balenalib/armv7hf-node:14-stretch
 
# 设置工作目录
WORKDIR /app
 
# 复制项目文件到工作目录
COPY . /app
 
# 安装项目依赖
RUN npm install
 
# 对外暴露的端口
EXPOSE 8080
 
# 启动node应用
CMD ["node", "index.js"]
