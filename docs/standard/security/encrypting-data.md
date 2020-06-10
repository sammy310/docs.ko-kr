---
title: 데이터 암호화
description: .NET에서 데이터를 암호화 하는 방법을 알아봅니다. 스트림에서 대칭 암호화를 사용 하거나 작은 바이트의 비대칭 암호화를 사용할 수 있습니다.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET Framework], symmetric
- symmetric encryption
- cryptography [.NET Framework], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 6cebdecd461f28f8228ebb8440dbff218dc211db
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662526"
---
# <a name="encrypting-data"></a><span data-ttu-id="c8eab-104">데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="c8eab-104">Encrypting Data</span></span>
<span data-ttu-id="c8eab-105">대칭 암호화와 비대칭 암호화는 서로 다른 프로세스를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-105">Symmetric encryption and asymmetric encryption are performed using different processes.</span></span> <span data-ttu-id="c8eab-106">대칭 암호화는 스트림에서 수행되므로 많은 양의 데이터를 암호화하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-106">Symmetric encryption is performed on streams and is therefore useful to encrypt large amounts of data.</span></span> <span data-ttu-id="c8eab-107">비대칭 암호화는 적은 수의 바이트에서 수행되므로 적은 양의 데이터에만 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-107">Asymmetric encryption is performed on a small number of bytes and is therefore useful only for small amounts of data.</span></span>  
  
## <a name="symmetric-encryption"></a><span data-ttu-id="c8eab-108">대칭 암호화</span><span class="sxs-lookup"><span data-stu-id="c8eab-108">Symmetric Encryption</span></span>  
 <span data-ttu-id="c8eab-109">관리되는 대칭 암호화 클래스는 읽은 데이터를 스트림으로 암호화하는 <xref:System.Security.Cryptography.CryptoStream> 이라는 특수 스트림 클래스와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-109">The managed symmetric cryptography classes are used with a special stream class called a <xref:System.Security.Cryptography.CryptoStream> that encrypts data read into the stream.</span></span> <span data-ttu-id="c8eab-110">**CryptoStream** 클래스는 관리되는 스트림 클래스, 암호화 알고리즘을 구현하는 클래스에서 만든 <xref:System.Security.Cryptography.ICryptoTransform> () 인터페이스를 구현하는 클래스 및 <xref:System.Security.Cryptography.CryptoStreamMode> CryptoStream **에 허용되는 액세스 형식을 설명하는**열거형을 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-110">The **CryptoStream** class is initialized with a managed stream class, a class implements the <xref:System.Security.Cryptography.ICryptoTransform> interface (created from a class that implements a cryptographic algorithm), and a <xref:System.Security.Cryptography.CryptoStreamMode> enumeration that describes the type of access permitted to the **CryptoStream**.</span></span> <span data-ttu-id="c8eab-111">, 및를 포함 하 여 클래스에서 파생 된 클래스를 사용 하 여 **CryptoStream** 클래스를 초기화할 수 있습니다 <xref:System.IO.Stream> <xref:System.IO.FileStream> <xref:System.IO.MemoryStream> <xref:System.Net.Sockets.NetworkStream> .</span><span class="sxs-lookup"><span data-stu-id="c8eab-111">The **CryptoStream** class can be initialized using any class that derives from the <xref:System.IO.Stream> class, including <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>, and <xref:System.Net.Sockets.NetworkStream>.</span></span> <span data-ttu-id="c8eab-112">이러한 클래스를 사용하여 다양한 스트림 개체에 대해 대칭 암호화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-112">Using these classes, you can perform symmetric encryption on a variety of stream objects.</span></span>  
  
 <span data-ttu-id="c8eab-113">다음 예제에서는 Rijndael 암호화 알고리즘을 구현하는 <xref:System.Security.Cryptography.RijndaelManaged> 의 새 인스턴스를 만들고 **CryptoStream** 클래스에서 암호화를 수행하는 데 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-113">The following example illustrates how to create a new instance of the <xref:System.Security.Cryptography.RijndaelManaged> class, which implements the Rijndael encryption algorithm, and use it to perform encryption on a **CryptoStream** class.</span></span> <span data-ttu-id="c8eab-114">이 예제에서 **CryptoStream** 은 임의 형식의 관리되는 스트림일 수 있는 `myStream` 이라는 스트림 개체를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-114">In this example, the **CryptoStream** is initialized with a stream object called `myStream` that can be any type of managed stream.</span></span> <span data-ttu-id="c8eab-115">**RijndaelManaged** 클래스의 **CreateEncryptor** 메서드에는 암호화에 사용되는 키 및 IV가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-115">The **CreateEncryptor** method from the **RijndaelManaged** class is passed the key and IV that are used for encryption.</span></span> <span data-ttu-id="c8eab-116">이 경우 `rmCrypto` 에서 생성되는 기본 키 및 IV가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-116">In this case, the default key and IV generated from `rmCrypto` are used.</span></span> <span data-ttu-id="c8eab-117">끝으로, **CryptoStreamMode.Write** 가 전달되어 스트림에 대한 쓰기 권한을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-117">Finally, the **CryptoStreamMode.Write** is passed, specifying write access to the stream.</span></span>  
  
