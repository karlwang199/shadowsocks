
安装依赖
yum -y groupinstall "Development Tools"
wget https://github.com/jedisct1/libsodium/releases/download/1.0.16/libsodium-1.0.16.tar.gz
tar xf libsodium-1.0.16.tar.gz && cd libsodium-1.0.16
./configure && make -j2 && make install
echo /usr/local/lib > /etc/ld.so.conf.d/usr_local_lib.conf
ldconfig


获取仓库文件

cd /root
yum -y install python-setuptools
easy_install pip
git clone -b manyuser https://github.com/karlwang199/shadowsocks.git
cd shadowsocks
pip install -r requirements.txt
cp apiconfig.py userapiconfig.py
cp config.json user-config.json
关闭防火墙
systemctl stop firewalld.service

编辑配置文件，对接节点
vi userapiconfig.py

确定都填写正确后，用调试模式先启动后端：
python server.py

./run.sh




























