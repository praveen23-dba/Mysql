### mysql Installation
 * Check current versions if any installed
```
 [yesdb@sn2ylvx1a020 ~]$ mysql -V
```
 * create a directory for copying binaries
```
 [yesdb@sn2ylvx1a020 ~]$ mkdir mysql8032
```
 * check if any files in installation location
```
 [yesdb@sn2ylvx1a020 ~]$ cd /var/lib/mysql
 [yesdb@sn2ylvx1a020 mysql]$ ll
total 4
```
 * Goto newly created directory
```
 [yesdb@sn2ylvx1a020 ~]$ cd mysql8032/
```
 * then copy mysql binaries from source location to newly created directory
```
 [yesdb@sn2ylvx1a020 mysql8032]$ scp yesdb@10.26.96.54:/backup/mysql-8.0.32-1.el7.x86_64.rpm-bundle.tar /home/yesdb/mysql8032/
 yesdb@10.26.96.54's password:
```
```
 mysql-8.0.32-1.el7.x86_64.rpm-bundle.tar                                                      100%  969MB  46.4MB/s   00:20
``` 
 * unzip tar file
```
 [yesdb@sn2ylvx1a020 mysql8032]$ tar -xvf /home/yesdb/mysql8032/mysql-8.0.32-1.el7.x86_64.rpm-bundle.tar   
```
```
mysql-community-client-8.0.32-1.el7.x86_64.rpm
mysql-community-client-plugins-8.0.32-1.el7.x86_64.rpm
mysql-community-common-8.0.32-1.el7.x86_64.rpm
mysql-community-debuginfo-8.0.32-1.el7.x86_64.rpm
mysql-community-devel-8.0.32-1.el7.x86_64.rpm
mysql-community-embedded-compat-8.0.32-1.el7.x86_64.rpm
mysql-community-icu-data-files-8.0.32-1.el7.x86_64.rpm
mysql-community-libs-8.0.32-1.el7.x86_64.rpm
mysql-community-libs-compat-8.0.32-1.el7.x86_64.rpm
mysql-community-server-8.0.32-1.el7.x86_64.rpm
mysql-community-server-debug-8.0.32-1.el7.x86_64.rpm
mysql-community-test-8.0.32-1.el7.x86_64.rpm
```
 * remove unwanted rpm like below
```
 [yesdb@sn2ylvx1a020 mysql8032]$ rm /home/yesdb/mysql8032/*debug*-8.0.32-1.el7.x86_64.rpm
```
 * then use below command to install mysql
```
 [yesdb@sn2ylvx1a020 mysql8032]$ sudo yum localinstall -y *.rpm
```
Loaded plugins: product-id, search-disabled-repos, subscription-manager

This system is not registered with an entitlement server. You can use subscription-manager to register.

