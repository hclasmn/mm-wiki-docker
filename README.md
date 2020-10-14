# mm-wiki-docker
每周自动更新一次镜像
Docker 部署（原作者https://github.com/phachon/mm-wiki）

# 数据库准备
# 导入docs/databases/data.sql和docs/databases/table.sql（注：需取消注释data.sql中第一条管理用户插入语句）

# 两种部署方式可用
# DockerHub（推荐）
# 从DockerHub下载v0.1.7版本
# 新增配置文件，数据存放目录以及Mysql数据库配置在mm-wiki.conf配置文件中设置
# 挂载配置文件及数据存放目录，启动端口为8080
# docker run -d -p 8080:8081 -v /data/mm-wiki/conf/:/opt/mm-wiki/conf/ -v /data/mm-wiki/data:/data/mm-wiki/data/ --name mm-wiki eahom/mm-wiki:v0.1.7

# 本地构建最新代码
# 构建项目镜像
# docker build -t mm-wiki-image .
# 新增配置文件，数据存放目录以及Mysql数据库配置在mm-wiki.conf配置文件中设置
# 挂载配置文件及数据存放目录，启动端口为8080
# docker run -d -p 8080:8081 -v /data/mm-wiki/conf/:/opt/mm-wiki/conf/ -v /data/mm-wiki/data/:/data/mm-wiki/data/ --name mm-wiki mm-wiki-image
