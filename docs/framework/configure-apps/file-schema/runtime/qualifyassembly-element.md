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
ms.openlocfilehash: 17cfe9fc39d65f146beef5d02c701f5e3e2fbbe1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73115777"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="91c1d-102">\<B l y > 요소</span><span class="sxs-lookup"><span data-stu-id="91c1d-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="91c1d-103">부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="91c1d-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="91c1d-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="91c1d-105">&nbsp; &nbsp;[ **\<runtime >** ](runtime-element.md) </span><span class="sxs-lookup"><span data-stu-id="91c1d-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="91c1d-106">&nbsp; &nbsp; &nbsp; &nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md) </span><span class="sxs-lookup"><span data-stu-id="91c1d-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="91c1d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<b l y >**</span><span class="sxs-lookup"><span data-stu-id="91c1d-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c1d-108">구문</span><span class="sxs-lookup"><span data-stu-id="91c1d-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="91c1d-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="91c1d-109">Attributes and Elements</span></span>  
 <span data-ttu-id="91c1d-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="91c1d-111">특성</span><span class="sxs-lookup"><span data-stu-id="91c1d-111">Attributes</span></span>  
  
|<span data-ttu-id="91c1d-112">특성</span><span class="sxs-lookup"><span data-stu-id="91c1d-112">Attribute</span></span>|<span data-ttu-id="91c1d-113">설명</span><span class="sxs-lookup"><span data-stu-id="91c1d-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="91c1d-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="91c1d-115">코드에 표시 되는 어셈블리의 부분 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="91c1d-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="91c1d-117">전역 어셈블리 캐시에 표시 되는 어셈블리의 전체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="91c1d-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="91c1d-118">Child Elements</span></span>  
 <span data-ttu-id="91c1d-119">없음.</span><span class="sxs-lookup"><span data-stu-id="91c1d-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="91c1d-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="91c1d-120">Parent Elements</span></span>  
  
|<span data-ttu-id="91c1d-121">요소</span><span class="sxs-lookup"><span data-stu-id="91c1d-121">Element</span></span>|<span data-ttu-id="91c1d-122">설명</span><span class="sxs-lookup"><span data-stu-id="91c1d-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="91c1d-123">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="91c1d-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="91c1d-125">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="91c1d-126">주의</span><span class="sxs-lookup"><span data-stu-id="91c1d-126">Remarks</span></span>  
 <span data-ttu-id="91c1d-127">부분 어셈블리 이름을 사용 하 여 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 메서드를 호출 하면 공용 언어 런타임이 응용 프로그램 기본 디렉터리 에서만 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="91c1d-128">응용 프로그램 구성 파일의 **\<b l y >** 요소를 사용 하 여 전체 어셈블리 정보 (이름, 버전, 공개 키 토큰 및 문화권)를 제공 하 고 공용 언어 런타임에서 전역으로 어셈블리를 검색 합니다. 어셈블리 캐시.</span><span class="sxs-lookup"><span data-stu-id="91c1d-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="91c1d-129">**FullName** 특성에는 어셈블리 id의 네 가지 필드인 이름, 버전, 공개 키 토큰 및 문화권이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="91c1d-130">**PartialName** 특성은 어셈블리를 부분적으로 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="91c1d-131">적어도 어셈블리의 텍스트 이름 (가장 일반적인 경우)을 지정 해야 하지만 버전, 공개 키 토큰 또는 문화권 (또는 4의 모든 조합)을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="91c1d-132">**PartialName** 은 호출에 지정 된 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="91c1d-133">예를 들어 `"math"`를 구성 파일에 **partialName** 특성으로 지정 하 고 코드에서 `Assembly.Load("math, Version=3.3.3.3")`를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91c1d-134">예제</span><span class="sxs-lookup"><span data-stu-id="91c1d-134">Example</span></span>  
 <span data-ttu-id="91c1d-135">다음 예에서는 호출 `Assembly.Load("math")`를 `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`으로 논리적으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="91c1d-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="91c1d-136">참조</span><span class="sxs-lookup"><span data-stu-id="91c1d-136">See also</span></span>

- [<span data-ttu-id="91c1d-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="91c1d-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="91c1d-138">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="91c1d-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="91c1d-139">[부분 어셈블리 참조](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="91c1d-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