Examining mysql-community-client-8.0.32-1.el7.x86_64.rpm: mysql-community-client-8.0.32-1.el7.x86_64
Marking mysql-community-client-8.0.32-1.el7.x86_64.rpm to be installed
Examining mysql-community-client-plugins-8.0.32-1.el7.x86_64.rpm: mysql-community-client-plugins-8.0.32-1.el7.x86_64
Marking mysql-community-client-plugins-8.0.32-1.el7.x86_64.rpm to be installed
Examining mysql-community-common-8.0.32-1.el7.x86_64.rpm: mysql-community-common-8.0.32-1.el7.x86_64
Marking mysql-community-common-8.0.32-1.el7.x86_64.rpm to be installed
Examining mysql-community-devel-8.0.32-1.el7.x86_64.rpm: mysql-community-devel-8.0.32-1.el7.x86_64
Marking mysql-community-devel-8.0.32-1.el7.x86_64.rpm to be installed
Examining mysql-community-embedded-compat-8.0.32-1.el7.x86_64.rpm: mysql-community-embedded-compat-8.0.32-1.el7.x86_64
Marking mysql-community-embedded-compat-8.0.32-1.el7.x86_64.rpm to be installed
Examining mysql-community-icu-data-files-8.0.32-1.el7.x86_64.rpm: mysql-community-icu-data-files-8.0.32-1.el7.x86_64
Marking mysql-community-icu-data-files-8.0.32-1.el7.x86_64.rpm to be installed
Examining mysql-community-libs-8.0.32-1.el7.x86_64.rpm: mysql-community-libs-8.0.32-1.el7.x86_64
Marking mysql-community-libs-8.0.32-1.el7.x86_64.rpm to be installed
Examining mysql-community-libs-compat-8.0.32-1.el7.x86_64.rpm: mysql-community-libs-compat-8.0.32-1.el7.x86_64
Marking mysql-community-libs-compat-8.0.32-1.el7.x86_64.rpm to be installed
Examining mysql-community-server-8.0.32-1.el7.x86_64.rpm: mysql-community-server-8.0.32-1.el7.x86_64
Marking mysql-community-server-8.0.32-1.el7.x86_64.rpm to be installed
Examining mysql-community-test-8.0.32-1.el7.x86_64.rpm: mysql-community-test-8.0.32-1.el7.x86_64
Marking mysql-community-test-8.0.32-1.el7.x86_64.rpm to be installed
Resolving Dependencies
--> Running transaction check
---> Package mariadb-libs.x86_64 1:5.5.68-1.el7 will be obsoleted
---> Package mysql-community-client.x86_64 0:8.0.32-1.el7 will be installed
---> Package mysql-community-client-plugins.x86_64 0:8.0.32-1.el7 will be installed
---> Package mysql-community-common.x86_64 0:8.0.32-1.el7 will be installed
---> Package mysql-community-devel.x86_64 0:8.0.32-1.el7 will be installed
--> Processing Dependency: pkgconfig(openssl) for package: mysql-community-devel-8.0.32-1.el7.x86_64
ansible-repo                                                                                             | 2.9 kB  00:00:00
extras-repo                                                                                              | 2.9 kB  00:00:00
optional-repo                                                                                            | 2.9 kB  00:00:00
rh-common-repo                                                                                           | 2.9 kB  00:00:00
server-rhscl-repo                                                                                        | 2.9 kB  00:00:00
server-rpms-repo                                                                                         | 3.0 kB  00:00:00
supplementary-repo                                                                                       | 2.9 kB  00:00:00
---> Package mysql-community-embedded-compat.x86_64 0:8.0.32-1.el7 will be installed
---> Package mysql-community-icu-data-files.x86_64 0:8.0.32-1.el7 will be installed
---> Package mysql-community-libs.x86_64 0:8.0.32-1.el7 will be obsoleting
---> Package mysql-community-libs-compat.x86_64 0:8.0.32-1.el7 will be obsoleting
---> Package mysql-community-server.x86_64 0:8.0.32-1.el7 will be installed
--> Processing Dependency: /usr/bin/perl for package: mysql-community-server-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Getopt::Long) for package: mysql-community-server-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(strict) for package: mysql-community-server-8.0.32-1.el7.x86_64
---> Package mysql-community-test.x86_64 0:8.0.32-1.el7 will be installed
--> Processing Dependency: perl(Carp) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Carp) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Cwd) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Cwd) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Data::Dumper) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Data::Dumper) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Exporter) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Exporter) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(File::Path) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(File::Path) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(File::Spec) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(File::Spec) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(File::Spec::Functions) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(File::Spec::Functions) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(File::Temp) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(File::Temp) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(JSON) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(JSON) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Test::More) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Time::HiRes) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(Time::HiRes) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(constant) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(threads) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Processing Dependency: perl(threads::shared) for package: mysql-community-test-8.0.32-1.el7.x86_64
--> Running transaction check
---> Package openssl-devel.x86_64 1:1.0.2k-25.el7_9 will be installed
--> Processing Dependency: zlib-devel(x86-64) for package: 1:openssl-devel-1.0.2k-25.el7_9.x86_64
--> Processing Dependency: krb5-devel(x86-64) for package: 1:openssl-devel-1.0.2k-25.el7_9.x86_64
---> Package perl.x86_64 4:5.16.3-299.el7_9 will be installed
--> Processing Dependency: perl-libs = 4:5.16.3-299.el7_9 for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl(Socket) >= 1.3 for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl(Scalar::Util) >= 1.10 for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl-macros for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl-libs for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl(Time::Local) for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl(Storable) for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl(Socket) for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl(Scalar::Util) for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl(Pod::Simple::XHTML) for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl(Pod::Simple::Search) for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: perl(Filter::Util::Call) for package: 4:perl-5.16.3-299.el7_9.x86_64
--> Processing Dependency: libperl.so()(64bit) for package: 4:perl-5.16.3-299.el7_9.x86_64
---> Package perl-Carp.noarch 0:1.26-244.el7 will be installed
---> Package perl-Data-Dumper.x86_64 0:2.145-3.el7 will be installed
---> Package perl-Exporter.noarch 0:5.68-3.el7 will be installed
---> Package perl-File-Path.noarch 0:2.09-2.el7 will be installed
---> Package perl-File-Temp.noarch 0:0.23.01-3.el7 will be installed
---> Package perl-Getopt-Long.noarch 0:2.40-3.el7 will be installed
--> Processing Dependency: perl(Pod::Usage) >= 1.14 for package: perl-Getopt-Long-2.40-3.el7.noarch
--> Processing Dependency: perl(Text::ParseWords) for package: perl-Getopt-Long-2.40-3.el7.noarch
---> Package perl-JSON.noarch 0:2.59-2.el7 will be installed
---> Package perl-PathTools.x86_64 0:3.40-5.el7 will be installed
---> Package perl-Test-Simple.noarch 0:0.98-243.el7 will be installed
--> Processing Dependency: perl(Test::Harness) >= 2.03 for package: perl-Test-Simple-0.98-243.el7.noarch
---> Package perl-Time-HiRes.x86_64 4:1.9725-3.el7 will be installed
---> Package perl-constant.noarch 0:1.27-2.el7 will be installed
---> Package perl-threads.x86_64 0:1.87-4.el7 will be installed
---> Package perl-threads-shared.x86_64 0:1.43-6.el7 will be installed
--> Running transaction check
---> Package krb5-devel.x86_64 0:1.15.1-51.el7_9 will be installed
--> Processing Dependency: libverto-devel for package: krb5-devel-1.15.1-51.el7_9.x86_64
--> Processing Dependency: libselinux-devel for package: krb5-devel-1.15.1-51.el7_9.x86_64
--> Processing Dependency: libcom_err-devel for package: krb5-devel-1.15.1-51.el7_9.x86_64
--> Processing Dependency: keyutils-libs-devel for package: krb5-devel-1.15.1-51.el7_9.x86_64
---> Package perl-Filter.x86_64 0:1.49-3.el7 will be installed
---> Package perl-Pod-Simple.noarch 1:3.28-4.el7 will be installed
--> Processing Dependency: perl(Pod::Escapes) >= 1.04 for package: 1:perl-Pod-Simple-3.28-4.el7.noarch
--> Processing Dependency: perl(Encode) for package: 1:perl-Pod-Simple-3.28-4.el7.noarch
---> Package perl-Pod-Usage.noarch 0:1.63-3.el7 will be installed
--> Processing Dependency: perl(Pod::Text) >= 3.15 for package: perl-Pod-Usage-1.63-3.el7.noarch
--> Processing Dependency: perl-Pod-Perldoc for package: perl-Pod-Usage-1.63-3.el7.noarch
---> Package perl-Scalar-List-Utils.x86_64 0:1.27-248.el7 will be installed
---> Package perl-Socket.x86_64 0:2.010-5.el7 will be installed
---> Package perl-Storable.x86_64 0:2.45-3.el7 will be installed
---> Package perl-Test-Harness.noarch 0:3.28-3.el7 will be installed
---> Package perl-Text-ParseWords.noarch 0:3.29-4.el7 will be installed
---> Package perl-Time-Local.noarch 0:1.2300-2.el7 will be installed
---> Package perl-libs.x86_64 4:5.16.3-299.el7_9 will be installed
---> Package perl-macros.x86_64 4:5.16.3-299.el7_9 will be installed
---> Package zlib-devel.x86_64 0:1.2.7-19.el7_9 will be installed
--> Running transaction check
---> Package keyutils-libs-devel.x86_64 0:1.5.8-3.el7 will be installed
---> Package libcom_err-devel.x86_64 0:1.42.9-19.el7 will be installed
---> Package libselinux-devel.x86_64 0:2.5-15.el7 will be installed
--> Processing Dependency: libsepol-devel(x86-64) >= 2.5-10 for package: libselinux-devel-2.5-15.el7.x86_64
--> Processing Dependency: pkgconfig(libsepol) for package: libselinux-devel-2.5-15.el7.x86_64
--> Processing Dependency: pkgconfig(libpcre) for package: libselinux-devel-2.5-15.el7.x86_64
---> Package libverto-devel.x86_64 0:0.2.5-4.el7 will be installed
---> Package perl-Encode.x86_64 0:2.51-7.el7 will be installed
---> Package perl-Pod-Escapes.noarch 1:1.04-299.el7_9 will be installed
---> Package perl-Pod-Perldoc.noarch 0:3.20-4.el7 will be installed
--> Processing Dependency: perl(parent) for package: perl-Pod-Perldoc-3.20-4.el7.noarch
--> Processing Dependency: perl(HTTP::Tiny) for package: perl-Pod-Perldoc-3.20-4.el7.noarch
---> Package perl-podlators.noarch 0:2.5.1-3.el7 will be installed
--> Running transaction check
---> Package libsepol-devel.x86_64 0:2.5-10.el7 will be installed
---> Package pcre-devel.x86_64 0:8.32-17.el7 will be installed
---> Package perl-HTTP-Tiny.noarch 0:0.033-3.el7 will be installed
---> Package perl-parent.noarch 1:0.225-244.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================================================================
 Package                           Arch     Version                Repository                                              Size
