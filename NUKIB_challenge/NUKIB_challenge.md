# NUKIB challenge

## Kód na stránce
1. `NDYgNGMgNDEgNDcgMmQgNTQgNGYgNDggNGMgNDUgMmQgNGEgNDUgMmQgNGEgNDUgNGUgMmQgNWEgNDEgNDMgNDEgNTQgNDUgNGI=`
2. CyberChef – from Base64, from HEX
3. echo <string> | base64 -d
    
> FLAG-TOHLE-JE-JEN-ZACATEK

## Neviditelné znaky na stránce
1. Ctrl+A a je vidět vlevo nahoře, nebo vyhledávání FLAG v kódu stránky Ctrl+Shift+I


> FLAG-PRISNE-TAJNE

## Prohledání  kódu stránky
Ctrl+Shift+I, Ctrl+F a najít flag
V komentáři je skryt flag

> FLAG-TAKY-LEHKE

## Script
Ve stránce je skript, Brave jej automaticky provede dole v konzoli. Některé prohlížeče  - musí se zkopírovat do konzole a spustit je, pak se provedou a zobrazí výsledek
    
> FLAG-OBFUSKACE

## PS obfuskace
1. Komentář v HTML: `KCgiezR9ezJ9ezV9ezZ9ezB9ezF9ezN9Ii1mJ1BTT0JGVVMnLCdDQVRFRF9GJywncicsJ0xBR30nLCdXJywnaXRlLScsJ2hvc3QgRkxBR3tUSElTX0lTXycpKSB8ICYoKGdWICcqTWRyKicpLk5BbUVbMywxMSwyXS1KT0luJycp`
2. CyberChef – from Base64
(("{4}{2}{5}{6}{0}{1}{3}"-f'PSOBFUS','CATED_F','r','LAG}','W','ite-','host FLAG{THIS_IS_')) | &((gV '*Mdr*').NAmE[3,11,2]-JOIn'')
3. Stačí takhle celé rovnou nakopírovat do powershellu a spustit. 

> FLAG THIS_IS_PSOBFUSCATED_FLAG

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

## Logo
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

## Logo2
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


## Adresní řetězec

1. Ještě jsem našla v zdroj kodu stránky tenhle řetězec, ale už nebyl čas něco zkoumat.
`\001F\008B\0008\0000\00AA\007C\0076\0061\0000\00FF\0005\0080\0041\0009\0000\0000\0008\0003\0013\0019\0042\0050\000F\00C1\00C7\00DE\00F6\000F\0032\00E6\0092\00E0\0057\00EA\0032\0005\006F\0075\00F3\000C\0000\0000\0000`
