---
title: 데이터 암호화
description: 대칭 알고리즘 또는 비대칭 알고리즘을 사용 하 여 .NET에서 데이터를 암호화 하는 방법에 대해 알아봅니다.
ms.date: 07/14/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encryption [.NET], symmetric
- symmetric encryption
- cryptography [.NET], asymmetric
- asymmetric encryption
ms.assetid: 7ecce51f-db5f-4bd4-9321-cceb6fcb2a77
ms.openlocfilehash: 75bb0fa52b8002efe0027f026de8c0910735e55e
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440974"
---
# <a name="encrypting-data"></a><span data-ttu-id="7e303-103">데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="7e303-103">Encrypting Data</span></span>

<span data-ttu-id="7e303-104">대칭 암호화와 비대칭 암호화는 서로 다른 프로세스를 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-104">Symmetric encryption and asymmetric encryption are performed using different processes.</span></span> <span data-ttu-id="7e303-105">대칭 암호화는 스트림에서 수행되므로 많은 양의 데이터를 암호화하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-105">Symmetric encryption is performed on streams and is therefore useful to encrypt large amounts of data.</span></span> <span data-ttu-id="7e303-106">비대칭 암호화는 적은 수의 바이트에서 수행되므로 적은 양의 데이터에만 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-106">Asymmetric encryption is performed on a small number of bytes and is therefore useful only for small amounts of data.</span></span>  
  
## <a name="symmetric-encryption"></a><span data-ttu-id="7e303-107">대칭 암호화</span><span class="sxs-lookup"><span data-stu-id="7e303-107">Symmetric Encryption</span></span>  

<span data-ttu-id="7e303-108">관리되는 대칭 암호화 클래스는 읽은 데이터를 스트림으로 암호화하는 <xref:System.Security.Cryptography.CryptoStream> 이라는 특수 스트림 클래스와 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-108">The managed symmetric cryptography classes are used with a special stream class called a <xref:System.Security.Cryptography.CryptoStream> that encrypts data read into the stream.</span></span> <span data-ttu-id="7e303-109">**CryptoStream** 클래스는 관리 되는 스트림 클래스, 인터페이스를 구현 하는 클래스 <xref:System.Security.Cryptography.ICryptoTransform> (암호화 알고리즘을 구현 하는 클래스에서 만들어짐) 및 <xref:System.Security.Cryptography.CryptoStreamMode> **CryptoStream** 에 허용 되는 액세스 형식을 설명 하는 열거형을 사용 하 여 초기화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-109">The **CryptoStream** class is initialized with a managed stream class, a class that implements the <xref:System.Security.Cryptography.ICryptoTransform> interface (created from a class that implements a cryptographic algorithm), and a <xref:System.Security.Cryptography.CryptoStreamMode> enumeration that describes the type of access permitted to the **CryptoStream**.</span></span> <span data-ttu-id="7e303-110">, 및를 포함 하 여 클래스에서 파생 된 클래스를 사용 하 여 **CryptoStream** 클래스를 초기화할 수 있습니다 <xref:System.IO.Stream> <xref:System.IO.FileStream> <xref:System.IO.MemoryStream> <xref:System.Net.Sockets.NetworkStream> .</span><span class="sxs-lookup"><span data-stu-id="7e303-110">The **CryptoStream** class can be initialized using any class that derives from the <xref:System.IO.Stream> class, including <xref:System.IO.FileStream>, <xref:System.IO.MemoryStream>, and <xref:System.Net.Sockets.NetworkStream>.</span></span> <span data-ttu-id="7e303-111">이러한 클래스를 사용하여 다양한 스트림 개체에 대해 대칭 암호화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-111">Using these classes, you can perform symmetric encryption on a variety of stream objects.</span></span>  
  
