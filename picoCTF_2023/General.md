## General
### money-ware
>flag: picotCTF{Petya}
### repetitions
>flag: picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_c0ac1752}
### Rules 2023
>flag: picoCTF{h34rd_und3r5700d_4ck_cba1c711}
### Permissions
>flag: picoCTF{uS1ng_v1m_3dit0r_021d10ab}

steps:
1. Run the instance and connect+login to the server
2. Search the server folder hierarchy
    - ls (nothing)
    - cd ..
        - cd ..
            - ls
                - we can see the ROOT folder
                    - we are not permitted to enter the folder
3. Hint 'What permissions do you have?'
    - whoami
    - id
    - sudo -l
        - 'User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi'
            - lets try that
4. VIM
    - https://gtfobins.github.io/

### chrono
>flag: picoCTF{Sch3DUL7NG_T45K3_L1NUX_7754e199}

Task is "How to automate tasks to run at intervals on linux servers?" - done with Cron, so the task is going to be to find crontab or related
steps:
 - start server & login via ssh
     - ssh picoplayer@saturn.picoctf.net -p55006
 - whoami, ls -la and the usual shenanigans
 - cd to /etc/ and cat crontab
 - BAM, got yo flag

### useless
>flag: picoCTF{us3l3ss_ch4ll3ng3_3xpl0it3d_5562}

steps:
1. start instance & login via ssh
    - ssh picoplayer@saturn.picoctf.net -p 65074
2. Explore folders and script
    - ls
        - cat useless
            - we have to read the script manual to obtain the flag
3. Obtain the flag
    - man useless

### Special
flag: 
The spell-checking shell blocks and/or corrects most of the shell commands so they're not able to execute, however the following cmds return a relevant value:
``whoami`` in double backticks or single quotes.
``awk`` is accepted as well
``grep`` is accepted as well
### Specialer
>flag: picoCTF{y0u_d0n7_4ppr3c1473_wh47_w3r3_d01ng_h3r3_38f5cc78}

Ugh, finally did it.
1. ssh in
2. notice that tabbing (hitting the TAB on keyboard) displays autocomplete, ~ls, but cat isn't allowed
3. `bla=$(<ala/kazam.txt) && echo $bla` to store and then read the file content