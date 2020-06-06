---
title: <cryptoClasses> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClasses
helpviewer_keywords:
- <cryptoClasses> element
- cryptoClasses element
ms.assetid: 290d5f96-946d-4f02-babb-1d31ec0b8295
ms.openlocfilehash: c93fadf51297d59ab499e25de283700364903049
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79155248"
---
# <a name="cryptoclasses-element"></a><span data-ttu-id="e2c27-102">\<cryptoClasses> 요소</span><span class="sxs-lookup"><span data-stu-id="e2c27-102">\<cryptoClasses> Element</span></span>
<span data-ttu-id="e2c27-103">요소의 이름에 매핑되는 암호화 클래스의 목록을 포함 [\<nameEntry>](nameentry-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c27-103">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClasses>**  
  
## <a name="syntax"></a><span data-ttu-id="e2c27-104">구문</span><span class="sxs-lookup"><span data-stu-id="e2c27-104">Syntax</span></span>  
  
```xml  
<cryptoClasses>
</cryptoClasses>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e2c27-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e2c27-105">Attributes and Elements</span></span>  
 <span data-ttu-id="e2c27-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c27-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e2c27-107">특성</span><span class="sxs-lookup"><span data-stu-id="e2c27-107">Attributes</span></span>  
 <span data-ttu-id="e2c27-108">없음</span><span class="sxs-lookup"><span data-stu-id="e2c27-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e2c27-109">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e2c27-109">Child Elements</span></span>  
  
|<span data-ttu-id="e2c27-110">요소</span><span class="sxs-lookup"><span data-stu-id="e2c27-110">Element</span></span>|<span data-ttu-id="e2c27-111">Description</span><span class="sxs-lookup"><span data-stu-id="e2c27-111">Description</span></span>|  
|-------------|-----------------|  
|[\<cryptoClass>](cryptoclass-element.md)|<span data-ttu-id="e2c27-112">요소의 이름에 매핑되는 암호화 클래스를 포함 **\<nameEntry>** 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c27-112">Contains a cryptography class that has a mapping to a friendly name in the **\<nameEntry>** element.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e2c27-113">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e2c27-113">Parent Elements</span></span>  
  
|<span data-ttu-id="e2c27-114">요소</span><span class="sxs-lookup"><span data-stu-id="e2c27-114">Element</span></span>|<span data-ttu-id="e2c27-115">Description</span><span class="sxs-lookup"><span data-stu-id="e2c27-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e2c27-116">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e2c27-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="e2c27-117">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2c27-117">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="e2c27-118">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2c27-118">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="e2c27-119">요소를 포함 `cryptographySettings` 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2c27-119">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e2c27-120">예제</span><span class="sxs-lookup"><span data-stu-id="e2c27-120">Example</span></span>  
 <span data-ttu-id="e2c27-121">다음 예제에서는 요소를 사용 하 여 **\<cryptoClass>** 암호화 클래스를 참조 하 고 런타임을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2c27-121">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="e2c27-122">그런 다음 "RSA" 문자열을 메서드에 전달 하 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 고 메서드를 사용 하 여 개체를 반환할 수 있습니다 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> `MyCryptoRSAClass` .</span><span class="sxs-lookup"><span data-stu-id="e2c27-122">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <!-- Other cryptography classes go here. -->  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
             <!-- Mappings to other cryptography classes go here. -->  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2c27-123">참조</span><span class="sxs-lookup"><span data-stu-id="e2c27-123">See also</span></span>

- <xref:System.Security.Cryptography>
- [<span data-ttu-id="e2c27-124">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="e2c27-124">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="e2c27-125">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e2c27-125">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e2c27-126">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="e2c27-126">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="e2c27-127">CryptoConfig. CreateFromName</span><span class="sxs-lookup"><span data-stu-id="e2c27-127">System.Security.Cryptography.CryptoConfig.CreateFromName</span></span>](xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A)
- [<span data-ttu-id="e2c27-128">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="e2c27-128">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
