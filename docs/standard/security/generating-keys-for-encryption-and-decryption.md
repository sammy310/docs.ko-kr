---
title: 암호화 및 해독용 키 생성
description: .NET의 암호화 및 암호 해독을 위해 대칭 및 비대칭 키를 만들고 관리 하는 방법에 대해 알아봅니다.
ms.date: 07/14/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET], keys
- symmetric keys
- asymmetric keys [.NET]
- cryptography [.NET], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: aa95204a90f2aee684cdd20095d1816e890a0306
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94831080"
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="c8538-103">암호화 및 해독용 키 생성</span><span class="sxs-lookup"><span data-stu-id="c8538-103">Generating Keys for Encryption and Decryption</span></span>
<span data-ttu-id="c8538-104">키 만들기 및 관리는 암호화 프로세스의 중요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-104">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="c8538-105">대칭 알고리즘을 사용할 때는 키와 IV(Initialization Vector)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-105">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="c8538-106">키는 데이터를 암호 해독해서는 안 되는 사람이 알 수 없도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-106">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="c8538-107">IV는 기밀이어야 할 필요는 없지만 각 세션에서 변경되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-107">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="c8538-108">비대칭 알고리즘에서는 퍼블릭 키와 프라이빗 키를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-108">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="c8538-109">퍼블릭 키는 모든 사용자에게 퍼블릭될 수 있는 반면, 프라이빗 키는 퍼블릭 키로 암호화된 데이터를 암호 해독하는 당사자만 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-109">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="c8538-110">이 섹션에서는 대칭 및 비대칭 알고리즘에 대한 키를 생성 및 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-110">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="c8538-111">대칭 키</span><span class="sxs-lookup"><span data-stu-id="c8538-111">Symmetric Keys</span></span>  
 <span data-ttu-id="c8538-112">.NET에서 제공 하는 대칭 암호화 클래스에는 데이터를 암호화 하 고 해독 하기 위해 키와 새 IV (초기화 벡터)가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-112">The symmetric encryption classes supplied by .NET require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="c8538-113">매개 변수가 없는 메서드를 사용 하 여 관리 되는 대칭 암호화 클래스 중 하나의 새 인스턴스를 만들 때마다 `Create()` 새 키와 IV가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-113">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the parameterless `Create()` method, a new key and IV are automatically created.</span></span> <span data-ttu-id="c8538-114">데이터를 암호 해독할 수 있도록 허용하는 모든 사용자는 동일한 키와 IV를 소유하고 동일한 알고리즘을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-114">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="c8538-115">일반적으로 새 키와 IV는 각 세션에 대해 생성되어야 하며, 이후 세션을 위해 키와 IV를 저장하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-115">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="c8538-116">대칭 키와 IV를 위치상 떨어져 있는 사용자에게 전달하려면 대개 비대칭 암호화를 사용하여 대칭 키를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-116">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="c8538-117">이 키를 암호화하지 않은 상태로 보안되지 않은 네트워크를 통해 보내면 다른 사람이 이 키 및 IV를 가로채어 데이터를 암호 해독할 수 있기 때문에 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-117">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span>  
  
 <span data-ttu-id="c8538-118">다음 예제에서는 알고리즘에 대 한 기본 구현 클래스의 새 인스턴스를 만드는 방법을 보여 줍니다 <xref:System.Security.Cryptography.Aes> .</span><span class="sxs-lookup"><span data-stu-id="c8538-118">The following example shows the creation of a new instance of the default implementation class for the <xref:System.Security.Cryptography.Aes> algorithm.</span></span>  
  
```vb  
Dim aes As Aes = Aes.Create()  
```  
  
```csharp  
Aes aes = Aes.Create();  
```  
  
 <span data-ttu-id="c8538-119">이전 코드를 실행하면 새 키와 IV가 생성되어 **키** 및 **IV** 속성에 각각 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-119">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="c8538-120">여러 키를 생성해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-120">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="c8538-121">이 경우 대칭 알고리즘을 구현하는 클래스의 새 인스턴스를 만든 다음 **GenerateKey** 및 **GenerateIV** 메서드를 호출하여 새 키와 IV를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-121">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="c8538-122">다음 코드 예제에서는 대칭 암호화 클래스의 새 인스턴스가 생성 된 후 새 키와 Iv를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-122">The following code example illustrates how to create new keys and IVs after a new instance of the symmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim aes As Aes = Aes.Create()  
