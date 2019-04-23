---
title: <runtime>에 대한 <assemblyBinding> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding
helpviewer_keywords:
- <assemblyBinding> element
- assemblyBinding element
- container tags, <assemblyBinding> element
ms.assetid: 964cbb35-ab49-4498-8471-209689e5dada
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eec77d4dd42a7b95d1e2cd0e353e2e54746676b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225250"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="6a1a3-102">\<assemblyBinding > 요소에 대 한 \<런타임 ></span><span class="sxs-lookup"><span data-stu-id="6a1a3-102">\<assemblyBinding> Element for \<runtime></span></span>
<span data-ttu-id="6a1a3-103">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
 <span data-ttu-id="6a1a3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="6a1a3-104">\<configuration></span></span>  
<span data-ttu-id="6a1a3-105">\<runtime></span><span class="sxs-lookup"><span data-stu-id="6a1a3-105">\<runtime></span></span>  
<span data-ttu-id="6a1a3-106">\<assemblyBinding></span><span class="sxs-lookup"><span data-stu-id="6a1a3-106">\<assemblyBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a1a3-107">구문</span><span class="sxs-lookup"><span data-stu-id="6a1a3-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding    
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6a1a3-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6a1a3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="6a1a3-109">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6a1a3-110">특성</span><span class="sxs-lookup"><span data-stu-id="6a1a3-110">Attributes</span></span>  
  
|<span data-ttu-id="6a1a3-111">특성</span><span class="sxs-lookup"><span data-stu-id="6a1a3-111">Attribute</span></span>|<span data-ttu-id="6a1a3-112">설명</span><span class="sxs-lookup"><span data-stu-id="6a1a3-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6a1a3-113">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="6a1a3-113">**xmlns**</span></span>|<span data-ttu-id="6a1a3-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="6a1a3-115">어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="6a1a3-116">문자열 string "urn:schemas-microsoft-com:asm.v1"을 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="6a1a3-117">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="6a1a3-117">**appliesTo**</span></span>|<span data-ttu-id="6a1a3-118">.NET Framework 어셈블리 리디렉션이 적용되는 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="6a1a3-119">이 선택적 특성은 .NET Framework 버전 번호를 사용하여 특성이 적용되는 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="6a1a3-120">**appliesTo** 특성이 지정되지 않으면 **\<assemblyBinding>** 요소는 .NET Framework의 모든 버전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="6a1a3-121">합니다 **appliesTo** 특성은.NET Framework 버전 1.1에서에서 도입 되었고;.NET Framework 버전 1.0에서 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="6a1a3-122">즉, .NET Framework 버전 1.0을 사용할 때는 **appliesTo** 특성을 지정해도 모든 **\<assemblyBinding>** 요소가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6a1a3-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6a1a3-123">Child Elements</span></span>  
  
|<span data-ttu-id="6a1a3-124">요소</span><span class="sxs-lookup"><span data-stu-id="6a1a3-124">Element</span></span>|<span data-ttu-id="6a1a3-125">설명</span><span class="sxs-lookup"><span data-stu-id="6a1a3-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6a1a3-126">\<dependentAssembly></span><span class="sxs-lookup"><span data-stu-id="6a1a3-126">\<dependentAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/dependentassembly-element.md)|<span data-ttu-id="6a1a3-127">어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="6a1a3-128">하나를 사용 하 여  **\<dependentAssembly >** 각 어셈블리에 대 한 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="6a1a3-129">\<probing></span><span class="sxs-lookup"><span data-stu-id="6a1a3-129">\<probing></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)|<span data-ttu-id="6a1a3-130">어셈블리를 로드할 때 공용 언어 런타임이 검색하는 하위 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="6a1a3-131">\<publisherPolicy></span><span class="sxs-lookup"><span data-stu-id="6a1a3-131">\<publisherPolicy></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/publisherpolicy-element.md)|<span data-ttu-id="6a1a3-132">런타임이 게시자 정책을 적용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="6a1a3-133">\<qualifyAssembly></span><span class="sxs-lookup"><span data-stu-id="6a1a3-133">\<qualifyAssembly></span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/qualifyassembly-element.md)|<span data-ttu-id="6a1a3-134">부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6a1a3-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6a1a3-135">Parent Elements</span></span>  
  
|<span data-ttu-id="6a1a3-136">요소</span><span class="sxs-lookup"><span data-stu-id="6a1a3-136">Element</span></span>|<span data-ttu-id="6a1a3-137">설명</span><span class="sxs-lookup"><span data-stu-id="6a1a3-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6a1a3-138">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="6a1a3-139">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6a1a3-140">예제</span><span class="sxs-lookup"><span data-stu-id="6a1a3-140">Example</span></span>  
 <span data-ttu-id="6a1a3-141">다음 예제에서는 어셈블리 버전을 다른 버전으로 리디렉션하는 방법을 보여 주고 Codebase를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <dependentAssembly>  
            <assemblyIdentity name="myAssembly"  
                              publicKeyToken="32ab4ba45e0a69a1"  
                              culture="neutral" />  
            <bindingRedirect oldVersion="1.0.0.0"  
                             newVersion="2.0.0.0"/>  
            <codeBase version="2.0.0.0"  
                      href="http://www.litwareinc.com/myAssembly.dll"/>  
         </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="6a1a3-142">다음 예제에서는 사용 하는 방법을 보여 줍니다 합니다 **appliesTo** .NET Framework 어셈블리의 바인딩을 리디렉션하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6a1a3-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
```xml  
<runtime>  
   <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
      <dependentAssembly>   
         <assemblyIdentity name="mscorcfg" publicKeyToken="b03f5f7f11d50a3a" culture=""/>  
         <bindingRedirect oldVersion="0.0.0.0-65535.65535.65535.65535" newVersion="1.0.3300.0"/>  
      </dependentAssembly>  
   </assemblyBinding>  
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6a1a3-143">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a1a3-143">See also</span></span>

- [<span data-ttu-id="6a1a3-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="6a1a3-144">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="6a1a3-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="6a1a3-145">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="6a1a3-146">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="6a1a3-146">Redirecting Assembly Versions</span></span>](../../../../../docs/framework/configure-apps/redirect-assembly-versions.md)