```vb  
Dim rmCrypto As New RijndaelManaged()  
Dim cryptStream As New CryptoStream(myStream, rmCrypto.CreateEncryptor(rmCrypto.Key, rmCrypto.IV), CryptoStreamMode.Write)  
```  
  
```csharp  
RijndaelManaged rmCrypto = new RijndaelManaged();  
CryptoStream cryptStream = new CryptoStream(myStream, rmCrypto.CreateEncryptor(), CryptoStreamMode.Write);  
```  
  
 <span data-ttu-id="c8eab-118">이 코드를 실행하면 **CryptoStream** 개체에 기록된 모든 데이터가 Rijndael 알고리즘을 사용하여 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-118">After this code is executed, any data written to the **CryptoStream** object is encrypted using the Rijndael algorithm.</span></span>  
  
 <span data-ttu-id="c8eab-119">다음 예제에서는 스트림을 만들고, 스트림을 암호화하고, 스트림에 쓰고, 스트림을 닫는 전체 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-119">The following example shows the entire process of creating a stream, encrypting the stream, writing to the stream, and closing the stream.</span></span> <span data-ttu-id="c8eab-120">이 예제에서는 **CryptoStream** 클래스 및 **RijndaelManaged** 클래스를 사용하여 암호화된 네트워크 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-120">This example creates a network stream that is encrypted using the **CryptoStream** class and the **RijndaelManaged** class.</span></span> <span data-ttu-id="c8eab-121"><xref:System.IO.StreamWriter> 클래스를 사용하여 암호화된 스트림에 메시지가 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-121">A message is written to the encrypted stream with the <xref:System.IO.StreamWriter> class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c8eab-122">이 예제를 사용하여 파일에 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-122">You can also use this example to write to a file.</span></span> <span data-ttu-id="c8eab-123">이렇게 하려면 <xref:System.Net.Sockets.TcpClient> 참조를 삭제하고 <xref:System.Net.Sockets.NetworkStream> 을 <xref:System.IO.FileStream>으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-123">To do that, delete the <xref:System.Net.Sockets.TcpClient> reference and replace the <xref:System.Net.Sockets.NetworkStream> with a <xref:System.IO.FileStream>.</span></span>  
  
