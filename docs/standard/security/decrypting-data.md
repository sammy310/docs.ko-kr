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
ms.openlocfilehash: 7e8fe5a8b7ed7c217a31a8ee91a5d111257fed45
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440987"
---
# <a name="decrypting-data"></a><span data-ttu-id="97fbd-103">데이터 해독</span><span class="sxs-lookup"><span data-stu-id="97fbd-103">Decrypting Data</span></span>

<span data-ttu-id="97fbd-104">암호 해독은 암호화의 반대 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-104">Decryption is the reverse operation of encryption.</span></span> <span data-ttu-id="97fbd-105">비밀 키 암호화의 경우 데이터를 암호화하는 데 사용된 키 및 IV를 모두 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-105">For secret-key encryption, you must know both the key and IV that were used to encrypt the data.</span></span> <span data-ttu-id="97fbd-106">퍼블릭 키 암호화의 경우 퍼블릭 키(프라이빗 키를 사용하여 데이터가 암호화된 경우) 또는 프라이빗 키(퍼블릭 키를 사용하여 데이터가 암호화된 경우)를 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-106">For public-key encryption, you must know either the public key (if the data was encrypted using the private key) or the private key (if the data was encrypted using the public key).</span></span>

## <a name="symmetric-decryption"></a><span data-ttu-id="97fbd-107">대칭 암호 해독</span><span class="sxs-lookup"><span data-stu-id="97fbd-107">Symmetric Decryption</span></span>

<span data-ttu-id="97fbd-108">대칭 알고리즘을 사용하여 암호화된 데이터의 암호 해독은 대칭 알고리즘을 사용하여 데이터를 암호화하는 데 사용된 프로세스와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-108">The decryption of data encrypted with symmetric algorithms is similar to the process used to encrypt data with symmetric algorithms.</span></span> <span data-ttu-id="97fbd-109">클래스는 관리 되는 <xref:System.Security.Cryptography.CryptoStream> 스트림 개체에서 읽은 데이터를 해독 하기 위해 .net에서 제공 하는 대칭 암호화 클래스와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-109">The <xref:System.Security.Cryptography.CryptoStream> class is used with symmetric cryptography classes provided by .NET to decrypt data read from any managed stream object.</span></span>

<span data-ttu-id="97fbd-110">다음 예제에서는 알고리즘에 대 한 기본 구현 클래스의 새 인스턴스를 만드는 방법을 보여 줍니다 <xref:System.Security.Cryptography.Aes> .</span><span class="sxs-lookup"><span data-stu-id="97fbd-110">The following example illustrates how to create a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span> <span data-ttu-id="97fbd-111">인스턴스는 개체에 대 한 암호 해독을 수행 하는 데 사용 됩니다 <xref:System.Security.Cryptography.CryptoStream> .</span><span class="sxs-lookup"><span data-stu-id="97fbd-111">The instance is used to perform decryption on a <xref:System.Security.Cryptography.CryptoStream> object.</span></span> <span data-ttu-id="97fbd-112">이 예제에서는 먼저 구현 클래스의 새 인스턴스를 만듭니다 <xref:System.Security.Cryptography.Aes> .</span><span class="sxs-lookup"><span data-stu-id="97fbd-112">This example first creates a new instance of the <xref:System.Security.Cryptography.Aes> implementation class.</span></span> <span data-ttu-id="97fbd-113">관리 되는 스트림 변수에서 IV (초기화 벡터) 값을 읽습니다 `myStream` .</span><span class="sxs-lookup"><span data-stu-id="97fbd-113">It reads the initialization vector (IV) value from a managed stream variable, `myStream`.</span></span> <span data-ttu-id="97fbd-114">그런 다음 개체를 인스턴스화하고 <xref:System.Security.Cryptography.CryptoStream> 인스턴스의 값으로 초기화 `myStream` 합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-114">Next it instantiates a <xref:System.Security.Cryptography.CryptoStream> object and initializes it to the value of the `myStream` instance.</span></span> <span data-ttu-id="97fbd-115"><xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType>인스턴스의 메서드에는 <xref:System.Security.Cryptography.Aes> IV 값과 암호화에 사용 된 동일한 키가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-115">The <xref:System.Security.Cryptography.SymmetricAlgorithm.CreateDecryptor%2A?displayProperty=nameWithType> method from the <xref:System.Security.Cryptography.Aes> instance is passed the IV value and the same key that was used for encryption.</span></span>

```vb
Dim aes As Aes = Aes.Create()
Dim cryptStream As New CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read)
```

```csharp
Aes aes = Aes.Create();
CryptoStream cryptStream = new CryptoStream(myStream, aes.CreateDecryptor(key, iv), CryptoStreamMode.Read);
```

