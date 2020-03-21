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
ms.openlocfilehash: b026dafbde796bbd8726de56b532ed6710ba2290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154311"
---
# <a name="assemblyidentity-element-for-runtime"></a><span data-ttu-id="54dec-102">\<어셈블리런타임 \<> 대한 어셈블리ID> 요소</span><span class="sxs-lookup"><span data-stu-id="54dec-102">\<assemblyIdentity> Element for \<runtime></span></span>
<span data-ttu-id="54dec-103">어셈블리에 대한 식별 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-103">Contains identifying information about the assembly.</span></span>  
  
<span data-ttu-id="54dec-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="54dec-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="54dec-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="54dec-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="54dec-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<어셈블리바인딩>**](assemblybinding-element-for-runtime.md)</span><span class="sxs-lookup"><span data-stu-id="54dec-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)</span></span>\
<span data-ttu-id="54dec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<종속어셈블리>**](dependentassembly-element.md)</span><span class="sxs-lookup"><span data-stu-id="54dec-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)</span></span>\
<span data-ttu-id="54dec-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<어셈블리정체성>**</span><span class="sxs-lookup"><span data-stu-id="54dec-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyIdentity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54dec-109">구문</span><span class="sxs-lookup"><span data-stu-id="54dec-109">Syntax</span></span>  
  
