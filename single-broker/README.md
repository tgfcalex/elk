
step.1
echo "vm.max_map_count=262144" >> /etc/sysctl.conf
echo "* hard nofile 65536" >> /etc/security/limits.conf
echo "* soft nofile 65536" >> /etc/security/limits.conf
echo "* soft memlock unlimited" >> /etc/security/limits.conf
echo "* hard memlock unlimited" >> /etc/security/limits.conf
sysctl -p
ulimit -a


step.2
docker network create elk_net


step.3
elk.yml
filebeat paths

step.4
filebeat.yml
paths

step.5
docker login -u sppo55 -p as54156415

step.6
cd elk/single-broker/
cp -rp * /opt/
cd /opt/
chmod 755 -R /opt/elasticsearch/
docker-compose -f zk.yml up -d
docker-compose -f elk.yml up -d
