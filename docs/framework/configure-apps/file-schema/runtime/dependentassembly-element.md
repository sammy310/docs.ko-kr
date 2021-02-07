---
description: '다음에 대 한 자세한 정보: <dependentAssembly> 요소'
title: <dependentAssembly> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly
- http://schemas.microsoft.com/.NetConfiguration/v2.0#dependentAssembly
helpviewer_keywords:
- container tags, <dependentAssembly> element
- dependentAssembly element
- <dependentAssembly> element
ms.assetid: 14e95627-dd79-4b82-ac85-e682aa3a31d8
ms.openlocfilehash: c804920de961fc609fd04a0853ecbdbc9202e5be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719086"
---
# <a name="dependentassembly-element"></a><span data-ttu-id="dd3e3-103">\<dependentAssembly> 요소</span><span class="sxs-lookup"><span data-stu-id="dd3e3-103">\<dependentAssembly> Element</span></span>

<span data-ttu-id="dd3e3-104">각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-104">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="dd3e3-105">`dependentAssembly`각 어셈블리에 대해 하나의 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-105">Use one `dependentAssembly` element for each assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<dependentAssembly>**  
  
## <a name="syntax"></a><span data-ttu-id="dd3e3-106">구문</span><span class="sxs-lookup"><span data-stu-id="dd3e3-106">Syntax</span></span>  
  
```xml  
<dependentAssembly>
</dependentAssembly>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dd3e3-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="dd3e3-107">Attributes and Elements</span></span>  

 <span data-ttu-id="dd3e3-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dd3e3-109">특성</span><span class="sxs-lookup"><span data-stu-id="dd3e3-109">Attributes</span></span>  

 <span data-ttu-id="dd3e3-110">없음</span><span class="sxs-lookup"><span data-stu-id="dd3e3-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dd3e3-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="dd3e3-111">Child Elements</span></span>  
  
|<span data-ttu-id="dd3e3-112">요소</span><span class="sxs-lookup"><span data-stu-id="dd3e3-112">Element</span></span>|<span data-ttu-id="dd3e3-113">설명</span><span class="sxs-lookup"><span data-stu-id="dd3e3-113">Description</span></span>|  
|-------------|-----------------|  
|`assemblyIdentity`|<span data-ttu-id="dd3e3-114">어셈블리에 대 한 식별 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-114">Contains identifying information about the assembly.</span></span> <span data-ttu-id="dd3e3-115">이 요소는 각 요소에 포함 되어야 합니다 `dependentAssembly` .</span><span class="sxs-lookup"><span data-stu-id="dd3e3-115">This element must be included in each `dependentAssembly` element.</span></span>|  
|`codeBase`|<span data-ttu-id="dd3e3-116">컴퓨터에 설치 되어 있지 않은 경우 런타임이 공유 어셈블리를 찾을 수 있는 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-116">Specifies where the runtime can find a shared assembly if it is not installed on the computer.</span></span>|  
|`bindingRedirect`|<span data-ttu-id="dd3e3-117">어셈블리 버전을 다른 버전으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-117">Redirects one assembly version to another.</span></span>|  
|`publisherPolicy`|<span data-ttu-id="dd3e3-118">런타임에서이 어셈블리에 대 한 게시자 정책을 적용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-118">Specifies whether the runtime applies publisher policy for this assembly.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dd3e3-119">부모 요소</span><span class="sxs-lookup"><span data-stu-id="dd3e3-119">Parent Elements</span></span>  
  
|<span data-ttu-id="dd3e3-120">요소</span><span class="sxs-lookup"><span data-stu-id="dd3e3-120">Element</span></span>|<span data-ttu-id="dd3e3-121">설명</span><span class="sxs-lookup"><span data-stu-id="dd3e3-121">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="dd3e3-122">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-122">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="dd3e3-123">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="dd3e3-124">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-124">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="dd3e3-125">예제</span><span class="sxs-lookup"><span data-stu-id="dd3e3-125">Example</span></span>  

 <span data-ttu-id="dd3e3-126">다음 예제에서는 두 어셈블리에 대 한 어셈블리 정보를 캡슐화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd3e3-126">The following example shows how to encapsulate assembly information for two assemblies.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for myAssembly.-->  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="mySecondAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <!--Redirection and codeBase policy for mySecondAssembly.-->  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dd3e3-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dd3e3-127">See also</span></span>

- [<span data-ttu-id="dd3e3-128">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="dd3e3-128">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dd3e3-129">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="dd3e3-129">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="dd3e3-130">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="dd3e3-130">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
