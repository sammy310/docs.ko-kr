---
description: '에 대 한 자세한 정보: <assemblyIdentity> 요소 <runtime>'
title: <runtime>에 대한 <assemblyIdentity> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/assemblyIdentity
- http://schemas.microsoft.com/.NetConfiguration/v2.0#assemblyIdentity
helpviewer_keywords:
- <assemblyIdentity> element
- container tags, <assemblyIdentity> element
- assemblyIdentity element
ms.assetid: cea4d187-6398-4da4-af09-c1abc6a349c1
ms.openlocfilehash: d53c4f7f5207fbcf9ad4a8f82667eacc1f57f5e2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719190"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="7e60e-103">\<runtime>에 대한 \<assemblyIdentity> 요소</span><span class="sxs-lookup"><span data-stu-id="7e60e-103">\<assemblyIdentity> Element for \<runtime></span></span>

<span data-ttu-id="7e60e-104">어셈블리에 대 한 식별 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-104">Contains identifying information about the assembly.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**  
  
## <a name="syntax"></a><span data-ttu-id="7e60e-105">구문</span><span class="sxs-lookup"><span data-stu-id="7e60e-105">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7e60e-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7e60e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="7e60e-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7e60e-108">특성</span><span class="sxs-lookup"><span data-stu-id="7e60e-108">Attributes</span></span>  
  
|<span data-ttu-id="7e60e-109">attribute</span><span class="sxs-lookup"><span data-stu-id="7e60e-109">Attribute</span></span>|<span data-ttu-id="7e60e-110">설명</span><span class="sxs-lookup"><span data-stu-id="7e60e-110">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="7e60e-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="7e60e-112">어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-112">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="7e60e-113">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7e60e-114">어셈블리의 언어 및 국가/지역을 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-114">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="7e60e-115">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7e60e-116">어셈블리의 강력한 이름을 지정 하는 16 진수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-116">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="7e60e-117">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="7e60e-118">프로세서 특정 코드를 포함 하는 어셈블리의 프로세서 아키텍처를 지정 하는 "x86", "amd64", "msil" 또는 "ia64" 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-118">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="7e60e-119">값은 대/소문자를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-119">The values are not case-sensitive.</span></span> <span data-ttu-id="7e60e-120">특성에 다른 값이 할당 된 경우에는 전체 `<assemblyIdentity>` 요소가 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-120">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="7e60e-121"><xref:System.Reflection.ProcessorArchitecture>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e60e-121">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="7e60e-122">processorArchitecture 특성</span><span class="sxs-lookup"><span data-stu-id="7e60e-122">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="7e60e-123">값</span><span class="sxs-lookup"><span data-stu-id="7e60e-123">Value</span></span>|<span data-ttu-id="7e60e-124">설명</span><span class="sxs-lookup"><span data-stu-id="7e60e-124">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="7e60e-125">AMD x86-64 아키텍처 전용.</span><span class="sxs-lookup"><span data-stu-id="7e60e-125">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="7e60e-126">Intel Itanium 아키텍처에만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-126">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="7e60e-127">프로세서 및 워드 당 비트에 대해 중립적입니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-127">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="7e60e-128">64 비트 플랫폼의 기본 또는 WOW (Windows on Windows) 환경에 있는 32 비트 x86 프로세서</span><span class="sxs-lookup"><span data-stu-id="7e60e-128">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7e60e-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7e60e-129">Child Elements</span></span>  

 <span data-ttu-id="7e60e-130">없음</span><span class="sxs-lookup"><span data-stu-id="7e60e-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7e60e-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7e60e-131">Parent Elements</span></span>  
  
|<span data-ttu-id="7e60e-132">요소</span><span class="sxs-lookup"><span data-stu-id="7e60e-132">Element</span></span>|<span data-ttu-id="7e60e-133">설명</span><span class="sxs-lookup"><span data-stu-id="7e60e-133">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="7e60e-134">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-134">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="7e60e-135">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-135">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="7e60e-136">각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-136">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="7e60e-137">`<dependentAssembly>`각 어셈블리에 대해 하나의 요소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-137">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="7e60e-138">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-138">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7e60e-139">설명</span><span class="sxs-lookup"><span data-stu-id="7e60e-139">Remarks</span></span>  

 <span data-ttu-id="7e60e-140">모든 **\<dependentAssembly>** 요소에는 자식 요소가 하나씩 있어야 합니다 **\<assemblyIdentity>** .</span><span class="sxs-lookup"><span data-stu-id="7e60e-140">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="7e60e-141">`processorArchitecture`특성이 있는 경우 `<assemblyIdentity>` 요소는 해당 프로세서 아키텍처를 사용 하는 어셈블리에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-141">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="7e60e-142">특성이 없는 경우 `processorArchitecture` `<assemblyIdentity>` 요소는 모든 프로세서 아키텍처를 사용 하 여 어셈블리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-142">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="7e60e-143">다음 예제에서는 두 개의 서로 다른 프로세서 아키텍처를 대상으로 하는 동일한 이름의 두 어셈블리에 대 한 구성 파일 및 해당 버전이 동기화에서 유지 관리 되지 않는 경우를 보여 줍니다. 응용 프로그램이 x86 플랫폼에서 실행 되는 경우 첫 번째 `<assemblyIdentity>` 요소가 적용 되 고 나머지 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-143">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="7e60e-144">응용 프로그램이 x86 또는 ia64 이외의 플랫폼에서 실행 되는 경우 둘 다 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-144">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"  
                  processorArchitecture="x86" />  
            <bindingRedirect oldVersion= "1.0.0.0"
                  newVersion="1.1.0.0" />  
         </dependentAssembly>  
         <dependentAssembly>  
            <assemblyIdentity name="MyAssembly"  
                  publicKeyToken="14a739be0244c389"  
                  culture="neutral"
                  processorArchitecture="ia64" />  
            <bindingRedirect oldVersion="1.0.0.0"
                  newVersion="2.0.0.0" />  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="7e60e-145">구성 파일에 `<assemblyIdentity>` `processorArchitecture` 특성이 없고 플랫폼과 일치 하는 요소가 포함 되지 않은 요소가 포함 된 경우 특성이 없는 요소가 `processorArchitecture` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-145">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7e60e-146">예제</span><span class="sxs-lookup"><span data-stu-id="7e60e-146">Example</span></span>  

 <span data-ttu-id="7e60e-147">다음 예제에서는 어셈블리에 대 한 정보를 제공 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7e60e-147">The following example shows how to provide information about an assembly.</span></span>  
  
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
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7e60e-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e60e-148">See also</span></span>

- [<span data-ttu-id="7e60e-149">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7e60e-149">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7e60e-150">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7e60e-150">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7e60e-151">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="7e60e-151">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