<span data-ttu-id="7e303-112">다음 예제에서는 알고리즘에 대 한 기본 구현 클래스의 새 인스턴스를 만드는 방법을 보여 줍니다 <xref:System.Security.Cryptography.Aes> .</span><span class="sxs-lookup"><span data-stu-id="7e303-112">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="7e303-113">인스턴스는 **CryptoStream** 클래스에서 암호화를 수행 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-113">The instance is used to perform encryption on a **CryptoStream** class.</span></span> <span data-ttu-id="7e303-114">이 예제에서 **CryptoStream** 은 임의 형식의 관리되는 스트림일 수 있는 `myStream` 이라는 스트림 개체를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-114">In this example, the **CryptoStream** is initialized with a stream object called `myStream` that can be any type of managed stream.</span></span> <span data-ttu-id="7e303-115">**Aes** 클래스의 **createencryptor** 메서드에는 암호화에 사용 되는 키와 IV가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-115">The **CreateEncryptor** method from the **Aes** class is passed the key and IV that are used for encryption.</span></span> <span data-ttu-id="7e303-116">이 경우 `aes` 에서 생성되는 기본 키 및 IV가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-116">In this case, the default key and IV generated from `aes` are used.</span></span>
  
```vb  
Dim aes As Aes = Aes.Create()  
Dim cryptStream As New CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write)  
```  
  
```csharp  
Aes aes = Aes.Create();  
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateEncryptor(key, iv), CryptoStreamMode.Write);  
```  
  
<span data-ttu-id="7e303-117">이 코드를 실행 한 후 **CryptoStream** 개체에 기록 된 모든 데이터는 AES 알고리즘을 사용 하 여 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-117">After this code is executed, any data written to the **CryptoStream** object is encrypted using the AES algorithm.</span></span>  
  
<span data-ttu-id="7e303-118">다음 예제에서는 스트림을 만들고, 스트림을 암호화하고, 스트림에 쓰고, 스트림을 닫는 전체 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-118">The following example shows the entire process of creating a stream, encrypting the stream, writing to the stream, and closing the stream.</span></span> <span data-ttu-id="7e303-119">이 예제에서는 **CryptoStream** 클래스와 **Aes** 클래스를 사용 하 여 암호화 되는 파일 스트림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-119">This example creates a file stream that is encrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="7e303-120">생성 된 IV는의 시작 부분에 기록 <xref:System.IO.FileStream> 되므로 암호 해독에 대해 읽고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-120">Generated IV is written to beginning of <xref:System.IO.FileStream>, so it can be read and used for decryption.</span></span> <span data-ttu-id="7e303-121">그런 다음 클래스를 사용 하 여 암호화 된 스트림에 메시지를 씁니다 <xref:System.IO.StreamWriter> .</span><span class="sxs-lookup"><span data-stu-id="7e303-121">Then a message is written to the encrypted stream with the <xref:System.IO.StreamWriter> class.</span></span> <span data-ttu-id="7e303-122">동일한 키를 여러 번 사용 하 여 데이터를 암호화 하 고 암호 해독 하는 동안 매번 새 임의 IV를 생성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-122">While the same key can be used multiple times to encrypt and decrypt data, it is recommended to generate a new random IV each time.</span></span> <span data-ttu-id="7e303-123">이러한 방식으로 일반 텍스트가 동일한 경우에도 암호화 된 데이터가 항상 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-123">This way the encrypted data is always different, even when plain text is the same.</span></span>
  
:::code language="csharp" source="snippets/encrypting-data/csharp/aes-encrypt.cs":::
:::code language="vb" source="snippets/encrypting-data/vb/aes-encrypt.vb":::

<span data-ttu-id="7e303-124">이 코드는 AES 대칭 알고리즘을 사용 하 여 스트림을 암호화 하 고 IV를 쓴 다음 "Hello World!"을 (를) 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-124">The code encrypts the stream using the AES symmetric algorithm, and writes IV and then encrypted "Hello World!"</span></span> <span data-ttu-id="7e303-125">씁니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-125">to the stream.</span></span> <span data-ttu-id="7e303-126">코드가 성공적으로 실행 되 면 *TestData.txt* 이라는 암호화 된 파일을 만들고 다음 텍스트를 콘솔에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-126">If the code is successful, it creates an encrypted file named *TestData.txt* and displays the following text to the console:</span></span>
  
