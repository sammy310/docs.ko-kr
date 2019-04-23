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
ms.openlocfilehash: da78140806ab8dbe7b7cb5e321e82755774ff25d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103820"
---
# <a name="cryptoclass-element"></a><span data-ttu-id="5085b-102">\<cryptoClass > 요소</span><span class="sxs-lookup"><span data-stu-id="5085b-102">\<cryptoClass> Element</span></span>
<span data-ttu-id="5085b-103">[\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 요소에 있는 이름에 매핑되는 암호화 클래스가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-103">Contains a cryptography class that has a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>  
  
 <span data-ttu-id="5085b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5085b-104">\<configuration></span></span>  
<span data-ttu-id="5085b-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="5085b-105">\<mscorlib></span></span>  
<span data-ttu-id="5085b-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="5085b-106">\<cryptographySettings></span></span>  
<span data-ttu-id="5085b-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="5085b-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="5085b-108">\<cryptoClasses></span><span class="sxs-lookup"><span data-stu-id="5085b-108">\<cryptoClasses></span></span>  
<span data-ttu-id="5085b-109">\<cryptoClass></span><span class="sxs-lookup"><span data-stu-id="5085b-109">\<cryptoClass></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5085b-110">구문</span><span class="sxs-lookup"><span data-stu-id="5085b-110">Syntax</span></span>  
  
```xml  
<cryptoClass customClassName="fully qualified type name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5085b-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5085b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5085b-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5085b-113">특성</span><span class="sxs-lookup"><span data-stu-id="5085b-113">Attributes</span></span>  
  
|<span data-ttu-id="5085b-114">특성</span><span class="sxs-lookup"><span data-stu-id="5085b-114">Attribute</span></span>|<span data-ttu-id="5085b-115">설명</span><span class="sxs-lookup"><span data-stu-id="5085b-115">Description</span></span>|  
|---------------|-----------------|  
|`customClassName`|<span data-ttu-id="5085b-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="5085b-117">암호화 클래스에 대 한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-117">Contains the information for the cryptography class.</span></span> <span data-ttu-id="5085b-118">클래스에 대 한 짧은 이름을 제공 하기 위해이 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-118">Use this attribute to provide a short name for your class.</span></span> <span data-ttu-id="5085b-119">에 지정 된 요구 사항을 충족 하는 문자열을 지정 해야 합니다 [정규화 된 형식 이름 지정](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-119">You must specify a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5085b-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5085b-120">Child Elements</span></span>  
 <span data-ttu-id="5085b-121">없음</span><span class="sxs-lookup"><span data-stu-id="5085b-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5085b-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5085b-122">Parent Elements</span></span>  
  
|<span data-ttu-id="5085b-123">요소</span><span class="sxs-lookup"><span data-stu-id="5085b-123">Element</span></span>|<span data-ttu-id="5085b-124">설명</span><span class="sxs-lookup"><span data-stu-id="5085b-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5085b-125">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptoClasses`|<span data-ttu-id="5085b-126">[\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) 요소에 있는 이름에 매핑되는 암호화 클래스의 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-126">Contains a list of cryptography classes that have a mapping to a friendly name in the [\<nameEntry>](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md) element.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="5085b-127">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-127">Contains cryptography settings.</span></span>|  
|`cryptoNameMapping`|<span data-ttu-id="5085b-128">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-128">Contains mappings of classes to friendly names.</span></span>|  
|`mscorlib`|<span data-ttu-id="5085b-129">[\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-129">Contains the [\<cryptographySettings>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md) element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5085b-130">예제</span><span class="sxs-lookup"><span data-stu-id="5085b-130">Example</span></span>  
 <span data-ttu-id="5085b-131">다음 방법을 보여 주는 예제는  **\<cryptoClass >** 암호화 클래스를 참조 하 고 런타임 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-131">The following example shows how use the **\<cryptoClass>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="5085b-132">"RSA" 문자열을 전달할 수 있습니다는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드 및 사용법을 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 반환 하는 방법을 `MyCryptoRSAClass` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="5085b-132">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5085b-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="5085b-133">See also</span></span>

- [<span data-ttu-id="5085b-134">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="5085b-134">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="5085b-135">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="5085b-135">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="5085b-136">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="5085b-136">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="5085b-137">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="5085b-137">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
