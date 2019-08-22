---
title: <cryptoNameMapping> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoNameMapping
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping
helpviewer_keywords:
- <cryptoNameMapping> element
- cryptoNameMapping element
ms.assetid: c59c9494-149b-4ce6-b38d-371f896ae85c
ms.openlocfilehash: c2652ac73c1d55f09a1f8511603003dc6d7291f9
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659638"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="c064d-102">\<cryptoNameMapping > 요소</span><span class="sxs-lookup"><span data-stu-id="c064d-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="c064d-103">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c064d-103">Contains mappings of classes to friendly names.</span></span>  
  
 <span data-ttu-id="c064d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="c064d-104">\<configuration></span></span>  
<span data-ttu-id="c064d-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="c064d-105">\<mscorlib></span></span>  
<span data-ttu-id="c064d-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="c064d-106">\<cryptographySettings></span></span>  
<span data-ttu-id="c064d-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="c064d-107">\<cryptoNameMapping></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c064d-108">구문</span><span class="sxs-lookup"><span data-stu-id="c064d-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>   
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c064d-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c064d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="c064d-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c064d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c064d-111">특성</span><span class="sxs-lookup"><span data-stu-id="c064d-111">Attributes</span></span>  
 <span data-ttu-id="c064d-112">없음</span><span class="sxs-lookup"><span data-stu-id="c064d-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c064d-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c064d-113">Child Elements</span></span>  
  
|<span data-ttu-id="c064d-114">요소</span><span class="sxs-lookup"><span data-stu-id="c064d-114">Element</span></span>|<span data-ttu-id="c064d-115">설명</span><span class="sxs-lookup"><span data-stu-id="c064d-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="c064d-116">**\<nameEntry>** 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c064d-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="c064d-117">클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c064d-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c064d-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c064d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c064d-119">요소</span><span class="sxs-lookup"><span data-stu-id="c064d-119">Element</span></span>|<span data-ttu-id="c064d-120">설명</span><span class="sxs-lookup"><span data-stu-id="c064d-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c064d-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="c064d-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="c064d-122">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c064d-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="c064d-123">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c064d-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="c064d-124">Cryptographysettings > 요소를 \<포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c064d-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="c064d-125">예제</span><span class="sxs-lookup"><span data-stu-id="c064d-125">Example</span></span>  
 <span data-ttu-id="c064d-126">다음 예제에서는  **\<cryptoNameMapping >** 요소를 사용 하 여 암호화 클래스를 참조 하 고 런타임을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c064d-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="c064d-127">그런 다음 "RSA" <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 문자열을 메서드에 전달 하 고 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 메서드를 사용 하 여 `MyCryptoRSAClass` 개체를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c064d-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c064d-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="c064d-128">See also</span></span>

- [<span data-ttu-id="c064d-129">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="c064d-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="c064d-130">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="c064d-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c064d-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="c064d-131">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="c064d-132">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="c064d-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
