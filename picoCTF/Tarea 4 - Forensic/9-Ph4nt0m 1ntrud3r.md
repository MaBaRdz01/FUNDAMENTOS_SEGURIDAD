## RETO
Ph4nt0m 1ntrud3r
## DESCRIPCION
A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!Find the PCAP file here [Network Traffic PCAP file](https://challenge-files.picoctf.net/c_verbal_sleep/bdda31c79c31975a5fe5402777bc87794655172e5d5bb2b569f1970df8efda34/myNetworkTraffic.pcap) and try to get the flag.
## SOLUCION
──(kali㉿kali)-[~]
└─$ cd Downloads 
                                                                                                                                                              
┌──(kali㉿kali)-[~/Downloads]
└─$ tshark -r myNetworkTraffic.pcap -T fields -e tcp.segment_data

Warning: program compiled against libxml 215 using older 214
394e677a5745493d
32556661684f453d
596d68664e484a6659513d3d
567357472f46453d
626e52666447673064413d3d
74766a724132343d
63476c6a62304e5552673d3d
4c30774e69316f3d
556f6f63574d453d
5a6a45324d446b344d413d3d
4f6a414b634a4d3d
3979533856454d3d
704965344b67303d
587a4d3063336c6664413d3d
70772b6a4e796f3d
66513d3d
526a304a5545513d
6b4369533636773d
5777412f546a413d
58475758364c733d
6c4c67764534553d
657a46305833633063773d3d
                                                                                 
┌──(kali㉿kali)-[~/Downloads]
└─$ tshark -r myNetworkTraffic.pcap -Y "tcp.len==12 || tcp.len==4" -T fields -e tcp.segment_data | xxd -r -p

Warning: program compiled against libxml 215 using older 214
YmhfNHJfYQ==bnRfdGg0dA==cGljb0NURg==ZjE2MDk4MA==XzM0c3lfdA==fQ==ezF0X3c0cw==                                       

Usamos cyberchef .
bh_4r_ant_th4t picoCTF f160980_34sy_t}   {1t_w4s

Como se observa es una flag desordenada, asi que la ordenaremos:



picoCTF{1t_w4snt_th4t_34sy_tbh_4r_af160980}

  

## NOTAS ADICIONALES

## REFERENCIAS