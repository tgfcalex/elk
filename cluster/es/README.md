1. 三台都宿主機務必先執行
echo "vm.max_map_count=262144" >> /etc/sysctl.conf
echo "* hard nofile 65536" >> /etc/security/limits.conf
echo "* soft nofile 65536" >> /etc/security/limits.conf
echo "* soft memlock unlimited" >> /etc/security/limits.conf
echo "* hard memlock unlimited" >> /etc/security/limits.conf
sysctl -p
ulimit -a
docker network create net --subnet=172.100.0.0/24

elasticsearch資料夾複製到/opt底下
docker-compose -f /elk.yml up -d