方法1
#以下代码一起复制粘贴回车

>yum install -y wget && wget -O install.sh http://download.bt.cn/install/install.sh && echo y | sh install.sh && \
wget -O update.sh http://download.bt.cn/install/update_pro.sh && bash update.sh pro && \
>/www/server/panel/data/userInfo.json && \
/etc/init.d/bt restart && /etc/init.d/bt default



方法2
#以下代码一起复制粘贴回车

wget -O install.sh http://download.bt.cn/install/install.sh && echo y | sh install.sh && \
wget -O update.sh http://download.bt.cn/install/update_pro.sh && bash update.sh pro && \
cd /www/server && cp -r panel panel-bak && \
wget http://download.bt.cn/install/update/LinuxPanel-5.9.0_pro.zip && \
unzip -o LinuxPanel-5.9.0_pro.zip panel/class/common.py && rm -f LinuxPanel-5.9.0_pro.zip && \
sed -i "s/data = panelAuth.panelAuth().get_order_status(None);/data = {'status' : True,'msg' : {'endtime' : 32503651199 }};/" /www/server/panel/class/common.py && \
>/www/server/panel/data/userInfo.json && \
/etc/init.d/bt restart && /etc/init.d/bt default
