**ช็คเวอร์ชั่น**

`gpg --version`

ปกติ gpg จะ install ใน linux อยู่แล้ว กรณีไม่มี **install** ได้ดังนี้ 

# ubuntu / debian

`apt install gnupg`


**เช็ค public key**

`gpg --list-keys`

**เช็ค private key**

`gpg --list-secret-keys`


**Create a new key pair**

`gpg --gen-key` (key จะมีอายุ 2 ปี)cle

`gpg --full-generate-key` (กรณีต้องการ key ไม่มีวันหมดอายุ)


**การลบ public key (ถ้ามี private key ต้อง ลบ private key ก่อน)**

`gpg --delete-key <email>`

**การลบ private key**

`gpg --delete-secret-key <email>`

**การ export public key**

`gpg --export --armor <email> > ><name>.asc`

**การ export private key**

`gpg --output <name>.asc --armor --export-secret-key <email>`

**การ import public key**

`gpg --import <public key path>`

**การ import private key**

`gpg --import <private key path>`


**encrypt-decrypt Asymmetric (encrypt public key and decrypt private key )**

**การ encrypt**

`gpg --yes --trust-model always --output <filename>.gpg --encrypt --armor --recipient '<email>' <filename>`

**การ decrypt**

`gpg -d <encrypt file> > <decrypt file name>`


**encrypt-decrypt Symmetric (encrypt public key and decrypt public key )**

**การ encrypt (must use passphrase)**

`gpg -yes --trust-model always --output <filename>.enc -c  --armor --recipient '<email>' <filename>`

**การ decrypt**

`gpg -d <filename>.enc > <decrypt file name>`