1：grafana 安装

wget https://dl.grafana.com/oss/release/grafana-5.4.2.darwin-amd64.tar.gz

tar -zxvf grafana-5.4.2.darwin-amd64.tar.gz

2：telegraf 安装

wget https://dl.influxdata.com/telegraf/releases/telegraf-1.9.2_linux_amd64.tar.gz

tar xvfz telegraf-1.9.2_linux_amd64.tar.gz

3：influxdb 安装

wget https://dl.influxdata.com/influxdb/releases/influxdb_1.7.2_amd64.deb

sudo dpkg -i influxdb_1.7.2_amd64.deb




brew update

brew install influxdb

ln -sfv /usr/local/opt/influxdb/*.plist ~/Library/LaunchAgents


# 配置文件在/etc/influxdb/influxdb.conf ，如果没有就将/usr/local/etc/influxdb.conf 拷一个过去

配置缓存：cache-max-memory-size

#启动服务

launchctl load ~/Library/LaunchAgents/homebrew.mxcl.influxdb.plist

#停止服务

launchctl unload ~/Library/LaunchAgents/homebrew.mxcl.influxdb.plist

#前台启动

influxd -config /usr/local/etc/influxdb.conf

查看influxdb运行配置

influxd config
