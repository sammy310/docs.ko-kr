---
description: '다음에 대 한 자세한 정보: <oidMap> 요소'
title: <oidMap> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidMap
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap
helpviewer_keywords:
- <oidMap> element
- oidMap element
ms.assetid: 7f0c2246-c070-4748-b96a-2f66a296c539
ms.openlocfilehash: 9a71cc54546f49fcada90a0f9915d44d1fc65e89
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729994"
---
# <a name="oidmap-element"></a><span data-ttu-id="314f2-103">\<oidMap> 요소</span><span class="sxs-lookup"><span data-stu-id="314f2-103">\<oidMap> Element</span></span>

<span data-ttu-id="314f2-104">클래스에 대 한 OID (개체 식별자) 매핑을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="314f2-104">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidMap>**

## <a name="syntax"></a><span data-ttu-id="314f2-105">구문</span><span class="sxs-lookup"><span data-stu-id="314f2-105">Syntax</span></span>  
  
```xml  
<oidMap>
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="314f2-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="314f2-106">Attributes and Elements</span></span>  

 <span data-ttu-id="314f2-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="314f2-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="314f2-108">특성</span><span class="sxs-lookup"><span data-stu-id="314f2-108">Attributes</span></span>  

 <span data-ttu-id="314f2-109">없음</span><span class="sxs-lookup"><span data-stu-id="314f2-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="314f2-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="314f2-110">Child Elements</span></span>  
  
|<span data-ttu-id="314f2-111">요소</span><span class="sxs-lookup"><span data-stu-id="314f2-111">Element</span></span>|<span data-ttu-id="314f2-112">설명</span><span class="sxs-lookup"><span data-stu-id="314f2-112">Description</span></span>|  
|-------------|-----------------|  
|[\<oidEntry>](oidentry-element.md)|<span data-ttu-id="314f2-113">ASN OID를 친숙 한 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="314f2-113">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="314f2-114">부모 요소</span><span class="sxs-lookup"><span data-stu-id="314f2-114">Parent Elements</span></span>  
  
|<span data-ttu-id="314f2-115">요소</span><span class="sxs-lookup"><span data-stu-id="314f2-115">Element</span></span>|<span data-ttu-id="314f2-116">설명</span><span class="sxs-lookup"><span data-stu-id="314f2-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="314f2-117">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="314f2-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="314f2-118">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314f2-118">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="314f2-119">요소를 포함 `cryptographySettings` 합니다.</span><span class="sxs-lookup"><span data-stu-id="314f2-119">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="314f2-120">예제</span><span class="sxs-lookup"><span data-stu-id="314f2-120">Example</span></span>  

 <span data-ttu-id="314f2-121">다음 예제에서는 요소를 사용 하 여 **\<oidMap>** RIPEMD-160 해시 알고리즘에 대 한 OID 매핑을 해당 해시 알고리즘의 구현에 포함 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="314f2-121">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="314f2-122">참조</span><span class="sxs-lookup"><span data-stu-id="314f2-122">See also</span></span>

- [<span data-ttu-id="314f2-123">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="314f2-123">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="314f2-124">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="314f2-124">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="314f2-125">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="314f2-125">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="314f2-126">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="314f2-126">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="314f2-127">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="314f2-127">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
