---
title: <mscorlib> 암호화 설정에 대 한 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: ec328bc4c63bd4754c6f975ac03e610718304245
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165154"
---
# <a name="mscorlib-element-for-cryptography-settings"></a><span data-ttu-id="f1def-102">\<mscorlib > 암호화 설정에 대 한 요소</span><span class="sxs-lookup"><span data-stu-id="f1def-102">\<mscorlib> Element for Cryptography Settings</span></span>
<span data-ttu-id="f1def-103">포함 된 [ \<cryptographySettings > 요소](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f1def-103">Contains the [\<cryptographySettings> element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).</span></span>  
  
 <span data-ttu-id="f1def-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="f1def-104">\<configuration></span></span>  
<span data-ttu-id="f1def-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="f1def-105">\<mscorlib></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1def-106">구문</span><span class="sxs-lookup"><span data-stu-id="f1def-106">Syntax</span></span>  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f1def-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f1def-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f1def-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1def-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f1def-109">특성</span><span class="sxs-lookup"><span data-stu-id="f1def-109">Attributes</span></span>  
 <span data-ttu-id="f1def-110">없음</span><span class="sxs-lookup"><span data-stu-id="f1def-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f1def-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f1def-111">Child Elements</span></span>  
  
|<span data-ttu-id="f1def-112">요소</span><span class="sxs-lookup"><span data-stu-id="f1def-112">Element</span></span>|<span data-ttu-id="f1def-113">설명</span><span class="sxs-lookup"><span data-stu-id="f1def-113">Description</span></span>|  
|-------------|-----------------|  
|`cryptographySettings`|<span data-ttu-id="f1def-114">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1def-114">Contains cryptography settings.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="f1def-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f1def-115">Parent Elements</span></span>  
  
|<span data-ttu-id="f1def-116">요소</span><span class="sxs-lookup"><span data-stu-id="f1def-116">Element</span></span>|<span data-ttu-id="f1def-117">설명</span><span class="sxs-lookup"><span data-stu-id="f1def-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f1def-118">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f1def-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="f1def-119">예제</span><span class="sxs-lookup"><span data-stu-id="f1def-119">Example</span></span>  
 <span data-ttu-id="f1def-120">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다  **\<mscorlib >** 암호화 클래스를 참조 하 고 런타임 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f1def-120">The following example shows how to use the **\<mscorlib>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="f1def-121">"RSA" 문자열을 전달할 수 있습니다는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드 및 사용법을 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 반환 하는 방법을 `MyCryptoRSAClass` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f1def-121">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f1def-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="f1def-122">See also</span></span>

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [<span data-ttu-id="f1def-123">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f1def-123">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="f1def-124">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f1def-124">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="f1def-125">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="f1def-125">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="f1def-126">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="f1def-126">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
