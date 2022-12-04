## Proyecto Final DevOPS Fullstack USIP

  # Integrantes
1. Edy Felix Tarqui Guarachi  

JenkisFile para el despliege de  proyectos para: backend y frontend

### -> Se adjunta una imagen con los stages recomendados ###

![Ejecucion](devops1.PNG)
### stages ###

![Ejecucion](devops2.PNG)

- ->Incluir un salida de ejecucion de salida de jenkins
    ```
      Started by user edy tarqui
      [Pipeline] Start of Pipeline
      [Pipeline] stage
      [Pipeline] { (Clone Backend Repository for DEV environment)
      [Pipeline] node
      Running on debian-test in /home/test/jenkins_slave/workspace/Modulo8_Devops
      [Pipeline] {
      [Pipeline] git
      The recommended git tool is: NONE
      No credentials specified
      Fetching changes from the remote Git repository
      > git rev-parse --resolve-git-dir /home/test/jenkins_slave/workspace/Modulo8_Devops/.git # timeout=10
      > git config remote.origin.url https://github.com/edytarqui3/m8-backend.git # timeout=10
      Fetching upstream changes from https://github.com/edytarqui3/m8-backend.git
      > git --version # timeout=10
      > git --version # 'git version 2.30.2'
      > git fetch --tags --force --progress -- https://github.com/edytarqui3/m8-backend.git +refs/heads/*:refs/remotes/origin/* # timeout=10
      Checking out Revision f470bb114549c9d172115f205c63a5761b19fc5c (refs/remotes/origin/main)
      Commit message: "Adding docker compose for backend"
      > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
      > git config core.sparsecheckout # timeout=10
      > git checkout -f f470bb114549c9d172115f205c63a5761b19fc5c # timeout=10
      > git branch -a -v --no-abbrev # timeout=10
      > git branch -D main # timeout=10
      > git checkout -b main f470bb114549c9d172115f205c63a5761b19fc5c # timeout=10
      > git rev-list --no-walk f470bb114549c9d172115f205c63a5761b19fc5c # timeout=10
      [Pipeline] echo
      Cloned Backend Project
      [Pipeline] }
      [Pipeline] // node
      [Pipeline] }
      [Pipeline] // stage
      [Pipeline] stage
      [Pipeline] { (Build backend for DEV with docker-compose)
      [Pipeline] node
      Running on debian-test in /home/test/jenkins_slave/workspace/Modulo8_Devops
      [Pipeline] {
      [Pipeline] sh
      + docker-compose up -d
      Found orphan containers (modulo8_devops_dev_1, modulo8_devops_hero-webapp_1) for this project. If you removed or renamed this service in your compose file, you can run this command with the --remove-orphans flag to clean it up.
      modulo8_devops_hero-backend_1 is up-to-date
      [Pipeline] echo
      Build DEV backend
      [Pipeline] }
      [Pipeline] // node
      [Pipeline] }
      [Pipeline] // stage
      [Pipeline] stage
      [Pipeline] { (Clone Frontend Repository for DEV environment)
      [Pipeline] node
      Running on debian-test in /home/test/jenkins_slave/workspace/Modulo8_Devops
      [Pipeline] {
      [Pipeline] git
      The recommended git tool is: NONE
      No credentials specified
      Fetching changes from the remote Git repository
      Checking out Revision 65e0ea336595660e4c10a128fe90d1223d76662e (refs/remotes/origin/main)
      Commit message: "Finalizing docker-compse frontend"
      > git rev-parse --resolve-git-dir /home/test/jenkins_slave/workspace/Modulo8_Devops/.git # timeout=10
      > git config remote.origin.url https://github.com/edytarqui3/m8-frontend.git # timeout=10
      Fetching upstream changes from https://github.com/edytarqui3/m8-frontend.git
      > git --version # timeout=10
      > git --version # 'git version 2.30.2'
      > git fetch --tags --force --progress -- https://github.com/edytarqui3/m8-frontend.git +refs/heads/*:refs/remotes/origin/* # timeout=10
      > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
      > git config core.sparsecheckout # timeout=10
      > git checkout -f 65e0ea336595660e4c10a128fe90d1223d76662e # timeout=10
      > git branch -a -v --no-abbrev # timeout=10
      > git branch -D main # timeout=10
      > git checkout -b main 65e0ea336595660e4c10a128fe90d1223d76662e # timeout=10
      > git rev-list --no-walk 65e0ea336595660e4c10a128fe90d1223d76662e # timeout=10
      [Pipeline] echo
      Cloned Frontend Project
      [Pipeline] }
      [Pipeline] // node
      [Pipeline] }
      [Pipeline] // stage
      [Pipeline] stage
      [Pipeline] { (Build frontend for DEV with docker-compose)
      [Pipeline] node
      Running on debian-test in /home/test/jenkins_slave/workspace/Modulo8_Devops
      [Pipeline] {
      [Pipeline] sh
      + docker-compose up -d dev
      Found orphan containers (modulo8_devops_hero-backend_1) for this project. If you removed or renamed this service in your compose file, you can run this command with the --remove-orphans flag to clean it up.
      Starting modulo8_devops_dev_1 ... 
      Starting modulo8_devops_dev_1 ... done
      [Pipeline] echo
      Build DEV frontend
      [Pipeline] }
      [Pipeline] // node
      [Pipeline] }
      [Pipeline] // stage
      [Pipeline] stage
      [Pipeline] { (Clone Backend Repository for PROD environment)
      [Pipeline] node
      Running on debian_server in /home/debian/jenkins_slave/workspace/Modulo8_Devops
      [Pipeline] {
      [Pipeline] git
      The recommended git tool is: NONE
      No credentials specified
      Fetching changes from the remote Git repository
      Checking out Revision f470bb114549c9d172115f205c63a5761b19fc5c (refs/remotes/origin/main)
      Commit message: "Adding docker compose for backend"
      [Pipeline] echo
      Cloned Backend Project
      [Pipeline] }
      > git rev-parse --resolve-git-dir /home/debian/jenkins_slave/workspace/Modulo8_Devops/.git # timeout=10
      > git config remote.origin.url https://github.com/edytarqui3/m8-backend.git # timeout=10
      Fetching upstream changes from https://github.com/edytarqui3/m8-backend.git
      > git --version # timeout=10
      > git --version # 'git version 2.30.2'
      > git fetch --tags --force --progress -- https://github.com/edytarqui3/m8-backend.git +refs/heads/*:refs/remotes/origin/* # timeout=10
      > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
      > git config core.sparsecheckout # timeout=10
      > git checkout -f f470bb114549c9d172115f205c63a5761b19fc5c # timeout=10
      > git branch -a -v --no-abbrev # timeout=10
      > git branch -D main # timeout=10
      > git checkout -b main f470bb114549c9d172115f205c63a5761b19fc5c # timeout=10
      [Pipeline] // node
      [Pipeline] }
      [Pipeline] // stage
      [Pipeline] stage
      [Pipeline] { (Build backend for PROD with docker-compose)
      [Pipeline] node
      Running on debian_server in /home/debian/jenkins_slave/workspace/Modulo8_Devops
      [Pipeline] {
      [Pipeline] sh
      + docker-compose up -d
      Building hero-backend
      Sending build context to Docker daemon  95.23kB

      Step 1/6 : FROM debian:10-slim
      ---> 6ed790cf98af
      Step 2/6 : WORKDIR /app
      ---> Running in dba4e584e546
      Removing intermediate container dba4e584e546
      ---> 7cee4313f06d
      Step 3/6 : RUN apt-get update   && apt-get install -y curl   && curl -sL https://deb.nodesource.com/setup_12.x | bash -   && apt-get install -y nodejs
      ---> Running in 4e2bd680c369
      Get:1 http://deb.debian.org/debian buster InRelease [122 kB]
      Get:2 http://deb.debian.org/debian-security buster/updates InRelease [34.8 kB]
      Get:3 http://deb.debian.org/debian buster-updates InRelease [56.6 kB]
      Get:4 http://deb.debian.org/debian buster/main arm64 Packages [7737 kB]
      Get:5 http://deb.debian.org/debian-security buster/updates/main arm64 Packages [396 kB]
      Get:6 http://deb.debian.org/debian buster-updates/main arm64 Packages [8780 B]
      Fetched 8355 kB in 4s (2261 kB/s)
      Reading package lists...
      Reading package lists...
      Building dependency tree...
      Reading state information...
      The following additional packages will be installed:
        ca-certificates krb5-locales libcurl4 libgssapi-krb5-2 libk5crypto3
        libkeyutils1 libkrb5-3 libkrb5support0 libldap-2.4-2 libldap-common
        libnghttp2-14 libpsl5 librtmp1 libsasl2-2 libsasl2-modules
        libsasl2-modules-db libssh2-1 libssl1.1 openssl publicsuffix
      Suggested packages:
        krb5-doc krb5-user libsasl2-modules-gssapi-mit
        | libsasl2-modules-gssapi-heimdal libsasl2-modules-ldap libsasl2-modules-otp
        libsasl2-modules-sql
      The following NEW packages will be installed:
        ca-certificates curl krb5-locales libcurl4 libgssapi-krb5-2 libk5crypto3
        libkeyutils1 libkrb5-3 libkrb5support0 libldap-2.4-2 libldap-common
        libnghttp2-14 libpsl5 librtmp1 libsasl2-2 libsasl2-modules
        libsasl2-modules-db libssh2-1 libssl1.1 openssl publicsuffix
      0 upgraded, 21 newly installed, 0 to remove and 0 not upgraded.
      Need to get 4800 kB of archives.
      After this operation, 11.4 MB of additional disk space will be used.
      Get:1 http://deb.debian.org/debian-security buster/updates/main arm64 krb5-locales all 1.17-3+deb10u5 [95.7 kB]
      Get:2 http://deb.debian.org/debian buster/main arm64 libkeyutils1 arm64 1.6-6 [14.9 kB]
      Get:3 http://deb.debian.org/debian-security buster/updates/main arm64 libkrb5support0 arm64 1.17-3+deb10u5 [65.2 kB]
      Get:4 http://deb.debian.org/debian-security buster/updates/main arm64 libk5crypto3 arm64 1.17-3+deb10u5 [123 kB]
      Get:5 http://deb.debian.org/debian buster/main arm64 libssl1.1 arm64 1.1.1n-0+deb10u3 [1392 kB]
      Get:6 http://deb.debian.org/debian-security buster/updates/main arm64 libkrb5-3 arm64 1.17-3+deb10u5 [351 kB]
      Get:7 http://deb.debian.org/debian-security buster/updates/main arm64 libgssapi-krb5-2 arm64 1.17-3+deb10u5 [150 kB]
      Get:8 http://deb.debian.org/debian buster/main arm64 openssl arm64 1.1.1n-0+deb10u3 [834 kB]
      Get:9 http://deb.debian.org/debian buster/main arm64 ca-certificates all 20200601~deb10u2 [166 kB]
      Get:10 http://deb.debian.org/debian buster/main arm64 libsasl2-modules-db arm64 2.1.27+dfsg-1+deb10u2 [69.4 kB]
      Get:11 http://deb.debian.org/debian buster/main arm64 libsasl2-2 arm64 2.1.27+dfsg-1+deb10u2 [105 kB]
      Get:12 http://deb.debian.org/debian buster/main arm64 libldap-common all 2.4.47+dfsg-3+deb10u7 [90.1 kB]
      Get:13 http://deb.debian.org/debian buster/main arm64 libldap-2.4-2 arm64 2.4.47+dfsg-3+deb10u7 [216 kB]
      Get:14 http://deb.debian.org/debian buster/main arm64 libnghttp2-14 arm64 1.36.0-2+deb10u1 [81.9 kB]
      Get:15 http://deb.debian.org/debian buster/main arm64 libpsl5 arm64 0.20.2-2 [53.6 kB]
      Get:16 http://deb.debian.org/debian buster/main arm64 librtmp1 arm64 2.4+20151223.gitfa8646d.1-2 [55.7 kB]
      Get:17 http://deb.debian.org/debian buster/main arm64 libssh2-1 arm64 1.8.0-2.1 [135 kB]
      Get:18 http://deb.debian.org/debian-security buster/updates/main arm64 libcurl4 arm64 7.64.0-4+deb10u3 [312 kB]
      Get:19 http://deb.debian.org/debian-security buster/updates/main arm64 curl arm64 7.64.0-4+deb10u3 [260 kB]
      Get:20 http://deb.debian.org/debian buster/main arm64 libsasl2-modules arm64 2.1.27+dfsg-1+deb10u2 [102 kB]
      Get:21 http://deb.debian.org/debian buster/main arm64 publicsuffix all 20220811.1734-0+deb10u1 [127 kB]
      [91mdebconf: delaying package configuration, since apt-utils is not installed
      [0mFetched 4800 kB in 1s (4675 kB/s)
      Selecting previously unselected package krb5-locales.
      (Reading database ... 
      (Reading database ... 5%
      (Reading database ... 10%
      (Reading database ... 15%
      (Reading database ... 20%
      (Reading database ... 25%
      (Reading database ... 30%
      (Reading database ... 35%
      (Reading database ... 40%
      (Reading database ... 45%
      (Reading database ... 50%
      (Reading database ... 55%
      (Reading database ... 60%
      (Reading database ... 65%
      (Reading database ... 70%
      (Reading database ... 75%
      (Reading database ... 80%
      (Reading database ... 85%
      (Reading database ... 90%
      (Reading database ... 95%
      (Reading database ... 100%
      (Reading database ... 6453 files and directories currently installed.)
      Preparing to unpack .../00-krb5-locales_1.17-3+deb10u5_all.deb ...
      Unpacking krb5-locales (1.17-3+deb10u5) ...
      Selecting previously unselected package libkeyutils1:arm64.
      Preparing to unpack .../01-libkeyutils1_1.6-6_arm64.deb ...
      Unpacking libkeyutils1:arm64 (1.6-6) ...
      Selecting previously unselected package libkrb5support0:arm64.
      Preparing to unpack .../02-libkrb5support0_1.17-3+deb10u5_arm64.deb ...
      Unpacking libkrb5support0:arm64 (1.17-3+deb10u5) ...
      Selecting previously unselected package libk5crypto3:arm64.
      Preparing to unpack .../03-libk5crypto3_1.17-3+deb10u5_arm64.deb ...
      Unpacking libk5crypto3:arm64 (1.17-3+deb10u5) ...
      Selecting previously unselected package libssl1.1:arm64.
      Preparing to unpack .../04-libssl1.1_1.1.1n-0+deb10u3_arm64.deb ...
      Unpacking libssl1.1:arm64 (1.1.1n-0+deb10u3) ...
      Selecting previously unselected package libkrb5-3:arm64.
      Preparing to unpack .../05-libkrb5-3_1.17-3+deb10u5_arm64.deb ...
      Unpacking libkrb5-3:arm64 (1.17-3+deb10u5) ...
      Selecting previously unselected package libgssapi-krb5-2:arm64.
      Preparing to unpack .../06-libgssapi-krb5-2_1.17-3+deb10u5_arm64.deb ...
      Unpacking libgssapi-krb5-2:arm64 (1.17-3+deb10u5) ...
      Selecting previously unselected package openssl.
      Preparing to unpack .../07-openssl_1.1.1n-0+deb10u3_arm64.deb ...
      Unpacking openssl (1.1.1n-0+deb10u3) ...
      Selecting previously unselected package ca-certificates.
      Preparing to unpack .../08-ca-certificates_20200601~deb10u2_all.deb ...
      Unpacking ca-certificates (20200601~deb10u2) ...
      Selecting previously unselected package libsasl2-modules-db:arm64.
      Preparing to unpack .../09-libsasl2-modules-db_2.1.27+dfsg-1+deb10u2_arm64.deb ...
      Unpacking libsasl2-modules-db:arm64 (2.1.27+dfsg-1+deb10u2) ...
      Selecting previously unselected package libsasl2-2:arm64.
      Preparing to unpack .../10-libsasl2-2_2.1.27+dfsg-1+deb10u2_arm64.deb ...
      Unpacking libsasl2-2:arm64 (2.1.27+dfsg-1+deb10u2) ...
      Selecting previously unselected package libldap-common.
      Preparing to unpack .../11-libldap-common_2.4.47+dfsg-3+deb10u7_all.deb ...
      Unpacking libldap-common (2.4.47+dfsg-3+deb10u7) ...
      Selecting previously unselected package libldap-2.4-2:arm64.
      Preparing to unpack .../12-libldap-2.4-2_2.4.47+dfsg-3+deb10u7_arm64.deb ...
      Unpacking libldap-2.4-2:arm64 (2.4.47+dfsg-3+deb10u7) ...
      Selecting previously unselected package libnghttp2-14:arm64.
      Preparing to unpack .../13-libnghttp2-14_1.36.0-2+deb10u1_arm64.deb ...
      Unpacking libnghttp2-14:arm64 (1.36.0-2+deb10u1) ...
      Selecting previously unselected package libpsl5:arm64.
      Preparing to unpack .../14-libpsl5_0.20.2-2_arm64.deb ...
      Unpacking libpsl5:arm64 (0.20.2-2) ...
      Selecting previously unselected package librtmp1:arm64.
      Preparing to unpack .../15-librtmp1_2.4+20151223.gitfa8646d.1-2_arm64.deb ...
      Unpacking librtmp1:arm64 (2.4+20151223.gitfa8646d.1-2) ...
      Selecting previously unselected package libssh2-1:arm64.
      Preparing to unpack .../16-libssh2-1_1.8.0-2.1_arm64.deb ...
      Unpacking libssh2-1:arm64 (1.8.0-2.1) ...
      Selecting previously unselected package libcurl4:arm64.
      Preparing to unpack .../17-libcurl4_7.64.0-4+deb10u3_arm64.deb ...
      Unpacking libcurl4:arm64 (7.64.0-4+deb10u3) ...
      Selecting previously unselected package curl.
      Preparing to unpack .../18-curl_7.64.0-4+deb10u3_arm64.deb ...
      Unpacking curl (7.64.0-4+deb10u3) ...
      Selecting previously unselected package libsasl2-modules:arm64.
      Preparing to unpack .../19-libsasl2-modules_2.1.27+dfsg-1+deb10u2_arm64.deb ...
      Unpacking libsasl2-modules:arm64 (2.1.27+dfsg-1+deb10u2) ...
      Selecting previously unselected package publicsuffix.
      Preparing to unpack .../20-publicsuffix_20220811.1734-0+deb10u1_all.deb ...
      Unpacking publicsuffix (20220811.1734-0+deb10u1) ...
      Setting up libkeyutils1:arm64 (1.6-6) ...
      Setting up libpsl5:arm64 (0.20.2-2) ...
      Setting up libssl1.1:arm64 (1.1.1n-0+deb10u3) ...
      debconf: unable to initialize frontend: Dialog
      debconf: (TERM is not set, so the dialog frontend is not usable.)
      debconf: falling back to frontend: Readline
      debconf: unable to initialize frontend: Readline
      debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/aarch64-linux-gnu/perl/5.28.1 /usr/local/share/perl/5.28.1 /usr/lib/aarch64-linux-gnu/perl5/5.28 /usr/share/perl5 /usr/lib/aarch64-linux-gnu/perl/5.28 /usr/share/perl/5.28 /usr/local/lib/site_perl /usr/lib/aarch64-linux-gnu/perl-base) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
      debconf: falling back to frontend: Teletype
      Setting up libsasl2-modules:arm64 (2.1.27+dfsg-1+deb10u2) ...
      Setting up libnghttp2-14:arm64 (1.36.0-2+deb10u1) ...
      Setting up krb5-locales (1.17-3+deb10u5) ...
      Setting up libldap-common (2.4.47+dfsg-3+deb10u7) ...
      Setting up libkrb5support0:arm64 (1.17-3+deb10u5) ...
      Setting up libsasl2-modules-db:arm64 (2.1.27+dfsg-1+deb10u2) ...
      Setting up librtmp1:arm64 (2.4+20151223.gitfa8646d.1-2) ...
      Setting up libk5crypto3:arm64 (1.17-3+deb10u5) ...
      Setting up libsasl2-2:arm64 (2.1.27+dfsg-1+deb10u2) ...
      Setting up libssh2-1:arm64 (1.8.0-2.1) ...
      Setting up libkrb5-3:arm64 (1.17-3+deb10u5) ...
      Setting up openssl (1.1.1n-0+deb10u3) ...
      Setting up publicsuffix (20220811.1734-0+deb10u1) ...
      Setting up libldap-2.4-2:arm64 (2.4.47+dfsg-3+deb10u7) ...
      Setting up ca-certificates (20200601~deb10u2) ...
      debconf: unable to initialize frontend: Dialog
      debconf: (TERM is not set, so the dialog frontend is not usable.)
      debconf: falling back to frontend: Readline
      debconf: unable to initialize frontend: Readline
      debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/aarch64-linux-gnu/perl/5.28.1 /usr/local/share/perl/5.28.1 /usr/lib/aarch64-linux-gnu/perl5/5.28 /usr/share/perl5 /usr/lib/aarch64-linux-gnu/perl/5.28 /usr/share/perl/5.28 /usr/local/lib/site_perl /usr/lib/aarch64-linux-gnu/perl-base) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
      debconf: falling back to frontend: Teletype
      Updating certificates in /etc/ssl/certs...
      137 added, 0 removed; done.
      Setting up libgssapi-krb5-2:arm64 (1.17-3+deb10u5) ...
      Setting up libcurl4:arm64 (7.64.0-4+deb10u3) ...
      Setting up curl (7.64.0-4+deb10u3) ...
      Processing triggers for libc-bin (2.28-10+deb10u2) ...
      Processing triggers for ca-certificates (20200601~deb10u2) ...
      Updating certificates in /etc/ssl/certs...
      0 added, 0 removed; done.
      Running hooks in /etc/ca-certificates/update.d...
      done.

      ================================================================================
      ================================================================================

                                    DEPRECATION WARNING                            

        Node.js 12.x is no longer actively supported!

        You will not receive security or critical stability updates for this version.

        You should migrate to a supported version of Node.js as soon as possible.
        Use the installation script that corresponds to the version of Node.js you
        wish to install. e.g.

        * https://deb.nodesource.com/setup_14.x — Node.js 14 LTS "Fermium" (recommended)
        * https://deb.nodesource.com/setup_16.x — Node.js 16 "Gallium"
        * https://deb.nodesource.com/setup_18.x — Node.js 18 "Eighteen" (current)

        Please see https://github.com/nodejs/Release for details about which
        version may be appropriate for you.

        The NodeSource Node.js distributions repository contains
        information both about supported versions of Node.js and supported Linux
        distributions. To learn more about usage, see the repository:
          https://github.com/nodesource/distributions

      ================================================================================
      ================================================================================

      Continuing in 20 seconds ...


      ## Installing the NodeSource Node.js 12.x repo...


      ## Populating apt-get cache...

      + apt-get update
      Hit:1 http://deb.debian.org/debian buster InRelease
      Hit:2 http://deb.debian.org/debian-security buster/updates InRelease
      Hit:3 http://deb.debian.org/debian buster-updates InRelease
      Reading package lists...

      ## Installing packages required for setup: lsb-release gnupg...

      + apt-get install -y lsb-release gnupg > /dev/null 2>&1

      ## Confirming "buster" is supported...

      + curl -sLf -o /dev/null 'https://deb.nodesource.com/node_12.x/dists/buster/Release'

      ## Adding the NodeSource signing key to your keyring...

      + curl -s https://deb.nodesource.com/gpgkey/nodesource.gpg.key | gpg --dearmor | tee /usr/share/keyrings/nodesource.gpg >/dev/null

      ## Creating apt sources list file for the NodeSource Node.js 12.x repo...

      + echo 'deb [signed-by=/usr/share/keyrings/nodesource.gpg] https://deb.nodesource.com/node_12.x buster main' > /etc/apt/sources.list.d/nodesource.list
      + echo 'deb-src [signed-by=/usr/share/keyrings/nodesource.gpg] https://deb.nodesource.com/node_12.x buster main' >> /etc/apt/sources.list.d/nodesource.list

      ## Running `apt-get update` for you...

      + apt-get update
      Hit:1 http://deb.debian.org/debian buster InRelease
      Hit:2 http://deb.debian.org/debian-security buster/updates InRelease
      Hit:3 http://deb.debian.org/debian buster-updates InRelease
      Get:4 https://deb.nodesource.com/node_12.x buster InRelease [4584 B]
      Get:5 https://deb.nodesource.com/node_12.x buster/main arm64 Packages [774 B]
      Fetched 5358 B in 2s (2797 B/s)
      Reading package lists...

      ## Run `sudo apt-get install -y nodejs` to install Node.js 12.x and npm
      ## You may also need development tools to build native addons:
          sudo apt-get install gcc g++ make
      ## To install the Yarn package manager, run:
          curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | gpg --dearmor | sudo tee /usr/share/keyrings/yarnkey.gpg >/dev/null
          echo "deb [signed-by=/usr/share/keyrings/yarnkey.gpg] https://dl.yarnpkg.com/debian stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
          sudo apt-get update && sudo apt-get install yarn


      Reading package lists...
      Building dependency tree...
      Reading state information...
      The following NEW packages will be installed:
        nodejs
      0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
      Need to get 17.2 MB of archives.
      After this operation, 92.4 MB of additional disk space will be used.
      Get:1 https://deb.nodesource.com/node_12.x buster/main arm64 nodejs arm64 12.22.12-deb-1nodesource1 [17.2 MB]
      [91mdebconf: delaying package configuration, since apt-utils is not installed
      [0mFetched 17.2 MB in 6s (3079 kB/s)
      Selecting previously unselected package nodejs.
      (Reading database ... 
      (Reading database ... 5%
      (Reading database ... 10%
      (Reading database ... 15%
      (Reading database ... 20%
      (Reading database ... 25%
      (Reading database ... 30%
      (Reading database ... 35%
      (Reading database ... 40%
      (Reading database ... 45%
      (Reading database ... 50%
      (Reading database ... 55%
      (Reading database ... 60%
      (Reading database ... 65%
      (Reading database ... 70%
      (Reading database ... 75%
      (Reading database ... 80%
      (Reading database ... 85%
      (Reading database ... 90%
      (Reading database ... 95%
      (Reading database ... 100%
      (Reading database ... 8073 files and directories currently installed.)
      Preparing to unpack .../nodejs_12.22.12-deb-1nodesource1_arm64.deb ...
      Unpacking nodejs (12.22.12-deb-1nodesource1) ...
      Setting up nodejs (12.22.12-deb-1nodesource1) ...
      Removing intermediate container 4e2bd680c369
      ---> 58043029eed9
      Step 4/6 : RUN npm install -g json-server
      ---> Running in c67c011240ac
      /usr/bin/json-server -> /usr/lib/node_modules/json-server/lib/cli/bin.js
      + json-server@0.17.1
      added 109 packages from 62 contributors in 12.296s
      Removing intermediate container c67c011240ac
      ---> be109b4d5cf9
      Step 5/6 : COPY . .
      ---> 75179aedc1ba
      Step 6/6 : ENTRYPOINT ["json-server", "db.json", "--port", "3333", "--host", "0.0.0.0"]
      ---> Running in ae62827da201
      Removing intermediate container ae62827da201
      ---> 7bf5e462cba4
      Successfully built 7bf5e462cba4
      Successfully tagged modulo8_devops_hero-backend:latest
      Image for service hero-backend was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
      Creating modulo8_devops_hero-backend_1 ... 
      Creating modulo8_devops_hero-backend_1 ... done
      [Pipeline] echo
      Build PROD backend
      [Pipeline] }
      [Pipeline] // node
      [Pipeline] }
      [Pipeline] // stage
      [Pipeline] stage
      [Pipeline] { (Clone Frontend Repository for PROD environment)
      [Pipeline] node
      Running on debian_server in /home/debian/jenkins_slave/workspace/Modulo8_Devops
      [Pipeline] {
      [Pipeline] git
      The recommended git tool is: NONE
      No credentials specified
      Fetching changes from the remote Git repository
      > git rev-parse --resolve-git-dir /home/debian/jenkins_slave/workspace/Modulo8_Devops/.git # timeout=10
      > git config remote.origin.url https://github.com/edytarqui3/m8-frontend.git # timeout=10
      Fetching upstream changes from https://github.com/edytarqui3/m8-frontend.git
      > git --version # timeout=10
      > git --version # 'git version 2.30.2'
      > git fetch --tags --force --progress -- https://github.com/edytarqui3/m8-frontend.git +refs/heads/*:refs/remotes/origin/* # timeout=10
      Checking out Revision 65e0ea336595660e4c10a128fe90d1223d76662e (refs/remotes/origin/main)
      Commit message: "Finalizing docker-compse frontend"
      [Pipeline] echo
      Cloned Frontend Project
      [Pipeline] }
      > git rev-parse refs/remotes/origin/main^{commit} # timeout=10
      > git config core.sparsecheckout # timeout=10
      > git checkout -f 65e0ea336595660e4c10a128fe90d1223d76662e # timeout=10
      > git branch -a -v --no-abbrev # timeout=10
      > git branch -D main # timeout=10
      > git checkout -b main 65e0ea336595660e4c10a128fe90d1223d76662e # timeout=10
      [Pipeline] // node
      [Pipeline] }
      [Pipeline] // stage
      [Pipeline] stage
      [Pipeline] { (Build frontend for PROD with docker-compose)
      [Pipeline] node
      Running on debian_server in /home/debian/jenkins_slave/workspace/Modulo8_Devops
      [Pipeline] {
      [Pipeline] sh
      + docker-compose up -d hero-webapp
      Found orphan containers (modulo8_devops_hero-backend_1) for this project. If you removed or renamed this service in your compose file, you can run this command with the --remove-orphans flag to clean it up.
      Building hero-webapp
      Sending build context to Docker daemon  8.968MB

      Step 1/10 : FROM node:16.18-alpine3.15 as build-stage
      ---> fb1708dc1692
      Step 2/10 : WORKDIR /app
      ---> Running in 3bbdd56aa502
      Removing intermediate container 3bbdd56aa502
      ---> db1643754532
      Step 3/10 : COPY package*.json ./
      ---> 871820cd5665
      Step 4/10 : RUN npm install
      ---> Running in 25a805309403
      [91mnpm WARN deprecated w3c-hr-time@1.0.2: Use your platform's native performance.now() and performance.timeOrigin.
      [0m[91mnpm WARN deprecated stable@0.1.8: Modern JS already guarantees Array#sort() is a stable sort, so this library is deprecated. See the compatibility table on MDN: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort#browser_compatibility
      [0m
      added 1250 packages, and audited 1251 packages in 25s

      104 packages are looking for funding
        run `npm fund` for details

      2 vulnerabilities (1 low, 1 critical)

      To address all issues, run:
        npm audit fix

      Run `npm audit` for details.
      [91mnpm notice[0m[91m 
      npm notice New major version of npm available! 8.19.2 -> 9.1.2
      npm notice Changelog: <https://github.com/npm/cli/releases/tag/v9.1.2>
      npm notice Run `npm install -g npm@9.1.2` to update!
      npm notice[0m[91m 
      [0mRemoving intermediate container 25a805309403
      ---> f7734acabb03
      Step 5/10 : COPY . .
      ---> 4575d205cb0f
      Step 6/10 : RUN npm run build
      ---> Running in 2b5cd1ba540f

      > vue-final-project@0.1.0 build
      > vue-cli-service build

      All browser targets in the browserslist configuration have supported ES module.
      Therefore we don't build two separate bundles for differential loading.


      [91m-  Building for production...
      [0m WARNING  Compiled with 1 warning12:37:42 AM

      warning  

      entrypoint size limit: The following entrypoint(s) combined asset size exceeds the recommended limit (244 KiB). This can impact web performance.
      Entrypoints:
        app (257 KiB)
            css/chunk-vendors.6d5840fb.css
            js/chunk-vendors.1a444403.js
            css/app.29bfc8d3.css
            js/app.c2a2edf1.js


        File                                   Size              Gzipped

        dist/js/chunk-vendors.1a444403.js      156.47 KiB        54.06 KiB
        dist/js/about.fec491a2.js              25.24 KiB         3.88 KiB
        dist/js/app.c2a2edf1.js                10.35 KiB         3.80 KiB
        dist/css/chunk-vendors.6d5840fb.css    90.19 KiB         9.06 KiB
        dist/css/app.29bfc8d3.css              0.46 KiB          0.29 KiB

        Images and other types of assets omitted.
        Build at: 2022-11-30T00:37:42.640Z - Hash: 64b2fe2babc079c7 - Time: 5806ms

      DONE  Build complete. The dist directory is ready to be deployed.
      INFO  Check out deployment instructions at https://cli.vuejs.org/guide/deployment.html
            
      Removing intermediate container 2b5cd1ba540f
      ---> 5f4dc2cf130f
      Step 7/10 : FROM nginx:1.23.2-alpine as production-stage
      ---> d0ddde8e3f4f
      Step 8/10 : COPY --from=build-stage /app/dist /usr/share/nginx/html
      ---> 550c003bf112
      Step 9/10 : EXPOSE 80
      ---> Running in 9331b06dbeef
      Removing intermediate container 9331b06dbeef
      ---> eeb52c2d41ee
      Step 10/10 : CMD ["nginx", "-g", "daemon off;"]
      ---> Running in bd7910bbc7c9
      Removing intermediate container bd7910bbc7c9
      ---> 86aaa5abafe7
      Successfully built 86aaa5abafe7
      Successfully tagged modulo8_devops_hero-webapp:latest
      Image for service hero-webapp was built because it did not already exist. To rebuild this image you must use `docker-compose build` or `docker-compose up --build`.
      Creating modulo8_devops_hero-webapp_1 ... 
      Creating modulo8_devops_hero-webapp_1 ... done
      [Pipeline] echo
      Build PROD frontend
      [Pipeline] }
      [Pipeline] // node
      [Pipeline] }
      [Pipeline] // stage
      [Pipeline] End of Pipeline
      Finished: SUCCESS
    ```
