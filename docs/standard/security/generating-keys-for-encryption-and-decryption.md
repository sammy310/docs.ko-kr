---
title: 암호화 및 해독용 키 생성
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keys, encryption and decryption
- keys, asymmetric
- keys, symmetric
- encryption [.NET Framework], keys
- symmetric keys
- asymmetric keys [.NET Framework]
- cryptography [.NET Framework], keys
ms.assetid: c197dfc9-a453-4226-898d-37a16638056e
ms.openlocfilehash: 88d8dac83c3d5bf267ed90ffb313cd9e24b42dea
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706190"
---
# <a name="generating-keys-for-encryption-and-decryption"></a><span data-ttu-id="14a28-102">암호화 및 해독용 키 생성</span><span class="sxs-lookup"><span data-stu-id="14a28-102">Generating Keys for Encryption and Decryption</span></span>
<span data-ttu-id="14a28-103">키 만들기 및 관리는 암호화 프로세스의 중요한 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-103">Creating and managing keys is an important part of the cryptographic process.</span></span> <span data-ttu-id="14a28-104">대칭 알고리즘을 사용할 때는 키와 IV(Initialization Vector)를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-104">Symmetric algorithms require the creation of a key and an initialization vector (IV).</span></span> <span data-ttu-id="14a28-105">키는 데이터를 암호 해독해서는 안 되는 사람이 알 수 없도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-105">The key must be kept secret from anyone who should not decrypt your data.</span></span> <span data-ttu-id="14a28-106">IV는 기밀이어야 할 필요는 없지만 각 세션에서 변경되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-106">The IV does not have to be secret, but should be changed for each session.</span></span> <span data-ttu-id="14a28-107">비대칭 알고리즘에서는 퍼블릭 키와 프라이빗 키를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-107">Asymmetric algorithms require the creation of a public key and a private key.</span></span> <span data-ttu-id="14a28-108">퍼블릭 키는 모든 사용자에게 퍼블릭될 수 있는 반면, 프라이빗 키는 퍼블릭 키로 암호화된 데이터를 암호 해독하는 당사자만 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-108">The public key can be made public to anyone, while the private key must known only by the party who will decrypt the data encrypted with the public key.</span></span> <span data-ttu-id="14a28-109">이 섹션에서는 대칭 및 비대칭 알고리즘에 대한 키를 생성 및 관리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-109">This section describes how to generate and manage keys for both symmetric and asymmetric algorithms.</span></span>  
  
