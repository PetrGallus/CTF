## Forensics
### PcapPoisoning
>flag: picoCTF{P64P_4N4L7S1S_SU55355FUL_dd89e21b}

steps:
1. download given file && open in Wireshark
2. Analyze -> Conversations
    2a. 5 IPv4 conversations
    2b. Only one of them sends real data (bits) from A -> B
    2c. Right click on this conversation -> Apply as Filter -> Selected -> A<->B
3. Find the flag
### hideme
>flag: picoCTF{Hiddinng_An_imag3_within_@n_ima9e_5cf64968}
### who is it
>flag: picoCTF{WilhelmZwalina}
steps:
1. download given file && open terminal
2. strings email-export.eml
3. Find the original sender IP address on any of these 4 places
    3a. ARC-Authentication
    3b. Received
    3c. Received-SPF
    3d. Authentication-Results
4. whois 173.249.33.206
5. person: Wilhelm Zwalina
### FindAndOpen {WIP}
>flag: picoCTF{R34DING_LOKd_fil56_succ3ss_8ec01288}

steps:
1. download given zip + pcap files && open dump.pcap in Wireshark
2. search packets for hints: 
 + "Flying on Ethernet secret: Is this the flag",
 + "Could the flag have been splitted?"
 + base64 encoded "This is the Secret: "picoCTF{R34DING_LOKd_" (packet 48)
3. open the zip file /w string: picoCTF{R34DING_LOKd_ to get access to archive & to obtain the flag

### MSB
>flag: picoCTF{15_y0ur_que57_qu1x071c_0r_h3r01c_b5e03bc5}

steps:
- after banging our heads for 2 hours and figuring out why the seventh bit is interesting Zihuatanejo peeked onto Discord to find a hint from other users -> sigbits
- download sigbits.py
- open console and run the following:
    - python sigbits.py -t=msb -o=rgb -out=output.txt -e=column Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png 
- cat output.txt && search "ctf"
    - somehow grepping did not work for me, it displayed the whole content of the file
### Invisible WORDs
>flag: 

steps:
1. download given file && open terminal
2. Hint 2: "How's the image quality?"
    - foremost -i output.bmp
        - 1 MB Size, Resolution 960x540
    - binwalk, strings, zsteg ... nothng