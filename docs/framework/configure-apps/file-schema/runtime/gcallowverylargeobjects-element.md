---
title: <gcAllowVeryLargeObjects> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 8b2f39a0867228474afdee788474fda11f14ca82
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154129"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="19ce6-102">\<gcAllowVery큰개체> 요소</span><span class="sxs-lookup"><span data-stu-id="19ce6-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="19ce6-103">64비트 플랫폼에서 총 크기가 2GB보다 큰 배열을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
<span data-ttu-id="19ce6-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="19ce6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="19ce6-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="19ce6-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="19ce6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVery큰개체>**</span><span class="sxs-lookup"><span data-stu-id="19ce6-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ce6-107">구문</span><span class="sxs-lookup"><span data-stu-id="19ce6-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="19ce6-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="19ce6-108">Attributes and Elements</span></span>  
 <span data-ttu-id="19ce6-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="19ce6-110">특성</span><span class="sxs-lookup"><span data-stu-id="19ce6-110">Attributes</span></span>  
  
|<span data-ttu-id="19ce6-111">attribute</span><span class="sxs-lookup"><span data-stu-id="19ce6-111">Attribute</span></span>|<span data-ttu-id="19ce6-112">Description</span><span class="sxs-lookup"><span data-stu-id="19ce6-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="19ce6-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="19ce6-114">총 크기가 2GB를 초과하는 배열이 64비트 플랫폼에서 활성화되는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="19ce6-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="19ce6-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="19ce6-116">값</span><span class="sxs-lookup"><span data-stu-id="19ce6-116">Value</span></span>|<span data-ttu-id="19ce6-117">Description</span><span class="sxs-lookup"><span data-stu-id="19ce6-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="19ce6-118">총 크기가 2GB를 초과하는 배열은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="19ce6-119">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="19ce6-120">총 크기가 2GB를 초과하는 배열은 64비트 플랫폼에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="19ce6-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="19ce6-121">Child Elements</span></span>  
 <span data-ttu-id="19ce6-122">없음</span><span class="sxs-lookup"><span data-stu-id="19ce6-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="19ce6-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="19ce6-123">Parent Elements</span></span>  
  
|<span data-ttu-id="19ce6-124">요소</span><span class="sxs-lookup"><span data-stu-id="19ce6-124">Element</span></span>|<span data-ttu-id="19ce6-125">Description</span><span class="sxs-lookup"><span data-stu-id="19ce6-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="19ce6-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="19ce6-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="19ce6-128">설명</span><span class="sxs-lookup"><span data-stu-id="19ce6-128">Remarks</span></span>  
 <span data-ttu-id="19ce6-129">응용 프로그램 구성 파일에서 이 요소를 사용하면 크기가 2GB보다 크지만 개체 크기 또는 배열 크기에 대한 다른 제한은 변경되지 않는 배열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="19ce6-130">배열의 최대 요소 수는 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="19ce6-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="19ce6-131">단일 차원의 최대 인덱스는 단일 바이트 구조의 바이트 배열 및 배열에 대한 2,147,483,591(0x7FFFFFC7) 및 다른 형식의 경우 2,146,435,071(0X7FFFFFFF)입니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="19ce6-132">문자열 및 기타 비배열 개체의 최대 크기는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="19ce6-133">이 기능을 활성화하기 전에 모든 배열의 크기가 2GB보다 작다고 가정하는 안전하지 않은 코드가 응용 프로그램에 포함되어 있지 않은지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="19ce6-134">예를 들어 배열을 버퍼로 사용하는 안전하지 않은 코드는 배열이 2GB를 초과하지 않는다는 가정하에 작성된 경우 버퍼 오버런에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19ce6-135">예제</span><span class="sxs-lookup"><span data-stu-id="19ce6-135">Example</span></span>  
 <span data-ttu-id="19ce6-136">다음 예제에서는 응용 프로그램에 대해 이 기능을 사용하도록 설정하는 방법을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="19ce6-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="19ce6-137">다음에서 지원:</span><span class="sxs-lookup"><span data-stu-id="19ce6-137">Supported in</span></span>

<span data-ttu-id="19ce6-138">.NET 프레임워크 4.5 이상 버전</span><span class="sxs-lookup"><span data-stu-id="19ce6-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="19ce6-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19ce6-139">See also</span></span>

- [<span data-ttu-id="19ce6-140">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="19ce6-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="19ce6-141">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="19ce6-141">Configuration File Schema</span></span>](../index.md)
