# How to install haste-client in Ubuntu
Hastebin Server

Introduction
haste-client is a simple client for uploading data to haste-server. All you do is pipe data in STDIN:
```
cat file | paste
```
Once the data has arrived on the server, a URL will be generated to view the output:
```
superloop@hastebin:~$ superloop host exec "show int status" --node pc-oobsw-105-iad4 | paste   
Password: 
https://hastebin.ops.kobo.com/uvemalikez
```
Typically when a user would like to share an output from shell, a traditional copy and paste to the group chat/channel would occur or a screen share via zoom. This essentially clutters the channel and may be difficult for others to follow along. Furthermore, formatting of text may be offset. Users can now share the URL in chat for viewing as oppose to the entire output.
Installation
First, ensure you have Ruby installed:
```
apt install ruby
```
```
root@hastebin:~# apt install ruby
Reading package lists... Done
Building dependency tree       
Reading state information... Done
The following additional packages will be installed:
  fonts-lato javascript-common libjs-jquery libruby2.7 rake ruby-minitest ruby-net-telnet ruby-power-assert ruby-test-unit
  ruby-xmlrpc ruby2.7 rubygems-integration unzip zip
Suggested packages:
  apache2 | lighttpd | httpd ri ruby-dev bundler
The following NEW packages will be installed:
  fonts-lato javascript-common libjs-jquery libruby2.7 rake ruby ruby-minitest ruby-net-telnet ruby-power-assert ruby-test-unit
  ruby-xmlrpc ruby2.7 rubygems-integration unzip zip
0 upgraded, 15 newly installed, 0 to remove and 239 not upgraded.
Need to get 7,231 kB of archives.
After this operation, 32.7 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://us.archive.ubuntu.com/ubuntu focal/main amd64 fonts-lato all 2.0-2 [2,698 kB]
Get:2 http://us.archive.ubuntu.com/ubuntu focal/main amd64 javascript-common all 11 [6,066 B]
Get:3 http://us.archive.ubuntu.com/ubuntu focal/main amd64 libjs-jquery all 3.3.1~dfsg-3 [329 kB]
Get:4 http://us.archive.ubuntu.com/ubuntu focal/main amd64 rubygems-integration all 1.16 [5,092 B]
Get:5 http://us.archive.ubuntu.com/ubuntu focal-updates/main amd64 ruby2.7 amd64 2.7.0-5ubuntu1.7 [95.6 kB]
Get:6 http://us.archive.ubuntu.com/ubuntu focal/main amd64 ruby amd64 1:2.7+1 [5,412 B]
Get:7 http://us.archive.ubuntu.com/ubuntu focal/main amd64 rake all 13.0.1-4 [61.6 kB]
Get:8 http://us.archive.ubuntu.com/ubuntu focal/main amd64 ruby-minitest all 5.13.0-1 [40.9 kB]
Get:9 http://us.archive.ubuntu.com/ubuntu focal/main amd64 ruby-net-telnet all 0.1.1-2 [12.6 kB]
Get:10 http://us.archive.ubuntu.com/ubuntu focal/main amd64 ruby-power-assert all 1.1.7-1 [11.4 kB]
Get:11 http://us.archive.ubuntu.com/ubuntu focal/main amd64 ruby-test-unit all 3.3.5-1 [73.2 kB]
Get:12 http://us.archive.ubuntu.com/ubuntu focal/main amd64 ruby-xmlrpc all 0.3.0-2 [23.8 kB]
Get:13 http://us.archive.ubuntu.com/ubuntu focal-updates/main amd64 libruby2.7 amd64 2.7.0-5ubuntu1.7 [3,533 kB]
Get:14 http://us.archive.ubuntu.com/ubuntu focal-updates/main amd64 unzip amd64 6.0-25ubuntu1.1 [168 kB]
Get:15 http://us.archive.ubuntu.com/ubuntu focal/main amd64 zip amd64 3.0-11build1 [167 kB]
Fetched 7,231 kB in 0s (15.5 MB/s)
Selecting previously unselected package fonts-lato.
(Reading database ... 143256 files and directories currently installed.)
Preparing to unpack .../00-fonts-lato_2.0-2_all.deb ...
Unpacking fonts-lato (2.0-2) ...
Selecting previously unselected package javascript-common.
Preparing to unpack .../01-javascript-common_11_all.deb ...
Unpacking javascript-common (11) ...
Selecting previously unselected package libjs-jquery.
Preparing to unpack .../02-libjs-jquery_3.3.1~dfsg-3_all.deb ...
Unpacking libjs-jquery (3.3.1~dfsg-3) ...
Selecting previously unselected package rubygems-integration.
Preparing to unpack .../03-rubygems-integration_1.16_all.deb ...
Unpacking rubygems-integration (1.16) ...
Selecting previously unselected package ruby2.7.
Preparing to unpack .../04-ruby2.7_2.7.0-5ubuntu1.7_amd64.deb ...
Unpacking ruby2.7 (2.7.0-5ubuntu1.7) ...
Selecting previously unselected package ruby.
Preparing to unpack .../05-ruby_1%3a2.7+1_amd64.deb ...
Unpacking ruby (1:2.7+1) ...
Selecting previously unselected package rake.
Preparing to unpack .../06-rake_13.0.1-4_all.deb ...
Unpacking rake (13.0.1-4) ...
Selecting previously unselected package ruby-minitest.
Preparing to unpack .../07-ruby-minitest_5.13.0-1_all.deb ...
Unpacking ruby-minitest (5.13.0-1) ...
Selecting previously unselected package ruby-net-telnet.
Preparing to unpack .../08-ruby-net-telnet_0.1.1-2_all.deb ...
Unpacking ruby-net-telnet (0.1.1-2) ...
Selecting previously unselected package ruby-power-assert.
Preparing to unpack .../09-ruby-power-assert_1.1.7-1_all.deb ...
Unpacking ruby-power-assert (1.1.7-1) ...
Selecting previously unselected package ruby-test-unit.
Preparing to unpack .../10-ruby-test-unit_3.3.5-1_all.deb ...
Unpacking ruby-test-unit (3.3.5-1) ...
Selecting previously unselected package ruby-xmlrpc.
Preparing to unpack .../11-ruby-xmlrpc_0.3.0-2_all.deb ...
Unpacking ruby-xmlrpc (0.3.0-2) ...
Selecting previously unselected package libruby2.7:amd64.
Preparing to unpack .../12-libruby2.7_2.7.0-5ubuntu1.7_amd64.deb ...
Unpacking libruby2.7:amd64 (2.7.0-5ubuntu1.7) ...
Selecting previously unselected package unzip.
Preparing to unpack .../13-unzip_6.0-25ubuntu1.1_amd64.deb ...
Unpacking unzip (6.0-25ubuntu1.1) ...
Selecting previously unselected package zip.
Preparing to unpack .../14-zip_3.0-11build1_amd64.deb ...
Unpacking zip (3.0-11build1) ...
Setting up javascript-common (11) ...
Setting up fonts-lato (2.0-2) ...
Setting up ruby-power-assert (1.1.7-1) ...
Setting up unzip (6.0-25ubuntu1.1) ...
Setting up rubygems-integration (1.16) ...
Setting up ruby-minitest (5.13.0-1) ...
Setting up zip (3.0-11build1) ...
Setting up ruby-test-unit (3.3.5-1) ...
Setting up ruby-net-telnet (0.1.1-2) ...
Setting up libjs-jquery (3.3.1~dfsg-3) ...
Setting up ruby-xmlrpc (0.3.0-2) ...
Setting up rake (13.0.1-4) ...
Setting up libruby2.7:amd64 (2.7.0-5ubuntu1.7) ...
Setting up ruby2.7 (2.7.0-5ubuntu1.7) ...
Setting up ruby (1:2.7+1) ...
Processing triggers for mime-support (3.64ubuntu1) ...
Processing triggers for libc-bin (2.31-0ubuntu9.2) ...
Processing triggers for man-db (2.9.1-1) ...
root@pc-netauto-001:~# gem install haste
Fetching haste-0.2.3.gem
Fetching multipart-post-2.3.0.gem
Fetching faraday-0.17.6.gem
Successfully installed multipart-post-2.3.0
Successfully installed faraday-0.17.6
Successfully installed haste-0.2.3
Parsing documentation for multipart-post-2.3.0
Installing ri documentation for multipart-post-2.3.0
Parsing documentation for faraday-0.17.6
Installing ri documentation for faraday-0.17.6
Parsing documentation for haste-0.2.3
Installing ri documentation for haste-0.2.3
Done installing documentation for multipart-post, faraday, haste after 0 seconds
3 gems installed
root@hastebin:~#
```

Now install the client:

```
gem install haste
```

Create an alias in your ~/.bashrc file:
```
vi ~/.bashrc
```
Once you're in ~/.bashrc, input the following:
```
alias paste="HASTE_SERVER=https://hastebin.ops.kobo.com/ haste"
```
Source your ~/.bashrc file so settings takes effect:
```
source ~/.bashrc
```
That's it! Now try to cat a file:
```
superloop@hastebin:~$ cat LICENSE.txt | paste
https://hastebin.ops.kobo.com/liyusedobe
```







Comment
Task

