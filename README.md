# secret-file : description
browser only web page based text file encryption/decryption utility

This is a single html file, containing the neccessary javascript to load/decrypt or encrypt/save whatever text is loaded in the textbox.

# operation
To use it, just open the html file in a browser (tested using chrome on Windows and Android). Enter a user name and passphrase (minimal size cis checked, but whatever you want), and the text to store in the textbox. Select a storage method using the url (see below for options) and hit the save button!

To load:decrypt, enter the correct user/passphrase and url to select the encrypted data source, and hit the load button. Its that simple....

If the user/passphrase are not corect for the encrypted data, then a popup will tell you...

# How it works
The encryption is AES256, using a AES key derived from the user's name and passphrase entered in the form. Before encrypting the text, a header line is added with the user, date, and a SHA1 hash of the text. This header line is used in the load/decrypt operation to check that the correct passphrase/user as obviously the decryption result is unlikely to have a valid header line.... (it also validates that no alteration or corruption has occured during the encryption/decryption) 

As only the encrypted data is ever stored outside of the form, no security implcations are expected from the storage mechanism.
The non-encrypted data only ever exists in the JS/DOM of the web page.

# Storage of the encrypted data
The encrypted output (as a base64 string) can be stored in:
 - browser localStorage (url : "ls://<key>")
 - local file system file (url : "file:" and a file chooser dialog will open)
 - directly in the url as data (url "data:<base64 string>" - this is useful on a mobile device for example as can be a copy from a drive file or an email)
 
Future versions may provide for storage on
 - remoteStorage (a server based version of localStorage)
 - google drive file
 - generic web server via GET/PUT operations
 - bluetooth file share device (maybe...)
 - ftp server
 

 Acknowledgements (full attributtion notices in the html file)
 - AES implementation from the SlowAES project : http://code.google.com/p/slowaes/
 - PBKDF2 implementation from http://anandam.com/pbkdf2 (modified to be syncrhonous api call)
 - SHA1 implementation frm http://pajhome.org.uk/crypt/md5/sha1.html
 
Thsnks guys!
