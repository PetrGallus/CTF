# picoMINI 2022
## General Skills
### Codebook
1. Download given files and analyse them
    - python script making decoding
    - text file with a string
2. Run the script to decrypt the message
    - python3 code.py


> picoCTF{c0d3b00k_455157_d9aa2df2}

### convertme
1. Download given file and analyse it
    - python script converting between decimal <-> binary
2. Run the script
    - we are given a decimal value
    - provide input with correct convertion to binary
> picoCTF{4ll_y0ur_b4535_722f6b39}

### fixme
1. Download given file and analyse it
    - python script not working properly
2. Run the script
    - IndentationError: unexpected indent on line 20
3. Fix the script
    - error seems to be on line 20
        - tab :-)
        - move the print function to the beginning of the line (delete tab)
4. Run the script to obtain the flag
> picoCTF{1nd3nt1ty_cr1515_09ee727a}

### PW Crack 1
1. Download given files and analyse them
    - level1.flag.txt.enc seems to be encrypted flag we want to obtain
    - level1.py is a python script to decrypt the flag file
2. Look at the level1.py code
    - lines 18+19
        ```
        if( user_pw == "1e1a"):
            print("Welcome back... your flag, user:")
        ```
3. Run the script and enter '1e1a' as a password to obtain the flag
> picoCTF{545h_r1ng1ng_fa343060}

### PW Crack 2
1.  Download given files and analyse them
    - level2.flag.txt.enc seems to be encrypted flag we want to obtain
    - level2.py is a python script to decrypt the flag file
2. Look at the level2.py code
    - lines 18+19
        ```
        if( user_pw == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36) ):
            print("Welcome back... your flag, user:")
        ```
3. Get the correct password for the encrypted file
    - decode chars from hex using CyberChef
        - de76 == chr(0x64) + chr(0x65) + chr(0x37) + chr(0x36)

4. Run the script and enter 'de76' as a password to obtain the flag

> picoCTF{tr45h_51ng1ng_489dea9a}

### PW Crack 3
1. Connect to the server using given prompt
    ```
    nc saturn.picoctf.net 50561
    ```
    - we can see this result in the terminal
        - 'picoCTF{gl17ch_m3_n07_' + chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64) + '}'

2. Decode chars from hex using CyberChef
    - 9c42a45d == chr(0x39) + chr(0x63) + chr(0x34) + chr(0x32) + chr(0x61) + chr(0x34) + chr(0x35) + chr(0x64)
    
3. Get the whole flag string

> picoCTF{gl17ch_m3_n07_9c42a45d} 

### PW Crack 4