```vb  
Imports System  
Imports System.IO  
Imports System.Security.Cryptography  
Imports System.Net.Sockets  
  
Module Module1  
Sub Main()  
   Try  
      'Create a TCP connection to a listening TCP process.  
      'Use "localhost" to specify the current computer or  
      'replace "localhost" with the IP address of the
      'listening process.
      Dim tcp As New TcpClient("localhost", 11000)  
  
      'Create a network stream from the TCP connection.
      Dim netStream As NetworkStream = tcp.GetStream()  
  
      'Create a new instance of the RijndaelManaged class  
      'and encrypt the stream.  
      Dim rmCrypto As New RijndaelManaged()  
  
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}  
  
      'Create a CryptoStream, pass it the NetworkStream, and encrypt
      'it with the Rijndael class.  
      Dim cryptStream As New CryptoStream(netStream, rmCrypto.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
  
      'Create a StreamWriter for easy writing to the
      'network stream.  
      Dim sWriter As New StreamWriter(cryptStream)  
  
      'Write to the stream.  
      sWriter.WriteLine("Hello World!")  
  
      'Inform the user that the message was written  
      'to the stream.  
      Console.WriteLine("The message was sent.")  
  
      'Close all the connections.  
      sWriter.Close()  
      cryptStream.Close()  
      netStream.Close()  
      tcp.Close()  
   Catch  
      'Inform the user that an exception was raised.  
      Console.WriteLine("The connection failed.")  
   End Try  
End Sub  
End Module  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Security.Cryptography;  
using System.Net.Sockets;  
  
public class main  
{  
   public static void Main(string[] args)  
   {  
      try  
      {  
         //Create a TCP connection to a listening TCP process.  
         //Use "localhost" to specify the current computer or  
         //replace "localhost" with the IP address of the
         //listening process.
         TcpClient tcp = new TcpClient("localhost",11000);  
  
         //Create a network stream from the TCP connection.
         NetworkStream netStream = tcp.GetStream();  
  
         //Create a new instance of the RijndaelManaged class  
         // and encrypt the stream.  
         RijndaelManaged rmCrypto = new RijndaelManaged();  
  
         byte[] key = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
         byte[] iv = {0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16};  
  
         //Create a CryptoStream, pass it the NetworkStream, and encrypt
         //it with the Rijndael class.  
         CryptoStream cryptStream = new CryptoStream(netStream,
         rmCrypto.CreateEncryptor(key, iv),
         CryptoStreamMode.Write);  
  
         //Create a StreamWriter for easy writing to the
         //network stream.  
         StreamWriter sWriter = new StreamWriter(cryptStream);  
  
         //Write to the stream.  
         sWriter.WriteLine("Hello World!");  
  
         //Inform the user that the message was written  
         //to the stream.  
         Console.WriteLine("The message was sent.");  
  
         //Close all the connections.  
         sWriter.Close();  
         cryptStream.Close();  
         netStream.Close();  
         tcp.Close();  
      }  
      catch  
      {  
         //Inform the user that an exception was raised.  
         Console.WriteLine("The connection failed.");  
      }  
   }  
}  
```  
  
 <span data-ttu-id="c8eab-124">이전 예제가 성공적으로 실행되려면 <xref:System.Net.Sockets.TcpClient> 클래스에 지정된 IP 주소 및 포트 번호에서 수신 대기하는 프로세스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-124">For the previous example to execute successfully, there must be a process listening on the IP address and port number specified in the <xref:System.Net.Sockets.TcpClient> class.</span></span> <span data-ttu-id="c8eab-125">수신 대기 프로세스가 있는 경우 코드가 수신 대기 프로세스에 연결하고, Rijndael 대칭 알고리즘을 사용하여 스트림을 암호화하며, 스트림에 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="c8eab-125">If a listening process exists, the code will connect to the listening process, encrypt the stream using the Rijndael symmetric algorithm, and write "Hello World!"</span></span> <span data-ttu-id="c8eab-126">씁니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-126">to the stream.</span></span> <span data-ttu-id="c8eab-127">코드가 성공하면 콘솔에 다음 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-127">If the code is successful, it displays the following text to the console:</span></span>  
  
```console  
The message was sent.  
```  
  
 <span data-ttu-id="c8eab-128">그러나 수신 대기 프로세스가 없거나 예외가 발생하는 경우 코드가 콘솔에 다음 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-128">However, if no listening process is found or an exception is raised, the code displays the following text to the console:</span></span>  
  
```console  
The connection failed.  
```  
  
