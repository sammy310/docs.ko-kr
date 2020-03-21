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
ms.openlocfilehash: d31c5cd52ffe0e2a6eb5784735e76436d216444b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155221"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="66b46-102">\<암호 네임 매핑> 요소</span><span class="sxs-lookup"><span data-stu-id="66b46-102">\<cryptoNameMapping> Element</span></span>
<span data-ttu-id="66b46-103">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66b46-103">Contains mappings of classes to friendly names.</span></span>  

<span data-ttu-id="66b46-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="66b46-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="66b46-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="66b46-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="66b46-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<암호화설정>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="66b46-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="66b46-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<암호 네임 매핑>**</span><span class="sxs-lookup"><span data-stu-id="66b46-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**</span></span>

## <a name="syntax"></a><span data-ttu-id="66b46-108">구문</span><span class="sxs-lookup"><span data-stu-id="66b46-108">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66b46-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="66b46-109">Attributes and Elements</span></span>  
 <span data-ttu-id="66b46-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66b46-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66b46-111">특성</span><span class="sxs-lookup"><span data-stu-id="66b46-111">Attributes</span></span>  
 <span data-ttu-id="66b46-112">없음</span><span class="sxs-lookup"><span data-stu-id="66b46-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="66b46-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="66b46-113">Child Elements</span></span>  
  
|<span data-ttu-id="66b46-114">요소</span><span class="sxs-lookup"><span data-stu-id="66b46-114">Element</span></span>|<span data-ttu-id="66b46-115">Description</span><span class="sxs-lookup"><span data-stu-id="66b46-115">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="66b46-116">\*\* \<nameEntry>\*\* 요소에 친숙 한 이름에 매핑이 암호화 클래스의 목록을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="66b46-116">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="66b46-117">클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66b46-117">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66b46-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="66b46-118">Parent Elements</span></span>  
  
|<span data-ttu-id="66b46-119">요소</span><span class="sxs-lookup"><span data-stu-id="66b46-119">Element</span></span>|<span data-ttu-id="66b46-120">Description</span><span class="sxs-lookup"><span data-stu-id="66b46-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="66b46-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="66b46-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="66b46-122">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66b46-122">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="66b46-123">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66b46-123">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="66b46-124">\<cryptographySettings> 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66b46-124">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="66b46-125">예제</span><span class="sxs-lookup"><span data-stu-id="66b46-125">Example</span></span>  
 <span data-ttu-id="66b46-126">다음 예제에서는 \*\* \<cryptoNameMapping>\*\* 요소를 사용하여 암호화 클래스를 참조하고 런타임을 구성하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66b46-126">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="66b46-127">그런 다음 문자열 "RSA"를 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드에 전달하고 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 메서드를 `MyCryptoRSAClass` 사용하여 개체를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66b46-127">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="66b46-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="66b46-128">See also</span></span>

- [<span data-ttu-id="66b46-129">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="66b46-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="66b46-130">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="66b46-130">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="66b46-131">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="66b46-131">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="66b46-132">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="66b46-132">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
