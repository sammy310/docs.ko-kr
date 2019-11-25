---
title: <cryptographySettings> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: ca0a9a4b37f28eb03f58de4fd9b120cb7e654e0c
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088650"
---
# <a name="cryptographysettings-element"></a><span data-ttu-id="dff2d-102">\<cryptographySettings > 요소</span><span class="sxs-lookup"><span data-stu-id="dff2d-102">\<cryptographySettings> Element</span></span>
<span data-ttu-id="dff2d-103">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dff2d-103">Contains cryptography settings.</span></span>  

<span data-ttu-id="dff2d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dff2d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dff2d-105">[**mscorlib >\<** ](mscorlib-element-for-cryptography-settings.md) &nbsp;&nbsp;</span><span class="sxs-lookup"><span data-stu-id="dff2d-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="dff2d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<cryptographySettings >**</span><span class="sxs-lookup"><span data-stu-id="dff2d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<cryptographySettings>**</span></span>

## <a name="syntax"></a><span data-ttu-id="dff2d-107">구문</span><span class="sxs-lookup"><span data-stu-id="dff2d-107">Syntax</span></span>  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dff2d-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dff2d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dff2d-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dff2d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dff2d-110">특성</span><span class="sxs-lookup"><span data-stu-id="dff2d-110">Attributes</span></span>  
 <span data-ttu-id="dff2d-111">없음.</span><span class="sxs-lookup"><span data-stu-id="dff2d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dff2d-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dff2d-112">Child Elements</span></span>  
  
|<span data-ttu-id="dff2d-113">요소</span><span class="sxs-lookup"><span data-stu-id="dff2d-113">Element</span></span>|<span data-ttu-id="dff2d-114">설명</span><span class="sxs-lookup"><span data-stu-id="dff2d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dff2d-115">\<cryptoNameMapping ></span><span class="sxs-lookup"><span data-stu-id="dff2d-115">\<cryptoNameMapping></span></span>](cryptonamemapping-element.md)|<span data-ttu-id="dff2d-116">이름에 대한 클래스의 매핑이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dff2d-116">Contains mappings of classes to friendly names.</span></span>|  
|[<span data-ttu-id="dff2d-117">\<oidMap ></span><span class="sxs-lookup"><span data-stu-id="dff2d-117">\<oidMap></span></span>](oidmap-element.md)|<span data-ttu-id="dff2d-118">클래스에 대 한 OID (개체 식별자) 매핑을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dff2d-118">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dff2d-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dff2d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dff2d-120">요소</span><span class="sxs-lookup"><span data-stu-id="dff2d-120">Element</span></span>|<span data-ttu-id="dff2d-121">설명</span><span class="sxs-lookup"><span data-stu-id="dff2d-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dff2d-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dff2d-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`mscorlib`|<span data-ttu-id="dff2d-123">`cryptographySettings` 요소를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dff2d-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dff2d-124">예제</span><span class="sxs-lookup"><span data-stu-id="dff2d-124">Example</span></span>  
 <span data-ttu-id="dff2d-125">다음 예에서는 **\<cryptographySettings >** 요소를 사용 하 여 암호화 이름 매핑과 OID 매핑을 포함 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dff2d-125">The following example shows how use the **\<cryptographySettings>** element to contain cryptography name mappings and OID mappings.</span></span> <span data-ttu-id="dff2d-126">이 예제에서는 <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType>에서 `MyHashClass` 개체를 반환 하 고 `MyCryptoClass` 클래스가 개체 식별자 1.3.36.2.1에 매핑되도록 런타임을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dff2d-126">This example configures the runtime so that <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> returns a `MyHashClass` object and the `MyCryptoClass` class maps to the object identifier 1.3.36.2.1.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dff2d-127">참조</span><span class="sxs-lookup"><span data-stu-id="dff2d-127">See also</span></span>

- [<span data-ttu-id="dff2d-128">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="dff2d-128">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="dff2d-129">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="dff2d-129">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dff2d-130">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="dff2d-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
