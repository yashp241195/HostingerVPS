Openlitespeed Server Configurations

VH Host Config for NodeJS App

1/ Basic

Base
Virtual Host Name	Example
Virtual Host Root	Example/
Config File	conf/vhosts/Example/vhconf.conf

Security
Follow Symbolic Link	Yes
Enable Scripts/ExtApps	Yes
Restrained	Yes
External App Set UID Mode	Server UID

2/ General

General
Document Root	$VH_ROOT/html/
Domain Name	Not Set
Domain Aliases	Not Set
Administrator Email	Not Set
Enable GZIP Compression	Yes

Index Files
Use Server Index Files	No
Index Files	index.html, index.php
Auto Index	No
Auto Index URI	/_autoindex/default.php

Customized Error Pages
Error Code	URL	Actions
	404 Not Found	/error404.html	
 
Expires Settings
Enable Expires	Yes

3/ Logs

Virtual Host Log
Use Server's Log	Yes
File Name	$VH_ROOT/logs/error.log
Log Level	DEBUG
Rolling Size (bytes)	10M

Access Log
Log Control	File Name	Log Format	Rolling Size (bytes)	Actions
Own Log File	$VH_ROOT/logs/access.log	Not Set	10M	
 
8/ Context 

Static Context Definition
URI	/.well-known/
Location	/usr/local/lsws/Example/html/.well-known/
Accessible	Yes

App Server Context Definition
URI	/
Location	/usr/local/lsws/Example/html/node/
Binary Path	/usr/bin/node
Application Type	Node

Adding Domain Name with SSL certificate.


Add a free 3 month certificate Zero SSL


Verification Method for example.com via DNS. (Zero SSL)

We need you to verify ownership of each domain in your certificate.
Please select your preferred verification method and click "Next Step".

* DNS (CNAME)
Follow the steps below
To verify your domain using a CNAME record, please follow the steps below:

Sign in to your DNS provider, typically the registrar of your domain.
Navigate to the section where DNS records are managed.
Add the following CNAME record:
Name
_8c02ec8d2b3a22ecef140646d11a1f0d
Point To
0c76719ba56c989361bd251a8eaa5a87.4fc34fe1e0f103b4bd64405306d4a17f.c373fbe39276455.comodoca.com.
TTL
3600 (or lower)
Save your CNAME record and click "Next Step" to continue.

Download the file "Q5BFND7WQwpjffR18Tba8Hs2CEP54l6csQX-S5shnQI.nUSO0F4kPv8-MKBJPZVHI0g74W3ZA5x9OQ2nmiXVadQ" 
after verification confirmation and Upload it on your server at ".well-known/" directory

Settings for DNS (Godaddy)

Type Name Data TTL

A	@	147.162.228.118	600 seconds		

A	sales	147.162.228.118	600 seconds		// adding the subdomain "sales.example.com"

NS	@	ns09.domaincontrol.com.	1 Hour	

NS	@	ns10.domaincontrol.com.	1 Hour	

CNAME	www	example.com. 1 Hour		

CNAME	_8c02ec8d2b3a22ecef140646d11a1f0d 

	0c76719ba56c989361bd251a8eaa5a87.4fc34fe1e0f103b4bd64405306d4a17f.c373fbe39276455.comodoca.com.	600 seconds		

CNAME	_domainconnect	_domainconnect.gd.domaincontrol.com.	1 Hour		

SOA	@	Primary nameserver: ns09.domaincontrol.com.	1 Hour		



VH Host Config

8/ Context

Context List
Type	URI	Accessible	Order	Actions
	Static	/.well-known/	Yes	1  	
  
	App Server	/	Not Set	2  	

Static Context Definition  
URI	/.well-known/
Location	/usr/local/lsws/Example/html/.well-known/
Accessible	Yes

upload "Q5BFND7WQwpjffR18Tba8Hs2CEP54l6csQX-S5shnQI.nUSO0F4kPv8-MKBJPZVHI0g74W3ZA5x9OQ2nmiXVadQ" file to /usr/local/lsws/Example/html/.well-known/ using FileZilla

Listener Config

Listener List
Listener Name	IP Address	Port	Secure	Actions
	Default	ANY	80	No	
 
	Defaultssl	ANY	443	Yes	
 
Listener Defaultssl 

1/ General

Address Settings
Listener Name	Defaultssl
IP Address	ANY IPv4
Port	443
Binding	Not Set
Enable REUSEPORT	Not Set
Secure	Yes
Notes	Not Set
Virtual Host Mappings
Virtual Host	Domains	Actions
	Example	example.com	

2/SSL

SSL Private Key & Certificate
Private Key File	/usr/local/lsws/conf/Example/private.key
Certificate File	/usr/local/lsws/conf/Example/certificate.crt
Chained Certificate /usr/local/lsws/conf/Example/ca_bundle.crt
CA Certificate Path	/usr/local/lsws/conf/Example/ca_bundle.crt
CA Certificate File	/usr/local/lsws/conf/Example/ca_bundle.crt

Upload SSL certificate via Filzilla at the location /usr/local/lsws/conf/Example/private.key