================================================================================================================================
Installing:
 mysql-community-client            x86_64   8.0.32-1.el7           /mysql-community-client-8.0.32-1.el7.x86_64             80 M
 mysql-community-client-plugins    x86_64   8.0.32-1.el7           /mysql-community-client-plugins-8.0.32-1.el7.x86_64     14 M
 mysql-community-common            x86_64   8.0.32-1.el7           /mysql-community-common-8.0.32-1.el7.x86_64             10 M
 mysql-community-devel             x86_64   8.0.32-1.el7           /mysql-community-devel-8.0.32-1.el7.x86_64              10 M
 mysql-community-embedded-compat   x86_64   8.0.32-1.el7           /mysql-community-embedded-compat-8.0.32-1.el7.x86_64    17 M
 mysql-community-icu-data-files    x86_64   8.0.32-1.el7           /mysql-community-icu-data-files-8.0.32-1.el7.x86_64    3.5 M
 mysql-community-libs              x86_64   8.0.32-1.el7           /mysql-community-libs-8.0.32-1.el7.x86_64              7.6 M
     replacing  mariadb-libs.x86_64 1:5.5.68-1.el7
 mysql-community-libs-compat       x86_64   8.0.32-1.el7           /mysql-community-libs-compat-8.0.32-1.el7.x86_64       3.7 M
     replacing  mariadb-libs.x86_64 1:5.5.68-1.el7
 mysql-community-server            x86_64   8.0.32-1.el7           /mysql-community-server-8.0.32-1.el7.x86_64            295 M
 mysql-community-test              x86_64   8.0.32-1.el7           /mysql-community-test-8.0.32-1.el7.x86_64              746 M