<span data-ttu-id="97fbd-116">다음 예제에서는 스트림을 만들고, 스트림을 암호 해독하고, 스트림에서 읽고, 스트림을 닫는 전체 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-116">The following example shows the entire process of creating a stream, decrypting the stream, reading from the stream, and closing the streams.</span></span> <span data-ttu-id="97fbd-117">*TestData.txt* 라는 파일을 읽는 파일 스트림 개체가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-117">A file stream object is created that reads a file named *TestData.txt*.</span></span> <span data-ttu-id="97fbd-118">그런 다음 **CryptoStream** 클래스와 **Aes** 클래스를 사용 하 여 파일 스트림을 해독 합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-118">The file stream is then decrypted using the **CryptoStream** class and the **Aes** class.</span></span> <span data-ttu-id="97fbd-119">이 예에서는 [데이터 암호화](encrypting-data.md)를 위한 대칭 암호화 예제에서 사용 되는 키 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-119">This example specifies key value that is used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="97fbd-120">이러한 값을 암호화 및 전송하는 데 필요한 코드는 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-120">It does not show the code needed to encrypt and transfer these values.</span></span>

:::code language="csharp" source="snippets/decrypting-data/csharp/aes-decrypt.cs":::
:::code language="vb" source="snippets/decrypting-data/vb/aes-decrypt.vb":::

<span data-ttu-id="97fbd-121">앞의 예제에서는 [데이터 암호화](encrypting-data.md)를 위한 대칭 암호화 예제에 사용 된 것과 동일한 키와 알고리즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-121">The preceding example uses the same key, and algorithm used in the symmetric encryption example for [Encrypting Data](encrypting-data.md).</span></span> <span data-ttu-id="97fbd-122">해당 예제에서 만든 *TestData.txt* 파일의 암호를 해독 하 고 콘솔에 원래 텍스트를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-122">It decrypts the *TestData.txt* file that is created by that example and displays the original text on the console.</span></span>

## <a name="asymmetric-decryption"></a><span data-ttu-id="97fbd-123">비대칭 암호 해독</span><span class="sxs-lookup"><span data-stu-id="97fbd-123">Asymmetric Decryption</span></span>

<span data-ttu-id="97fbd-124">일반적으로 당사자(당사자 A)는 퍼블릭 키와 프라이빗 키를 둘 다 생성하고 메모리 또는 암호화 키 컨테이너에 키를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-124">Typically, a party (party A) generates both a public and private key and stores the key either in memory or in a cryptographic key container.</span></span> <span data-ttu-id="97fbd-125">당사자 A가 다른 당사자(당사자 B)에게 공개 키를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-125">Party A then sends the public key to another party (party B).</span></span> <span data-ttu-id="97fbd-126">공개 키를 사용 하 여 파티 B는 데이터를 암호화 하 고 파티 A에 데이터를 다시 보냅니다. 파티는 데이터를 받은 후에 해당 하는 개인 키를 사용 하 여 암호를 해독 합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-126">Using the public key, party B encrypts data and sends the data back to party A. After receiving the data, party A decrypts it using the private key that corresponds.</span></span> <span data-ttu-id="97fbd-127">암호 해독은 당사자 A가 당사자 B에서 데이터를 암호화하는 데 사용한 퍼블릭 키에 해당하는 프라이빗 키를 사용하는 경우에만 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-127">Decryption will be successful only if party A uses the private key that corresponds to the public key Party B used to encrypt the data.</span></span>

<span data-ttu-id="97fbd-128">안전한 암호화 키 컨테이너에 비대칭 키를 저장하는 방법 및 나중에 비대칭 키를 검색하는 방법에 대한 자세한 내용은 [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97fbd-128">For information on how to store an asymmetric key in secure cryptographic key container and how to later retrieve the asymmetric key, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>

<span data-ttu-id="97fbd-129">다음 예제에서는 대칭 키 및 IV를 나타내는 두 바이트 배열의 암호 해독을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-129">The following example illustrates the decryption of two arrays of bytes that represent a symmetric key and IV.</span></span> <span data-ttu-id="97fbd-130">제3자에게 쉽게 보낼 수 있는 형식으로 <xref:System.Security.Cryptography.RSA> 개체에서 비대칭 공개 키를 추출하는 방법에 대한 자세한 내용은 [Encrypting Data](encrypting-data.md)이라는 관리되는 스트림의 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="97fbd-130">For information on how to extract the asymmetric public key from the <xref:System.Security.Cryptography.RSA> object in a format that you can easily send to a third party, see [Encrypting Data](encrypting-data.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="97fbd-131">참조</span><span class="sxs-lookup"><span data-stu-id="97fbd-131">See also</span></span>

- [<span data-ttu-id="97fbd-132">암호화 및 해독용 키 생성</span><span class="sxs-lookup"><span data-stu-id="97fbd-132">Generating Keys for Encryption and Decryption</span></span>](generating-keys-for-encryption-and-decryption.md)
- [<span data-ttu-id="97fbd-133">데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="97fbd-133">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="97fbd-134">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="97fbd-134">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="97fbd-135">암호화 모델</span><span class="sxs-lookup"><span data-stu-id="97fbd-135">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="97fbd-136">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="97fbd-136">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="97fbd-137">패딩을 사용하는 CBC 모드 대칭 암호 해독의 타이밍 취약성</span><span class="sxs-lookup"><span data-stu-id="97fbd-137">Timing vulnerabilities with CBC-mode symmetric decryption using padding</span></span>](vulnerabilities-cbc-mode.md)
- [<span data-ttu-id="97fbd-138">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="97fbd-138">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
