---
title: 데이터 해독
description: 대칭 알고리즘 또는 비대칭 알고리즘을 사용 하 여 .NET에서 데이터의 암호를 해독 하는 방법에 대해 알아봅니다.
ms.date: 07/16/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [.NET], decryption
- symmetric decryption
- asymmetric decryption
- decryption
ms.assetid: 9b266b6c-a9b2-4d20-afd8-b3a0d8fd48a0
ms.openlocfilehash: 2ba4c3ba43d688aeb66c67ec3f94f4a503d47892
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87556984"
---
# <a name="decrypting-data"></a><span data-ttu-id="ab848-103">데이터 해독</span><span class="sxs-lookup"><span data-stu-id="ab848-103">Decrypting Data</span></span>

<span data-ttu-id="ab848-104">암호 해독은 암호화의 반대 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-104">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="ab848-105">비밀 키 암호화의 경우 데이터를 암호화하는 데 사용된 키 및 IV를 모두 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-105">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="ab848-106">퍼블릭 키 암호화의 경우 퍼블릭 키(프라이빗 키를 사용하여 데이터가 암호화된 경우) 또는 프라이빗 키(퍼블릭 키를 사용하여 데이터가 암호화된 경우)를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-106">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="ab848-107">대칭 암호 해독</span><span class="sxs-lookup"><span data-stu-id="ab848-107">Symmetric Decryption</span></span>

<span data-ttu-id="ab848-108">대칭 알고리즘을 사용하여 암호화된 데이터의 암호 해독은 대칭 알고리즘을 사용하여 데이터를 암호화하는 데 사용된 프로세스와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-108">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="ab848-109">클래스는 관리 되는 <xref:System.Security.Cryptography.CryptoStream> 스트림 개체에서 읽은 데이터를 해독 하기 위해 .net에서 제공 하는 대칭 암호화 클래스와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-109">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by .NET to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="ab848-110">다음 예제에서는 알고리즘에 대 한 기본 구현 클래스의 새 인스턴스를 만드는 방법을 보여 줍니다 <xref:System.Security.Cryptography.Aes> .</span><span class="sxs-lookup"><span data-stu-id="ab848-110">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="ab848-111">인스턴스는 개체에 대 한 암호 해독을 수행 하는 데 사용 됩니다 <xref:System.Security.Cryptography.CryptoStream> .</span><span class="sxs-lookup"><span data-stu-id="ab848-111">The instance is used to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="ab848-112">이 예제에서는 먼저 **Aes** 구현 클래스의 새 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-112">This example first creates a new instance of the **Aes** implementation class.</span></span> <span data-ttu-id="ab848-113">그런 다음 **CryptoStream** 개체를 만들고 `myStream`이라는 관리되는 스트림의 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-113">Next it creates a **CryptoStream** object and initializes it to the value of a managed stream called `myStream`.</span></span> <span data-ttu-id="ab848-114">그런 다음 **Aes** 클래스의 **CreateDecryptor** 메서드에는 암호화에 사용 된 것과 동일한 키와 IV가 전달 된 다음 **CryptoStream** 생성자에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-114">Next, the **CreateDecryptor** method from the **Aes** class is passed the same key and IV that was used for encryption and is then passed to the **CryptoStream** constructor.</span></span>

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

<span data-ttu-id="ab848-115">다음 예제에서는 스트림을 만들고, 스트림을 암호 해독하고, 스트림에서 읽고, 스트림을 닫는 전체 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-115">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="ab848-116">*TestData.txt*라는 파일을 읽는 파일 스트림 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-116">A file stream object is created that reads a file named *TestData.txt*.</span></span> <span data-ttu-id="ab848-117">그런 다음 **CryptoStream** 클래스와 **Aes** 클래스를 사용 하 여 파일 스트림을 해독 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-117">The file stream is then decrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="ab848-118">이 예에서는 [데이터 암호화](encrypting-data.md)를 위한 대칭 암호화 예제에서 사용 되는 키 및 IV 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-118">This example specifies key and IV values that are used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="ab848-119">이러한 값을 암호화 및 전송하는 데 필요한 코드는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-119">It does not show the code needed to encrypt and transfer these values.</span></span>

```vb
Imports System
Imports System.IO
Imports System.Security.Cryptography

Module Module1
    Sub Main()
            'The key and IV must be the same values that were used
            'to encrypt the stream.
            Dim key As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
            Dim iv As Byte() = {&H1, &H2, &H3, &H4, &H5, &H6, &H7, &H8, &H9, &H10, &H11, &H12, &H13, &H14, &H15, &H16}
        Try
            'Create a file stream.
            Dim myStream As FileStream = new FileStream("TestData.txt", FileMode.Open)

            'Create a new instance of the default Aes implementation class
            'and decrypt the stream.
            Dim aes As Aes = Aes.Create()

            'Create an instance of the CryptoStream class, pass it the file stream, and decrypt
            'it with the Rijndael class using the key and IV.
            Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)

            'Read the stream.
            Dim sReader As New StreamReader(cryptStream)

            'Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd())

            'Close the streams.
            sReader.Close()
            myStream.Close()
            'Catch any exceptions.
        Catch
            Console.WriteLine("The decryption Failed.")
            Throw
        End Try
    End Sub
End Module
```

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