Installing for dependencies:
 keyutils-libs-devel               x86_64   1.5.8-3.el7            server-rpms-repo                                        37 k
 krb5-devel                        x86_64   1.15.1-51.el7_9        server-rpms-repo                                       273 k
 libcom_err-devel                  x86_64   1.42.9-19.el7          server-rpms-repo                                        32 k
 libselinux-devel                  x86_64   2.5-15.el7             server-rpms-repo                                       187 k
 libsepol-devel                    x86_64   2.5-10.el7             server-rpms-repo                                        77 k
 libverto-devel                    x86_64   0.2.5-4.el7            server-rpms-repo                                        12 k
 openssl-devel                     x86_64   1:1.0.2k-25.el7_9      server-rpms-repo                                       1.5 M
 pcre-devel                        x86_64   8.32-17.el7            server-rpms-repo                                       480 k
 perl                              x86_64   4:5.16.3-299.el7_9     server-rpms-repo                                       8.0 M
 perl-Carp                         noarch   1.26-244.el7           server-rpms-repo                                        19 k
 perl-Data-Dumper                  x86_64   2.145-3.el7            server-rpms-repo                                        47 k
 perl-Encode                       x86_64   2.51-7.el7             server-rpms-repo                                       1.5 M
 perl-Exporter                     noarch   5.68-3.el7             server-rpms-repo                                        28 k
 perl-File-Path                    noarch   2.09-2.el7             server-rpms-repo                                        27 k
 perl-File-Temp                    noarch   0.23.01-3.el7          server-rpms-repo                                        56 k
 perl-Filter                       x86_64   1.49-3.el7             server-rpms-repo                                        76 k
 perl-Getopt-Long                  noarch   2.40-3.el7             server-rpms-repo                                        56 k
 perl-HTTP-Tiny                    noarch   0.033-3.el7            server-rpms-repo                                        38 k
 perl-JSON                         noarch   2.59-2.el7             server-rpms-repo                                        96 k
 perl-PathTools                    x86_64   3.40-5.el7             server-rpms-repo                                        83 k
 perl-Pod-Escapes                  noarch   1:1.04-299.el7_9       server-rpms-repo                                        52 k
 perl-Pod-Perldoc                  noarch   3.20-4.el7             server-rpms-repo                                        87 k
 perl-Pod-Simple                   noarch   1:3.28-4.el7           server-rpms-repo                                       216 k
 perl-Pod-Usage                    noarch   1.63-3.el7             server-rpms-repo                                        27 k
 perl-Scalar-List-Utils            x86_64   1.27-248.el7           server-rpms-repo                                        36 k
 perl-Socket                       x86_64   2.010-5.el7            server-rpms-repo                                        49 k
 perl-Storable                     x86_64   2.45-3.el7             server-rpms-repo                                        77 k
 perl-Test-Harness                 noarch   3.28-3.el7             server-rpms-repo                                       302 k
 perl-Test-Simple                  noarch   0.98-243.el7           server-rpms-repo                                       170 k
 perl-Text-ParseWords              noarch   3.29-4.el7             server-rpms-repo                                        14 k
 perl-Time-HiRes                   x86_64   4:1.9725-3.el7         server-rpms-repo                                        45 k
 perl-Time-Local                   noarch   1.2300-2.el7           server-rpms-repo                                        24 k
 perl-constant                     noarch   1.27-2.el7             server-rpms-repo                                        19 k
 perl-libs                         x86_64   4:5.16.3-299.el7_9     server-rpms-repo                                       690 k
 perl-macros                       x86_64   4:5.16.3-299.el7_9     server-rpms-repo                                        44 k
 perl-parent                       noarch   1:0.225-244.el7        server-rpms-repo                                        12 k
 perl-podlators                    noarch   2.5.1-3.el7            server-rpms-repo                                       112 k
 perl-threads                      x86_64   1.87-4.el7             server-rpms-repo                                        49 k
 perl-threads-shared               x86_64   1.43-6.el7             server-rpms-repo                                        39 k
 zlib-devel                        x86_64   1.2.7-19.el7_9         server-rpms-repo                                        50 k

Transaction Summary
================================================================================================================================
Install  10 Packages (+40 Dependent packages)

