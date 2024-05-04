# DNS (Domain Name System) Explained

## Overview

DNS (Domain Name System) is a distributed naming system used to translate domain names (e.g., example.com) into IP addresses (e.g., 192.0.2.1). It serves as the "phonebook" of the internet, mapping human-readable domain names to numerical IP addresses.

# Tech-Components
Tech Components - which provides details of content
![image](https://user-images.githubusercontent.com/115500959/195164522-c579247d-39eb-45cd-bde4-4d964d81ec53.png)

### What happens when you type a URL into your browser?

The diagram below illustrates the steps.<br>

1. Bob enters a URL into the browser and hits Enter. In this example, the URL is composed of 4 parts:<br>

🔹 scheme - 𝒉𝒕𝒕𝒑://. This tells the browser to send a connection to the server using HTTP.<br>
🔹 domain - 𝒆𝒙𝒂𝒎𝒑𝒍𝒆.𝒄𝒐𝒎. This is the domain name of the site.<br>
🔹 path - 𝒑𝒓𝒐𝒅𝒖𝒄𝒕/𝒆𝒍𝒆𝒄𝒕𝒓𝒊𝒄. It is the path on the server to the requested resource: phone.<br>
🔹 resource - 𝒑𝒉𝒐𝒏𝒆. It is the name of the resource Bob wants to visit.<br>

2. The browser looks up the IP address for the domain with a domain name system (DNS) lookup. To make the lookup process fast,
data is cached at different layers: browser cache, OS cache, local network cache, and ISP cache. <br>

2.1 If the IP address cannot be found at any of the caches, 
the browser goes to DNS servers to do a recursive DNS lookup until the IP address is found (this will be covered in another post). <br>

3. Now that we have the IP address of the server, the browser establishes a TCP connection with the server.<br>

4. The browser sends an HTTP request to the server. The request looks like this:<br>

𝘎𝘌𝘛 /𝘱𝘩𝘰𝘯𝘦 𝘏𝘛𝘛𝘗/1.1<br>
𝘏𝘰𝘴𝘵: 𝘦𝘹𝘢𝘮𝘱𝘭𝘦.𝘤𝘰𝘮<br>

5. The server processes the request and sends back the response. For a successful response (the status code is 200). The HTML response might look like this: <br>

𝘏𝘛𝘛𝘗/1.1 200 𝘖𝘒<br>
𝘋𝘢𝘵𝘦: 𝘚𝘶𝘯, 30 𝘑𝘢𝘯 2022 00:01:01 𝘎𝘔𝘛<br>
𝘚𝘦𝘳𝘷𝘦𝘳: 𝘈𝘱𝘢𝘤𝘩𝘦<br>
𝘊𝘰𝘯𝘵𝘦𝘯𝘵-𝘛𝘺𝘱𝘦: 𝘵𝘦𝘹𝘵/𝘩𝘵𝘮𝘭; 𝘤𝘩𝘢𝘳𝘴𝘦𝘵=𝘶𝘵𝘧-8<br>

<!𝘋𝘖𝘊𝘛𝘠𝘗𝘌 𝘩𝘵𝘮𝘭><br>
<𝘩𝘵𝘮𝘭 𝘭𝘢𝘯𝘨="𝘦𝘯"><br>
𝘏𝘦𝘭𝘭𝘰 𝘸𝘰𝘳𝘭𝘥<br>
</𝘩𝘵𝘮𝘭><br>

6. The browser renders the HTML content.<br>

![image](https://user-images.githubusercontent.com/115500959/207751464-bbe34d12-1c02-4f7c-a539-1a78a2b5ad7f.png)


### Components

- **Domain Name**: A hierarchical naming system used to identify resources on the internet, organized into domains, subdomains, and hostnames.
- **DNS Resolver**: Software or service responsible for initiating and processing DNS queries on behalf of client devices.
- **DNS Server**: Servers that store DNS records and respond to DNS queries. There are several types of DNS servers, including recursive, authoritative, and caching servers.

## How DNS Works in Day-to-Day Life

1. **Browsing Websites**: When you enter a domain name (e.g., www.example.com) into your web browser, the browser sends a DNS query to a DNS resolver, typically provided by your ISP or configured in your network settings.

2. **DNS Resolution**: The DNS resolver checks its cache to see if it has a recent record of the domain name's IP address. If not, it sends a DNS query to one of the root DNS servers.

3. **Recursive Resolution**: The root DNS server responds to the resolver with a referral to the appropriate Top-Level Domain (TLD) server (e.g., .com, .net). The resolver then sends a query to the TLD server.

4. **Authoritative Resolution**: The TLD server responds with a referral to the authoritative DNS server responsible for the domain name (e.g., ns1.example.com). The resolver sends a query to the authoritative server.

5. **IP Address Retrieval**: The authoritative server responds with the IP address corresponding to the domain name. The resolver caches the response for future use and returns the IP address to the client's web browser.

## Real-Life Scenarios

- **Accessing Websites**: DNS enables you to access websites by translating domain names into IP addresses.For example, when you type "www.google.com" into your browser, DNS resolves it to an IP address, allowing you to connect to Google's servers.
- **Sending Emails**: DNS is used to locate the mail server associated with a recipient's email address. When you send an email to someone, your email client queries DNS to find the MX (Mail Exchange) records for the recipient's domain to deliver the email.
- **Streaming Media**: DNS resolves domain names for streaming media services like Netflix or YouTube, allowing you to access and stream videos by translating domain names into the IP addresses of content delivery servers.
- **Remote Access**: DNS enables remote access to devices using domain names instead of IP addresses.For example, when you connect to a remote server using SSH (Secure Shell), DNS translates the server's hostname to its IP address for communication.

DNS plays a crucial role in facilitating internet communication and accessing online services, making it an essential component of our daily interactions with the internet.
