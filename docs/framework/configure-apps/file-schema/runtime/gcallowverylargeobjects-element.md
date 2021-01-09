---
title: gcAllowVeryLargeObjects 요소
ms.date: 03/30/2017
helpviewer_keywords:
- gcAllowVeryLargeObjects element
- <gcAllowVeryLargeObjects> element
ms.assetid: 5c7ea24a-39ac-4e5f-83b7-b9f9a1b556ab
ms.openlocfilehash: 1e54b0780ffb5bbe81ab1be2b376ff7a038ee05c
ms.sourcegitcommit: 0273f8845eb1ea8de64086bef2271b4f22182c91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2021
ms.locfileid: "98058131"
---
# <a name="gcallowverylargeobjects-element"></a><span data-ttu-id="e6381-102">\<gcAllowVeryLargeObjects> 요소</span><span class="sxs-lookup"><span data-stu-id="e6381-102">\<gcAllowVeryLargeObjects> element</span></span>

<span data-ttu-id="e6381-103">64비트 플랫폼에서 총 크기가 2GB보다 큰 배열을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-103">On 64-bit platforms, enables arrays that are greater than 2 gigabytes (GB) in total size.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<gcAllowVeryLargeObjects>**  
  
## <a name="syntax"></a><span data-ttu-id="e6381-104">구문</span><span class="sxs-lookup"><span data-stu-id="e6381-104">Syntax</span></span>  
  
```xml  
<gcAllowVeryLargeObjects enabled="true|false" />  
```  
  
## <a name="attributes"></a><span data-ttu-id="e6381-105">특성</span><span class="sxs-lookup"><span data-stu-id="e6381-105">Attributes</span></span>
  
|<span data-ttu-id="e6381-106">attribute</span><span class="sxs-lookup"><span data-stu-id="e6381-106">Attribute</span></span>|<span data-ttu-id="e6381-107">설명</span><span class="sxs-lookup"><span data-stu-id="e6381-107">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="e6381-108">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-108">Required attribute.</span></span><br /><br /> <span data-ttu-id="e6381-109">총 크기에서 2gb 보다 큰 배열을 64 비트 플랫폼에서 사용할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-109">Specifies whether arrays that are greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="e6381-110">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="e6381-110">enabled attribute</span></span>  
  
|<span data-ttu-id="e6381-111">값</span><span class="sxs-lookup"><span data-stu-id="e6381-111">Value</span></span>|<span data-ttu-id="e6381-112">설명</span><span class="sxs-lookup"><span data-stu-id="e6381-112">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="e6381-113">전체 크기의 2gb 보다 큰 배열은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-113">Arrays greater than 2 GB in total size are not enabled.</span></span> <span data-ttu-id="e6381-114">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-114">This is the default.</span></span>|  
|`true`|<span data-ttu-id="e6381-115">총 크기가 2gb 보다 큰 배열은 64 비트 플랫폼에서 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-115">Arrays greater than 2 GB in total size are enabled on 64-bit platforms.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="e6381-116">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e6381-116">Child elements</span></span>  

<span data-ttu-id="e6381-117">없음</span><span class="sxs-lookup"><span data-stu-id="e6381-117">None.</span></span>  
  
## <a name="parent-elements"></a><span data-ttu-id="e6381-118">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e6381-118">Parent elements</span></span>
  
|<span data-ttu-id="e6381-119">요소</span><span class="sxs-lookup"><span data-stu-id="e6381-119">Element</span></span>|<span data-ttu-id="e6381-120">설명</span><span class="sxs-lookup"><span data-stu-id="e6381-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e6381-121">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="e6381-122">런타임 초기화 옵션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-122">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6381-123">설명</span><span class="sxs-lookup"><span data-stu-id="e6381-123">Remarks</span></span>  

 <span data-ttu-id="e6381-124">응용 프로그램 구성 파일에서이 요소를 사용 하면 크기가 2gb 보다 큰 배열은 가능 하지만 개체 크기나 배열 크기에 대 한 다른 제한은 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-124">Using this element in your application configuration file enables arrays that are larger than 2 GB in size, but does not change other limits on object size or array size:</span></span>  
  
- <span data-ttu-id="e6381-125">배열의 최대 요소 수는 <xref:System.UInt32.MaxValue?displayProperty=nameWithType> 입니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-125">The maximum number of elements in an array is <xref:System.UInt32.MaxValue?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="e6381-126">단일 차원의 최대 크기는 바이트 배열 및 단일 바이트 구조의 배열에 대해 2147483591 (0x7FFFFFC7)이 고 다른 형식을 포함 하는 배열의 경우 2146435071 (0X7FEFFFFF)입니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-126">The maximum size in any single dimension is 2,147,483,591 (0x7FFFFFC7) for byte arrays and arrays of single-byte structures, and 2,146,435,071 (0X7FEFFFFF) for arrays containing other types.</span></span>  
  
- <span data-ttu-id="e6381-127">문자열 및 기타 배열 이외의 개체에 대 한 최대 크기는 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-127">The maximum size for strings and other non-array objects is unchanged.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="e6381-128">이 기능을 사용 하도록 설정 하기 전에 모든 배열이 2gb 보다 작은 것으로 가정 하는 안전 하지 않은 코드가 응용 프로그램에 포함 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-128">Before enabling this feature, ensure that your application does not include unsafe code that assumes that all arrays are smaller than 2 GB in size.</span></span> <span data-ttu-id="e6381-129">예를 들어 배열을 버퍼로 사용 하는 안전 하지 않은 코드는 배열이 2gb를 초과 하지 않는다는 가정 하에 작성 되는 버퍼 오버런에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-129">For example, unsafe code that uses arrays as buffers might be susceptible to buffer overruns if it's written on the assumption that arrays will not exceed 2 GB.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6381-130">예제</span><span class="sxs-lookup"><span data-stu-id="e6381-130">Example</span></span>  

 <span data-ttu-id="e6381-131">다음 예제에서는 응용 프로그램에 대해이 기능을 사용 하도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e6381-131">The following example shows how to enable this feature for an application.</span></span>  
  
```xml  
<configuration>  
  <runtime>  
    <gcAllowVeryLargeObjects enabled="true" />  
  </runtime>  
</configuration>  
```  
  
## <a name="supported-in"></a><span data-ttu-id="e6381-132">다음에서 지원:</span><span class="sxs-lookup"><span data-stu-id="e6381-132">Supported in</span></span>

<span data-ttu-id="e6381-133">.NET Framework 4.5 이상 버전</span><span class="sxs-lookup"><span data-stu-id="e6381-133">.NET Framework 4.5 and later versions</span></span>

## <a name="see-also"></a><span data-ttu-id="e6381-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6381-134">See also</span></span>

- [<span data-ttu-id="e6381-135">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="e6381-135">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e6381-136">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="e6381-136">Configuration File Schema</span></span>](../index.md)
