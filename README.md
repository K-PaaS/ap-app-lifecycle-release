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
    $ wget -O src.zip https://nextcloud.k-paas.org/index.php/s/ogJQDLAER6mfbwd/download    
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
    │   └── postgresql-11.21.tar.gz
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
