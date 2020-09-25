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
ms.openlocfilehash: 9ffae33a3c8a06d6cfcabf5a58b7d72baeda79c5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201800"
---
# <a name="cryptonamemapping-element"></a><span data-ttu-id="9bd1c-102">\<cryptoNameMapping> 요소</span><span class="sxs-lookup"><span data-stu-id="9bd1c-102">\<cryptoNameMapping> Element</span></span>

<span data-ttu-id="9bd1c-103">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd1c-103">Contains mappings of classes to friendly names.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoNameMapping>**

## <a name="syntax"></a><span data-ttu-id="9bd1c-104">구문</span><span class="sxs-lookup"><span data-stu-id="9bd1c-104">Syntax</span></span>  
  
```xml  
      <cryptoNameMapping>
</cryptoNameMapping>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9bd1c-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9bd1c-105">Attributes and Elements</span></span>  

 <span data-ttu-id="9bd1c-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd1c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9bd1c-107">특성</span><span class="sxs-lookup"><span data-stu-id="9bd1c-107">Attributes</span></span>  

 <span data-ttu-id="9bd1c-108">없음</span><span class="sxs-lookup"><span data-stu-id="9bd1c-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9bd1c-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9bd1c-109">Child Elements</span></span>  
  
|<span data-ttu-id="9bd1c-110">요소</span><span class="sxs-lookup"><span data-stu-id="9bd1c-110">Element</span></span>|<span data-ttu-id="9bd1c-111">설명</span><span class="sxs-lookup"><span data-stu-id="9bd1c-111">Description</span></span>|  
|-------------|-----------------|  
|`cryptoClasses`|<span data-ttu-id="9bd1c-112">요소의 이름에 매핑되는 암호화 클래스의 목록을 포함 **\<nameEntry>** 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd1c-112">Contains a list of cryptography classes that have a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
|`nameEntry`|<span data-ttu-id="9bd1c-113">클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd1c-113">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9bd1c-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9bd1c-114">Parent Elements</span></span>  
  
|<span data-ttu-id="9bd1c-115">요소</span><span class="sxs-lookup"><span data-stu-id="9bd1c-115">Element</span></span>|<span data-ttu-id="9bd1c-116">설명</span><span class="sxs-lookup"><span data-stu-id="9bd1c-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9bd1c-117">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd1c-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="9bd1c-118">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd1c-118">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="9bd1c-119">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd1c-119">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="9bd1c-120">요소를 포함 \<cryptographySettings> 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd1c-120">Contains the \<cryptographySettings> element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9bd1c-121">예제</span><span class="sxs-lookup"><span data-stu-id="9bd1c-121">Example</span></span>  

 <span data-ttu-id="9bd1c-122">다음 예제에서는 요소를 사용 하 여 **\<cryptoNameMapping>** 암호화 클래스를 참조 하 고 런타임을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bd1c-122">The following example shows how to use the **\<cryptoNameMapping>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="9bd1c-123">그런 다음 "RSA" 문자열을 메서드에 전달 하 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 고 메서드를 사용 하 여 개체를 반환할 수 있습니다 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> `MyCryptoRSAClass` .</span><span class="sxs-lookup"><span data-stu-id="9bd1c-123">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9bd1c-124">참조</span><span class="sxs-lookup"><span data-stu-id="9bd1c-124">See also</span></span>

- [<span data-ttu-id="9bd1c-125">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="9bd1c-125">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="9bd1c-126">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="9bd1c-126">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="9bd1c-127">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="9bd1c-127">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="9bd1c-128">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="9bd1c-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