```console  
The text was encrypted.
```  

<span data-ttu-id="7e303-127">[데이터 암호 해독](decrypting-data.md)의 대칭 암호 해독 예제를 사용 하 여 파일의 암호를 해독할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-127">You can decrypt the file by using the symmetric decryption example in [Decrypting Data](decrypting-data.md).</span></span> <span data-ttu-id="7e303-128">이 예에서는 동일한 키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-128">That example and this example specify the same key.</span></span>

<span data-ttu-id="7e303-129">그러나 예외가 발생 하는 경우 코드는 콘솔에 다음 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-129">However, if an exception is raised, the code displays the following text to the console:</span></span>
  
```console  
The encryption failed.
```

## <a name="asymmetric-encryption"></a><span data-ttu-id="7e303-130">비대칭 암호화</span><span class="sxs-lookup"><span data-stu-id="7e303-130">Asymmetric Encryption</span></span>

<span data-ttu-id="7e303-131">비대칭 알고리즘은 일반적으로 대칭 키 및 IV의 암호화와 같은 적은 양의 데이터를 암호화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-131">Asymmetric algorithms are usually used to encrypt small amounts of data such as the encryption of a symmetric key and IV.</span></span> <span data-ttu-id="7e303-132">일반적으로 비대칭 암호화를 수행하는 개인은 다른 당사자가 생성한 공개 키를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-132">Typically, an individual performing asymmetric encryption uses the public key generated by another party.</span></span> <span data-ttu-id="7e303-133"><xref:System.Security.Cryptography.RSA>클래스는 이러한 용도로 .net에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-133">The <xref:System.Security.Cryptography.RSA> class is provided by .NET for this purpose.</span></span>  
  
<span data-ttu-id="7e303-134">다음 예제에서는 공개 키 정보를 사용하여 대칭 키 및 IV를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-134">The following example uses public key information to encrypt a symmetric key and IV.</span></span> <span data-ttu-id="7e303-135">타사의 공개 키를 나타내는 2바이트 배열이 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-135">Two byte arrays are initialized that represent the public key of a third party.</span></span> <span data-ttu-id="7e303-136"><xref:System.Security.Cryptography.RSAParameters> 개체는 이러한 값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-136">An <xref:System.Security.Cryptography.RSAParameters> object is initialized to these values.</span></span> <span data-ttu-id="7e303-137">그런 다음 메서드를 사용 하 여 **RSAParameters** 개체 (이 개체가 나타내는 공개 키와 함께)를 **RSA** 인스턴스로 가져옵니다 <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7e303-137">Next, the **RSAParameters** object (along with the public key it represents) is imported into an **RSA** instance using the <xref:System.Security.Cryptography.RSA.ImportParameters%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7e303-138">마지막으로, 클래스에서 만든 개인 키 및 IV <xref:System.Security.Cryptography.Aes> 가 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-138">Finally, the private key and IV created by an <xref:System.Security.Cryptography.Aes> class are encrypted.</span></span> <span data-ttu-id="7e303-139">이 예제에서는 시스템에 128비트 암호화가 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e303-139">This example requires systems to have 128-bit encryption installed.</span></span>  
  
