# NUKIB challenge
https://nukib.github.io/salina.html


## 1 Kód na stránce
1. `NDYgNGMgNDEgNDcgMmQgNTQgNGYgNDggNGMgNDUgMmQgNGEgNDUgMmQgNGEgNDUgNGUgMmQgNWEgNDEgNDMgNDEgNTQgNDUgNGI=`
2. CyberChef – from Base64, from HEX
3. echo <string> | base64 -d
    
> FLAG-TOHLE-JE-JEN-ZACATEK

## 2 Neviditelné znaky na stránce
1. Ctrl+A a je vidět vlevo nahoře, nebo vyhledávání FLAG v kódu stránky Ctrl+Shift+I

> FLAG-PRISNE-TAJNE

## 3 Prohledání kódu stránky
Ctrl+Shift+I, Ctrl+F a najít flag
V komentáři je skryt flag

> FLAG-TAKY-LEHKE

## 4 Prohledání kódu stránky 2
1. F12 - Style Editor - @font-face
    `fKFkRkzXRJqcHSLAj5EDoaW.woff2`
2. CyberChef - `fKFkRkzXRJqcHSLAj5EDoaW` -> from Base58

> FLAG-ZNAS-BASE58?

## 5 Menší text na konci
1. V dolní části webu je text menším písmem o právech a povinnostech
2. Flag je napsán přímo v něm

> Flag-hledame-i-pravniky

## 6 Verze stránky
1. v patičce webu je řetězec ```Verze: 464c4147-2d4e-454e-4954-4f2d55554944```
2. CyberChef - From Hex

> FLAG-NENITO-UUID

## 7 Script
Ve stránce je skript, Brave jej automaticky provede dole v konzoli. Některé prohlížeče  - musí se zkopírovat do konzole a spustit je, pak se provedou a zobrazí výsledek

> FLAG-OBFUSKACE

## 8 PS obfuskace
1. Komentář v HTML: `KCgiezR9ezJ9ezV9ezZ9ezB9ezF9ezN9Ii1mJ1BTT0JGVVMnLCdDQVRFRF9GJywncicsJ0xBR30nLCdXJywnaXRlLScsJ2hvc3QgRkxBR3tUSElTX0lTXycpKSB8ICYoKGdWICcqTWRyKicpLk5BbUVbMywxMSwyXS1KT0luJycp`
2. CyberChef – from Base64
(("{4}{2}{5}{6}{0}{1}{3}"-f'PSOBFUS','CATED_F','r','LAG}','W','ite-','host FLAG{THIS_IS_')) | &((gV '*Mdr*').NAmE[3,11,2]-JOIn'')
3. Stačí takhle celé rovnou nakopírovat do powershellu a spustit. 

> FLAG{THIS_IS_PSOBFUSCATED_FLAG}

