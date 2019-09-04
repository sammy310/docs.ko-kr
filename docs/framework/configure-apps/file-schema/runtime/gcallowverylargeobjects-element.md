---
title: <gcAllowVeryLargeObjects> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f638a880aaa21bc41d2575f3609dabae158c1a0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252579"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="2e472-102">\<Gcallowverylargeobjects> > 요소</span><span class="sxs-lookup"><span data-stu-id="2e472-102">\<gcAllowVeryLargeObjects> Element</span></span>
<span data-ttu-id="2e472-103">64비트 플랫폼에서 총 크기가 2GB보다 큰 배열을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
<span data-ttu-id="2e472-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e472-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2e472-105">&nbsp;&nbsp;[ **\<런타임 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="2e472-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="2e472-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<gcAllowVeryLargeObjects>**</span><span class="sxs-lookup"><span data-stu-id="2e472-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e472-107">구문</span><span class="sxs-lookup"><span data-stu-id="2e472-107">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects    
   enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e472-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2e472-108">Attributes and Elements</span></span>  
 <span data-ttu-id="2e472-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e472-110">특성</span><span class="sxs-lookup"><span data-stu-id="2e472-110">Attributes</span></span>  
  
|<span data-ttu-id="2e472-111">특성</span><span class="sxs-lookup"><span data-stu-id="2e472-111">Attribute</span></span>|<span data-ttu-id="2e472-112">설명</span><span class="sxs-lookup"><span data-stu-id="2e472-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="2e472-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="2e472-114">총 크기에서 2gb 보다 큰 배열을 64 비트 플랫폼에서 사용할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-114">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="2e472-115">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="2e472-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="2e472-116">값</span><span class="sxs-lookup"><span data-stu-id="2e472-116">Value</span></span>|<span data-ttu-id="2e472-117">설명</span><span class="sxs-lookup"><span data-stu-id="2e472-117">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="2e472-118">전체 크기의 2gb 보다 큰 배열은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-118">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="2e472-119">이 값이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-119">This is the default.</span></span>|  
|`true`|<span data-ttu-id="2e472-120">총 크기가 2gb 보다 큰 배열은 64 비트 플랫폼에서 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-120">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e472-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2e472-121">Child Elements</span></span>  
 <span data-ttu-id="2e472-122">없음</span><span class="sxs-lookup"><span data-stu-id="2e472-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2e472-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2e472-123">Parent Elements</span></span>  
  
|<span data-ttu-id="2e472-124">요소</span><span class="sxs-lookup"><span data-stu-id="2e472-124">Element</span></span>|<span data-ttu-id="2e472-125">설명</span><span class="sxs-lookup"><span data-stu-id="2e472-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2e472-126">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="2e472-127">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-127">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2e472-128">설명</span><span class="sxs-lookup"><span data-stu-id="2e472-128">Remarks</span></span>  
 <span data-ttu-id="2e472-129">응용 프로그램 구성 파일에서이 요소를 사용 하면 크기가 2gb 보다 큰 배열은 가능 하지만 개체 크기나 배열 크기에 대 한 다른 제한은 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-129">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="2e472-130">배열의 최대 요소 수는 <xref:System.UInt32.MaxValue?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-130">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="2e472-131">단일 차원의 최대 인덱스는 바이트 배열 및 단일 바이트 구조의 배열에 대해 2147483591 (0x7FFFFFC7)이 고 다른 형식의 경우 2146435071 (0X7FEFFFFF)입니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-131">The maximum index in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for other types.</span></span>  
  
- <span data-ttu-id="2e472-132">문자열 및 기타 배열 이외의 개체에 대 한 최대 크기는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-132">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="2e472-133">이 기능을 사용 하도록 설정 하기 전에 모든 배열이 2gb 보다 작은 것으로 가정 하는 안전 하지 않은 코드가 응용 프로그램에 포함 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-133">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="2e472-134">예를 들어 배열을 버퍼로 사용 하는 안전 하지 않은 코드는 배열이 2gb를 초과 하지 않는다는 가정 하에 작성 되는 경우 버퍼 오버런에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-134">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it is written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e472-135">예제</span><span class="sxs-lookup"><span data-stu-id="2e472-135">Example</span></span>  
 <span data-ttu-id="2e472-136">다음 예제에서는 응용 프로그램에 대해이 기능을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e472-136">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="2e472-137">다음에서 지원:</span><span class="sxs-lookup"><span data-stu-id="2e472-137">Supported in</span></span>

<span data-ttu-id="2e472-138">.NET Framework 4.5 이상 버전</span><span class="sxs-lookup"><span data-stu-id="2e472-138">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="2e472-139">참고자료</span><span class="sxs-lookup"><span data-stu-id="2e472-139">See also</span></span>

- [<span data-ttu-id="2e472-140">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="2e472-140">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="2e472-141">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="2e472-141">Configuration File Schema</span></span>](../index.md)
