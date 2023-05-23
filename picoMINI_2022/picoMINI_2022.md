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

