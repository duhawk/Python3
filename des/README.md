# Python 3.* -> DES
```
类初始化
--------------------
pyDes.des（key，[mode]，[IV]，[pad]，[padmode]）
pyDes.triple_des（key，[mode]，[IV]，[pad]，[padmode]）

key->包含加密密钥的字节。DES 8字节，16或24字节
	   用于三重DES
mode->加密类型的可选参数，可以是
	   pyDes.ECB（电子密码簿）或pyDes.CBC（密码块链接）
	   如果使用CBC模式，则必须提供IV->可选的初始值字节。
	   长度必须为8个字节。
pad->可选参数，设置填充字符（PAD_NORMAL）以在
	   使用此实例完成的所有加密/解密操作。
padmode->可选参数，设置填充模式（PAD_NORMAL或PAD_PKCS5）
	   在对此实例执行的所有加密/解密操作期间使用。

我建议使用PAD_PKCS5填充，因为这样您就不必担心任何
填充问题，因为在解密时可以明确删除填充
使用PAD_PKCS5填充模式加密的数据。

常用方法
--------------
加密（数据，[pad]，[padmode]）
解密（数据，[pad]，[padmode]）

数据->要加密/解密的字节

pad->可选参数。仅在使用PAD_NORMAL的padmode时。对于
	   加密，则在以下情况下将此字符添加到数据块的末尾
	   数据不是8个字节的倍数。对于解密，将删除
	   最后8个与此填充字符匹配的结尾字符
	   未加密数据块的字节。
padmode->可选参数，设置填充模式，必须为PAD_NORMAL之一
	   或PAD_PKCS5）。默认为PAD_NORMAL。
```
