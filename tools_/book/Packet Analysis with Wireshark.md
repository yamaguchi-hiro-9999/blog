# ping google.com
get ip

# nslookup google.com
get ip

## tcp.port==80

## ip.src == 202.6.246.238

## 「ip.src==IPアドレス」と「http」というフィルタを組み合わせて「ip.src==IPアドレス and http」

“If you notice the previous screenshot, the fieldname http.request.uri is selected to check if it is equal to (Relation) google.com (Value).
Hence the complete filter expression becomes 
## http.request.uri==google.com.”

“The same conversation is captured by choosing the destination MAC address using the display filter eth.addr == 06:73:7a:4c:2f:85.”

抜粋:: Anish Nath  “Packet Analysis with Wireshark”。 Apple Books  


# tcpdump -i eth0 -X
https://knowledge.sakura.ad.jp/6311/

```
ip.addr==	ip.addr==192.168.1.1	192.168.1.1を送信元、又は宛先IPアドレスとするフレーム
ip.src==	ip.src==192.168.1.2	送信元:192.168.1.2のフレーム
ip.dst==	ip.dst==192.168.1.3	宛先192.168.1.3のフレーム
プロトコル	icmp	icmpプロトコルのフレーム(他にはtcp,udp,http,arp等)
tcp.port==	tcp.port==80	TCPポート番号80を送信元、又は宛先とするフレーム
udp.port==	udp.port==53	UDPポート番号53を送信元、又は宛先とするフレーム
　条件式を利用してもう少し複雑なフィルタも書けます。以下に例を示します。

【複雑なフィルタ例】
条件式	フィルタ例	説明
&&	ip.src==102.168.1.2 && ip.dst==192.168.1.3	送信元192.168.1.2、且つ宛先192.168.1.3のフレーム
||	ip.src==102.168.1.2 || ip.dst==192.168.1.3	送信元192.168.1.2、又は宛先192.168.1.3のフレーム
()	(ip.src==192.168.1.2 && ip.dst==192.168.1.3) || (ip.src==192.168.1.4 && ip.dst==192.168.1.5)	送信元192.168.1.2で宛先192.168.1.3、送信元192.168.1.4で宛先192.168.1.5両方のフレーム
```