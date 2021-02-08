---
description: '다음에 대 한 자세한 정보: <disableCachingBindingFailures> 요소'
title: <disableCachingBindingFailures> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#disableCachingBindingFailures
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/disableCachingBindingFailures
helpviewer_keywords:
- assemblies [.NET Framework],caching binding failures
- caching assembly binding failures
- <disableCachingBindingFailures> element
- disableCachingBindingFailures element
ms.assetid: bf598873-83b7-48de-8955-00b0504fbad0
ms.openlocfilehash: b1f36f6a8fc7c78a0dc90ecc78ad725b677fdf40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787112"
---
# <a name="disablecachingbindingfailures-element"></a><span data-ttu-id="837b8-103">\<disableCachingBindingFailures> 요소</span><span class="sxs-lookup"><span data-stu-id="837b8-103">\<disableCachingBindingFailures> Element</span></span>

<span data-ttu-id="837b8-104">검색을 통해 어셈블리를 찾을 수 없기 때문에 발생 하는 바인딩 실패의 캐싱을 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-104">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<disableCachingBindingFailures>**  
  
## <a name="syntax"></a><span data-ttu-id="837b8-105">구문</span><span class="sxs-lookup"><span data-stu-id="837b8-105">Syntax</span></span>  
  
```xml  
<disableCachingBindingFailures enabled="0|1"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="837b8-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="837b8-106">Attributes and Elements</span></span>  

 <span data-ttu-id="837b8-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="837b8-108">특성</span><span class="sxs-lookup"><span data-stu-id="837b8-108">Attributes</span></span>  
  
|<span data-ttu-id="837b8-109">attribute</span><span class="sxs-lookup"><span data-stu-id="837b8-109">Attribute</span></span>|<span data-ttu-id="837b8-110">설명</span><span class="sxs-lookup"><span data-stu-id="837b8-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="837b8-111">사용</span><span class="sxs-lookup"><span data-stu-id="837b8-111">enabled</span></span>|<span data-ttu-id="837b8-112">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="837b8-113">검색을 통해 어셈블리를 찾을 수 없기 때문에 발생 하는 바인딩 실패의 캐싱을 사용 하지 않도록 설정할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-113">Specifies whether to disable the caching of binding failures that occur because the assembly was not found by probing.</span></span>|  
  
## <a name="enabled-attribute"></a><span data-ttu-id="837b8-114">enabled 특성</span><span class="sxs-lookup"><span data-stu-id="837b8-114">enabled Attribute</span></span>  
  
|<span data-ttu-id="837b8-115">값</span><span class="sxs-lookup"><span data-stu-id="837b8-115">Value</span></span>|<span data-ttu-id="837b8-116">설명</span><span class="sxs-lookup"><span data-stu-id="837b8-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="837b8-117">0</span><span class="sxs-lookup"><span data-stu-id="837b8-117">0</span></span>|<span data-ttu-id="837b8-118">검색을 통해 어셈블리를 찾을 수 없기 때문에 발생 하는 바인딩 실패의 캐싱을 사용 하지 않도록 설정 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="837b8-118">Do not disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="837b8-119">이는 .NET Framework 버전 2.0부터 시작 하는 기본 바인딩 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-119">This is the default binding behavior starting with the .NET Framework version 2.0.</span></span>|  
|<span data-ttu-id="837b8-120">1</span><span class="sxs-lookup"><span data-stu-id="837b8-120">1</span></span>|<span data-ttu-id="837b8-121">검색을 통해 어셈블리를 찾을 수 없기 때문에 발생 하는 바인딩 실패의 캐싱을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-121">Disable the caching of binding failures that occur because the assembly was not found by probing.</span></span> <span data-ttu-id="837b8-122">이 설정은 .NET Framework 버전 1.1의 바인딩 동작으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-122">This setting reverts to the binding behavior of the .NET Framework version 1.1.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="837b8-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="837b8-123">Child Elements</span></span>  

 <span data-ttu-id="837b8-124">없음</span><span class="sxs-lookup"><span data-stu-id="837b8-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="837b8-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="837b8-125">Parent Elements</span></span>  
  
|<span data-ttu-id="837b8-126">요소</span><span class="sxs-lookup"><span data-stu-id="837b8-126">Element</span></span>|<span data-ttu-id="837b8-127">설명</span><span class="sxs-lookup"><span data-stu-id="837b8-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="837b8-128">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="837b8-129">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-129">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="837b8-130">설명</span><span class="sxs-lookup"><span data-stu-id="837b8-130">Remarks</span></span>  

 <span data-ttu-id="837b8-131">.NET Framework 버전 2.0부터 어셈블리를 로드 하는 기본 동작은 모든 바인딩과 로드 오류를 캐시 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-131">Starting with the .NET Framework version 2.0, the default behavior for loading assemblies is to cache all binding and loading failures.</span></span> <span data-ttu-id="837b8-132">즉, 어셈블리를 로드 하지 못한 경우 어셈블리를 찾지 않고도 동일한 어셈블리를 로드 하는 후속 요청이 즉시 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-132">That is, if an attempt to load an assembly fails, subsequent requests to load the same assembly fail immediately, without any attempt to locate the assembly.</span></span> <span data-ttu-id="837b8-133">이 요소는 어셈블리를 검색 경로에서 찾을 수 없기 때문에 발생 하는 바인딩 실패에 대 한 기본 동작을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-133">This element disables that default behavior for binding failures that occur because the assembly could not be found in the probing path.</span></span> <span data-ttu-id="837b8-134">이러한 오류는 throw <xref:System.IO.FileNotFoundException> 됩니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-134">These failures throw <xref:System.IO.FileNotFoundException>.</span></span>  
  
 <span data-ttu-id="837b8-135">일부 바인딩 및 로드 오류는이 요소의 영향을 받지 않으며 항상 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-135">Some binding and loading failures are not affected by this element, and are always cached.</span></span> <span data-ttu-id="837b8-136">이러한 오류는 어셈블리를 찾았지만 로드할 수 없기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-136">These failures occur because the assembly was found but could not be loaded.</span></span> <span data-ttu-id="837b8-137"><xref:System.BadImageFormatException>또는를 throw <xref:System.IO.FileLoadException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-137">They throw <xref:System.BadImageFormatException> or <xref:System.IO.FileLoadException>.</span></span> <span data-ttu-id="837b8-138">다음 목록에 이러한 오류의 몇 가지 예가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-138">The following list includes some examples of such failures.</span></span>  
  
- <span data-ttu-id="837b8-139">올바른 어셈블리가 아닌 파일을 로드 하려고 시도 하는 경우 잘못 된 파일이 올바른 어셈블리로 바뀐 경우에도 이후에 어셈블리를 로드 하려는 시도가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-139">If you attempt to load a file is not a valid assembly, subsequent attempts to load the assembly will fail even if the bad file is replaced with the correct assembly.</span></span>  
  
- <span data-ttu-id="837b8-140">파일 시스템에 의해 잠긴 어셈블리를 로드 하려고 하면 파일 시스템에서 어셈블리를 해제 한 후에도 이후에 어셈블리를 로드 하려는 시도가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-140">If you attempt to load an assembly that is locked by the file system, subsequent attempts to load the assembly will fail even after the assembly is released by the file system.</span></span>  
  
- <span data-ttu-id="837b8-141">로드 하려는 하나 이상의 어셈블리 버전이 검색 경로에 있지만 요청 하는 특정 버전이 검색 경로에 없는 경우 올바른 버전이 검색 경로로 이동 되더라도 이후 버전의 로드 시도는 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-141">If one or more versions of the assembly that you are attempting to load is in the probing path, but the specific version you are requesting is not among them, subsequent attempts to load that version will fail even if the correct version is moved into the probing path.</span></span>  
  
## <a name="example"></a><span data-ttu-id="837b8-142">예제</span><span class="sxs-lookup"><span data-stu-id="837b8-142">Example</span></span>  

 <span data-ttu-id="837b8-143">다음 예제에서는 어셈블리를 검색 하 여 찾을 수 없기 때문에 발생 하는 어셈블리 바인딩 실패의 캐싱을 사용 하지 않도록 설정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="837b8-143">The following example shows how to disable the caching of assembly binding failures that occur because the assembly was not found by probing.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <disableCachingBindingFailures enabled="1" />  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="837b8-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="837b8-144">See also</span></span>

- [<span data-ttu-id="837b8-145">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="837b8-145">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="837b8-146">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="837b8-146">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="837b8-147">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="837b8-147">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
