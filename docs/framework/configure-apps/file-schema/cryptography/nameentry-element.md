---
description: '다음에 대 한 자세한 정보: <nameEntry> 요소'
title: <nameEntry> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#nameEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/cryptoNameMapping/nameEntry
helpviewer_keywords:
- <nameEntry> element
- nameEntry element
ms.assetid: 7d7535e9-4b4a-4b8c-82e2-e40dff5a7821
ms.openlocfilehash: 0ca227a2ba17a6b1e67fb75ec91aac9194b54737
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99730007"
---
# <a name="nameentry-element"></a><span data-ttu-id="0c50a-103">\<nameEntry> 요소</span><span class="sxs-lookup"><span data-stu-id="0c50a-103">\<nameEntry> Element</span></span>

<span data-ttu-id="0c50a-104">클래스 이름을 알고리즘 이름에 매핑하며, 이를 통해 하나의 클래스가 여러 이름을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c50a-104">Maps a class name to a friendly algorithm name, which allows one class to have many friendly names.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptoNameMapping>**](cryptonamemapping-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<nameEntry>**  
  
## <a name="syntax"></a><span data-ttu-id="0c50a-105">구문</span><span class="sxs-lookup"><span data-stu-id="0c50a-105">Syntax</span></span>  
  
```xml  
<nameEntry name="friendly name" Class="class name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0c50a-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0c50a-106">Attributes and Elements</span></span>  

 <span data-ttu-id="0c50a-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0c50a-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0c50a-108">특성</span><span class="sxs-lookup"><span data-stu-id="0c50a-108">Attributes</span></span>  
  
|<span data-ttu-id="0c50a-109">attribute</span><span class="sxs-lookup"><span data-stu-id="0c50a-109">Attribute</span></span>|<span data-ttu-id="0c50a-110">설명</span><span class="sxs-lookup"><span data-stu-id="0c50a-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0c50a-111">**name**</span><span class="sxs-lookup"><span data-stu-id="0c50a-111">**name**</span></span>|<span data-ttu-id="0c50a-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0c50a-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="0c50a-113">암호화 클래스가 구현 하는 알고리즘의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c50a-113">Specifies the friendly name of the algorithm that the cryptography class implements.</span></span>|  
|<span data-ttu-id="0c50a-114">**class**</span><span class="sxs-lookup"><span data-stu-id="0c50a-114">**class**</span></span>|<span data-ttu-id="0c50a-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0c50a-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="0c50a-116">요소의 **name** 특성에 대 한 값을 지정 합니다 [\<cryptoClass>](cryptoclass-element.md) .</span><span class="sxs-lookup"><span data-stu-id="0c50a-116">Specifies the value for the **name** attribute in the [\<cryptoClass>](cryptoclass-element.md) element.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0c50a-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0c50a-117">Child Elements</span></span>  

 <span data-ttu-id="0c50a-118">없음</span><span class="sxs-lookup"><span data-stu-id="0c50a-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0c50a-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0c50a-119">Parent Elements</span></span>  
  
|<span data-ttu-id="0c50a-120">요소</span><span class="sxs-lookup"><span data-stu-id="0c50a-120">Element</span></span>|<span data-ttu-id="0c50a-121">설명</span><span class="sxs-lookup"><span data-stu-id="0c50a-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0c50a-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0c50a-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.web`|<span data-ttu-id="0c50a-123">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0c50a-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c50a-124">설명</span><span class="sxs-lookup"><span data-stu-id="0c50a-124">Remarks</span></span>  

 <span data-ttu-id="0c50a-125">**Name** 특성은 네임 스페이스에 있는 추상 클래스 중 하나의 이름일 수 있습니다 <xref:System.Security.Cryptography> .</span><span class="sxs-lookup"><span data-stu-id="0c50a-125">The **name** attribute can be the name of one of the abstract classes found in the <xref:System.Security.Cryptography> namespace.</span></span> <span data-ttu-id="0c50a-126">추상 암호화 클래스에서 **Create** 메서드를 호출 하는 경우 추상 클래스 이름이 메서드에 전달 됩니다 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> .</span><span class="sxs-lookup"><span data-stu-id="0c50a-126">When you call the **Create** method on an abstract cryptography class, the abstract class name is passed to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A> method.</span></span> <span data-ttu-id="0c50a-127">**Createfromname** 은 **클래스** 특성이 나타내는 형식의 인스턴스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c50a-127">**CreateFromName** returns an instance of the type indicated by the **class** attribute.</span></span> <span data-ttu-id="0c50a-128">**이름** 특성이 RSA와 같은 짧은 이름인 경우 **createfromname** 메서드를 호출할 때 해당 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c50a-128">If the **name** attribute is a short name, such as RSA, you can use that name when calling the **CreateFromName** method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0c50a-129">예제</span><span class="sxs-lookup"><span data-stu-id="0c50a-129">Example</span></span>  

 <span data-ttu-id="0c50a-130">다음 예제에서는 요소를 사용 하 여 **\<nameEntry>** 암호화 클래스를 참조 하 고 런타임을 구성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0c50a-130">The following example shows how to use the **\<nameEntry>** element to reference a cryptography class and to configure the runtime.</span></span> <span data-ttu-id="0c50a-131">그런 다음 "RSA" 문자열을 메서드에 전달 하 <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> 고 메서드를 사용 하 여 개체를 반환할 수 있습니다 <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> `MyCryptoRSAClass` .</span><span class="sxs-lookup"><span data-stu-id="0c50a-131">You can then pass the string "RSA" to the <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> method and use the <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> method to return a `MyCryptoRSAClass` object.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0c50a-132">참조</span><span class="sxs-lookup"><span data-stu-id="0c50a-132">See also</span></span>

- [<span data-ttu-id="0c50a-133">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="0c50a-133">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="0c50a-134">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="0c50a-134">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0c50a-135">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="0c50a-135">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="0c50a-136">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="0c50a-136">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
