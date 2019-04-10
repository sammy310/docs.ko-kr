---
title: <UseSmallInternalThreadStacks> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9833d768b84faaf6e1dcf8c9cb8b00b92adc3d1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144829"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="eb30c-102">\<UseSmallInternalThreadStacks > 요소</span><span class="sxs-lookup"><span data-stu-id="eb30c-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="eb30c-103">요청 된 CLR (공용 언어 런타임)는 메모리를 줄일 이러한 스레드에 대 한 기본 스택 크기를 사용 하는 대신 내부적으로 사용 되는 특정 스레드를 만들 때 명시적 스택 크기를 지정 하 여 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
 <span data-ttu-id="eb30c-104">\<구성 > 요소</span><span class="sxs-lookup"><span data-stu-id="eb30c-104">\<configuration> Element</span></span>  
<span data-ttu-id="eb30c-105">\<런타임 > 요소</span><span class="sxs-lookup"><span data-stu-id="eb30c-105">\<runtime> Element</span></span>  
<span data-ttu-id="eb30c-106">\<UseSmallInternalThreadStacks > 요소</span><span class="sxs-lookup"><span data-stu-id="eb30c-106">\<UseSmallInternalThreadStacks> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb30c-107">구문</span><span class="sxs-lookup"><span data-stu-id="eb30c-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb30c-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="eb30c-108">Attributes and Elements</span></span>  
 <span data-ttu-id="eb30c-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb30c-110">특성</span><span class="sxs-lookup"><span data-stu-id="eb30c-110">Attributes</span></span>  
  
|<span data-ttu-id="eb30c-111">특성</span><span class="sxs-lookup"><span data-stu-id="eb30c-111">Attribute</span></span>|<span data-ttu-id="eb30c-112">설명</span><span class="sxs-lookup"><span data-stu-id="eb30c-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="eb30c-113">사용</span><span class="sxs-lookup"><span data-stu-id="eb30c-113">enabled</span></span>|<span data-ttu-id="eb30c-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="eb30c-115">여부를 지정 하도록 요청 하는 기본 스택 크기 대신 CLR 사용 하 여 명시적 스택 크기 내부적으로 사용 되는 특정 스레드를 만들 때.</span><span class="sxs-lookup"><span data-stu-id="eb30c-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="eb30c-116">명시적 스택 크기는 1MB의 기본 스택 크기 보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="eb30c-117">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="eb30c-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="eb30c-118">값</span><span class="sxs-lookup"><span data-stu-id="eb30c-118">Value</span></span>|<span data-ttu-id="eb30c-119">설명</span><span class="sxs-lookup"><span data-stu-id="eb30c-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb30c-120">true</span><span class="sxs-lookup"><span data-stu-id="eb30c-120">true</span></span>|<span data-ttu-id="eb30c-121">명시적 스택 크기를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="eb30c-122">False</span><span class="sxs-lookup"><span data-stu-id="eb30c-122">false</span></span>|<span data-ttu-id="eb30c-123">기본 스택 크기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-123">Use the default stack size.</span></span> <span data-ttu-id="eb30c-124">에 대 한 기본값을 [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)]입니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-124">This is the default for the [!INCLUDE[net_v40_long](../../../../../includes/net-v40-long-md.md)].</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="eb30c-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="eb30c-125">Child Elements</span></span>  
 <span data-ttu-id="eb30c-126">없음</span><span class="sxs-lookup"><span data-stu-id="eb30c-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="eb30c-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="eb30c-127">Parent Elements</span></span>  
  
|<span data-ttu-id="eb30c-128">요소</span><span class="sxs-lookup"><span data-stu-id="eb30c-128">Element</span></span>|<span data-ttu-id="eb30c-129">설명</span><span class="sxs-lookup"><span data-stu-id="eb30c-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eb30c-130">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="eb30c-131">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb30c-132">설명</span><span class="sxs-lookup"><span data-stu-id="eb30c-132">Remarks</span></span>  
 <span data-ttu-id="eb30c-133">이 구성 요소는 요청이 적용 되는 경우 CLR에서 내부 스레드를 사용 하는 명시적 스레드 크기는 기본 크기 보다 작은 때문에 프로세스에서 축소 된 가상 메모리 사용을 요청에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb30c-134">이 구성 요소는 요청은 절대적인 요구 사항이 아닌 CLR을 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="eb30c-135">에 [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], x86에 대해서만 요청이 수행 됩니다 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-135">In the [!INCLUDE[net_v40_short](../../../../../includes/net-v40-short-md.md)], the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="eb30c-136">이 요소는 CLR의 이후 버전에서는 완전히 무시 또는 선택한 내부 스레드에 항상 사용 되는 명시적 스택 크기 바뀝니다 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="eb30c-137">이 구성 요소 거래 작은 가상 메모리 사용에 대 한 안정성 CLR은 요청을 하는 경우 스택 크기가 작은 스택을 만들 수 있으므로 지정 오버플로가 발생할 가능성이 더 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb30c-138">예제</span><span class="sxs-lookup"><span data-stu-id="eb30c-138">Example</span></span>  
 <span data-ttu-id="eb30c-139">다음 예에서는 CLR 사용 하 여 명시적 스택 크기 특정 내부적으로 사용 하는 스레드를 요청 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eb30c-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb30c-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="eb30c-140">See also</span></span>

- [<span data-ttu-id="eb30c-141">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="eb30c-141">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="eb30c-142">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="eb30c-142">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
