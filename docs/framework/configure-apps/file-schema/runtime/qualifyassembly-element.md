---
title: <qualifyAssembly> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#qualifyAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/qualifyAssembly
helpviewer_keywords:
- container tags, <qualifyAssembly> element
- <qualifyAssembly> element
- qualifyAssembly element
ms.assetid: ad6442f6-1a9d-43b6-b733-04ac1b7f9b82
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a4741c6a4745bdba00fdb525b39b70d0b15e005
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704858"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="df517-102">\<qualifyAssembly > 요소</span><span class="sxs-lookup"><span data-stu-id="df517-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="df517-103">부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="df517-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
 <span data-ttu-id="df517-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="df517-104">\<configuration></span></span>  
<span data-ttu-id="df517-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="df517-105">\<runtime></span></span>  
<span data-ttu-id="df517-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="df517-106">\<assemblyBinding></span></span>  
<span data-ttu-id="df517-107">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="df517-107">\<qualifyAssembly></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df517-108">구문</span><span class="sxs-lookup"><span data-stu-id="df517-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="df517-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="df517-109">Attributes and Elements</span></span>  
 <span data-ttu-id="df517-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="df517-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="df517-111">특성</span><span class="sxs-lookup"><span data-stu-id="df517-111">Attributes</span></span>  
  
|<span data-ttu-id="df517-112">특성</span><span class="sxs-lookup"><span data-stu-id="df517-112">Attribute</span></span>|<span data-ttu-id="df517-113">설명</span><span class="sxs-lookup"><span data-stu-id="df517-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="df517-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="df517-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="df517-115">코드에 표시 된 대로 어셈블리의 부분 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df517-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="df517-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="df517-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="df517-117">전역 어셈블리 캐시에 표시 된 대로 어셈블리의 전체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df517-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="df517-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="df517-118">Child Elements</span></span>  
 <span data-ttu-id="df517-119">없음</span><span class="sxs-lookup"><span data-stu-id="df517-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="df517-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="df517-120">Parent Elements</span></span>  
  
|<span data-ttu-id="df517-121">요소</span><span class="sxs-lookup"><span data-stu-id="df517-121">Element</span></span>|<span data-ttu-id="df517-122">설명</span><span class="sxs-lookup"><span data-stu-id="df517-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="df517-123">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="df517-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="df517-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="df517-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="df517-125">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="df517-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df517-126">설명</span><span class="sxs-lookup"><span data-stu-id="df517-126">Remarks</span></span>  
 <span data-ttu-id="df517-127">호출 된 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 부분 어셈블리 이름을 사용 하는 메서드를 사용 하면 응용 프로그램 기본 디렉터리에만 어셈블리에 대 한 확인을 공용 언어 런타임.</span><span class="sxs-lookup"><span data-stu-id="df517-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="df517-128">사용 된  **\<qualifyAssembly >** (이름, 버전, 공개 키 토큰 및 문화권)에 전체 어셈블리 정보를 제공 하 여 검색 하려면 공용 언어 런타임이 응용 프로그램 구성 파일의 요소 전역 어셈블리 캐시에서 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="df517-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="df517-129">합니다 **fullName** 특성의 어셈블리 id는 4 개의 필드를 포함 해야 합니다: 이름, 버전, 공개 키 토큰 및 문화권입니다.</span><span class="sxs-lookup"><span data-stu-id="df517-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="df517-130">합니다 **partialName** 특성 어셈블리를 부분적으로 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df517-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="df517-131">어셈블리의 텍스트 이름 (가장 일반적인 경우)를 하나 이상 지정 해야 하지만 버전, 공개 키 토큰 또는 culture (또는 일부 4의 조합)을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df517-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="df517-132">합니다 **partialName** 호출에 지정 된 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="df517-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="df517-133">예를 들어 지정할 수 없습니다 `"math"` 으로 **partialName** 호출 프로그램과 구성 파일의 특성 `Assembly.Load("math, Version=3.3.3.3")` 코드에서.</span><span class="sxs-lookup"><span data-stu-id="df517-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df517-134">예제</span><span class="sxs-lookup"><span data-stu-id="df517-134">Example</span></span>  
 <span data-ttu-id="df517-135">다음 예제에서는 호출을 논리적으로 변환 `Assembly.Load("math")` 에 `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`입니다.</span><span class="sxs-lookup"><span data-stu-id="df517-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <qualifyAssembly partialName="math"   
                         fullName=  
"math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="df517-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="df517-136">See also</span></span>

- [<span data-ttu-id="df517-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="df517-137">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="df517-138">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="df517-138">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="df517-139">[부분 어셈블리 참조](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="df517-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
