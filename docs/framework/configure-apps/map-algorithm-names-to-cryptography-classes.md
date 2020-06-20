---
title: 알고리즘 이름을 암호화 클래스에 매핑
description: 알고리즘 이름을 .NET의 암호화 클래스에 매핑합니다. 개발자에 게는 암호화 개체를 만드는 4 가지 옵션이 있습니다.
ms.date: 03/30/2017
helpviewer_keywords:
- mapping algorithm names
- cryptography, mapping algorithm names
- cryptographic algorithms
- names [.NET Framework], algorithm mapping
ms.assetid: 01327c69-c5e1-4ef6-b73f-0a58351f0492
ms.openlocfilehash: 5a1d7acdd34182dd82f4dce66d136c4ef4de6e95
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "85105358"
---
# <a name="mapping-algorithm-names-to-cryptography-classes"></a><span data-ttu-id="15f2f-104">알고리즘 이름을 암호화 클래스에 매핑</span><span class="sxs-lookup"><span data-stu-id="15f2f-104">Mapping Algorithm Names to Cryptography Classes</span></span>
<span data-ttu-id="15f2f-105">개발자가 Windows SDK를 사용 하 여 암호화 개체를 만들 수 있는 네 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-105">There are four ways a developer can create a cryptography object using the Windows SDK:</span></span>  
  
- <span data-ttu-id="15f2f-106">**New** 연산자를 사용 하 여 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-106">Create an object by using the **new** operator.</span></span>  
  
- <span data-ttu-id="15f2f-107">해당 알고리즘의 추상 클래스에서 **create** 메서드를 호출 하 여 특정 암호화 알고리즘을 구현 하는 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-107">Create an object that implements a particular cryptography algorithm by calling the **Create** method on the abstract class for that algorithm.</span></span>  
  
- <span data-ttu-id="15f2f-108">메서드를 호출 하 여 특정 암호화 알고리즘을 구현 하는 개체를 만듭니다 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="15f2f-108">Create an object that implements a particular cryptography algorithm by calling the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method.</span></span>  
  
- <span data-ttu-id="15f2f-109">해당 알고리즘 형식 (예:)에 대 한 추상 클래스에서 **Create** 메서드를 호출 하 여 대칭 블록 암호화와 같은 암호화 알고리즘의 클래스를 구현 하는 개체를 만듭니다 <xref:System.Security.Cryptography.SymmetricAlgorithm> .</span><span class="sxs-lookup"><span data-stu-id="15f2f-109">Create an object that implements a class of cryptographic algorithms (such as a symmetric block cipher) by calling the **Create** method on the abstract class for that type of algorithm (such as <xref:System.Security.Cryptography.SymmetricAlgorithm>).</span></span>  
  
 <span data-ttu-id="15f2f-110">예를 들어 개발자가 바이트 집합의 SHA1 해시를 계산 하려고 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-110">For example, suppose a developer wants to compute the SHA1 hash of a set of bytes.</span></span> <span data-ttu-id="15f2f-111"><xref:System.Security.Cryptography>네임 스페이스에는 완전히 관리 되는 구현과 CryptoAPI를 래핑하는 SHA1 알고리즘의 두 가지 구현이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-111">The <xref:System.Security.Cryptography> namespace contains two implementations of the SHA1 algorithm, one purely managed implementation and one that wraps CryptoAPI.</span></span> <span data-ttu-id="15f2f-112">개발자는 new 연산자를 호출 하 여와 같은 특정 SHA1 구현을 인스턴스화할 수 있습니다 <xref:System.Security.Cryptography.SHA1Managed> . **new**</span><span class="sxs-lookup"><span data-stu-id="15f2f-112">The developer can choose to instantiate a particular SHA1 implementation (such as the <xref:System.Security.Cryptography.SHA1Managed>) by calling the **new** operator.</span></span> <span data-ttu-id="15f2f-113">그러나 클래스가 SHA1 해시 알고리즘을 구현 하는 한 공용 언어 런타임에서 로드 하는 클래스가 중요 하지 않은 경우 개발자는 메서드를 호출 하 여 개체를 만들 수 있습니다 <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="15f2f-113">However, if it does not matter which class the common language runtime loads as long as the class implements the SHA1 hash algorithm, the developer can create an object by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="15f2f-114">이 메서드는 SHA1 해시 알고리즘의 구현을 반환 해야 하는 **CryptoConfig ("system.web**. s s i s. s. s. s. s")를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-114">This method calls **System.Security.Cryptography.CryptoConfig.CreateFromName("System.Security.Cryptography.SHA1")**, which must return an implementation of the SHA1 hash algorithm.</span></span>  
  
 <span data-ttu-id="15f2f-115">기본적으로 .NET Framework에서 제공 되는 알고리즘에 대 한 짧은 이름을 포함 하기 때문에 개발자는 **CryptoConfig ("SHA1")** 를 호출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-115">The developer can also call **System.Security.Cryptography.CryptoConfig.CreateFromName("SHA1")** because, by default, cryptography configuration includes short names for the algorithms shipped in the .NET Framework.</span></span>  
  
 <span data-ttu-id="15f2f-116">사용 되는 해시 알고리즘에 상관 없이 개발자는 <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> 해시 변환을 구현 하는 개체를 반환 하는 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-116">If it does not matter which hash algorithm is used, the developer can call the <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> method, which returns an object that implements a hashing transformation.</span></span>  
  