## <a name="symmetric-keys"></a><span data-ttu-id="14a28-110">대칭 키</span><span class="sxs-lookup"><span data-stu-id="14a28-110">Symmetric Keys</span></span>  
 <span data-ttu-id="14a28-111">.NET Framework에서 제공하는 대칭 암호화 클래스가 데이터를 암호화 및 암호 해독하려면 키와 새 IV(초기화 벡터)가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-111">The symmetric encryption classes supplied by the .NET Framework require a key and a new initialization vector (IV) to encrypt and decrypt data.</span></span> <span data-ttu-id="14a28-112">매개 변수가 없는 생성자를 사용 하 여 관리 되는 대칭 암호화 클래스 중 하나의 새 인스턴스를 만들 때마다 새 키와 IV가 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-112">Whenever you create a new instance of one of the managed symmetric cryptographic classes using the parameterless constructor, a new key and IV are automatically created.</span></span> <span data-ttu-id="14a28-113">데이터를 암호 해독할 수 있도록 허용하는 모든 사용자는 동일한 키와 IV를 소유하고 동일한 알고리즘을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-113">Anyone that you allow to decrypt your data must possess the same key and IV and use the same algorithm.</span></span> <span data-ttu-id="14a28-114">일반적으로 새 키와 IV는 각 세션에 대해 생성되어야 하며, 이후 세션을 위해 키와 IV를 저장하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-114">Generally, a new key and IV should be created for every session, and neither the key nor IV should be stored for use in a later session.</span></span>  
  
 <span data-ttu-id="14a28-115">대칭 키와 IV를 위치상 떨어져 있는 사용자에게 전달하려면 대개 비대칭 암호화를 사용하여 대칭 키를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-115">To communicate a symmetric key and IV to a remote party, you would usually encrypt the symmetric key by using asymmetric encryption.</span></span> <span data-ttu-id="14a28-116">이 키를 암호화하지 않은 상태로 보안되지 않은 네트워크를 통해 보내면 다른 사람이 이 키 및 IV를 가로채어 데이터를 암호 해독할 수 있기 때문에 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-116">Sending the key across an insecure network without encrypting it is unsafe, because anyone who intercepts the key and IV can then decrypt your data.</span></span> <span data-ttu-id="14a28-117">암호화를 사용하여 데이터를 교환하는 방법에 대한 자세한 내용은 [암호화 체계 만들기](../../../docs/standard/security/creating-a-cryptographic-scheme.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14a28-117">For more information about exchanging data by using encryption, see [Creating a Cryptographic Scheme](../../../docs/standard/security/creating-a-cryptographic-scheme.md).</span></span>  
  
 <span data-ttu-id="14a28-118">다음 예제에서는 TripleDES 알고리즘을 구현하는 <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> 클래스의 새 인스턴스를 만드는 과정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-118">The following example shows the creation of a new instance of the <xref:System.Security.Cryptography.TripleDESCryptoServiceProvider> class that implements the TripleDES algorithm.</span></span>  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
```  
  
 <span data-ttu-id="14a28-119">이전 코드를 실행하면 새 키와 IV가 생성되어 **키** 및 **IV** 속성에 각각 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-119">When the previous code is executed, a new key and IV are generated and placed in the **Key** and **IV** properties, respectively.</span></span>  
  
 <span data-ttu-id="14a28-120">여러 키를 생성해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-120">Sometimes you might need to generate multiple keys.</span></span> <span data-ttu-id="14a28-121">이 경우 대칭 알고리즘을 구현하는 클래스의 새 인스턴스를 만든 다음 **GenerateKey** 및 **GenerateIV** 메서드를 호출하여 새 키와 IV를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-121">In this situation, you can create a new instance of a class that implements a symmetric algorithm and then create a new key and IV by calling the **GenerateKey** and **GenerateIV** methods.</span></span> <span data-ttu-id="14a28-122">다음 코드 예제에서는 대칭 암호화 클래스의 새 인스턴스가 생성 된 후 새 키와 Iv를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-122">The following code example illustrates how to create new keys and IVs after a new instance of the symmetric cryptographic class has been made.</span></span>  
  
```vb  
Dim tdes As TripleDESCryptoServiceProvider = new TripleDESCryptoServiceProvider()  
tdes.GenerateIV()  
tdes.GenerateKey()  
```  
  
```csharp  
TripleDESCryptoServiceProvider tdes = new TripleDESCryptoServiceProvider();  
tdes.GenerateIV();  
tdes.GenerateKey();  
```  
  
 <span data-ttu-id="14a28-123">이전 코드를 실행하면 **TripleDESCryptoServiceProvider** 의 새 인스턴스를 만들 때 키와 IV가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-123">When the previous code is executed, a key and IV are generated when the new instance of **TripleDESCryptoServiceProvider** is made.</span></span> <span data-ttu-id="14a28-124">**GenerateKey** 및 **GenerateIV** 메서드를 호출할 때 다른 키와 IV가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-124">Another key and IV are created when the **GenerateKey** and **GenerateIV** methods are called.</span></span>  
  
## <a name="asymmetric-keys"></a><span data-ttu-id="14a28-125">비대칭 키</span><span class="sxs-lookup"><span data-stu-id="14a28-125">Asymmetric Keys</span></span>  
 <span data-ttu-id="14a28-126">.NET Framework에서는 비대칭 암호화를 위해 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 및 <xref:System.Security.Cryptography.DSACryptoServiceProvider> 클래스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-126">The .NET Framework provides the <xref:System.Security.Cryptography.RSACryptoServiceProvider> and <xref:System.Security.Cryptography.DSACryptoServiceProvider> classes for asymmetric encryption.</span></span> <span data-ttu-id="14a28-127">이러한 클래스는 매개 변수가 없는 생성자를 사용 하 여 새 인스턴스를 만들 때 공개/개인 키 쌍을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-127">These classes create a public/private key pair when you use the parameterless constructor to create a new instance.</span></span> <span data-ttu-id="14a28-128">비대칭 키는 여러 세션에서 사용하기 위해 저장하거나 하나의 세션에 대해서만 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-128">Asymmetric keys can be either stored for use in multiple sessions or generated for one session only.</span></span> <span data-ttu-id="14a28-129">퍼블릭 키는 모든 사용자에게 퍼블릭될 수 있는 반면 프라이빗 키는 엄격하게 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-129">While the public key can be made generally available, the private key should be closely guarded.</span></span>  
  
 <span data-ttu-id="14a28-130">퍼블릭/프라이빗 키 쌍은 비대칭 알고리즘 클래스의 새 인스턴스를 만들 때마다 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-130">A public/private key pair is generated whenever a new instance of an asymmetric algorithm class is created.</span></span> <span data-ttu-id="14a28-131">클래스의 새 인스턴스가 생성된 후 다음 두 메서드 중 하나를 사용하여 키 정보를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-131">After a new instance of the class is created, the key information can be extracted using one of two methods:</span></span>  
  
- <span data-ttu-id="14a28-132"><xref:System.Security.Cryptography.RSA.ToXmlString%2A> 메서드 - 키 정보의 XML 표현을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-132">The <xref:System.Security.Cryptography.RSA.ToXmlString%2A> method, which returns an XML representation of the key information.</span></span>  
  
- <span data-ttu-id="14a28-133"><xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> 메서드 - 키 정보를 보유하는 <xref:System.Security.Cryptography.RSAParameters> 구조체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-133">The <xref:System.Security.Cryptography.RSACryptoServiceProvider.ExportParameters%2A> method, which returns an <xref:System.Security.Cryptography.RSAParameters> structure that holds the key information.</span></span>  
  
 <span data-ttu-id="14a28-134">두 메서드는 퍼블릭 키 정보만 반환할지 또는 퍼블릭 키와 프라이빗 키 정보를 모두 반환할지를 나타내는 부울 값을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-134">Both methods accept a Boolean value that indicates whether to return only the public key information or to return both the public-key and the private-key information.</span></span> <span data-ttu-id="14a28-135">**메서드를 사용하여** RSACryptoServiceProvider **클래스를** RSAParameters <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> 구조체의 값으로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-135">An **RSACryptoServiceProvider** class can be initialized to the value of an **RSAParameters** structure by using the <xref:System.Security.Cryptography.RSACryptoServiceProvider.ImportParameters%2A> method.</span></span>  
  
 <span data-ttu-id="14a28-136">비대칭 프라이빗 키는 로컬 컴퓨터에 축자로 저장하거나 일반 텍스트로 저장해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-136">Asymmetric private keys should never be stored verbatim or in plain text on the local computer.</span></span> <span data-ttu-id="14a28-137">프라이빗 키를 저장해야 하는 경우에는 키 컨테이너를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-137">If you need to store a private key, you should use a key container.</span></span> <span data-ttu-id="14a28-138">키 컨테이너에서 프라이빗 키를 저장하는 방법에 대한 자세한 내용은 [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="14a28-138">For more on how to store a private key in a key container, see [How to: Store Asymmetric Keys in a Key Container](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md).</span></span>  
  
 <span data-ttu-id="14a28-139">다음 코드 예제에서는 퍼블릭/프라이빗 키 쌍을 만들어 **RSACryptoServiceProvider** 클래스의 새 인스턴스를 만들고 퍼블릭 키 정보를 **RSAParameters** 구조체에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="14a28-139">The following code example creates a new instance of the **RSACryptoServiceProvider** class, creating a public/private key pair, and saves the public key information to an **RSAParameters** structure.</span></span>  
  
```vb  
'Generate a public/private key pair.  
Dim rsa as RSACryptoServiceProvider = new RSACryptoServiceProvider()  
'Save the public key information to an RSAParameters structure.  
Dim rsaKeyInfo As RSAParameters = rsa.ExportParameters(false)  
```  
  
```csharp  
//Generate a public/private key pair.  
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();  
//Save the public key information to an RSAParameters structure.  
RSAParameters rsaKeyInfo = rsa.ExportParameters(false);  
```  
  
## <a name="see-also"></a><span data-ttu-id="14a28-140">참조</span><span class="sxs-lookup"><span data-stu-id="14a28-140">See also</span></span>

- [<span data-ttu-id="14a28-141">데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="14a28-141">Encrypting Data</span></span>](../../../docs/standard/security/encrypting-data.md)
- [<span data-ttu-id="14a28-142">데이터 해독</span><span class="sxs-lookup"><span data-stu-id="14a28-142">Decrypting Data</span></span>](../../../docs/standard/security/decrypting-data.md)
- [<span data-ttu-id="14a28-143">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="14a28-143">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="14a28-144">How to: Store Asymmetric Keys in a Key Container</span><span class="sxs-lookup"><span data-stu-id="14a28-144">How to: Store Asymmetric Keys in a Key Container</span></span>](../../../docs/standard/security/how-to-store-asymmetric-keys-in-a-key-container.md)
