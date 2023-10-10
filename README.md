## Related Repositories

<table>
  <tr>
    <td colspan=2 align=center>플랫폼</td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/paasta-deployment">어플리케이션 플랫폼</a></td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/container-platform">컨테이너 플랫폼</a></td>
  </tr>
  <tr>
    <td colspan=2 rowspan=2 align=center>포털</td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/portal-deployment">AP 포털</a></td>
    <td colspan=2 align=center><a href="https://github.com/K-PaaS/cp-portal-release">CP 포털</a></td>
  </tr>
  <tr align=center>
    <td colspan=4><a href="https://github.com/K-PaaS/PaaS-TA-Monitoring">모니터링 대시보드</a></td>
  </tr>
  <tr align=center>
    <td rowspan=2 colspan=2><a href="https://github.com/K-PaaS/monitoring-deployment">모니터링</a></td>
    <td><a href="https://github.com/K-PaaS/PaaS-TA-Monitoring-Release">Monitoring</a></td>
    <td><a href="https://github.com/K-PaaS/paas-ta-monitoring-logsearch-release">Logsearch</a></td>
    <td><a href="https://github.com/K-PaaS/paas-ta-monitoring-influxdb-release">InfluxDB</a></td>
    <td><a href="https://github.com/K-PaaS/paas-ta-monitoring-redis-release">Redis</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/K-PaaS/PAAS-TA-PINPOINT-MONITORING-RELEASE">Pinpoint</td>
    <td><a href="https://github.com/K-PaaS/PAAS-TA-PINPOINT-MONITORING-BUILDPACK">Pinpoint Buildpack</td>
    <td></td>
    <td></td>
  </tr>
  </tr>
  <tr align=center>
    <td rowspan=4 colspan=2><a href="https://github.com/K-PaaS/service-deployment">AP 서비스</a></td>
    <td><a href="https://github.com/K-PaaS/PAAS-TA-CUBRID-RELEASE">Cubrid</a></td>
    <td><a href="https://github.com/K-PaaS/ap-api-gateway-release">Gateway</a></td>
    <td><a href="https://github.com/K-PaaS/ap-glusterfs-release">GlusterFS</a></td>
    <td><a href="https://github.com/K-PaaS/ap-app-lifecycle-release">🚩 Lifecycle</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/K-PaaS/PAAS-TA-LOGGING-SERVICE-RELEASE">Logging</a></td>
    <td><a href="https://github.com/K-PaaS/ap-mongodb-shard-release">MongoDB</a></td>
    <td><a href="https://github.com/K-PaaS/ap-mysql-release">MySQL</a></td>
    <td><a href="https://github.com/K-PaaS/ap-pinpoint-release">Pinpoint APM</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/K-PaaS/ap-pipeline-release">Pipeline</a></td>
    <td align=center><a href="https://github.com/K-PaaS/ap-rabbitmq-release">RabbitMQ</a></td>
    <td><a href="https://github.com/K-PaaS/ap-on-demand-redis-release">Redis</a></td>
    <td><a href="https://github.com/K-PaaS/ap-source-control-release">Source Control</a></td>
  </tr>
  <tr align=center>
    <td><a href="https://github.com/K-PaaS/ap-web-ide-release">WEB-IDE</a></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr align=center>
    <td rowspan=1 colspan=2><a href="https://github.com/K-PaaS/cp-deployment">CP 서비스</a></td>
    <td><a href="https://github.com/K-PaaS/container-platform-pipeline-release">Pipeline</a></td>
    <td><a href="https://github.com/K-PaaS/container-platform-source-control-release">Source Control</a></td>
    <td></td>
    <td></td>
  </tr>
</table>
<i>🚩 You are here.</i>



  

  


## ap-app-lifecycle-release

### Application Platform APP Lifecycle Service Configuration
- app-lifecycle-server :: N machine(s)
- ap-app-lifecycle-broker :: 1 machine
- mariadb :: 1 machine

### Create Application Platform APP Lifecycle Service Release
- Download the latest APP Lifecycle Release
    ```
    $ git clone https://github.com/K-PaaS/ap-app-lifecycle-release.git
    ```
- Download & Copy "source files" into the src directory
    ```
    ## download source files
    $ wget -O src.zip https://nextcloud.k-paas.org/index.php/s/7Do7Rr57EifaSoS/download
    
    ## unzip download source files
    $ unzip src.zip 
    
    ## final src directory
    src
    ├── common
    │   ├── pid_utils.sh
    │   └── syslog_utils.sh
    ├── java
    │   └── OpenJDK8U-jre_x64_linux_hotspot_8u212b03.tar.gz
    ├── mariadb
    │   └── mariadb-10.5.17-linux-x86_64.tar.gz
    ├── nginx
    │   └── nginx-1.21.3.tar.gz
    ├── postgres
    │   ├── downloaurl
    │   └── postgresql-11.20.tar.gz
    ├── ap-app-lifecycle-broker
    │   └── ap-app-lifecycle-broker.jar
    ├── taiga-back
    │   ├── get-pip.py
    │   ├── gosu-amd64
    │   └── taiga-back-6.7.0.zip
    └── taiga-front
        └── taiga-front-dist-6.7.0.zip
    ```
- Create APP Lifecycle Release
    ```
    $ cd ap-app-lifecycle-release
    ## <RELEASE_TARBALL_PATH> :: release file path (e.g. /home/ubuntu/workspace/ap-app-lifecycle-release.tgz) 
    $ bosh -e <bosh_name> create-release --name=ap-app-lifecycle --version=1.1.1 --tarball=<RELEASE_TARBALL_PATH> --force
    ```

### 참고 자료
- https://bosh.io/docs
- https://taigaio.github.io/taiga-doc/dist/

## Contributors ✨

<a href="https://github.com/K-PaaS/ap-api-gateway-release/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=K-PaaS/ap-api-gateway-release" />
</a>
