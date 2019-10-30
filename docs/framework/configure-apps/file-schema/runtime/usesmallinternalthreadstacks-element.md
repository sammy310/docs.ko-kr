---
title: <UseSmallInternalThreadStacks> 요소
ms.date: 03/30/2017
helpviewer_keywords:
- UseSmallInternalThreadStacks element
- <UseSmallInternalThreadStacks> element
ms.assetid: 1e3f6ec0-1cac-4e1c-9c81-17d948ae5874
ms.openlocfilehash: 2fd776ce8605e6dcf288dcb3852ded16638a1873
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73114930"
---
# <a name="usesmallinternalthreadstacks-element"></a><span data-ttu-id="3721d-102">\<UseSmallInternalThreadStacks > 요소</span><span class="sxs-lookup"><span data-stu-id="3721d-102">\<UseSmallInternalThreadStacks> Element</span></span>
<span data-ttu-id="3721d-103">CLR (공용 언어 런타임)이 해당 스레드에 대 한 기본 스택 크기를 사용 하는 대신 내부적으로 사용 하는 특정 스레드를 만들 때 명시적 스택 크기를 지정 하 여 메모리 사용을 줄이도록 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-103">Requests that the common language runtime (CLR) reduce memory use by specifying explicit stack sizes when it creates certain threads that it uses internally, instead of using the default stack size for those threads.</span></span>  
  
<span data-ttu-id="3721d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="3721d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="3721d-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="3721d-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="3721d-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<UseSmallInternalThreadStacks >**</span><span class="sxs-lookup"><span data-stu-id="3721d-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<UseSmallInternalThreadStacks>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3721d-107">구문</span><span class="sxs-lookup"><span data-stu-id="3721d-107">Syntax</span></span>  
  
```xml  
<UseSmallInternalThreadStacks enabled="true|false" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3721d-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="3721d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="3721d-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3721d-110">특성</span><span class="sxs-lookup"><span data-stu-id="3721d-110">Attributes</span></span>  
  
|<span data-ttu-id="3721d-111">특성</span><span class="sxs-lookup"><span data-stu-id="3721d-111">Attribute</span></span>|<span data-ttu-id="3721d-112">설명</span><span class="sxs-lookup"><span data-stu-id="3721d-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="3721d-113">사용</span><span class="sxs-lookup"><span data-stu-id="3721d-113">enabled</span></span>|<span data-ttu-id="3721d-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="3721d-115">내부적으로 사용 하는 특정 스레드를 만들 때 CLR에서 기본 스택 크기 대신 명시적 스택 크기를 사용 하도록 요청할 것인지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-115">Specifies whether to request that the CLR use explicit stack sizes instead of the default stack size when it creates certain threads that it uses internally.</span></span> <span data-ttu-id="3721d-116">명시적 스택 크기는 1mb의 기본 스택 크기 보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-116">The explicit stack sizes are smaller than the default stack size of 1 MB.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="3721d-117">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="3721d-117">enabled Attribute</span></span>  
  
|<span data-ttu-id="3721d-118">값</span><span class="sxs-lookup"><span data-stu-id="3721d-118">Value</span></span>|<span data-ttu-id="3721d-119">설명</span><span class="sxs-lookup"><span data-stu-id="3721d-119">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="3721d-120">true</span><span class="sxs-lookup"><span data-stu-id="3721d-120">true</span></span>|<span data-ttu-id="3721d-121">명시적 스택 크기를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-121">Request explicit stack sizes.</span></span>|  
|<span data-ttu-id="3721d-122">False</span><span class="sxs-lookup"><span data-stu-id="3721d-122">false</span></span>|<span data-ttu-id="3721d-123">기본 스택 크기를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-123">Use the default stack size.</span></span> <span data-ttu-id="3721d-124">.NET Framework 4의 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-124">This is the default for the .NET Framework 4.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3721d-125">자식 요소</span><span class="sxs-lookup"><span data-stu-id="3721d-125">Child Elements</span></span>  
 <span data-ttu-id="3721d-126">없음.</span><span class="sxs-lookup"><span data-stu-id="3721d-126">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3721d-127">부모 요소</span><span class="sxs-lookup"><span data-stu-id="3721d-127">Parent Elements</span></span>  
  
|<span data-ttu-id="3721d-128">요소</span><span class="sxs-lookup"><span data-stu-id="3721d-128">Element</span></span>|<span data-ttu-id="3721d-129">설명</span><span class="sxs-lookup"><span data-stu-id="3721d-129">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3721d-130">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-130">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="3721d-131">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-131">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3721d-132">주의</span><span class="sxs-lookup"><span data-stu-id="3721d-132">Remarks</span></span>  
 <span data-ttu-id="3721d-133">이 구성 요소는 CLR이 내부 스레드에 사용 하는 명시적 스레드 크기 (요청이 적용 되는 경우)가 기본 크기 보다 작기 때문에 프로세스에서 축소 된 가상 메모리 사용을 요청 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-133">This configuration element is used to request reduced virtual memory use in a process, because the explicit thread sizes that the CLR uses for its internal threads, if the request is honored, are smaller than the default size.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3721d-134">이 구성 요소는 절대 요구 사항이 아닌 CLR에 대 한 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-134">This configuration element is a request to the CLR rather than an absolute requirement.</span></span> <span data-ttu-id="3721d-135">.NET Framework 4에서 요청은 x86 아키텍처에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-135">In the .NET Framework 4, the request is honored only for the x86 architecture.</span></span> <span data-ttu-id="3721d-136">이 요소는 CLR의 이후 버전에서 완전히 무시 되거나 선택한 내부 스레드에 항상 사용 되는 명시적 스택 크기로 대체 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-136">This element might be ignored completely in future versions of the CLR, or replaced by explicit stack sizes that are always used for selected internal threads.</span></span>  
  
 <span data-ttu-id="3721d-137">이 구성 요소를 지정 하면 CLR에서 요청을 지 원하는 경우 더 작은 가상 메모리 사용에 대 한 안정성을 유지 합니다 .이로 인해 스택 크기가 작을수록 스택 오버플로가 발생할 가능성이 높아집니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-137">Specifying this configuration element trades reliability for smaller virtual memory use if the CLR honors the request, because smaller stack sizes could potentially make stack overflows more likely.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3721d-138">예제</span><span class="sxs-lookup"><span data-stu-id="3721d-138">Example</span></span>  
 <span data-ttu-id="3721d-139">다음 예제에서는 CLR에서 내부적으로 사용 하는 특정 스레드에 대해 명시적 스택 크기를 사용 하도록 요청 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3721d-139">The following example shows how to request that the CLR use explicit stack sizes for certain threads that it uses internally.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <UseSmallInternalThreadStacks enabled="true" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3721d-140">참조</span><span class="sxs-lookup"><span data-stu-id="3721d-140">See also</span></span>

- [<span data-ttu-id="3721d-141">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="3721d-141">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3721d-142">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="3721d-142">Configuration File Schema</span></span>](../index.md)