> Jedná se jen o zpřeházení řetězců podle pořadí v závorkách, takže lze i ručně,
> 0 je PSOBFUS
> 1 je CATED_F
> 2 je r
> 3 je LAG
> 4 je W
> 5 je ite-
> 6 je host FLAG{THIS_IS_
> Seskládám podle "{4}{2}{5}{6}{0}{1}{3}"
> Write-host FLAG{THIS_IS_PSOBFUSCATED_FLAG}
> Po provedení příkazu v shelllu Write-host FLAG{THIS_IS_PSOBFUSCATED_FLAG} je výsledek stejný

## 9 Logo
1. Logo-kariera2.png metadata
2. Obrázkem najedu na ikonu programu exiftool.exe a pokud je název ve tvaru exiftool(-a -u -g1 -w txt).exe, tak mi nalezená metadata uloží do .txt se stejným názvem, jako je prověřovaný soubor.
3. V linuxu je příkaz
```
$ Strings ./logo-kariera2.png
$ Strings ./logo-kariera2.png > strings.txt (výpis nezobrazí ale uloží do souboru string.txt)
```
4. Mezi metadaty je string `RkxBRy1IZXNsby1rLWFyY2hpdnUtamUtVGFrVHJvY2h1SmluYVN0YXRuaVNwcmF2YQ==`
5. CyberChef, from Base64

>FLAG-Heslo-k-archivu-je-TakTrochuJinaStatniSprava

## 10 Logo2
1. Logo-kariera2.png. vnořený zaheslovaný zip
2. Příkaz v linuxu pro prověření obsahu souboru 
    `$ binwalk ./logo-kariera2.png` a pak uvidíme, že je tam .zip a v něm je soubor flag.txt
```
DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0                PNG image, 300 x 300, 8-bit/color RGBA, non-interlaced
54            0x36            Zlib compressed data, compressed
40597         0x9E95    TIFF image data, big-endian, offset of first image directory: 8
40773         0x9F45    Zip archive data, encrypted at least v2.0 to extract, compressed size: 55, uncompressed size: 43, name: FLAG.txt
40956         0x9FFC      End of Zip archive, footer length: 22
```

3. Příkazem `$ binwalk –e ./logo-kariera2.png` extrahujeme všechny soubory do složky s názvem prověřovaného souboru. Ve složce otevřu .zip a při pokusu o otevření souboru flag.txt se objeví heslo. Tam zadám to z metadat (TakTrochuJinaStatniSprava) a v texťáku je flag
    
> FLAG-Posli-zivotopis-na-analyticke-oddeleni

## 11 Mini-ikona stránky
Obsah faviconu loga na stránce
1. F12 - Network -  favicon.png
2. Stahnout "favicon.png"
3. `strings favicon.png` nebo `xxd favicon.png`

> FLAG-FAVICON

## 12 Odkaz na pozici analytika
1. `Analytik síťového provozu – budeš vyšetřovat útoky a hledat škodlivé aktivity v síťových záznamech.`
2. Odkay na pozici -> https://www.nukib.cz/cs/o-nukib/kariera/analytik-sitoveho-provozu/?ex=RkxBRy1leGZpbHRyYWNlLWRhdC1qZS1tb3puYS1pLXByZXMtZ2V0LXBhcmFtZXRyLW5hcHJpa2xhZC12LW9ka2F6dS0temt1cy1wcmFjaS12LU9BU1Ah
3. CyberChef: From Base64 `RkxBRy1leGZpbHRyYWNlLWRhdC1qZS1tb3puYS1pLXByZXMtZ2V0LXBhcmFtZXRyLW5hcHJpa2xhZC12LW9ka2F6dS0temt1cy1wcmFjaS12LU9BU1Ah`

> FLAG-exfiltrace-dat-je-mozna-i-pres-get-parametr-napriklad-v-odkazu--zkus-praci-v-OASP!

## 13 Adresní řetězec

1. Zdroj kod stránky: 
`\001F\008B\0008\0000\00AA\007C\0076\0061\0000\00FF\0005\0080\0041\0009\0000\0000\0008\0003\0013\0019\0042\0050\000F\00C1\00C7\00DE\00F6\000F\0032\00E6\0092\00E0\0057\00EA\0032\0005\006F\0075\00F3\000C\0000\0000\0000`
2. Prevedeni do hex formatu 
`0x1F 0x8B 0x08 0x00 0xAA 0x7C 0x76 0x61 0x00 0xFF 0x05 0x80 0x41 0x09 0x00 0x00 0x08 0x03 0x13 0x19 0x42 0x50 0x0F 0xC1 0xC7 0xDE 0xF6 0x0F 0x32 0xE6 0x92 0xE0 0x57 0xEA 0x32 0x05 0x6F 0x75 0xF3 0x0C 0x00 0x00 0x00`
3. CyberChef: From hex + Gunzip

> FLAG-GZIPPED

## 14 PGP signature
1. na web je nahraná složka .well-known, jejíž obsahem je soubor "security.txt" (https://github.com/NUKIB/nukib.github.io/blob/master/.well-known/security.txt)
2. PGP podpis obsahuje flag
```-----BEGIN PGP SIGNED MESSAGE-----
Hash: SHA1
Contact: mailto:cert@nukib.cz
Encryption: https://www.nukib.cz/download/kontakty/cert_pub.asc
Hiring: https://kariera.nukib.cz
Preferred-Languages: cs, en
-----BEGIN PGP SIGNATURE-----
Version: GnuPG v1.4.6 (MingW32)
aW1wb3J0IGJhc2U2NAoKZGVmIGhleF90b19iYXNlNjQoZGF0YTogc3RyKSAtPiBzdHI6CglyYWlz
ZSBOb3RJbXBsZW1lbnRlZEVycm9yCgpkZWYgYmFzZTY0X3RvX3N0cmluZyhkYXRhOiBzdHIpIC0+
IHN0cjoKCXJhaXNlIE5vdEltcGxlbWVudGVkRXJyb3IKCmZsYWdfZW5jb2RlZCA9ICc1MjZiNzg0
MjUyMzM3NDRmNTY1NTc0NGE1MTY5MzE1MTU1NmI0NjQ0NTI1MzMwNzc0ZDQ0NjQzOScKCg==
-----END PGP SIGNATURE-----
```
3. Dekódování řetězce pomocí Base64 -> flag_encoded = '526b78425233744f5655744a51693151556b4644525330774d446439'
```aW1wb3J0IGJhc2U2NAoKZGVmIGhleF90b19iYXNlNjQoZGF0YTogc3RyKSAtPiBzdHI6CglyYWlz
ZSBOb3RJbXBsZW1lbnRlZEVycm9yCgpkZWYgYmFzZTY0X3RvX3N0cmluZyhkYXRhOiBzdHIpIC0+
IHN0cjoKCXJhaXNlIE5vdEltcGxlbWVudGVkRXJyb3IKCmZsYWdfZW5jb2RlZCA9ICc1MjZiNzg0
MjUyMzM3NDRmNTY1NTc0NGE1MTY5MzE1MTU1NmI0NjQ0NTI1MzMwNzc0ZDQ0NjQzOScKCg==
```
4. Dekódování řetězce From Hex a From base64
```526b78425233744f5655744a51693151556b4644525330774d446439``` 

> FLAG{NUKIB-PRACE-007}