```vb  
Imports System
Imports System.Security.Cryptography

Module Module1

    Sub Main()
        'Initialize the byte arrays to the public key information.  
        Dim modulus As Byte() = {214, 46, 220, 83, 160, 73, 40, 39, 201, 155, 19, 202, 3, 11, 191, 178, 56, 74, 90, 36, 248, 103, 18, 144, 170, 163, 145, 87, 54, 61, 34, 220, 222, 207, 137, 149, 173, 14, 92, 120, 206, 222, 158, 28, 40, 24, 30, 16, 175, 108, 128, 35, 230, 118, 40, 121, 113, 125, 216, 130, 11, 24, 90, 48, 194, 240, 105, 44, 76, 34, 57, 249, 228, 125, 80, 38, 9, 136, 29, 117, 207, 139, 168, 181, 85, 137, 126, 10, 126, 242, 120, 247, 121, 8, 100, 12, 201, 171, 38, 226, 193, 180, 190, 117, 177, 87, 143, 242, 213, 11, 44, 180, 113, 93, 106, 99, 179, 68, 175, 211, 164, 116, 64, 148, 226, 254, 172, 147}

        Dim exponent As Byte() = {1, 0, 1}

        'Create values to store encrypted symmetric keys.  
        Dim encryptedSymmetricKey() As Byte
        Dim encryptedSymmetricIV() As Byte

        'Create a new instance of the default RSA implementation class.
        Dim rsa As RSA = RSA.Create()

        'Create a new instance of the RSAParameters structure.  
        Dim rsaKeyInfo As New RSAParameters()

        'Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus
        rsaKeyInfo.Exponent = exponent

        'Import key parameters into rsa
        rsa.ImportParameters(rsaKeyInfo)

        'Create a new instance of the default Aes implementation class.  
        Dim aes As Aes = Aes.Create()

        'Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1)
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1)
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
        byte[] modulus = {214,46,220,83,160,73,40,39,201,155,19,202,3,11,191,178,56,
            74,90,36,248,103,18,144,170,163,145,87,54,61,34,220,222,
            207,137,149,173,14,92,120,206,222,158,28,40,24,30,16,175,
            108,128,35,230,118,40,121,113,125,216,130,11,24,90,48,194,
            240,105,44,76,34,57,249,228,125,80,38,9,136,29,117,207,139,
            168,181,85,137,126,10,126,242,120,247,121,8,100,12,201,171,
            38,226,193,180,190,117,177,87,143,242,213,11,44,180,113,93,
            106,99,179,68,175,211,164,116,64,148,226,254,172,147};

        byte[] exponent = { 1, 0, 1 };

        //Create values to store encrypted symmetric keys.  
        byte[] encryptedSymmetricKey;
        byte[] encryptedSymmetricIV;

        //Create a new instance of the RSA class.  
        RSA rsa = RSA.Create();

        //Create a new instance of the RSAParameters structure.  
        RSAParameters rsaKeyInfo = new RSAParameters();

        //Set rsaKeyInfo to the public key values.
        rsaKeyInfo.Modulus = modulus;
        rsaKeyInfo.Exponent = exponent;

        //Import key parameters into rsa.  
        rsa.ImportParameters(rsaKeyInfo);

        //Create a new instance of the default Aes implementation class.  
        Aes aes = Aes.Create();

        //Encrypt the symmetric key and IV.  
        encryptedSymmetricKey = rsa.Encrypt(aes.Key, RSAEncryptionPadding.Pkcs1);
        encryptedSymmetricIV = rsa.Encrypt(aes.IV, RSAEncryptionPadding.Pkcs1);
    }
}
```  
  
## <a name="see-also"></a><span data-ttu-id="7e303-140">참조</span><span class="sxs-lookup"><span data-stu-id="7e303-140">See also</span></span>

- [<span data-ttu-id="7e303-141">암호화 및 해독용 키 생성</span><span class="sxs-lookup"><span data-stu-id="7e303-141">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="7e303-142">데이터 해독</span><span class="sxs-lookup"><span data-stu-id="7e303-142">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="7e303-143">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="7e303-143">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="7e303-144">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="7e303-144">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="7e303-145">패딩을 사용하는 CBC 모드 대칭 암호 해독의 타이밍 취약성</span><span class="sxs-lookup"><span data-stu-id="7e303-145">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="7e303-146">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="7e303-146">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