```xml  
   <assemblyIdentity
name="assembly name"  
publicKeyToken="public key token"  
culture="assembly culture"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="54dec-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="54dec-110">Attributes and Elements</span></span>  
 <span data-ttu-id="54dec-111">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="54dec-112">특성</span><span class="sxs-lookup"><span data-stu-id="54dec-112">Attributes</span></span>  
  
|<span data-ttu-id="54dec-113">attribute</span><span class="sxs-lookup"><span data-stu-id="54dec-113">Attribute</span></span>|<span data-ttu-id="54dec-114">Description</span><span class="sxs-lookup"><span data-stu-id="54dec-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="54dec-115">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="54dec-116">어셈블리의 이름</span><span class="sxs-lookup"><span data-stu-id="54dec-116">The name of the assembly</span></span>|  
|`culture`|<span data-ttu-id="54dec-117">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="54dec-118">어셈블리의 언어 및 국가/지역을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-118">A string that specifies the language and country/region of the assembly.</span></span>|  
|`publicKeyToken`|<span data-ttu-id="54dec-119">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="54dec-120">어셈블리의 강력한 이름을 지정하는 육각형 값입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-120">A hexadecimal value that specifies the strong name of the assembly.</span></span>|  
|`processorArchitecture`|<span data-ttu-id="54dec-121">선택적 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="54dec-122">프로세서 별 코드를 포함하는 어셈블리의 프로세서 아키텍처를 지정하는 값 "x86", "amd64", "msil" 또는 "ia64"의 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-122">One of the values "x86", "amd64", "msil", or "ia64", specifying the processor architecture for an assembly that contains processor-specific code.</span></span> <span data-ttu-id="54dec-123">값은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-123">The values are not case-sensitive.</span></span> <span data-ttu-id="54dec-124">특성에 다른 값이 할당되면 전체 `<assemblyIdentity>` 요소가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-124">If the attribute is assigned any other value, the entire `<assemblyIdentity>` element is ignored.</span></span> <span data-ttu-id="54dec-125"><xref:System.Reflection.ProcessorArchitecture>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54dec-125">See <xref:System.Reflection.ProcessorArchitecture>.</span></span>|  
  
## <a name="processorarchitecture-attribute"></a><span data-ttu-id="54dec-126">프로세서아키텍처 속성</span><span class="sxs-lookup"><span data-stu-id="54dec-126">processorArchitecture Attribute</span></span>  
  
|<span data-ttu-id="54dec-127">값</span><span class="sxs-lookup"><span data-stu-id="54dec-127">Value</span></span>|<span data-ttu-id="54dec-128">Description</span><span class="sxs-lookup"><span data-stu-id="54dec-128">Description</span></span>|  
|-----------|-----------------|  
|`amd64`|<span data-ttu-id="54dec-129">AMD x86-64 아키텍처전용입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-129">AMD x86-64 architecture only.</span></span>|  
|`ia64`|<span data-ttu-id="54dec-130">인텔 이타늄 아키텍처만.</span><span class="sxs-lookup"><span data-stu-id="54dec-130">Intel Itanium architecture only.</span></span>|  
|`msil`|<span data-ttu-id="54dec-131">프로세서 및 워드 당 비트에 대해 중립적입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-131">Neutral with respect to processor and bits-per-word.</span></span>|  
|`x86`|<span data-ttu-id="54dec-132">64비트 플랫폼의 기본 또는 Windows(WOW) 환경에서 32비트 x86 프로세서입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-132">A 32-bit x86 processor, either native or in the Windows on Windows (WOW) environment on a 64-bit platform.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="54dec-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="54dec-133">Child Elements</span></span>  
 <span data-ttu-id="54dec-134">없음</span><span class="sxs-lookup"><span data-stu-id="54dec-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="54dec-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="54dec-135">Parent Elements</span></span>  
  
|<span data-ttu-id="54dec-136">요소</span><span class="sxs-lookup"><span data-stu-id="54dec-136">Element</span></span>|<span data-ttu-id="54dec-137">Description</span><span class="sxs-lookup"><span data-stu-id="54dec-137">Description</span></span>|  
|-------------|-----------------|  
|`assemblyBinding`|<span data-ttu-id="54dec-138">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-138">Contains information about assembly version redirection and the locations of assemblies.</span></span>|  
|`configuration`|<span data-ttu-id="54dec-139">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`dependentAssembly`|<span data-ttu-id="54dec-140">각 어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-140">Encapsulates binding policy and assembly location for each assembly.</span></span> <span data-ttu-id="54dec-141">각 `<dependentAssembly>` 어셈블리에 대해 하나의 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-141">Use one `<dependentAssembly>` element for each assembly.</span></span>|  
|`runtime`|<span data-ttu-id="54dec-142">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-142">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="54dec-143">설명</span><span class="sxs-lookup"><span data-stu-id="54dec-143">Remarks</span></span>  
 <span data-ttu-id="54dec-144">모든 \*\* \<종속어셈블리>\*\* 요소에는 하나의 \*\* \<어셈블리가\*\* 있어야 id>자식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-144">Every **\<dependentAssembly>** element must have one **\<assemblyIdentity>** child element.</span></span>  
  
 <span data-ttu-id="54dec-145">특성이 `processorArchitecture` 있는 경우 `<assemblyIdentity>` 요소는 해당 프로세서 아키텍처가 있는 어셈블리에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-145">If the `processorArchitecture` attribute is present, the `<assemblyIdentity>` element applies only to the assembly with the corresponding processor architecture.</span></span> <span data-ttu-id="54dec-146">특성이 `processorArchitecture` 없는 경우 `<assemblyIdentity>` 요소는 프로세서 아키텍처가 있는 어셈블리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-146">If the `processorArchitecture` attribute is not present, the `<assemblyIdentity>` element can apply to an assembly with any processor architecture.</span></span>  
  
 <span data-ttu-id="54dec-147">다음 예제에서는 두 개의 서로 다른 두 프로세서 아키텍처를 대상으로 하는 이름이 같은 두 어셈블리에 대한 구성 파일과 동기화된 버전이 유지되지 않은 구성 파일을 보여 주십니다. 응용 프로그램이 x86 플랫폼에서 실행되면 `<assemblyIdentity>` 첫 번째 요소가 적용되고 다른 요소는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-147">The following example shows a configuration file for two assemblies with the same name that target two different two processor architectures, and whose versions have not been maintained in synch. When the application executes on the x86 platform the first `<assemblyIdentity>` element applies and the other is ignored.</span></span> <span data-ttu-id="54dec-148">응용 프로그램이 x86 또는 ia64 이외의 플랫폼에서 실행되는 경우 둘 다 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-148">If the application executes on a platform other than x86 or ia64, both are ignored.</span></span>  
  
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
  
 <span data-ttu-id="54dec-149">구성 파일에 특성이 `<assemblyIdentity>` 없는 `processorArchitecture` 요소가 포함되어 있고 플랫폼과 일치하는 요소가 없는 경우 `processorArchitecture` 특성이 없는 요소가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-149">If a configuration file contains an `<assemblyIdentity>` element with no `processorArchitecture` attribute, and does not contain an element that matches the platform, the element without the `processorArchitecture` attribute is used.</span></span>  
  
## <a name="example"></a><span data-ttu-id="54dec-150">예제</span><span class="sxs-lookup"><span data-stu-id="54dec-150">Example</span></span>  
 <span data-ttu-id="54dec-151">다음 예제에서는 어셈블리에 대한 정보를 제공하는 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54dec-151">The following example shows how to provide information about an assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="54dec-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54dec-152">See also</span></span>

- [<span data-ttu-id="54dec-153">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="54dec-153">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="54dec-154">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="54dec-154">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="54dec-155">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="54dec-155">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
