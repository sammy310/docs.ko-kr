---
title: <oidEntry> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings/oidMap/oidEntry
- http://schemas.microsoft.com/.NetConfiguration/v2.0#oidEntry
helpviewer_keywords:
- <oidEntry> element
- oidEntry element
ms.assetid: 22fb88b0-bf27-489c-9ca0-e65950ac136c
ms.openlocfilehash: eed2a4d06906d2928be62aed20a75484c3eea946
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699762"
---
# <a name="oidentry-element"></a><span data-ttu-id="f5189-102">\<oidEntry > 요소</span><span class="sxs-lookup"><span data-stu-id="f5189-102">\<oidEntry> Element</span></span>
<span data-ttu-id="f5189-103">ASN.1 OID(개체 식별자)를 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  
  
[<span data-ttu-id="f5189-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="f5189-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="f5189-105">&nbsp; @ no__t[ **\<mscorlib >** ](mscorlib-element-for-cryptography-settings.md)</span><span class="sxs-lookup"><span data-stu-id="f5189-105">&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)</span></span>  
<span data-ttu-id="f5189-106">&nbsp; @ no__t-1 @ no__t @ no__t[ **\<cryptographySettings >** ](cryptographysettings-element.md)</span><span class="sxs-lookup"><span data-stu-id="f5189-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)</span></span>  
<span data-ttu-id="f5189-107">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5[ **\<oidMap >** ](oidmap-element.md)</span><span class="sxs-lookup"><span data-stu-id="f5189-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)</span></span>  
<span data-ttu-id="f5189-108">&nbsp; @ no__t-1 @ no__t @ no__t @ @ no__t-4 @ no__t-5 @ no__t-6 **\<oidEntry >**</span><span class="sxs-lookup"><span data-stu-id="f5189-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5189-109">구문</span><span class="sxs-lookup"><span data-stu-id="f5189-109">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5189-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f5189-110">Attributes and Elements</span></span>  
 <span data-ttu-id="f5189-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5189-112">특성</span><span class="sxs-lookup"><span data-stu-id="f5189-112">Attributes</span></span>  
  
|<span data-ttu-id="f5189-113">특성</span><span class="sxs-lookup"><span data-stu-id="f5189-113">Attribute</span></span>|<span data-ttu-id="f5189-114">설명</span><span class="sxs-lookup"><span data-stu-id="f5189-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f5189-115">**OID**</span><span class="sxs-lookup"><span data-stu-id="f5189-115">**OID**</span></span>|<span data-ttu-id="f5189-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="f5189-117">클래스에서 구현 하는 알고리즘에 해당 하는 ASN OID를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-117">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="f5189-118">**name**</span><span class="sxs-lookup"><span data-stu-id="f5189-118">**name**</span></span>|<span data-ttu-id="f5189-119">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="f5189-120">[@No__t-2nameEntry >](nameentry-element.md) 태그에 **name** 특성의 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-120">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5189-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f5189-121">Child Elements</span></span>  
 <span data-ttu-id="f5189-122">없음</span><span class="sxs-lookup"><span data-stu-id="f5189-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5189-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f5189-123">Parent Elements</span></span>  
  
|<span data-ttu-id="f5189-124">요소</span><span class="sxs-lookup"><span data-stu-id="f5189-124">Element</span></span>|<span data-ttu-id="f5189-125">설명</span><span class="sxs-lookup"><span data-stu-id="f5189-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f5189-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="f5189-127">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-127">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="f5189-128">요소를 `cryptographySettings` 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-128">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="f5189-129">클래스에 대 한 OID (개체 식별자) 매핑을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-129">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f5189-130">설명</span><span class="sxs-lookup"><span data-stu-id="f5189-130">Remarks</span></span>  
 <span data-ttu-id="f5189-131">ASN 개체 식별자는 일부 암호화 형식의 알고리즘을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-131">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="f5189-132">식별 하려는 알고리즘의 이름에 개체 식별자를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-132">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5189-133">예제</span><span class="sxs-lookup"><span data-stu-id="f5189-133">Example</span></span>  
 <span data-ttu-id="f5189-134">다음 예제에서는 **\<oidEntry >** 요소를 사용 하 여 160 RIPEMD 해시 알고리즘에 대 한 개체 식별자를 해당 해시 알고리즘의 구현에 매핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5189-134">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f5189-135">참조</span><span class="sxs-lookup"><span data-stu-id="f5189-135">See also</span></span>

- [<span data-ttu-id="f5189-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="f5189-136">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="f5189-137">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="f5189-137">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f5189-138">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="f5189-138">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="f5189-139">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="f5189-139">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="f5189-140">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="f5189-140">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
