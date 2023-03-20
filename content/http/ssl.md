# 优化SSL层

## 使用ecc算法

ECC(Elliptic curve cryptography), 意为椭圆曲线密码编码学，和RSA算法一样，ECC算法也属于公开密钥算法。最初由Koblitz和Miller两人于1985年提出，其数学基础是利用椭圆曲线上的有理点构成Abel加法群上椭圆离散对数的计算困难性。


ECC算法的数学理论非常深奥和复杂，在工程应用中比较难于实现，但它的单位安全强度相对较高，它的破译或求解难度基本上是指数级的，黑客很难用通常使用的暴力破解的方法来破解。RSA算法的特点之一是数学原理相对简单，在工程应用中比较易于实现，但它的单位安全强度相对较低。因此，ECC算法的可以用较少的计算能力提供比RSA加密算法更高的安全强度，有效地解决了“提高安全强度必须增加密钥长度”的工程实现问题。


<div  align="center">
	<p>图：ECC vs RSA</p>
	<img src="../assets/chapter2/ecc.png" width = "350"  align=center />
</div>

ECC与RSA相比，拥有突出优势：
* 更适用于移动互联网， ECC加密算法的密钥长度很短，意味着占用更少的存储空间，更低的CPU开销和占用更少的带宽
* 更好的安全性,ECC加密算法提供更强的保护，比目前的其他加密算法能更好的防止攻击.
* 计算量小，处理速度更快，在私钥的处理速度上（解密和签名），ECC远比RSA、DSA快得多。

### 算法安全性比较

下表为ECC和RSA的安全性比较

攻破时间(MIPS年)|RSA/DSA密钥长度| ECC密钥长度|RSA/ECC密钥长度比
:---|:---|:---
104|512|106|5:1
108|768|132|6:1
1011|1024|160|7:1
1020|2048|210|10:1
1078|21000|600|35:1

### ECC证书兼容性

ECC在主流操作系统的兼容情况

操作系统|最低版本要求
:---|:--
Apple OS X|OS X 10.6
Microsoft Windows | Windows Vista
Red Hat Enterprise| 6.5
iOS| iOS7.x
Android OS|3.7
Microsoft Windows Phone | 7.x