Total size: 1.2 G
Total download size: 15 M
Downloading packages:
(1/40): keyutils-libs-devel-1.5.8-3.el7.x86_64.rpm                                                       |  37 kB  00:00:00
(2/40): krb5-devel-1.15.1-51.el7_9.x86_64.rpm                                                            | 273 kB  00:00:00
(3/40): libcom_err-devel-1.42.9-19.el7.x86_64.rpm                                                        |  32 kB  00:00:00
(4/40): libselinux-devel-2.5-15.el7.x86_64.rpm                                                           | 187 kB  00:00:00
(5/40): libverto-devel-0.2.5-4.el7.x86_64.rpm                                                            |  12 kB  00:00:00
(6/40): libsepol-devel-2.5-10.el7.x86_64.rpm                                                             |  77 kB  00:00:00
(7/40): pcre-devel-8.32-17.el7.x86_64.rpm                                                                | 480 kB  00:00:00
(8/40): openssl-devel-1.0.2k-25.el7_9.x86_64.rpm                                                         | 1.5 MB  00:00:00
(9/40): perl-Carp-1.26-244.el7.noarch.rpm                                                                |  19 kB  00:00:00
(10/40): perl-Data-Dumper-2.145-3.el7.x86_64.rpm                                                         |  47 kB  00:00:00
(11/40): perl-5.16.3-299.el7_9.x86_64.rpm                                                                | 8.0 MB  00:00:00
(12/40): perl-Encode-2.51-7.el7.x86_64.rpm                                                               | 1.5 MB  00:00:00
(13/40): perl-Exporter-5.68-3.el7.noarch.rpm                                                             |  28 kB  00:00:00
(14/40): perl-File-Path-2.09-2.el7.noarch.rpm                                                            |  27 kB  00:00:00
(15/40): perl-File-Temp-0.23.01-3.el7.noarch.rpm                                                         |  56 kB  00:00:00
(16/40): perl-Filter-1.49-3.el7.x86_64.rpm                                                               |  76 kB  00:00:00
(17/40): perl-Getopt-Long-2.40-3.el7.noarch.rpm                                                          |  56 kB  00:00:00
(18/40): perl-HTTP-Tiny-0.033-3.el7.noarch.rpm                                                           |  38 kB  00:00:00
(19/40): perl-JSON-2.59-2.el7.noarch.rpm                                                                 |  96 kB  00:00:00
(20/40): perl-PathTools-3.40-5.el7.x86_64.rpm                                                            |  83 kB  00:00:00
(21/40): perl-Pod-Escapes-1.04-299.el7_9.noarch.rpm                                                      |  52 kB  00:00:00
(22/40): perl-Pod-Perldoc-3.20-4.el7.noarch.rpm                                                          |  87 kB  00:00:00
(23/40): perl-Pod-Simple-3.28-4.el7.noarch.rpm                                                           | 216 kB  00:00:00
(24/40): perl-Pod-Usage-1.63-3.el7.noarch.rpm                                                            |  27 kB  00:00:00
(25/40): perl-Scalar-List-Utils-1.27-248.el7.x86_64.rpm                                                  |  36 kB  00:00:00
(26/40): perl-Socket-2.010-5.el7.x86_64.rpm                                                              |  49 kB  00:00:00
(27/40): perl-Storable-2.45-3.el7.x86_64.rpm                                                             |  77 kB  00:00:00
(28/40): perl-Test-Simple-0.98-243.el7.noarch.rpm                                                        | 170 kB  00:00:00
(29/40): perl-Test-Harness-3.28-3.el7.noarch.rpm                                                         | 302 kB  00:00:00
(30/40): perl-Text-ParseWords-3.29-4.el7.noarch.rpm                                                      |  14 kB  00:00:00
(31/40): perl-Time-HiRes-1.9725-3.el7.x86_64.rpm                                                         |  45 kB  00:00:00
(32/40): perl-Time-Local-1.2300-2.el7.noarch.rpm                                                         |  24 kB  00:00:00
(33/40): perl-constant-1.27-2.el7.noarch.rpm                                                             |  19 kB  00:00:00
(34/40): perl-libs-5.16.3-299.el7_9.x86_64.rpm                                                           | 690 kB  00:00:00
(35/40): perl-macros-5.16.3-299.el7_9.x86_64.rpm                                                         |  44 kB  00:00:00
(36/40): perl-parent-0.225-244.el7.noarch.rpm                                                            |  12 kB  00:00:00
(37/40): perl-threads-1.87-4.el7.x86_64.rpm                                                              |  49 kB  00:00:00
(38/40): perl-podlators-2.5.1-3.el7.noarch.rpm                                                           | 112 kB  00:00:00
(39/40): perl-threads-shared-1.43-6.el7.x86_64.rpm                                                       |  39 kB  00:00:00
(40/40): zlib-devel-1.2.7-19.el7_9.x86_64.rpm                                                            |  50 kB  00:00:00
--------------------------------------------------------------------------------------------------------------------------------
Total                                                                                            16 MB/s |  15 MB  00:00:00
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : mysql-community-common-8.0.32-1.el7.x86_64                                                                  1/51
  Installing : mysql-community-client-plugins-8.0.32-1.el7.x86_64                                                          2/51
  Installing : mysql-community-libs-8.0.32-1.el7.x86_64                                                                    3/51
  Installing : mysql-community-client-8.0.32-1.el7.x86_64                                                                  4/51
  Installing : 1:perl-parent-0.225-244.el7.noarch                                                                          5/51
  Installing : perl-HTTP-Tiny-0.033-3.el7.noarch                                                                           6/51
  Installing : perl-podlators-2.5.1-3.el7.noarch                                                                           7/51
  Installing : perl-Pod-Perldoc-3.20-4.el7.noarch                                                                          8/51
  Installing : 1:perl-Pod-Escapes-1.04-299.el7_9.noarch                                                                    9/51
  Installing : perl-Encode-2.51-7.el7.x86_64                                                                              10/51
  Installing : perl-Text-ParseWords-3.29-4.el7.noarch                                                                     11/51
  Installing : perl-Pod-Usage-1.63-3.el7.noarch                                                                           12/51
  Installing : 4:perl-Time-HiRes-1.9725-3.el7.x86_64                                                                      13/51
  Installing : perl-Exporter-5.68-3.el7.noarch                                                                            14/51
  Installing : perl-constant-1.27-2.el7.noarch                                                                            15/51
  Installing : perl-Socket-2.010-5.el7.x86_64                                                                             16/51
  Installing : perl-Filter-1.49-3.el7.x86_64                                                                              17/51
  Installing : perl-Time-Local-1.2300-2.el7.noarch                                                                        18/51
  Installing : perl-Carp-1.26-244.el7.noarch                                                                              19/51
  Installing : 4:perl-macros-5.16.3-299.el7_9.x86_64                                                                      20/51
  Installing : perl-Storable-2.45-3.el7.x86_64                                                                            21/51
  Installing : perl-PathTools-3.40-5.el7.x86_64                                                                           22/51
  Installing : perl-Scalar-List-Utils-1.27-248.el7.x86_64                                                                 23/51
  Installing : 1:perl-Pod-Simple-3.28-4.el7.noarch                                                                        24/51
  Installing : perl-threads-shared-1.43-6.el7.x86_64                                                                      25/51
  Installing : perl-threads-1.87-4.el7.x86_64                                                                             26/51
  Installing : perl-File-Temp-0.23.01-3.el7.noarch                                                                        27/51
  Installing : perl-File-Path-2.09-2.el7.noarch                                                                           28/51
  Installing : 4:perl-libs-5.16.3-299.el7_9.x86_64                                                                        29/51
  Installing : perl-Getopt-Long-2.40-3.el7.noarch                                                                         30/51
  Installing : 4:perl-5.16.3-299.el7_9.x86_64                                                                             31/51
  Installing : perl-Data-Dumper-2.145-3.el7.x86_64                                                                        32/51
  Installing : perl-JSON-2.59-2.el7.noarch                                                                                33/51
  Installing : perl-Test-Harness-3.28-3.el7.noarch                                                                        34/51
  Installing : perl-Test-Simple-0.98-243.el7.noarch                                                                       35/51
  Installing : libcom_err-devel-1.42.9-19.el7.x86_64                                                                      36/51
  Installing : mysql-community-icu-data-files-8.0.32-1.el7.x86_64                                                         37/51
  Installing : mysql-community-server-8.0.32-1.el7.x86_64                                                                 38/51
  Installing : pcre-devel-8.32-17.el7.x86_64                                                                              39/51
  Installing : libsepol-devel-2.5-10.el7.x86_64                                                                           40/51
  Installing : libselinux-devel-2.5-15.el7.x86_64                                                                         41/51
  Installing : zlib-devel-1.2.7-19.el7_9.x86_64                                                                           42/51
  Installing : libverto-devel-0.2.5-4.el7.x86_64                                                                          43/51
  Installing : keyutils-libs-devel-1.5.8-3.el7.x86_64                                                                     44/51
  Installing : krb5-devel-1.15.1-51.el7_9.x86_64                                                                          45/51
  Installing : 1:openssl-devel-1.0.2k-25.el7_9.x86_64                                                                     46/51
  Installing : mysql-community-devel-8.0.32-1.el7.x86_64                                                                  47/51
  Installing : mysql-community-test-8.0.32-1.el7.x86_64                                                                   48/51
  Installing : mysql-community-libs-compat-8.0.32-1.el7.x86_64                                                            49/51
  Installing : mysql-community-embedded-compat-8.0.32-1.el7.x86_64                                                        50/51
  Erasing    : 1:mariadb-libs-5.5.68-1.el7.x86_64                                                                         51/51
  Verifying  : perl-HTTP-Tiny-0.033-3.el7.noarch                                                                           1/51
  Verifying  : libselinux-devel-2.5-15.el7.x86_64                                                                          2/51
  Verifying  : perl-JSON-2.59-2.el7.noarch                                                                                 3/51
  Verifying  : mysql-community-libs-compat-8.0.32-1.el7.x86_64                                                             4/51
  Verifying  : perl-threads-shared-1.43-6.el7.x86_64                                                                       5/51
  Verifying  : 4:perl-Time-HiRes-1.9725-3.el7.x86_64                                                                       6/51
  Verifying  : perl-Exporter-5.68-3.el7.noarch                                                                             7/51
  Verifying  : perl-constant-1.27-2.el7.noarch                                                                             8/51
  Verifying  : perl-PathTools-3.40-5.el7.x86_64                                                                            9/51
  Verifying  : perl-Socket-2.010-5.el7.x86_64                                                                             10/51
  Verifying  : mysql-community-server-8.0.32-1.el7.x86_64                                                                 11/51
  Verifying  : keyutils-libs-devel-1.5.8-3.el7.x86_64                                                                     12/51
  Verifying  : 1:perl-parent-0.225-244.el7.noarch                                                                         13/51
  Verifying  : perl-Test-Simple-0.98-243.el7.noarch                                                                       14/51
  Verifying  : libverto-devel-0.2.5-4.el7.x86_64                                                                          15/51
  Verifying  : perl-Test-Harness-3.28-3.el7.noarch                                                                        16/51
  Verifying  : mysql-community-test-8.0.32-1.el7.x86_64                                                                   17/51
  Verifying  : perl-Filter-1.49-3.el7.x86_64                                                                              18/51
  Verifying  : perl-File-Temp-0.23.01-3.el7.noarch                                                                        19/51
  Verifying  : krb5-devel-1.15.1-51.el7_9.x86_64                                                                          20/51
  Verifying  : 1:perl-Pod-Simple-3.28-4.el7.noarch                                                                        21/51
  Verifying  : perl-Time-Local-1.2300-2.el7.noarch                                                                        22/51
  Verifying  : 1:perl-Pod-Escapes-1.04-299.el7_9.noarch                                                                   23/51
  Verifying  : mysql-community-common-8.0.32-1.el7.x86_64                                                                 24/51
  Verifying  : perl-Carp-1.26-244.el7.noarch                                                                              25/51
  Verifying  : perl-Data-Dumper-2.145-3.el7.x86_64                                                                        26/51
  Verifying  : 4:perl-macros-5.16.3-299.el7_9.x86_64                                                                      27/51
  Verifying  : perl-Storable-2.45-3.el7.x86_64                                                                            28/51
  Verifying  : 1:openssl-devel-1.0.2k-25.el7_9.x86_64                                                                     29/51
  Verifying  : zlib-devel-1.2.7-19.el7_9.x86_64                                                                           30/51
  Verifying  : perl-Scalar-List-Utils-1.27-248.el7.x86_64                                                                 31/51
  Verifying  : mysql-community-embedded-compat-8.0.32-1.el7.x86_64                                                        32/51
  Verifying  : libsepol-devel-2.5-10.el7.x86_64                                                                           33/51
  Verifying  : perl-Pod-Usage-1.63-3.el7.noarch                                                                           34/51
  Verifying  : perl-Encode-2.51-7.el7.x86_64                                                                              35/51
  Verifying  : mysql-community-client-8.0.32-1.el7.x86_64                                                                 36/51
  Verifying  : mysql-community-libs-8.0.32-1.el7.x86_64                                                                   37/51
  Verifying  : perl-Pod-Perldoc-3.20-4.el7.noarch                                                                         38/51
  Verifying  : perl-podlators-2.5.1-3.el7.noarch                                                                          39/51
  Verifying  : pcre-devel-8.32-17.el7.x86_64                                                                              40/51
  Verifying  : 4:perl-5.16.3-299.el7_9.x86_64                                                                             41/51
  Verifying  : mysql-community-icu-data-files-8.0.32-1.el7.x86_64                                                         42/51
  Verifying  : perl-threads-1.87-4.el7.x86_64                                                                             43/51
  Verifying  : mysql-community-devel-8.0.32-1.el7.x86_64                                                                  44/51
  Verifying  : perl-Getopt-Long-2.40-3.el7.noarch                                                                         45/51
  Verifying  : perl-Text-ParseWords-3.29-4.el7.noarch                                                                     46/51
  Verifying  : libcom_err-devel-1.42.9-19.el7.x86_64                                                                      47/51
  Verifying  : perl-File-Path-2.09-2.el7.noarch                                                                           48/51
  Verifying  : 4:perl-libs-5.16.3-299.el7_9.x86_64                                                                        49/51
  Verifying  : mysql-community-client-plugins-8.0.32-1.el7.x86_64                                                         50/51
  Verifying  : 1:mariadb-libs-5.5.68-1.el7.x86_64                                                                         51/51

