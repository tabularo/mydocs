# Installation @Ubuntu

```{note}
Make shure proper JAVA version is installed, see Chapter JAVA.
```

## Install unzip
Install unzip if it's not already installed:

 ```{code-block} shell
 :caption: Terminal @guest
 
sudo apt update
sudo apt install unzip -y
 
```

## Download NiFi
Download the NiFi binary using wget:

 ```{code-block} shell
 :caption: Terminal @guest
 
wget https://www.apache.org/dyn/closer.lua?path=/nifi/2.0.0-M3/nifi-2.0.0-M3-bin.zip -O nifi-2.0.0-M3-bin.zip
 
```

## Extract Download
Extract the downloaded zip file:
 ```{code-block} shell
 :caption: Terminal @guest
 
unzip nifi-2.0.0-M3-bin.zip
 
```

## Clean up
Rename the extracted directory for convenience (optional):
 ```{code-block} shell
 :caption: Terminal @guest
 
mv nifi-2.0.0-M3 nifi
 
```

## Verfiy Nifi Installation

From `~/nifi/bin` run

 ```{code-block} shell
 :caption: Terminal @guest
 
./nifi.sh start
./nifi.sh status
 
```

## Start FrontEnd

Type in your browser:

 ```{code-block} shell
 :caption: Terminal @guest
 
https://localhost:8443
 
```

```{warning}
If you face an error in your browser, it could be a nightmare to solve the issue. My known troubleshootings, see below. 
```

## Troubleshooting FE

### nifi.properties
In this file there is an entry you probably might to change. For me it worked, cause of my WSL2 Setup on Win11.

 ```{code-block} shell
 :caption: Terminal @guest
 
 nifi.web.https.host=localhost          # default
 nifi.web.https.host=0.0.0.0            # changed to

 
```

```{note}

**Explanation:**

**Binding to Localhost:** nifi.web.https.host=localhost binds the NiFi web server to the localhost interface, meaning it will only accept connections from the same machine. This is suitable for local development or instances where you do not need to access the NiFi UI from other machines.
When bound to localhost, the server listens only on the loopback network interface (127.0.0.1). As a result, attempts to connect from other machines, even within the same network, will be refused.

**Binding to 0.0.0.0:** nifi.web.https.host=0.0.0.0 binds the NiFi web server to all available network interfaces on the machine. This allows the server to accept connections from any IP address assigned to the machine, including external and internal network interfaces.
This configuration is useful when you want to access the NiFi UI from other machines within your local network, or when setting up NiFi in a server environment where multiple clients or users need access.


**Why the Change Worked:**

**Accessibility:** By changing the binding address to 0.0.0.0, you make the NiFi UI accessible from any machine that can reach the server's IP address. This is crucial for remote administration, multi-user environments, or when running NiFi in a networked server setup.
Firewall and Proxy Settings: With 0.0.0.0, firewall and port proxy settings can be correctly configured to allow traffic from external sources, making the server reachable over the network.

**Security Considerations:** Exposure: Binding to 0.0.0.0 exposes the NiFi instance to the network, which may have security implications. Ensure proper firewall rules, access controls, and SSL/TLS configurations are in place to protect the instance.
Restricted Access: Consider using network security groups, VPNs, or reverse proxies to restrict access to the NiFi UI to only trusted users or networks.

By understanding the implications of binding the NiFi web server to different interfaces, you can make informed decisions about how to configure access to your NiFi instance based on your specific requirements and security posture.

```