aes.GenerateIV()  
aes.GenerateKey()  
```  
  
```csharp  
Aes aes = Aes.Create();  
aes.GenerateIV();  
aes.GenerateKey();  
```  
  
 <span data-ttu-id="c8538-123">이전 코드를 실행 하면 **Aes** 의 새 인스턴스가 만들어질 때 키와 IV가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-123">When the preceding code is executed, a key and IV are generated when the new instance of **Aes** is made.</span></span> <span data-ttu-id="c8538-124">**GenerateKey** 및 **GenerateIV** 메서드를 호출할 때 다른 키와 IV가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-124">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>
  
## <a name="asymmetric-keys"></a><span data-ttu-id="c8538-125">비대칭 키</span><span class="sxs-lookup"><span data-stu-id="c8538-125">Asymmetric Keys</span></span>

 <span data-ttu-id="c8538-126">.NET에서는 <xref:System.Security.Cryptography.RSA> 비대칭 암호화를 위한 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-126">.NET provides the <xref:System.Security.Cryptography.RSA> class for asymmetric encryption.</span></span> <span data-ttu-id="c8538-127">이 클래스는 매개 변수가 없는 메서드를 사용 하 여 새 인스턴스를 만들 때 공개/개인 키 쌍을 만듭니다 `Create()` .</span><span class="sxs-lookup"><span data-stu-id="c8538-127">This class creates a public/private key pair when you use the parameterless `Create()` method to create a new instance.</span></span> <span data-ttu-id="c8538-128">비대칭 키는 여러 세션에서 사용하기 위해 저장하거나 하나의 세션에 대해서만 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-128">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="c8538-129">퍼블릭 키는 모든 사용자에게 퍼블릭될 수 있는 반면 프라이빗 키는 엄격하게 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-129">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="c8538-130">퍼블릭/프라이빗 키 쌍은 비대칭 알고리즘 클래스의 새 인스턴스를 만들 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-130">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="c8538-131">클래스의 새 인스턴스를 만든 후에는 키 <xref:System.Security.Cryptography.RSA.ExportParameters%2A> <xref:System.Security.Cryptography.RSAParameters> 정보를 포함 하는 구조체를 반환 하는 메서드를 사용 하 여 키 정보를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-131">After a new instance of the class is created, the key information can be extracted using the <xref:System.Security.Cryptography.RSA.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span> <span data-ttu-id="c8538-132">메서드는 공개 키 정보만 반환할지 또는 공개 키와 개인 키 정보를 모두 반환할지를 나타내는 부울 값을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-132">The method accepts a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span>

<span data-ttu-id="c8538-133">또한 다음과 같은 주요 정보를 추출할 수 있는 다른 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-133">There are also other methods that let you extract key information, such as:</span></span>

* <xref:System.Security.Cryptography.RSA.ExportRSAPublicKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.RSA.ExportRSAPrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportSubjectPublicKeyInfo%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportPkcs8PrivateKey%2A?displayProperty=nameWithType>
* <xref:System.Security.Cryptography.AsymmetricAlgorithm.ExportEncryptedPkcs8PrivateKey%2A?displayProperty=nameWithType>

<span data-ttu-id="c8538-134">**RSA** 인스턴스는 메서드를 사용 하 여 **RSAParameters** 구조체의 값으로 초기화할 수 있습니다 <xref:System.Security.Cryptography.RSA.ImportParameters%2A> .</span><span class="sxs-lookup"><span data-stu-id="c8538-134">An **RSA** instance can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSA.ImportParameters%2A> method.</span></span> <span data-ttu-id="c8538-135">또는 메서드를 사용 하 여 새 인스턴스를 만듭니다 <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="c8538-135">Or create a new instance by using the <xref:System.Security.Cryptography.RSA.Create(System.Security.Cryptography.RSAParameters)?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="c8538-136">비대칭 프라이빗 키는 로컬 컴퓨터에 축자로 저장하거나 일반 텍스트로 저장해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-136">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="c8538-137">프라이빗 키를 저장해야 하는 경우에는 키 컨테이너를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-137">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="c8538-138">키 컨테이너에 개인 키를 저장 하는 방법에 대 한 자세한 내용은 [방법: 키 컨테이너에 비대칭 키 저장](how-to-store-asymmetric-keys-in-a-key-container.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c8538-138">For more information about how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="c8538-139">다음 코드 예제에서는 **RSA** 클래스의 새 인스턴스를 만들고, 공개/개인 키 쌍을 만들고, 공개 키 정보를 **RSAParameters** 구조체에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c8538-139">The following code example creates a new instance of the **RSA** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSA = RSA.Create()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSA rsa = RSA.Create();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="c8538-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c8538-140">See also</span></span>

- [<span data-ttu-id="c8538-141">데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="c8538-141">Encrypting Data</span></span>](encrypting-data.md)
- [<span data-ttu-id="c8538-142">데이터 해독</span><span class="sxs-lookup"><span data-stu-id="c8538-142">Decrypting Data</span></span>](decrypting-data.md)
- [<span data-ttu-id="c8538-143">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="c8538-143">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="c8538-144">방법: 키 컨테이너에 비대칭 키 저장</span><span class="sxs-lookup"><span data-stu-id="c8538-144">How to: Store Asymmetric Keys in a Key Container</span></span>](how-to-store-asymmetric-keys-in-a-key-container.md)
- [<span data-ttu-id="c8538-145">플랫폼 간 암호화</span><span class="sxs-lookup"><span data-stu-id="c8538-145">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="c8538-146">ASP.NET Core 데이터 보호</span><span class="sxs-lookup"><span data-stu-id="c8538-146">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