Installed:
  mysql-community-client.x86_64 0:8.0.32-1.el7                    mysql-community-client-plugins.x86_64 0:8.0.32-1.el7
  mysql-community-common.x86_64 0:8.0.32-1.el7                    mysql-community-devel.x86_64 0:8.0.32-1.el7
  mysql-community-embedded-compat.x86_64 0:8.0.32-1.el7           mysql-community-icu-data-files.x86_64 0:8.0.32-1.el7
  mysql-community-libs.x86_64 0:8.0.32-1.el7                      mysql-community-libs-compat.x86_64 0:8.0.32-1.el7
  mysql-community-server.x86_64 0:8.0.32-1.el7                    mysql-community-test.x86_64 0:8.0.32-1.el7

Dependency Installed:
  keyutils-libs-devel.x86_64 0:1.5.8-3.el7     krb5-devel.x86_64 0:1.15.1-51.el7_9    libcom_err-devel.x86_64 0:1.42.9-19.el7
  libselinux-devel.x86_64 0:2.5-15.el7         libsepol-devel.x86_64 0:2.5-10.el7     libverto-devel.x86_64 0:0.2.5-4.el7
  openssl-devel.x86_64 1:1.0.2k-25.el7_9       pcre-devel.x86_64 0:8.32-17.el7        perl.x86_64 4:5.16.3-299.el7_9
  perl-Carp.noarch 0:1.26-244.el7              perl-Data-Dumper.x86_64 0:2.145-3.el7  perl-Encode.x86_64 0:2.51-7.el7
  perl-Exporter.noarch 0:5.68-3.el7            perl-File-Path.noarch 0:2.09-2.el7     perl-File-Temp.noarch 0:0.23.01-3.el7
  perl-Filter.x86_64 0:1.49-3.el7              perl-Getopt-Long.noarch 0:2.40-3.el7   perl-HTTP-Tiny.noarch 0:0.033-3.el7
  perl-JSON.noarch 0:2.59-2.el7                perl-PathTools.x86_64 0:3.40-5.el7     perl-Pod-Escapes.noarch 1:1.04-299.el7_9
  perl-Pod-Perldoc.noarch 0:3.20-4.el7         perl-Pod-Simple.noarch 1:3.28-4.el7    perl-Pod-Usage.noarch 0:1.63-3.el7
  perl-Scalar-List-Utils.x86_64 0:1.27-248.el7 perl-Socket.x86_64 0:2.010-5.el7       perl-Storable.x86_64 0:2.45-3.el7
  perl-Test-Harness.noarch 0:3.28-3.el7        perl-Test-Simple.noarch 0:0.98-243.el7 perl-Text-ParseWords.noarch 0:3.29-4.el7
  perl-Time-HiRes.x86_64 4:1.9725-3.el7        perl-Time-Local.noarch 0:1.2300-2.el7  perl-constant.noarch 0:1.27-2.el7
  perl-libs.x86_64 4:5.16.3-299.el7_9          perl-macros.x86_64 4:5.16.3-299.el7_9  perl-parent.noarch 1:0.225-244.el7
  perl-podlators.noarch 0:2.5.1-3.el7          perl-threads.x86_64 0:1.87-4.el7       perl-threads-shared.x86_64 0:1.43-6.el7
  zlib-devel.x86_64 0:1.2.7-19.el7_9

