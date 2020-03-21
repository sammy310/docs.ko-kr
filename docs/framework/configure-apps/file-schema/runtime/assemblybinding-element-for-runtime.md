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
ms.openlocfilehash: 202b063ad3f0f9696cdc12aff434d61fe5a813e6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79154324"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="7f9ab-102">\<런타임> \<대한 어셈블리 바인딩> 요소</span><span class="sxs-lookup"><span data-stu-id="7f9ab-102">\<assemblyBinding> Element for \<runtime></span></span>
<span data-ttu-id="7f9ab-103">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
<span data-ttu-id="7f9ab-104">[**\<구성>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f9ab-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7f9ab-105">&nbsp;&nbsp;[**\<런타임>**](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="7f9ab-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="7f9ab-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<어셈블리바인딩>**</span><span class="sxs-lookup"><span data-stu-id="7f9ab-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f9ab-107">구문</span><span class="sxs-lookup"><span data-stu-id="7f9ab-107">Syntax</span></span>  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7f9ab-108">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7f9ab-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7f9ab-109">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7f9ab-110">특성</span><span class="sxs-lookup"><span data-stu-id="7f9ab-110">Attributes</span></span>  
  
|<span data-ttu-id="7f9ab-111">attribute</span><span class="sxs-lookup"><span data-stu-id="7f9ab-111">Attribute</span></span>|<span data-ttu-id="7f9ab-112">Description</span><span class="sxs-lookup"><span data-stu-id="7f9ab-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7f9ab-113">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="7f9ab-113">**xmlns**</span></span>|<span data-ttu-id="7f9ab-114">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="7f9ab-115">어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-115">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="7f9ab-116">문자열 string "urn:schemas-microsoft-com:asm.v1"을 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-116">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="7f9ab-117">**Appliesto**</span><span class="sxs-lookup"><span data-stu-id="7f9ab-117">**appliesTo**</span></span>|<span data-ttu-id="7f9ab-118">.NET Framework 어셈블리 리디렉션이 적용되는 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-118">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="7f9ab-119">이 선택적 특성은 .NET Framework 버전 번호를 사용하여 특성이 적용되는 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-119">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="7f9ab-120">**appliesTo** 특성이 지정되지 않으면 **\<assemblyBinding>** 요소는 .NET Framework의 모든 버전에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-120">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="7f9ab-121">**적용To** 특성은 .NET Framework 버전 1.1에서 도입되었습니다. .NET Framework 버전 1.0에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-121">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="7f9ab-122">즉, **적용하는** 특성이 지정된 경우에도 .NET Framework 버전 1.0을 사용할 때 모든 \*\* \<어셈블리바인딩>\*\* 요소가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-122">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7f9ab-123">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7f9ab-123">Child Elements</span></span>  
  
|<span data-ttu-id="7f9ab-124">요소</span><span class="sxs-lookup"><span data-stu-id="7f9ab-124">Element</span></span>|<span data-ttu-id="7f9ab-125">Description</span><span class="sxs-lookup"><span data-stu-id="7f9ab-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7f9ab-126">\<종속어셈블리></span><span class="sxs-lookup"><span data-stu-id="7f9ab-126">\<dependentAssembly></span></span>](dependentassembly-element.md)|<span data-ttu-id="7f9ab-127">어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-127">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="7f9ab-128">각 어셈블리에 대해 \*\* \<하나의 종속어셈블리>\*\* 태그를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-128">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[<span data-ttu-id="7f9ab-129">\<프로빙></span><span class="sxs-lookup"><span data-stu-id="7f9ab-129">\<probing></span></span>](probing-element.md)|<span data-ttu-id="7f9ab-130">어셈블리를 로드할 때 공용 언어 런타임이 검색하는 하위 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-130">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[<span data-ttu-id="7f9ab-131">\<게시자정책></span><span class="sxs-lookup"><span data-stu-id="7f9ab-131">\<publisherPolicy></span></span>](publisherpolicy-element.md)|<span data-ttu-id="7f9ab-132">런타임이 게시자 정책을 적용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-132">Specifies whether the runtime applies publisher policy.</span></span>|  
|[<span data-ttu-id="7f9ab-133">\<자격 어셈블리></span><span class="sxs-lookup"><span data-stu-id="7f9ab-133">\<qualifyAssembly></span></span>](qualifyassembly-element.md)|<span data-ttu-id="7f9ab-134">부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-134">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7f9ab-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7f9ab-135">Parent Elements</span></span>  
  
|<span data-ttu-id="7f9ab-136">요소</span><span class="sxs-lookup"><span data-stu-id="7f9ab-136">Element</span></span>|<span data-ttu-id="7f9ab-137">Description</span><span class="sxs-lookup"><span data-stu-id="7f9ab-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="7f9ab-138">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="7f9ab-139">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-139">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7f9ab-140">예제</span><span class="sxs-lookup"><span data-stu-id="7f9ab-140">Example</span></span>  
 <span data-ttu-id="7f9ab-141">다음 예제에서는 어셈블리 버전을 다른 버전으로 리디렉션하는 방법을 보여 주고 Codebase를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f9ab-141">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
  
 <span data-ttu-id="7f9ab-142">다음 예제에서는 를 사용 하는 방법을 보여 주며합니다 .NET Framework 어셈블리의 바인딩을 리디렉션하려면 **특성이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7f9ab-142">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7f9ab-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f9ab-143">See also</span></span>

- [<span data-ttu-id="7f9ab-144">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="7f9ab-144">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="7f9ab-145">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="7f9ab-145">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="7f9ab-146">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="7f9ab-146">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
