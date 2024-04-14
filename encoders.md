### Encoders - 

Resource - ```https://www.scriptjunkie.us/2011/04/why-encoding-does-not-matter-and-how-metasploit-generates-exes```

Info - msfencode was replaced by msfvenom in 18 July 2015 so to encode use msfvenom -e and it should encode.

### Exe Generation with no Payload
``` echo -n | msfvenom -a x86 --platform Windows -e generic/none -f exe > myn.exe ```

### Example for Virus Total test with generic none encoding.
``` root@cloud1:/opt/sqlmap# echo -n | msfvenom -a x86 --platform Windows -e generic/none -f exe > myn.exe
Attempting to read payload from STDIN...
Found 1 compatible encoders
Attempting to encode payload with 1 iterations of generic/none
generic/none succeeded with size 0 (iteration=0)
generic/none chosen with final size 0
Payload size: 0 bytes
Final size of exe file: 73802 bytes
```
### Check file encoded 

```ls -ls myn.exe && file myn.exe```

```76 -rw-r--r-- 1 root root 73802 Apr 13 23:15 myn.exe```

```myn.exe: PE32 executable (GUI) Intel 80386, for MS Windows```