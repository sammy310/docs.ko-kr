---
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
ms.openlocfilehash: d5766b76f18dce441cb260887a753dcf64642a6f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098704"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="d79fb-102">\<assemblyIdentity > 요소에 대 한 \<런타임 ></span><span class="sxs-lookup"><span data-stu-id="d79fb-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="d79fb-103">어셈블리에 대 한 식별 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-103">Contains identifying information about the assembly.</span></span>  
  
 <span data-ttu-id="d79fb-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d79fb-104">\<configuration></span></span>  
<span data-ttu-id="d79fb-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="d79fb-105">\<runtime></span></span>  
<span data-ttu-id="d79fb-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="d79fb-106">\<assemblyBinding></span></span>  
<span data-ttu-id="d79fb-107">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="d79fb-107">\<dependentAssembly></span></span>  
<span data-ttu-id="d79fb-108">\<assemblyIdentity></span><span class="sxs-lookup"><span data-stu-id="d79fb-108">\<assemblyIdentity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79fb-109">구문</span><span class="sxs-lookup"><span data-stu-id="d79fb-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity    
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d79fb-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d79fb-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d79fb-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d79fb-112">특성</span><span class="sxs-lookup"><span data-stu-id="d79fb-112">Attributes</span></span>  
  
|<span data-ttu-id="d79fb-113">특성</span><span class="sxs-lookup"><span data-stu-id="d79fb-113">Attribute</span></span>|<span data-ttu-id="d79fb-114">설명</span><span class="sxs-lookup"><span data-stu-id="d79fb-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d79fb-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="d79fb-116">어셈블리의 이름</span><span class="sxs-lookup"><span data-stu-id="d79fb-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="d79fb-117">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d79fb-118">언어 및 국가/지역을 어셈블리를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="d79fb-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d79fb-120">어셈블리의 강력한 이름을 지정 하는 16 진수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="d79fb-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d79fb-122">중 값 "x86", "amd64", "msil" 또는 "ia64" 프로세서 특정 코드로 포함 된 어셈블리에 대 한 프로세서 아키텍처를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="d79fb-123">값은 대/소문자 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-123">The values are not case-sensitive.</span></span> <span data-ttu-id="d79fb-124">특성에 다른 값을 전체 할당 된 경우 `<assemblyIdentity>` 요소는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="d79fb-125"><xref:System.Reflection.ProcessorArchitecture>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d79fb-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="d79fb-126">processorArchitecture 특성</span><span class="sxs-lookup"><span data-stu-id="d79fb-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="d79fb-127">값</span><span class="sxs-lookup"><span data-stu-id="d79fb-127">Value</span></span>|<span data-ttu-id="d79fb-128">설명</span><span class="sxs-lookup"><span data-stu-id="d79fb-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="d79fb-129">AMD 64 x86 아키텍처에만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="d79fb-130">Intel Itanium 아키텍처에만 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="d79fb-131">프로세서 및 워드 당 비트에 대해 중립적입니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="d79fb-132">32 비트 x86 프로세서, 네이티브 또는 64 비트 플랫폼에서 Windows (WOW) 환경에서 Windows에서.</span><span class="sxs-lookup"><span data-stu-id="d79fb-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d79fb-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d79fb-133">Child Elements</span></span>  
 <span data-ttu-id="d79fb-134">없음</span><span class="sxs-lookup"><span data-stu-id="d79fb-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d79fb-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d79fb-135">Parent Elements</span></span>  
  
|<span data-ttu-id="d79fb-136">요소</span><span class="sxs-lookup"><span data-stu-id="d79fb-136">Element</span></span>|<span data-ttu-id="d79fb-137">설명</span><span class="sxs-lookup"><span data-stu-id="d79fb-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="d79fb-138">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="d79fb-139">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="d79fb-140">각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="d79fb-141">하나를 사용 하 여 `<dependentAssembly>` 각 어셈블리에 대 한 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="d79fb-142">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d79fb-143">설명</span><span class="sxs-lookup"><span data-stu-id="d79fb-143">Remarks</span></span>  
 <span data-ttu-id="d79fb-144">모든  **\<dependentAssembly >** 요소가 하나 있어야  **\<assemblyIdentity >** 자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="d79fb-145">경우는 `processorArchitecture` 특성이 있는 경우는 `<assemblyIdentity>` 요소 해당 프로세서 아키텍처를 사용 하 여 어셈블리에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="d79fb-146">경우는 `processorArchitecture` 특성이 있는 `<assemblyIdentity>` 요소 모든 프로세서 아키텍처를 사용 하 여 어셈블리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="d79fb-147">다음 예제에서는 두 개의 서로 다른 두 프로세서 아키텍처를 대상으로 하 고 버전이 유지 하지 동기화 같은 이름의 두 어셈블리에 대 한 구성 파일을 보여 줍니다. X86 응용 프로그램을 실행 하는 경우 첫 번째 플랫폼 `<assemblyIdentity>` 요소 적용 하 고 나머지는 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="d79fb-148">응용 프로그램 이외의 x86 또는 ia64 플랫폼에서 실행 하는 경우 모두 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
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
  
 <span data-ttu-id="d79fb-149">구성 파일을 포함 하는 경우는 `<assemblyIdentity>` 없는 요소에 `processorArchitecture` 특성을 포함 하 고 있지는 플랫폼에 없는 요소를 일치 하는 요소는 `processorArchitecture` 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d79fb-150">예제</span><span class="sxs-lookup"><span data-stu-id="d79fb-150">Example</span></span>  
 <span data-ttu-id="d79fb-151">다음 예제에서는 어셈블리에 대 한 정보를 제공 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d79fb-151">The following example shows how to provide information about an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d79fb-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="d79fb-152">See also</span></span>

- [<span data-ttu-id="d79fb-153">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="d79fb-153">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="d79fb-154">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="d79fb-154">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="d79fb-155">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="d79fb-155">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
