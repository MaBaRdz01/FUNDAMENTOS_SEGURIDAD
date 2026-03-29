## RETO
MY GIT
## DESCRIPCION
I have built my own Git server with my own rules! You can clone the challenge repo using the command below. git clone ssh://git@foggy-cliff.picoctf.net:51177/git/challenge.git Here's the password: e38a0906 Check the README to get your flag!

## SOLUCION
**`picoCTF{1mp3rs0n4t4_g17_345y_02a39618}`**



git clone ssh://git@foggy-cliff.picoctf.net:51177/git/challenge.git  
cd challenge

git config user.name "root"  
git config user.email "root@picoctf"

echo "peticion de flag" > flag.txt

git add flag.txt  
git commit -m "Give me the flag"

git push origin master



**`picoCTF{1mp3rs0n4t4_g17_345y_02a39618}`**

- -----------------------------------------------------------------------

bytemancy 0

Description

Can you conjure the right bytes? The program's source code can be downloaded here. Connect to the program with netcat: $ nc candy-mountain.picoctf.net 52057

Solución

picoCTF{pr1n74813_ch4r5_2f7a75e5}

- @antho  nc candy-mountain.picoctf.net 52057  
    ⊹──────[ BYTEMANCY-0 ]──────⊹  
    ☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐  
    <br/>Send me ASCII DECIMAL 101, 101, 101, side-by-side, no space.  
    <br/>☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐☉⟊☽☈⟁⧋⟡☍⟐  
    ⊹─────────────⟡─────────────⊹  
    ==> eee  
    picoCTF{pr1n74813_ch4r5_2f7a75e5}  
    ^C  
    (base)    
    ✘  mié 18 mar - 21:29  ~   
    @antho     


## NOTAS ADICIONALES

## REFERENCIAS