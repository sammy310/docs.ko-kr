---
title: <cryptoClass> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/cryptoClasses/cryptoClass
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptoClass
helpviewer_keywords:
- cryptoClass element
- <cryptoClass> element
ms.assetid: 03db52ef-010e-44ea-b6fd-b9c900ecad50
ms.openlocfilehash: 4872fbd6fa043902e8c69f158bee5d0c915ec83a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088654"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="fc774-102">\<cryptoClass> 요소</span><span class="sxs-lookup"><span data-stu-id="fc774-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="fc774-103">요소의 이름에 매핑되는 암호화 클래스를 포함 [\<nameEntry>](nameentry-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoClasses>**](cryptoclasses-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptoClass>**

## <a name="syntax"></a><span data-ttu-id="fc774-104">구문</span><span class="sxs-lookup"><span data-stu-id="fc774-104">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc774-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fc774-105">Attributes and Elements</span></span>  
 <span data-ttu-id="fc774-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc774-107">특성</span><span class="sxs-lookup"><span data-stu-id="fc774-107">Attributes</span></span>  
  
|<span data-ttu-id="fc774-108">attribute</span><span class="sxs-lookup"><span data-stu-id="fc774-108">Attribute</span></span>|<span data-ttu-id="fc774-109">Description</span><span class="sxs-lookup"><span data-stu-id="fc774-109">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="fc774-110">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="fc774-111">암호화 클래스에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-111">Contains the information for the cryptography class.</span></span> <span data-ttu-id="fc774-112">클래스에 짧은 이름을 제공 하려면이 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-112">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="fc774-113">정규화 된 [형식 이름 지정](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md)에 지정 된 요구 사항을 충족 하는 문자열을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-113">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc774-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fc774-114">Child Elements</span></span>  
 <span data-ttu-id="fc774-115">없음</span><span class="sxs-lookup"><span data-stu-id="fc774-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fc774-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fc774-116">Parent Elements</span></span>  
  
|<span data-ttu-id="fc774-117">요소</span><span class="sxs-lookup"><span data-stu-id="fc774-117">Element</span></span>|<span data-ttu-id="fc774-118">Description</span><span class="sxs-lookup"><span data-stu-id="fc774-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fc774-119">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="fc774-120">요소의 이름에 매핑되는 암호화 클래스의 목록을 포함 [\<nameEntry>](nameentry-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-120">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="fc774-121">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-121">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="fc774-122">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-122">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="fc774-123">요소를 포함 [\<cryptographySettings>](cryptographysettings-element.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-123">Contains the [\<cryptographySettings>](cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc774-124">예제</span><span class="sxs-lookup"><span data-stu-id="fc774-124">Example</span></span>  
 <span data-ttu-id="fc774-125">다음 예제에서는 요소를 사용 하 여 **\<cryptoClass>** 암호화 클래스를 참조 하 고 런타임을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc774-125">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="fc774-126">그런 다음 "RSA" 문자열을 메서드에 전달 하 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 고 메서드를 사용 하 여 개체를 반환할 수 있습니다 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> `MyCryptoRSAClass` .</span><span class="sxs-lookup"><span data-stu-id="fc774-126">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fc774-127">참조</span><span class="sxs-lookup"><span data-stu-id="fc774-127">See also</span></span>

- [<span data-ttu-id="fc774-128">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="fc774-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="fc774-129">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="fc774-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fc774-130">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="fc774-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="fc774-131">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="fc774-131">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
