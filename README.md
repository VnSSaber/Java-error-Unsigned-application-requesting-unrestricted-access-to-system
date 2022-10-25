Created by Vns Saber - TCX

Fix Java error : Unsigned application requesting unrestricted access to system.

Issue : 
Can't use McAfee WebGateway Java-Webstart after update Java Version 8 Update 351.

Can be fixed temporary with :
- C:\Program Files (x86)\Java\jre***\lib\security\java.security
- Added a hash # in front of the line : "jdk.jar.disabledAlgorithms=MD2, MD5, RSA keySize < 1024"
- After fixed, can't access to Cisco ASDM.

Root cause :
Java Version 8 Update 351 have disabled SHA-1 JARs signed after 2019-01-01.

Extention .jnpl file consider as SHA-1 JARs

Change log : https://www.java.com/en/jre-jdk-cryptoroadmap.html#releasedChangesTable

Fixed permanently :
- C:\Program Files (x86)\Java\jre***\lib\security\java.security
- Delete "SHA1 usage SignedJAR & denyAfter 2019-01-01" or "SHA1 denyAfter 2019-01-01"
- After fixed, access to Cisco ASDM and McAfee WebGateway Java-Webstart normally.

Reference link : https://www.java.com/en/configure_crypto.html#DisableSHA1SignedJars
