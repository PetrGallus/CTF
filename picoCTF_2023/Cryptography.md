## Cryptography
### rotation
>flag: picoCTF{r0tat1on_d3crypt3d_7ecd1c61}

steps:
1. https://www.dcode.fr/rot-cipher
2. input roted text: xqkwKBN{z0bib1wv_l3kzgxb3l_7mkl1k61}
3. Decrypt
4. search page for string "picoCTF"
### ReadMyCert
>flag: picoCTF{read_mycert_7834c5f2}

steps:
1. download given file && open terminal
2. cat readmycert.csr
3. copy the certificate request (base64 long string)
4. https://gchq.github.io/CyberChef/
5. recipe: From Base64


### HideToSee
>flag: picoCTF{atbash_crack_7142fde9}

steps:
1. download given file
2. binwalk, strings, zsteg...no output, only picture
3. stegseek tool
    - stegseek atbash.jpg /usr/share/wordlists/rockyou.txt
    - cat atbash.jpg.out
        - krxlXGU{zgyzhs_xizxp_4v847zx1}
            - decode it using atbash cipher (https://www.dcode.fr/atbash-cipher)