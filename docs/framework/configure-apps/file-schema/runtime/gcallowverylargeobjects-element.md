---
description: '다음에 대 한 자세한 정보: <gcAllowVeryLargeObjects> 요소'
title: gcAllowVeryLargeObjects 요소
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: ff8380a13c4284cc24178e185344207c3b9a39b7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787021"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="04db1-103">\<gcAllowVeryLargeObjects> 요소</span><span class="sxs-lookup"><span data-stu-id="04db1-103">\<gcAllowVeryLargeObjects> element</span></span>

<span data-ttu-id="04db1-104">64비트 플랫폼에서 총 크기가 2GB보다 큰 배열을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-104">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="04db1-105">구문</span><span class="sxs-lookup"><span data-stu-id="04db1-105">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects enabled="true|false" />  
```  
  
## <a name="attributes"></a><span data-ttu-id="04db1-106">특성</span><span class="sxs-lookup"><span data-stu-id="04db1-106">Attributes</span></span>
  
|<span data-ttu-id="04db1-107">attribute</span><span class="sxs-lookup"><span data-stu-id="04db1-107">Attribute</span></span>|<span data-ttu-id="04db1-108">설명</span><span class="sxs-lookup"><span data-stu-id="04db1-108">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="04db1-109">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-109">Required attribute.</span></span><br /><br /> <span data-ttu-id="04db1-110">총 크기에서 2gb 보다 큰 배열을 64 비트 플랫폼에서 사용할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-110">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="04db1-111">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="04db1-111">enabled attribute</span></span>  
  
|<span data-ttu-id="04db1-112">값</span><span class="sxs-lookup"><span data-stu-id="04db1-112">Value</span></span>|<span data-ttu-id="04db1-113">설명</span><span class="sxs-lookup"><span data-stu-id="04db1-113">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="04db1-114">전체 크기의 2gb 보다 큰 배열은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-114">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="04db1-115">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-115">This is the default.</span></span>|  
|`true`|<span data-ttu-id="04db1-116">총 크기가 2gb 보다 큰 배열은 64 비트 플랫폼에서 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-116">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="04db1-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="04db1-117">Child elements</span></span>  

<span data-ttu-id="04db1-118">없음</span><span class="sxs-lookup"><span data-stu-id="04db1-118">None.</span></span>  
  
## <a name="parent-elements"></a><span data-ttu-id="04db1-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="04db1-119">Parent elements</span></span>
  
|<span data-ttu-id="04db1-120">요소</span><span class="sxs-lookup"><span data-stu-id="04db1-120">Element</span></span>|<span data-ttu-id="04db1-121">설명</span><span class="sxs-lookup"><span data-stu-id="04db1-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="04db1-122">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="04db1-123">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-123">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04db1-124">설명</span><span class="sxs-lookup"><span data-stu-id="04db1-124">Remarks</span></span>  

 <span data-ttu-id="04db1-125">응용 프로그램 구성 파일에서이 요소를 사용 하면 크기가 2gb 보다 큰 배열은 가능 하지만 개체 크기나 배열 크기에 대 한 다른 제한은 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-125">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="04db1-126">배열의 최대 요소 수는 <xref:System.UInt32.MaxValue?displayProperty=nameWithType> 입니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-126">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="04db1-127">단일 차원의 최대 크기는 바이트 배열 및 단일 바이트 구조의 배열에 대해 2147483591 (0x7FFFFFC7)이 고 다른 형식을 포함 하는 배열의 경우 2146435071 (0X7FEFFFFF)입니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-127">The maximum size in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for arrays containing other types.</span></span>  
  
- <span data-ttu-id="04db1-128">문자열 및 기타 배열 이외의 개체에 대 한 최대 크기는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-128">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="04db1-129">이 기능을 사용 하도록 설정 하기 전에 모든 배열이 2gb 보다 작은 것으로 가정 하는 안전 하지 않은 코드가 응용 프로그램에 포함 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-129">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="04db1-130">예를 들어 배열을 버퍼로 사용 하는 안전 하지 않은 코드는 배열이 2gb를 초과 하지 않는다는 가정 하에 작성 되는 버퍼 오버런에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-130">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it's written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04db1-131">예제</span><span class="sxs-lookup"><span data-stu-id="04db1-131">Example</span></span>  

 <span data-ttu-id="04db1-132">다음 예제에서는 응용 프로그램에 대해이 기능을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04db1-132">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="04db1-133">다음에서 지원:</span><span class="sxs-lookup"><span data-stu-id="04db1-133">Supported in</span></span>

<span data-ttu-id="04db1-134">.NET Framework 4.5 이상 버전</span><span class="sxs-lookup"><span data-stu-id="04db1-134">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="04db1-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04db1-135">See also</span></span>

- [<span data-ttu-id="04db1-136">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="04db1-136">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="04db1-137">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="04db1-137">Configuration File Schema</span></span>](../index.md)
