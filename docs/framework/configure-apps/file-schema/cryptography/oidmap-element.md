---
title: <oidMap> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: a28eaf68fe1e6ab3f26592eee5ae2d0f2e7a3256
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155169"
---
# <a name="oidmap-element"></a><span data-ttu-id="518bb-102">\<oidMap> 요소</span><span class="sxs-lookup"><span data-stu-id="518bb-102">\<oidMap> Element</span></span>
<span data-ttu-id="518bb-103">클래스에 ASN.1 개체 식별자(OID) 매핑을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="518bb-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

<span data-ttu-id="518bb-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="518bb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="518bb-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="518bb-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>\
<span data-ttu-id="518bb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<암호화설정>**](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="518bb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>\
<span data-ttu-id="518bb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span><span class="sxs-lookup"><span data-stu-id="518bb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**</span></span>

## <a name="syntax"></a><span data-ttu-id="518bb-108">구문</span><span class="sxs-lookup"><span data-stu-id="518bb-108">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="518bb-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="518bb-109">Attributes and Elements</span></span>  
 <span data-ttu-id="518bb-110">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="518bb-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="518bb-111">특성</span><span class="sxs-lookup"><span data-stu-id="518bb-111">Attributes</span></span>  
 <span data-ttu-id="518bb-112">없음</span><span class="sxs-lookup"><span data-stu-id="518bb-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="518bb-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="518bb-113">Child Elements</span></span>  
  
|<span data-ttu-id="518bb-114">요소</span><span class="sxs-lookup"><span data-stu-id="518bb-114">Element</span></span>|<span data-ttu-id="518bb-115">Description</span><span class="sxs-lookup"><span data-stu-id="518bb-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="518bb-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="518bb-116">\<oidEntry></span></span>](oidentry-element.md)|<span data-ttu-id="518bb-117">ASN.1 OID를 친숙한 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="518bb-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="518bb-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="518bb-118">Parent Elements</span></span>  
  
|<span data-ttu-id="518bb-119">요소</span><span class="sxs-lookup"><span data-stu-id="518bb-119">Element</span></span>|<span data-ttu-id="518bb-120">Description</span><span class="sxs-lookup"><span data-stu-id="518bb-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="518bb-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="518bb-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="518bb-122">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518bb-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="518bb-123">요소를 `cryptographySettings` 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="518bb-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="518bb-124">예제</span><span class="sxs-lookup"><span data-stu-id="518bb-124">Example</span></span>  
 <span data-ttu-id="518bb-125">다음 예제에서는 \*\* \<oidMap>\*\* 요소를 사용하여 RIPEMD-160 해시 알고리즘에 대한 OID의 매핑을 해당 해시 알고리즘의 구현에 포함하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="518bb-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RIPEMD-160" class="MyCrypto"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"  name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="518bb-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="518bb-126">See also</span></span>

- [<span data-ttu-id="518bb-127">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="518bb-127">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="518bb-128">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="518bb-128">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="518bb-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="518bb-129">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="518bb-130">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="518bb-130">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="518bb-131">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="518bb-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
