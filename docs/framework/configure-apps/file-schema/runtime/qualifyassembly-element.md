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
ms.openlocfilehash: 581b19cf74dcb5c2d5c4a549847629503fe0b6ff
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252366"
---
# <a name="qualifyassembly-element"></a><span data-ttu-id="5fe13-102">\<B l y > 요소</span><span class="sxs-lookup"><span data-stu-id="5fe13-102">\<qualifyAssembly> Element</span></span>
<span data-ttu-id="5fe13-103">부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-103">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>  
  
<span data-ttu-id="5fe13-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fe13-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5fe13-105">&nbsp;&nbsp;[ **\<런타임 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="5fe13-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="5fe13-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<assemblyBinding >** ](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="5fe13-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="5fe13-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<qualifyAssembly>**</span><span class="sxs-lookup"><span data-stu-id="5fe13-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<qualifyAssembly>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe13-108">구문</span><span class="sxs-lookup"><span data-stu-id="5fe13-108">Syntax</span></span>  
  
```xml  
      <qualifyAssembly partialName=  
      "PartialAssemblyName"  
                 fullName="FullAssemblyName"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5fe13-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5fe13-109">Attributes and Elements</span></span>  
 <span data-ttu-id="5fe13-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5fe13-111">특성</span><span class="sxs-lookup"><span data-stu-id="5fe13-111">Attributes</span></span>  
  
|<span data-ttu-id="5fe13-112">특성</span><span class="sxs-lookup"><span data-stu-id="5fe13-112">Attribute</span></span>|<span data-ttu-id="5fe13-113">설명</span><span class="sxs-lookup"><span data-stu-id="5fe13-113">Description</span></span>|  
|---------------|-----------------|  
|`partialName`|<span data-ttu-id="5fe13-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="5fe13-115">코드에 표시 되는 어셈블리의 부분 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-115">Specifies the partial name of the assembly as it appears in the code.</span></span>|  
|`fullName`|<span data-ttu-id="5fe13-116">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="5fe13-117">전역 어셈블리 캐시에 표시 되는 어셈블리의 전체 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-117">Specifies the full name of the assembly as it appears in the global assembly cache.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5fe13-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5fe13-118">Child Elements</span></span>  
 <span data-ttu-id="5fe13-119">없음</span><span class="sxs-lookup"><span data-stu-id="5fe13-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5fe13-120">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5fe13-120">Parent Elements</span></span>  
  
|<span data-ttu-id="5fe13-121">요소</span><span class="sxs-lookup"><span data-stu-id="5fe13-121">Element</span></span>|<span data-ttu-id="5fe13-122">설명</span><span class="sxs-lookup"><span data-stu-id="5fe13-122">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="5fe13-123">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-123">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="5fe13-124">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="5fe13-125">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-125">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5fe13-126">설명</span><span class="sxs-lookup"><span data-stu-id="5fe13-126">Remarks</span></span>  
 <span data-ttu-id="5fe13-127">부분 어셈블리 <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> 이름을 사용 하 여 메서드를 호출 하면 공용 언어 런타임이 응용 프로그램 기본 디렉터리 에서만 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-127">Calling the <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> method using partial assembly names causes the common language runtime to look for the assembly only in the application base directory.</span></span> <span data-ttu-id="5fe13-128">응용 프로그램 구성 파일에서  **bly>요소를사용하여전체어셈블리정보(이름,버전,공개키토큰및문화권)를제공하고공용언어런타임에서어셈블리를검색합니다.\<** 전역 어셈블리 캐시입니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-128">Use the **\<qualifyAssembly>** element in your application configuration file to provide the full assembly information (name, version, public key token, and culture) and cause the common language runtime to search for the assembly in the global assembly cache.</span></span>  
  
 <span data-ttu-id="5fe13-129">**FullName** 특성에는 어셈블리 id의 네 가지 필드인 이름, 버전, 공개 키 토큰 및 문화권이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-129">The **fullName** attribute must include the four fields of assembly identity: name, version, public key token, and culture.</span></span> <span data-ttu-id="5fe13-130">**PartialName** 특성은 어셈블리를 부분적으로 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-130">The **partialName** attribute must partially reference an assembly.</span></span> <span data-ttu-id="5fe13-131">적어도 어셈블리의 텍스트 이름 (가장 일반적인 경우)을 지정 해야 하지만 버전, 공개 키 토큰 또는 문화권 (또는 4의 모든 조합)을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-131">You must specify at least the assembly's text name (the most common case), but you can also include version, public key token, or culture (or any combination of the four, but not all four).</span></span> <span data-ttu-id="5fe13-132">**PartialName** 은 호출에 지정 된 이름과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-132">The **partialName** must match the name specified in your call.</span></span> <span data-ttu-id="5fe13-133">예를 들어 구성 파일에서 `"math"` 를 **partialName** 특성으로 지정 하 고 코드에서를 `Assembly.Load("math, Version=3.3.3.3")` 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-133">For example, you cannot specify `"math"` as the **partialName** attribute in your configuration file and call `Assembly.Load("math, Version=3.3.3.3")` in your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5fe13-134">예제</span><span class="sxs-lookup"><span data-stu-id="5fe13-134">Example</span></span>  
 <span data-ttu-id="5fe13-135">다음 예제에서는에 대 한 호출 `Assembly.Load("math")` 을 `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`논리적으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5fe13-135">The following example logically turns the call `Assembly.Load("math")` into `Assembly.Load("math,version=1.0.0.0,publicKeyToken=a1690a5ea44bab32,culture=neutral")`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5fe13-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="5fe13-136">See also</span></span>

- [<span data-ttu-id="5fe13-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="5fe13-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="5fe13-138">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="5fe13-138">How the Runtime Locates Assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
- <span data-ttu-id="5fe13-139">[부분 어셈블리 참조](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5fe13-139">[Partial Assembly References](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/0a7zy9z5(v=vs.100))</span></span>
