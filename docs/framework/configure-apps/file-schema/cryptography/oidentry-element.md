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
ms.openlocfilehash: 4564cf59e3b6cfbdcd9dca06cd0f966d524834de
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088545"
---
# <a name="oidentry-element"></a><span data-ttu-id="afe9b-102">\<oidEntry> 요소</span><span class="sxs-lookup"><span data-stu-id="afe9b-102">\<oidEntry> Element</span></span>
<span data-ttu-id="afe9b-103">ASN.1 OID(개체 식별자)를 이름에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-103">Maps an ASN.1 object identifier (OID) to a friendly name.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<mscorlib>**](mscorlib-element-for-cryptography-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<cryptographySettings>**](cryptographysettings-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oidMap>**](oidmap-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oidEntry>**

## <a name="syntax"></a><span data-ttu-id="afe9b-104">구문</span><span class="sxs-lookup"><span data-stu-id="afe9b-104">Syntax</span></span>  
  
```xml  
<oidEntry OID="object identifier number" name="friendly name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="afe9b-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="afe9b-105">Attributes and Elements</span></span>  
 <span data-ttu-id="afe9b-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="afe9b-107">특성</span><span class="sxs-lookup"><span data-stu-id="afe9b-107">Attributes</span></span>  
  
|<span data-ttu-id="afe9b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="afe9b-108">Attribute</span></span>|<span data-ttu-id="afe9b-109">Description</span><span class="sxs-lookup"><span data-stu-id="afe9b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="afe9b-110">**OID**</span><span class="sxs-lookup"><span data-stu-id="afe9b-110">**OID**</span></span>|<span data-ttu-id="afe9b-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="afe9b-112">클래스에서 구현 하는 알고리즘에 해당 하는 ASN OID를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-112">Specifies the ASN.1 OID corresponding to the algorithm implemented by your class.</span></span>|  
|<span data-ttu-id="afe9b-113">**name**</span><span class="sxs-lookup"><span data-stu-id="afe9b-113">**name**</span></span>|<span data-ttu-id="afe9b-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="afe9b-115">태그의 **이름** 특성에 대 한 값을 지정 합니다 [\<nameEntry>](nameentry-element.md) .</span><span class="sxs-lookup"><span data-stu-id="afe9b-115">Specifies the value for the **name** attribute in the [\<nameEntry>](nameentry-element.md) tag.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="afe9b-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="afe9b-116">Child Elements</span></span>  
 <span data-ttu-id="afe9b-117">없음</span><span class="sxs-lookup"><span data-stu-id="afe9b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="afe9b-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="afe9b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="afe9b-119">요소</span><span class="sxs-lookup"><span data-stu-id="afe9b-119">Element</span></span>|<span data-ttu-id="afe9b-120">Description</span><span class="sxs-lookup"><span data-stu-id="afe9b-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="afe9b-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`cryptographySettings`|<span data-ttu-id="afe9b-122">암호화 설정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-122">Contains cryptography settings.</span></span>|  
|`mscorlib`|<span data-ttu-id="afe9b-123">요소를 포함 `cryptographySettings` 합니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-123">Contains the `cryptographySettings` element.</span></span>|  
|`oidMap`|<span data-ttu-id="afe9b-124">클래스에 대 한 OID (개체 식별자) 매핑을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-124">Contains ASN.1 object identifier (OID) mappings to classes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="afe9b-125">설명</span><span class="sxs-lookup"><span data-stu-id="afe9b-125">Remarks</span></span>  
 <span data-ttu-id="afe9b-126">ASN 개체 식별자는 일부 암호화 형식의 알고리즘을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-126">ASN.1 object identifiers identify algorithms in some cryptographic formats.</span></span> <span data-ttu-id="afe9b-127">식별 하려는 알고리즘의 이름에 개체 식별자를 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-127">Map object identifiers to friendly names for the algorithms you want to identify.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afe9b-128">예제</span><span class="sxs-lookup"><span data-stu-id="afe9b-128">Example</span></span>  
 <span data-ttu-id="afe9b-129">다음 예제에서는 요소를 사용 하 여 **\<oidEntry>** RIPEMD-160 해시 알고리즘에 대 한 개체 식별자를 해당 해시 알고리즘의 구현에 매핑하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="afe9b-129">The following example shows how to use the **\<oidEntry>** element to map an object identifier for the RIPEMD-160 hash algorithm to an implementation of that hash algorithm.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="afe9b-130">참조</span><span class="sxs-lookup"><span data-stu-id="afe9b-130">See also</span></span>

- [<span data-ttu-id="afe9b-131">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="afe9b-131">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="afe9b-132">암호화 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="afe9b-132">Cryptography Settings Schema</span></span>](index.md)
- [<span data-ttu-id="afe9b-133">암호화 서비스</span><span class="sxs-lookup"><span data-stu-id="afe9b-133">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
- [<span data-ttu-id="afe9b-134">암호화 클래스 구성</span><span class="sxs-lookup"><span data-stu-id="afe9b-134">Configuring Cryptography Classes</span></span>](../../configure-cryptography-classes.md)
- [<span data-ttu-id="afe9b-135">개체 식별자를 암호화 알고리즘에 매핑</span><span class="sxs-lookup"><span data-stu-id="afe9b-135">Mapping Object Identifiers to Cryptography Algorithms</span></span>](../../map-object-identifiers-to-cryptography-algorithms.md)
