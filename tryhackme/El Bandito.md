---
description: Can you help capture El Bandito before he leaves the galaxy
---

# Empty

First, let's use nmap to enumerate open ports :
```
└─$ nmap -T4 -n -sC -sV -Pn -p- 10.10.163.160                  
Starting Nmap 7.94SVN ( https://nmap.org ) at 2025-01-12 20:01 EST
Nmap scan report for 10.10.163.160
Host is up (0.11s latency).
Not shown: 65531 closed tcp ports (reset)
PORT     STATE SERVICE  VERSION
22/tcp   open  ssh      OpenSSH 8.2p1 Ubuntu 4ubuntu0.11 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 db:1d:a8:27:3b:46:d4:9b:df:17:67:11:48:67:89:39 (RSA)
|   256 85:06:3c:8d:2f:80:0c:e1:e7:b8:97:c0:d1:a7:d0:e7 (ECDSA)
|_  256 ba:ee:c9:ab:f2:c2:bd:2e:6b:f7:6b:2d:76:d7:78:7e (ED25519)
80/tcp   open  ssl/http El Bandito Server
|_http-server-header: El Bandito Server
| ssl-cert: Subject: commonName=localhost
| Subject Alternative Name: DNS:localhost
| Not valid before: 2021-04-10T06:51:56
|_Not valid after:  2031-04-08T06:51:56
| fingerprint-strings: 
|   FourOhFourRequest: 
|     HTTP/1.1 404 NOT FOUND
|     Date: Mon, 13 Jan 2025 01:07:57 GMT
|     Content-Type: text/html; charset=utf-8
|     Content-Length: 207
|     Content-Security-Policy: default-src 'self'; script-src 'self'; object-src 'none';
|     X-Content-Type-Options: nosniff
|     X-Frame-Options: SAMEORIGIN
|     X-XSS-Protection: 1; mode=block
|     Feature-Policy: microphone 'none'; geolocation 'none';
|     Age: 0
|     Server: El Bandito Server
|     Connection: close
|     <!doctype html>
|     <html lang=en>
|     <title>404 Not Found</title>
|     <h1>Not Found</h1>
|     <p>The requested URL was not found on the server. If you entered the URL manually please check your spelling and try again.</p>
|   GetRequest: 
|     HTTP/1.1 200 OK
|     Date: Mon, 13 Jan 2025 01:07:03 GMT
|     Content-Type: text/html; charset=utf-8
|     Content-Length: 58
|     Content-Security-Policy: default-src 'self'; script-src 'self'; object-src 'none';
|     X-Content-Type-Options: nosniff
|     X-Frame-Options: SAMEORIGIN
|     X-XSS-Protection: 1; mode=block
|     Feature-Policy: microphone 'none'; geolocation 'none';
|     Age: 0
|     Server: El Bandito Server
|     Accept-Ranges: bytes
|     Connection: close
|     nothing to see <script src='/static/messages.js'></script>
|   HTTPOptions: 
|     HTTP/1.1 200 OK
|     Date: Mon, 13 Jan 2025 01:07:04 GMT
|     Content-Type: text/html; charset=utf-8
|     Content-Length: 0
|     Allow: HEAD, POST, GET, OPTIONS
|     Content-Security-Policy: default-src 'self'; script-src 'self'; object-src 'none';
|     X-Content-Type-Options: nosniff
|     X-Frame-Options: SAMEORIGIN
|     X-XSS-Protection: 1; mode=block
|     Feature-Policy: microphone 'none'; geolocation 'none';
|     Age: 0
|     Server: El Bandito Server
|     Accept-Ranges: bytes
|     Connection: close
|   RTSPRequest: 
|_    HTTP/1.1 400 Bad Request
|_ssl-date: TLS randomness does not represent time
|_http-title: Site doesn't have a title (text/html; charset=utf-8).
631/tcp  open  ipp      CUPS 2.4
|_http-server-header: CUPS/2.4 IPP/2.1
|_http-title: Forbidden - CUPS v2.4.7
8080/tcp open  http     nginx
|_http-favicon: Spring Java Framework
|_http-title: Site doesn't have a title (application/json;charset=UTF-8).
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port80-TCP:V=7.94SVN%T=SSL%I=7%D=1/12%Time=67846737%P=x86_64-pc-linux-g
SF:nu%r(GetRequest,1E5,"HTTP/1\.1\x20200\x20OK\r\nDate:\x20Mon,\x2013\x20J
SF:an\x202025\x2001:07:03\x20GMT\r\nContent-Type:\x20text/html;\x20charset
SF:=utf-8\r\nContent-Length:\x2058\r\nContent-Security-Policy:\x20default-
SF:src\x20'self';\x20script-src\x20'self';\x20object-src\x20'none';\r\nX-C
SF:ontent-Type-Options:\x20nosniff\r\nX-Frame-Options:\x20SAMEORIGIN\r\nX-
SF:XSS-Protection:\x201;\x20mode=block\r\nFeature-Policy:\x20microphone\x2
SF:0'none';\x20geolocation\x20'none';\r\nAge:\x200\r\nServer:\x20El\x20Ban
SF:dito\x20Server\r\nAccept-Ranges:\x20bytes\r\nConnection:\x20close\r\n\r
SF:\nnothing\x20to\x20see\x20<script\x20src='/static/messages\.js'></scrip
SF:t>")%r(HTTPOptions,1CB,"HTTP/1\.1\x20200\x20OK\r\nDate:\x20Mon,\x2013\x
SF:20Jan\x202025\x2001:07:04\x20GMT\r\nContent-Type:\x20text/html;\x20char
SF:set=utf-8\r\nContent-Length:\x200\r\nAllow:\x20HEAD,\x20POST,\x20GET,\x
SF:20OPTIONS\r\nContent-Security-Policy:\x20default-src\x20'self';\x20scri
SF:pt-src\x20'self';\x20object-src\x20'none';\r\nX-Content-Type-Options:\x
SF:20nosniff\r\nX-Frame-Options:\x20SAMEORIGIN\r\nX-XSS-Protection:\x201;\
SF:x20mode=block\r\nFeature-Policy:\x20microphone\x20'none';\x20geolocatio
SF:n\x20'none';\r\nAge:\x200\r\nServer:\x20El\x20Bandito\x20Server\r\nAcce
SF:pt-Ranges:\x20bytes\r\nConnection:\x20close\r\n\r\n")%r(RTSPRequest,1C,
SF:"HTTP/1\.1\x20400\x20Bad\x20Request\r\n\r\n")%r(FourOhFourRequest,26C,"
SF:HTTP/1\.1\x20404\x20NOT\x20FOUND\r\nDate:\x20Mon,\x2013\x20Jan\x202025\
SF:x2001:07:57\x20GMT\r\nContent-Type:\x20text/html;\x20charset=utf-8\r\nC
SF:ontent-Length:\x20207\r\nContent-Security-Policy:\x20default-src\x20'se
SF:lf';\x20script-src\x20'self';\x20object-src\x20'none';\r\nX-Content-Typ
SF:e-Options:\x20nosniff\r\nX-Frame-Options:\x20SAMEORIGIN\r\nX-XSS-Protec
SF:tion:\x201;\x20mode=block\r\nFeature-Policy:\x20microphone\x20'none';\x
SF:20geolocation\x20'none';\r\nAge:\x200\r\nServer:\x20El\x20Bandito\x20Se
SF:rver\r\nConnection:\x20close\r\n\r\n<!doctype\x20html>\n<html\x20lang=e
SF:n>\n<title>404\x20Not\x20Found</title>\n<h1>Not\x20Found</h1>\n<p>The\x
SF:20requested\x20URL\x20was\x20not\x20found\x20on\x20the\x20server\.\x20I
SF:f\x20you\x20entered\x20the\x20URL\x20manually\x20please\x20check\x20you
SF:r\x20spelling\x20and\x20try\x20again\.</p>\n");
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 473.79 seconds
                                                               
```
``
![](../imgs/Pasted%20image%2020250112200505.png)

