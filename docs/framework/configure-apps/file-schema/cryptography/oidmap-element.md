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
ms.openlocfilehash: 80564c5895e08884f78a4ec7c955ecdb11126e35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705170"
---
# <a name="oidmap-element"></a><span data-ttu-id="329e6-102">\<oidMap > 요소</span><span class="sxs-lookup"><span data-stu-id="329e6-102">\<oidMap> Element</span></span>
<span data-ttu-id="329e6-103">ASN.1 클래스 개체 식별자 (OID) 매핑이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="329e6-103">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>  
  
 <span data-ttu-id="329e6-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="329e6-104">\<configuration></span></span>  
<span data-ttu-id="329e6-105">\<mscorlib></span><span class="sxs-lookup"><span data-stu-id="329e6-105">\<mscorlib></span></span>  
<span data-ttu-id="329e6-106">\<cryptographySettings></span><span class="sxs-lookup"><span data-stu-id="329e6-106">\<cryptographySettings></span></span>  
<span data-ttu-id="329e6-107">\<oidMap></span><span class="sxs-lookup"><span data-stu-id="329e6-107">\<oidMap></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329e6-108">구문</span><span class="sxs-lookup"><span data-stu-id="329e6-108">Syntax</span></span>  
  
```xml  
<oidMap>   
</oidMap>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="329e6-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="329e6-109">Attributes and Elements</span></span>  
 <span data-ttu-id="329e6-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="329e6-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="329e6-111">특성</span><span class="sxs-lookup"><span data-stu-id="329e6-111">Attributes</span></span>  
 <span data-ttu-id="329e6-112">없음</span><span class="sxs-lookup"><span data-stu-id="329e6-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="329e6-113">자식 요소</span><span class="sxs-lookup"><span data-stu-id="329e6-113">Child Elements</span></span>  
  
|<span data-ttu-id="329e6-114">요소</span><span class="sxs-lookup"><span data-stu-id="329e6-114">Element</span></span>|<span data-ttu-id="329e6-115">설명</span><span class="sxs-lookup"><span data-stu-id="329e6-115">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="329e6-116">\<oidEntry></span><span class="sxs-lookup"><span data-stu-id="329e6-116">\<oidEntry></span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|<span data-ttu-id="329e6-117">ASN.1 OID 이름에 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="329e6-117">Maps an ASN.1 OID to a friendly name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="329e6-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="329e6-118">Parent Elements</span></span>  
  
|<span data-ttu-id="329e6-119">요소</span><span class="sxs-lookup"><span data-stu-id="329e6-119">Element</span></span>|<span data-ttu-id="329e6-120">설명</span><span class="sxs-lookup"><span data-stu-id="329e6-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="329e6-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="329e6-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="329e6-122">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="329e6-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="329e6-123">포함 된 `cryptographySettings` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="329e6-123">Contains the `cryptographySettings` element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="329e6-124">예제</span><span class="sxs-lookup"><span data-stu-id="329e6-124">Example</span></span>  
 <span data-ttu-id="329e6-125">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다  **\<oidMap >** 해당 해시 알고리즘의 구현에 RIPEMD-160 해시 알고리즘의 OID의 매핑을 포함 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="329e6-125">The following example shows how to use the **\<oidMap>** element to contain a mapping of an OID for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="329e6-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="329e6-126">See also</span></span>

- [<span data-ttu-id="329e6-127">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="329e6-127">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="329e6-128">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="329e6-128">Cryptography Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [<span data-ttu-id="329e6-129">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="329e6-129">Cryptographic Services</span></span>](../../../../../docs/standard/security/cryptographic-services.md)
- [<span data-ttu-id="329e6-130">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="329e6-130">Configuring Cryptography Classes</span></span>](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
- [<span data-ttu-id="329e6-131">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="329e6-131">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../../../../docs/framework/configure-apps/map-object-identifiers-to-cryptography-algorithms.md)