Replaced:
  mariadb-libs.x86_64 1:5.5.68-1.el7

Complete!
```
 * after successful installation enable mysqld
```
 [yesdb@sn2ylvx1a020 mysql8032]$ sudo systemctl enable mysqld
```
 * start mysql service
```
[yesdb@sn2ylvx1a020 mysql8032]$ sudo systemctl start mysqld
```
 * check status
```
[yesdb@sn2ylvx1a020 mysql8032]$ sudo systemctl status mysqld
```
```
● mysqld.service - MySQL Server
   Loaded: loaded (/usr/lib/systemd/system/mysqld.service; enabled; vendor preset: disabled)
   Active: active (running) since Thu 2023-02-16 15:56:56 +08; 17s ago
     Docs: man:mysqld(8)
           http://dev.mysql.com/doc/refman/en/using-systemd.html
  Process: 28440 ExecStartPre=/usr/bin/mysqld_pre_systemd (code=exited, status=0/SUCCESS)
 Main PID: 28514 (mysqld)
   Status: "Server is operational"
   CGroup: /system.slice/mysqld.service
           └─28514 /usr/sbin/mysqld

Feb 16 15:56:41 sn2ylvx1a020 systemd[1]: Starting MySQL Server...
Feb 16 15:56:56 sn2ylvx1a020 systemd[1]: Started MySQL Server.
```
 * file temporary password for root
``` 
 [yesdb@sn2ylvx1a020 mysql8032]$sudo grep -i pass /var/log/mysqld.log
```
```
2023-02-16T07:56:47.123847Z 6 [Note] [MY-010454] [Server] A temporary password is generated for root@localhost: /y<sOg&o>0hc
```
 * change permissions
```
 [yesdb@sn2ylvx1a020 mysql8032]$ sudo chmod 644 /var/log/mysqld.log
```
```
 [yesdb@sn2ylvx1a020 mysql8032]$ grep -i pass /var/log/mysqld.log
```
```
 2023-02-16T07:56:47.123847Z 6 [Note] [MY-010454] [Server] A temporary password is generated for root@localhost: /y<sOg&o>0hc
```
 * login to mysql shell using temporary root password
```
 [yesdb@sn2ylvx1a020 mysql8032]$ mysql -uroot -p
```
```
Enter password:
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 8
Server version: 8.0.32

Copyright (c) 2000, 2023, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

 * set root password
```
 mysql> set password ='Invalid_Pa55w0rd';
 Query OK, 0 rows affected (0.02 sec)
```
