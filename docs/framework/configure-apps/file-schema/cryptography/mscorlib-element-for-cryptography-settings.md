---
title: 암호화 설정에 대한 <mscorlib> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: d1d805f7154c18dba2dcd4eb7228cc200d8da811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155183"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="363ab-102">\<암호화 설정에 대한 mscorlib> 요소</span><span class="sxs-lookup"><span data-stu-id="363ab-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="363ab-103">[ \<암호화를 포함설정> 요소입니다.](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="363ab-103">Contains the [\<cryptographySettings> element](cryptographysettings-element.md).</span></span>  
  
[<span data-ttu-id="363ab-104">**\<구성>**</span><span class="sxs-lookup"><span data-stu-id="363ab-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="363ab-105">&nbsp;&nbsp;**\<mscorlib>**</span><span class="sxs-lookup"><span data-stu-id="363ab-105">&nbsp;&nbsp;**\<mscorlib>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="363ab-106">구문</span><span class="sxs-lookup"><span data-stu-id="363ab-106">Syntax</span></span>  
  
```xml  
      <mscorlib>
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="363ab-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="363ab-107">Attributes and Elements</span></span>  
 <span data-ttu-id="363ab-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="363ab-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="363ab-109">특성</span><span class="sxs-lookup"><span data-stu-id="363ab-109">Attributes</span></span>  
 <span data-ttu-id="363ab-110">없음</span><span class="sxs-lookup"><span data-stu-id="363ab-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="363ab-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="363ab-111">Child Elements</span></span>  
  
|<span data-ttu-id="363ab-112">요소</span><span class="sxs-lookup"><span data-stu-id="363ab-112">Element</span></span>|<span data-ttu-id="363ab-113">Description</span><span class="sxs-lookup"><span data-stu-id="363ab-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="363ab-114">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="363ab-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="363ab-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="363ab-115">Parent Elements</span></span>  
  
|<span data-ttu-id="363ab-116">요소</span><span class="sxs-lookup"><span data-stu-id="363ab-116">Element</span></span>|<span data-ttu-id="363ab-117">Description</span><span class="sxs-lookup"><span data-stu-id="363ab-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="363ab-118">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="363ab-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="363ab-119">예제</span><span class="sxs-lookup"><span data-stu-id="363ab-119">Example</span></span>  
 <span data-ttu-id="363ab-120">다음 예제에서는 \*\* \<mscorlib>\*\* 요소를 사용하여 암호화 클래스를 참조하고 런타임을 구성하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="363ab-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="363ab-121">그런 다음 문자열 "RSA"를 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드에 전달하고 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 메서드를 `MyCryptoRSAClass` 사용하여 개체를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="363ab-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="363ab-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="363ab-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="363ab-123">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="363ab-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="363ab-124">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="363ab-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="363ab-125">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="363ab-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="363ab-126">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="363ab-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
