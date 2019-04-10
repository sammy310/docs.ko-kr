---
title: <nameEntry> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: 97521ba9073820beeea62f5fc7cab480b5422fb0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225328"
---
# <a name="nameentry-element"></a><span data-ttu-id="05bd5-102">\<m t r y > 요소</span><span class="sxs-lookup"><span data-stu-id="05bd5-102">\<nameEntry> Element</span></span>
<span data-ttu-id="05bd5-103">클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-103">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
 <span data-ttu-id="05bd5-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="05bd5-104">\<configuration></span></span>  
<span data-ttu-id="05bd5-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="05bd5-105">\<mscorlib></span></span>  
<span data-ttu-id="05bd5-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="05bd5-106">\<cryptographySettings></span></span>  
<span data-ttu-id="05bd5-107">\<cryptoNameMapping></span><span class="sxs-lookup"><span data-stu-id="05bd5-107">\<cryptoNameMapping></span></span>  
<span data-ttu-id="05bd5-108">\<nameEntry></span><span class="sxs-lookup"><span data-stu-id="05bd5-108">\<nameEntry></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05bd5-109">구문</span><span class="sxs-lookup"><span data-stu-id="05bd5-109">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05bd5-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="05bd5-110">Attributes and Elements</span></span>  
 <span data-ttu-id="05bd5-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05bd5-112">특성</span><span class="sxs-lookup"><span data-stu-id="05bd5-112">Attributes</span></span>  
  
|<span data-ttu-id="05bd5-113">특성</span><span class="sxs-lookup"><span data-stu-id="05bd5-113">Attribute</span></span>|<span data-ttu-id="05bd5-114">설명</span><span class="sxs-lookup"><span data-stu-id="05bd5-114">Description</span></span>|  
|---------------|-----------------|  
|**<span data-ttu-id="05bd5-115">name</span><span class="sxs-lookup"><span data-stu-id="05bd5-115">name</span></span>**|<span data-ttu-id="05bd5-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="05bd5-117">암호화 클래스를 구현 하는 알고리즘의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-117">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|**<span data-ttu-id="05bd5-118">클래스</span><span class="sxs-lookup"><span data-stu-id="05bd5-118">class</span></span>**|<span data-ttu-id="05bd5-119">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="05bd5-120">에 대 한 값을 지정 합니다 **이름** 특성을 [ \<cryptoClass >](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-120">Specifies the value for the **name** attribute in the [\<cryptoClass>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05bd5-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="05bd5-121">Child Elements</span></span>  
 <span data-ttu-id="05bd5-122">없음</span><span class="sxs-lookup"><span data-stu-id="05bd5-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05bd5-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="05bd5-123">Parent Elements</span></span>  
  
|<span data-ttu-id="05bd5-124">요소</span><span class="sxs-lookup"><span data-stu-id="05bd5-124">Element</span></span>|<span data-ttu-id="05bd5-125">설명</span><span class="sxs-lookup"><span data-stu-id="05bd5-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="05bd5-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="05bd5-127">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05bd5-128">설명</span><span class="sxs-lookup"><span data-stu-id="05bd5-128">Remarks</span></span>  
 <span data-ttu-id="05bd5-129">**이름을** 특성에 있는 추상 클래스 중 하나의 이름을 수는 <xref:System.Security.Cryptography> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-129">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="05bd5-130">호출 하는 경우는 **만들기** 추상 암호화 클래스에 메서드를 추상 클래스 이름에 전달 되는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="05bd5-130">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="05bd5-131">**CreateFromName** 하 여 지정 된 형식의 인스턴스를 반환 합니다 **클래스** 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-131">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="05bd5-132">경우는 **이름** 특성은 약식 이름, RSA와 같은 이름을 사용할 수 있습니다는 호출 하는 경우를 **CreateFromName** 메서드.</span><span class="sxs-lookup"><span data-stu-id="05bd5-132">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05bd5-133">예제</span><span class="sxs-lookup"><span data-stu-id="05bd5-133">Example</span></span>  
 <span data-ttu-id="05bd5-134">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다  **\<m t r y >** 암호화 클래스를 참조 하 고 런타임 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-134">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="05bd5-135">"RSA" 문자열을 전달할 수 있습니다는 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 메서드 및 사용법을 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> 반환 하는 방법을 `MyCryptoRSAClass` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="05bd5-135">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="05bd5-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="05bd5-136">See also</span></span>

- [<span data-ttu-id="05bd5-137">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="05bd5-137">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="05bd5-138">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="05bd5-138">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="05bd5-139">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="05bd5-139">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="05bd5-140">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="05bd5-140">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