## <a name="mapping-algorithm-names-in-configuration-files"></a><span data-ttu-id="15f2f-117">구성 파일에서 알고리즘 이름 매핑</span><span class="sxs-lookup"><span data-stu-id="15f2f-117">Mapping Algorithm Names in Configuration Files</span></span>  
 <span data-ttu-id="15f2f-118">기본적으로 런타임은 <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> 네 가지 시나리오 모두에 대해 개체를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-118">By default, the runtime returns a <xref:System.Security.Cryptography.SHA1CryptoServiceProvider> object for all four scenarios.</span></span> <span data-ttu-id="15f2f-119">그러나 컴퓨터 관리자는 마지막 두 시나리오의 메서드가 반환 하는 개체의 유형을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-119">However, a machine administrator can change the type of object that the methods in the last two scenarios return.</span></span> <span data-ttu-id="15f2f-120">이렇게 하려면 컴퓨터 구성 파일 (Machine.config)에서 사용 하려는 클래스에 친숙 한 알고리즘 이름을 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-120">To do this, you must map a friendly algorithm name to the class you want to use in the machine configuration file (Machine.config).</span></span>  
  
 <span data-ttu-id="15f2f-121">다음 예제에서는 CryptoConfig, HashAlgorithm, **("SHA1")** 및 **System.Security.Cryptography.HashAlgorithm.Create** 가 개체를 반환 하도록 런타임을 구성 하는 방법을 보여 줍니다 **.이 예제**에서는 개체를 반환 합니다. `MySHA1HashClass`</span><span class="sxs-lookup"><span data-stu-id="15f2f-121">The following example shows how to configure the runtime so that **System.Security.Cryptography.SHA1.Create**, **System.Security.CryptoConfig.CreateFromName("SHA1")**, and **System.Security.Cryptography.HashAlgorithm.Create** return a `MySHA1HashClass` object.</span></span>  
  
```xml  
<configuration>  
   <!-- Other configuration settings. -->  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass MySHA1Hash="MySHA1HashClass, MyAssembly  
                  Culture='en', PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="SHA1" class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.SHA1"  
                       class="MySHA1Hash"/>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MySHA1Hash"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
 <span data-ttu-id="15f2f-122">[<cryptoClass \> 요소](./file-schema/cryptography/cryptoclass-element.md) 에서 특성의 이름을 지정할 수 있습니다. 이전 예제에서는 특성의 이름을 지정 합니다 `MySHA1Hash` .</span><span class="sxs-lookup"><span data-stu-id="15f2f-122">You can specify the name of the attribute in the [<cryptoClass\> element](./file-schema/cryptography/cryptoclass-element.md) (the previous example names the attribute `MySHA1Hash`).</span></span> <span data-ttu-id="15f2f-123">요소의 특성 값은 **\<cryptoClass>** 공용 언어 런타임에서 클래스를 찾는 데 사용 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-123">The value of the attribute in the **\<cryptoClass>** element is a string that the common language runtime uses to find the class.</span></span> <span data-ttu-id="15f2f-124">정규화 된 [형식 이름 지정](../reflection-and-codedom/specifying-fully-qualified-type-names.md)에 지정 된 요구 사항을 충족 하는 모든 문자열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-124">You can use any string that meets the requirements specified in [Specifying Fully Qualified Type Names](../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>  
  
 <span data-ttu-id="15f2f-125">많은 알고리즘 이름을 동일한 클래스에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-125">Many algorithm names can map to the same class.</span></span> <span data-ttu-id="15f2f-126">[ \<nameEntry> 요소](./file-schema/cryptography/nameentry-element.md) 는 클래스를 친숙 한 알고리즘 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-126">The [\<nameEntry> element](./file-schema/cryptography/nameentry-element.md) maps a class to one friendly algorithm name.</span></span> <span data-ttu-id="15f2f-127">**Name** 특성은 **CryptoConfig** 메서드를 호출할 때 사용 되는 문자열 이거나 네임 스페이스에 있는 추상 암호화 클래스의 이름일 수 있습니다. <xref:System.Security.Cryptography></span><span class="sxs-lookup"><span data-stu-id="15f2f-127">The **name** attribute can be either a string that is used when calling the **System.Security.Cryptography.CryptoConfig.CreateFromName** method or the name of an abstract cryptography class in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="15f2f-128">**Class** 특성의 값은 요소에 있는 특성의 이름입니다 **\<cryptoClass>** .</span><span class="sxs-lookup"><span data-stu-id="15f2f-128">The value of the **class** attribute is the name of the attribute in the **\<cryptoClass>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="15f2f-129"><xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType>또는 **CryptoConfig ("sha1")** 메서드를 호출 하 여 SHA1 알고리즘을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-129">You can get an SHA1 algorithm by calling the <xref:System.Security.Cryptography.SHA1.Create%2A?displayProperty=nameWithType> or the **Security.CryptoConfig.CreateFromName("SHA1")** method.</span></span> <span data-ttu-id="15f2f-130">각 메서드는 SHA1 알고리즘을 구현 하는 개체만 반환 하도록 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-130">Each method guarantees only that it returns an object that implements the SHA1 algorithm.</span></span> <span data-ttu-id="15f2f-131">알고리즘의 각 식별 이름을 구성 파일의 동일한 클래스에 매핑할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15f2f-131">You do not have to map each friendly name of an algorithm to the same class in the configuration file.</span></span>  
  
 <span data-ttu-id="15f2f-132">기본 이름 및 매핑되는 클래스 목록은를 참조 하십시오 <xref:System.Security.Cryptography.CryptoConfig> .</span><span class="sxs-lookup"><span data-stu-id="15f2f-132">For a list of default names and the classes they map to, see <xref:System.Security.Cryptography.CryptoConfig>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f2f-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15f2f-133">See also</span></span>

- [<span data-ttu-id="15f2f-134">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="15f2f-134">Cryptographic Services</span></span>](../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="15f2f-135">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="15f2f-135">Configuring Cryptography Classes</span></span>](configure-cryptography-classes.md)
