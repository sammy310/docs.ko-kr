---
title: <gcAllowVeryLargeObjects> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19103b2ac6e6dbba930050074fcea3cfd5a97661
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704663"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="80f55-102">\<gcAllowVeryLargeObjects > 요소</span><span class="sxs-lookup"><span data-stu-id="80f55-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="80f55-103">64비트 플랫폼에서 총 크기가 2GB보다 큰 배열을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
 <span data-ttu-id="80f55-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="80f55-104">\<configuration> Element</span></span>  
<span data-ttu-id="80f55-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="80f55-105">\<runtime> Element</span></span>  
<span data-ttu-id="80f55-106">\<gcAllowVeryLargeObjects > 요소</span><span class="sxs-lookup"><span data-stu-id="80f55-106">\<gcAllowVeryLargeObjects> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80f55-107">구문</span><span class="sxs-lookup"><span data-stu-id="80f55-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="80f55-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="80f55-108">Attributes and Elements</span></span>  
 <span data-ttu-id="80f55-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="80f55-110">특성</span><span class="sxs-lookup"><span data-stu-id="80f55-110">Attributes</span></span>  
  
|<span data-ttu-id="80f55-111">특성</span><span class="sxs-lookup"><span data-stu-id="80f55-111">Attribute</span></span>|<span data-ttu-id="80f55-112">설명</span><span class="sxs-lookup"><span data-stu-id="80f55-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="80f55-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="80f55-114">64 비트 플랫폼에서 총 크기가 2GB 보다 큰 배열을 사용 되는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="80f55-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="80f55-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="80f55-116">값</span><span class="sxs-lookup"><span data-stu-id="80f55-116">Value</span></span>|<span data-ttu-id="80f55-117">설명</span><span class="sxs-lookup"><span data-stu-id="80f55-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="80f55-118">총 크기가 2GB 보다 큰 배열 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="80f55-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="80f55-120">총 크기가 2GB 보다 큰 배열 64 비트 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="80f55-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="80f55-121">Child Elements</span></span>  
 <span data-ttu-id="80f55-122">없음</span><span class="sxs-lookup"><span data-stu-id="80f55-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="80f55-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="80f55-123">Parent Elements</span></span>  
  
|<span data-ttu-id="80f55-124">요소</span><span class="sxs-lookup"><span data-stu-id="80f55-124">Element</span></span>|<span data-ttu-id="80f55-125">설명</span><span class="sxs-lookup"><span data-stu-id="80f55-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="80f55-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="80f55-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="80f55-128">설명</span><span class="sxs-lookup"><span data-stu-id="80f55-128">Remarks</span></span>  
 <span data-ttu-id="80f55-129">이 요소를 사용 하 여 응용 프로그램 구성 파일의 크기가 2GB 보다 큰 배열을 사용 하도록 설정 하지만 개체 크기 또는 배열 크기에 대 한 다른도 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="80f55-130">배열에 있는 요소의 최대 수는 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="80f55-131">임의의 단일 차원에 있는 최대 색인 2,147,483,591 바이트 배열 및 싱글바이트 구조의 배열에 대 한 (0x7FFFFFC7) 및 다른 유형의 2,146,435,071 (0X7FEFFFFF).</span><span class="sxs-lookup"><span data-stu-id="80f55-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="80f55-132">문자열 및 기타 비 배열 개체에 대 한 최대 크기 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="80f55-133">이 기능을 사용 하기 전에 응용 프로그램 크기가 2GB 보다 작은 모든 배열은 가정 하는 안전 하지 않은 코드에 포함 되지 않습니다 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="80f55-134">예를 들어, 배열 2GB를 초과 하지 것입니다 가정 하에서 작성 된 경우 버퍼 배열을 사용 하는 안전 하지 않은 코드 버퍼 오버런에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80f55-135">예제</span><span class="sxs-lookup"><span data-stu-id="80f55-135">Example</span></span>  
 <span data-ttu-id="80f55-136">다음 예제에서는 응용 프로그램에 대해이 기능을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="80f55-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="80f55-137">참고자료</span><span class="sxs-lookup"><span data-stu-id="80f55-137">See also</span></span>

- [<span data-ttu-id="80f55-138">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="80f55-138">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="80f55-139">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="80f55-139">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