## <a name="asymmetric-encryption"></a><span data-ttu-id="c8eab-129">비대칭 암호화</span><span class="sxs-lookup"><span data-stu-id="c8eab-129">Asymmetric Encryption</span></span>  
 <span data-ttu-id="c8eab-130">비대칭 알고리즘은 일반적으로 대칭 키 및 IV의 암호화와 같은 적은 양의 데이터를 암호화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-130">Asymmetric algorithms are usually used to encrypt small amounts of data such as the encryption of a symmetric key and IV.</span></span> <span data-ttu-id="c8eab-131">일반적으로 비대칭 암호화를 수행하는 개인은 다른 당사자가 생성한 공개 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-131">Typically, an individual performing asymmetric encryption uses the public key generated by another party.</span></span> <span data-ttu-id="c8eab-132"><xref:System.Security.Cryptography.RSACryptoServiceProvider> 클래스는 이 목적을 위해 .NET Framework에서 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-132">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is provided by the .NET Framework for this purpose.</span></span>  
  
 <span data-ttu-id="c8eab-133">다음 예제에서는 공개 키 정보를 사용하여 대칭 키 및 IV를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-133">The following example uses public key information to encrypt a symmetric key and IV.</span></span> <span data-ttu-id="c8eab-134">타사의 공개 키를 나타내는 2바이트 배열이 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-134">Two byte arrays are initialized that represent the public key of a third party.</span></span> <span data-ttu-id="c8eab-135"><xref:System.Security.Cryptography.RSAParameters> 개체는 이러한 값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-135">An <xref:System.Security.Cryptography.RSAParameters> object is initialized to these values.</span></span> <span data-ttu-id="c8eab-136">다음에는 **메서드를 사용하여** RSAParameters **개체(이 개체가 나타내는 공개 키 포함)를** RSACryptoServiceProvider <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> 로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-136">Next, the **RSAParameters** object (along with the public key it represents) is imported into an **RSACryptoServiceProvider** using the <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="c8eab-137">끝으로, <xref:System.Security.Cryptography.RijndaelManaged> 클래스에서 만든 프라이빗 키 및 IV가 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-137">Finally, the private key and IV created by a <xref:System.Security.Cryptography.RijndaelManaged> class are encrypted.</span></span> <span data-ttu-id="c8eab-138">이 예제에서는 시스템에 128비트 암호화가 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8eab-138">This example requires systems to have 128-bit encryption installed.</span></span>  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
  
    Sub Main()  
        'Initialize the byte arrays to the public key information.  
      Dim publicKey As Byte() =  {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19,202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}  
  
        Dim exponent As Byte() = {1, 0, 1}  
  
        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte  
        Dim encryptedSymmetricIV() As Byte  
  
        'Create a new instance of the RSACryptoServiceProvider class.  
        Dim rsa As New RSACryptoServiceProvider()  
  
        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()  
  
        'Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = publicKey  
        rsaKeyInfo.Exponent = exponent  
  
        'Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo)  
  
        'Create a new instance of the RijndaelManaged class.  
        Dim RM As New RijndaelManaged()  
  
        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(RM.Key, False)  
        encryptedSymmetricIV = rsa.Encrypt(RM.IV, False)  
    End Sub  
  
End Module  
```  
  
```csharp  
using System;  
using System.Security.Cryptography;  
  
class Class1  
{  
   static void Main()  
   {  
      //Initialize the byte arrays to the public key information.  
      byte[] publicKey = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,  
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,  
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,  
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,  
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,  
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,  
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,  
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};  
  
      byte[] exponent = {1,0,1};  
  
      //Create values to store encrypted symmetric keys.  
      byte[] encryptedSymmetricKey;  
      byte[] encryptedSymmetricIV;  
  
      //Create a new instance of the RSACryptoServiceProvider class.  
      RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
  
      //Create a new instance of the RSAParameters structure.  
      RSAParameters rsaKeyInfo = new RSAParameters();  
  
      //Set rsaKeyInfo to the public key values.
      rsaKeyInfo.Modulus = publicKey;  
      rsaKeyInfo.Exponent = exponent;  
  
      //Import key parameters into RSA.  
      rsa.ImportParameters(rsaKeyInfo);  
  
      //Create a new instance of the RijndaelManaged class.  
      RijndaelManaged rm = new RijndaelManaged();  
  
      //Encrypt the symmetric key and IV.  
      encryptedSymmetricKey = rsa.Encrypt(rm.Key, false);  
      encryptedSymmetricIV = rsa.Encrypt(rm.IV, false);  
   }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8eab-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8eab-139">See also</span></span>

- [<span data-ttu-id="c8eab-140">암호화 및 해독용 키 생성</span><span class="sxs-lookup"><span data-stu-id="c8eab-140">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="c8eab-141">데이터 해독</span><span class="sxs-lookup"><span data-stu-id="c8eab-141">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="c8eab-142">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="c8eab-142">Cryptographic Services</span></span>](cryptographic-services.md)