class Class1
{
    static void Main(string[] args)
    {
        //The key and IV must be the same values that were used
        //to encrypt the stream.
        byte[] key = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        byte[] iv = { 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x10, 0x11, 0x12, 0x13, 0x14, 0x15, 0x16 };
        try
        {
            //Create a file stream.
            FileStream myStream = new FileStream("TestData.txt", FileMode.Open);

            //Create a new instance of the default Aes implementation class
            Aes aes = Aes.Create();

            //Create a CryptoStream, pass it the file stream, and decrypt
            //it with the Aes class using the key and IV.
            CryptoStream cryptStream = new CryptoStream(
               myStream,
               aes.CreateDecryptor(key, iv),
               CryptoStreamMode.Read);

            //Read the stream.
            StreamReader sReader = new StreamReader(cryptStream);

            //Display the message.
            Console.WriteLine("The decrypted original message: {0}", sReader.ReadToEnd());

            //Close the streams.
            sReader.Close();
            myStream.Close();
        }
        //Catch any exceptions.
        catch
        {
            Console.WriteLine("The decryption failed.");
            throw;
        }
    }
}
```

<span data-ttu-id="ab848-120">앞의 예제에서는 [데이터 암호화](encrypting-data.md)를 위한 대칭 암호화 예제에 사용 된 것과 동일한 키, IV 및 알고리즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-120">The preceding example uses the same key, IV, and algorithm used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="ab848-121">해당 예제에서 만든 *TestData.txt* 파일의 암호를 해독 하 고 콘솔에 원래 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-121">It decrypts the *TestData.txt* file that is created by that example and displays the original text on the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="ab848-122">비대칭 암호 해독</span><span class="sxs-lookup"><span data-stu-id="ab848-122">Asymmetric Decryption</span></span>

<span data-ttu-id="ab848-123">일반적으로 당사자(당사자 A)는 퍼블릭 키와 프라이빗 키를 둘 다 생성하고 메모리 또는 암호화 키 컨테이너에 키를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-123">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="ab848-124">당사자 A가 다른 당사자(당사자 B)에게 공개 키를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-124">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="ab848-125">공개 키를 사용 하 여 파티 B는 데이터를 암호화 하 고 파티 A에 데이터를 다시 보냅니다. 파티는 데이터를 받은 후에 해당 하는 개인 키를 사용 하 여 암호를 해독 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-125">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="ab848-126">암호 해독은 당사자 A가 당사자 B에서 데이터를 암호화하는 데 사용한 퍼블릭 키에 해당하는 프라이빗 키를 사용하는 경우에만 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-126">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="ab848-127">안전한 암호화 키 컨테이너에 비대칭 키를 저장하는 방법 및 나중에 비대칭 키를 검색하는 방법에 대한 자세한 내용은 [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab848-127">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="ab848-128">다음 예제에서는 대칭 키 및 IV를 나타내는 두 바이트 배열의 암호 해독을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-128">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="ab848-129">제3자에게 쉽게 보낼 수 있는 형식으로 <xref:System.Security.Cryptography.RSA> 개체에서 비대칭 공개 키를 추출하는 방법에 대한 자세한 내용은 [Encrypting Data](encrypting-data.md)이라는 관리되는 스트림의 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="ab848-129">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSA> object in a format that you can easily send to a third party, see [Encrypting Data](encrypting-data.md).</span></span>

```vb
'Create a new instance of the RSA class.
Dim rsa As RSA = RSA.Create()

' Export the public key information and send it to a third party.
' Wait for the third party to encrypt some data and send it back.

'Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1)
symmetricIV = rsa.Decrypt(encryptedSymmetricIV, RSAEncryptionPadding.Pkcs1)
```

```csharp
//Create a new instance of the RSA class.
RSA rsa = RSA.Create();

// Export the public key information and send it to a third party.
// Wait for the third party to encrypt some data and send it back.

//Decrypt the symmetric key and IV.
symmetricKey = rsa.Decrypt(encryptedSymmetricKey, RSAEncryptionPadding.Pkcs1);
symmetricIV = rsa.Decrypt(encryptedSymmetricIV , RSAEncryptionPadding.Pkcs1);
```

## <a name="see-also"></a><span data-ttu-id="ab848-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab848-130">See also</span></span>

- [<span data-ttu-id="ab848-131">암호화 및 해독용 키 생성</span><span class="sxs-lookup"><span data-stu-id="ab848-131">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="ab848-132">데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="ab848-132">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="ab848-133">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="ab848-133">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="ab848-134">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="ab848-134">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="ab848-135">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="ab848-135">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="ab848-136">패딩을 사용하는 CBC 모드 대칭 암호 해독의 타이밍 취약성</span><span class="sxs-lookup"><span data-stu-id="ab848-136">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="ab848-137">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="ab848-137">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
