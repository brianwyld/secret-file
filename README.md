# secret-file
browser only web page based text file encryption/decryption utility

This is a single html file, containing the neccessary javascript to load/decrypt or encrypt/save whatever text is loaded in the textbox.

The encryption is AES256, using a AES key derived from the user's name and passphrase entered in the form.

The encrypted output (as a base64 string) can be stored in:
 - browser localStorage (url : "ls://<key>")
 - local file system file (url : "file:" and a file chooser dialog will open)
 - directly in the url as data (url "data:<base64 string>" - this is useful on a mobile device for example)
 
Future versions may provide for storage on
 - remoteStorage
 - google drive file
 - generic web server via GET/PUT operations
 - bluetooth file share device (maybe...)
 - ftp server
 
As only the encrypted data is ever stored, no security implcations are expected from the storage mechanism.

The non-encrypted data only ever exists in the JS/DOM of the web page.

 Acknowledgements (full attributtion notices in the html file)
 - AES implementation from the SlowAES project : http://code.google.com/p/slowaes/
 - PBKDF2 implementation from http://anandam.com/pbkdf2 (modified to be syncrhonous api call)
 - SHA1 implementation frm http://pajhome.org.uk/crypt/md5/sha1.html
 
Thsnks guys!