In the page code, there a script located at : /static/messages.js
It seems to possible to send & receive to the server.
```
document.addEventListener("DOMContentLoaded", function () {
	const discussions = document.querySelectorAll(".discussion");
	const messagesChat = document.querySelector(".messages-chat");
	const headerName = document.querySelector(".header-chat .name");
	const writeMessageInput = document.querySelector(".write-message");
	let userMessages = {
		JACK: [],
		OLIVER: [],
	};

	// Function to fetch messages from the server
	function fetchMessages() {
		fetch("/getMessages")
			.then((response) => {
				if (!response.ok) {
					throw new Error("Failed to fetch messages");
				}
				return response.json();
			})
			.then((messages) => {
				userMessages = messages;
				userMessages.JACK === undefined
					? (userMessages = { OLIVER: messages.OLIVER, JACK: [] })
					: userMessages.OLIVER === undefined &&
					  (userMessages = { JACK: messages.JACK, OLIVER: [] });

				displayMessages("JACK");
			})
			.catch((error) => console.error("Error fetching messages:", error));
	}

	// Function to display messages for the selected user
	function displayMessages(userName) {
		headerName.innerText = userName;
		messagesChat.innerHTML = "";
		userMessages[userName].forEach(function (messageData) {
			appendMessage(messageData);
		});
	}

	// Function to append a message to the chat area
	function appendMessage(messageData) {
		const newMessage = document.createElement("div");
		console.log({ messageData });
		newMessage.classList.add("message", "text-only");
		newMessage.innerHTML = `
           ${messageData.sender !== "Bot" ? '<div class="response">' : ""}
        <div class="text">${messageData}</div>
    ${messageData.sender !== "Bot" ? "</div>" : ""}
        `;
		messagesChat.appendChild(newMessage);
	}

	// Function to send a message to the server
	function sendMessage() {
		const messageText = writeMessageInput.value.trim();
		if (messageText !== "") {
			const activeUser = headerName.innerText;
			const urlParams = new URLSearchParams(window.location.search);
			const isBot =
				urlParams.has("msg") && urlParams.get("msg") === messageText;

			const messageData = {
				message: messageText,
				sender: isBot ? "Bot" : activeUser, // Set the sender as "Bot"
			};
			userMessages[activeUser].push(messageData);
			appendMessage(messageText);
			writeMessageInput.value = "";
			scrollToBottom();
			console.log({ activeUser });
			fetch("/send_message", {
				method: "POST",
				headers: {
					"Content-Type": "application/x-www-form-urlencoded",
				},
				body: "data="+messageText
			})
				.then((response) => {
					if (!response.ok) {
						throw new Error("Network response was not ok");
					}
					console.log("Message sent successfully");
				})
				.catch((error) => {
					console.error("Error sending message:", error);
					// Handle error (e.g., display error message to the user)
				});
		}
	}

	// Event listeners
	discussions.forEach(function (discussion) {
		discussion.addEventListener("click", function () {
			const userName = this.dataset.name;
			console.log({ userName });
			displayMessages(userName.toUpperCase());
		});
	});

	const sendButton = document.querySelector(".send");
	sendButton.addEventListener("click", sendMessage);
	writeMessageInput.addEventListener("keydown", function (event) {
		if (event.key === "Enter") {
			event.preventDefault();
			sendMessage();
		}
	});

	// Initial actions
	fetchMessages();
});

// Function to scroll to the bottom of the messages chat
function scrollToBottom() {
	const messagesChat = document.getElementById("messages-chat");
	messagesChat.scrollTop = messagesChat.scrollHeight;
}
```
/getMessages will return the login page

![](../imgs/Pasted%20image%2020250112201230.png)

Port 631, returns the CUPS server that seems to be inacessible :

![](../../Pasted%20image%2020250112202012.png)

Port 8080, leads to a Digital Rebellion with Bandit-Coin... that looks shady.
![](../../Pasted%20image%2020250112203709.png)

