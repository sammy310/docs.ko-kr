---
description: '다음에 대 한 자세한 정보: <oidEntry> 요소'
title: <oidEntry> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: d5fe22018377e247ffa0b6addb58cbeee7119e66
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698754"
---
# <a name="oidentry-element"></a><span data-ttu-id="44f0d-103">\<oidEntry> 요소</span><span class="sxs-lookup"><span data-stu-id="44f0d-103">\<oidEntry> Element</span></span>

<span data-ttu-id="44f0d-104">ASN.1 OID(개체 식별자)를 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-104">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**

## <a name="syntax"></a><span data-ttu-id="44f0d-105">구문</span><span class="sxs-lookup"><span data-stu-id="44f0d-105">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="44f0d-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="44f0d-106">Attributes and Elements</span></span>  

 <span data-ttu-id="44f0d-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="44f0d-108">특성</span><span class="sxs-lookup"><span data-stu-id="44f0d-108">Attributes</span></span>  
  
|<span data-ttu-id="44f0d-109">attribute</span><span class="sxs-lookup"><span data-stu-id="44f0d-109">Attribute</span></span>|<span data-ttu-id="44f0d-110">설명</span><span class="sxs-lookup"><span data-stu-id="44f0d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="44f0d-111">**OID**</span><span class="sxs-lookup"><span data-stu-id="44f0d-111">**OID**</span></span>|<span data-ttu-id="44f0d-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="44f0d-113">클래스에서 구현 하는 알고리즘에 해당 하는 ASN OID를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-113">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="44f0d-114">**name**</span><span class="sxs-lookup"><span data-stu-id="44f0d-114">**name**</span></span>|<span data-ttu-id="44f0d-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="44f0d-116">태그의 **이름** 특성에 대 한 값을 지정 합니다 [\<nameEntry>](nameentry-element.md) .</span><span class="sxs-lookup"><span data-stu-id="44f0d-116">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="44f0d-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="44f0d-117">Child Elements</span></span>  

 <span data-ttu-id="44f0d-118">없음</span><span class="sxs-lookup"><span data-stu-id="44f0d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="44f0d-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="44f0d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="44f0d-120">요소</span><span class="sxs-lookup"><span data-stu-id="44f0d-120">Element</span></span>|<span data-ttu-id="44f0d-121">설명</span><span class="sxs-lookup"><span data-stu-id="44f0d-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="44f0d-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="44f0d-123">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-123">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="44f0d-124">요소를 포함 `cryptographySettings` 합니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-124">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="44f0d-125">클래스에 대 한 OID (개체 식별자) 매핑을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-125">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44f0d-126">설명</span><span class="sxs-lookup"><span data-stu-id="44f0d-126">Remarks</span></span>  

 <span data-ttu-id="44f0d-127">ASN 개체 식별자는 일부 암호화 형식의 알고리즘을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-127">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="44f0d-128">식별 하려는 알고리즘의 이름에 개체 식별자를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-128">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="44f0d-129">예제</span><span class="sxs-lookup"><span data-stu-id="44f0d-129">Example</span></span>  

 <span data-ttu-id="44f0d-130">다음 예제에서는 요소를 사용 하 여 **\<oidEntry>** RIPEMD-160 해시 알고리즘에 대 한 개체 식별자를 해당 해시 알고리즘의 구현에 매핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44f0d-130">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="44f0d-131">참조</span><span class="sxs-lookup"><span data-stu-id="44f0d-131">See also</span></span>

- [<span data-ttu-id="44f0d-132">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="44f0d-132">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="44f0d-133">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="44f0d-133">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="44f0d-134">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="44f0d-134">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="44f0d-135">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="44f0d-135">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="44f0d-136">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="44f0d-136">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
