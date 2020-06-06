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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "79154324"
---
# <a name="assemblybinding-element-for-runtime"></a><span data-ttu-id="cb973-102">\<runtime>에 대한 \<assemblyBinding> 요소</span><span class="sxs-lookup"><span data-stu-id="cb973-102">\<assemblyBinding> Element for \<runtime></span></span>
<span data-ttu-id="cb973-103">어셈블리 버전 리디렉션 및 어셈블리 위치에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-103">Contains information about assembly version redirection and the locations of assemblies.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<assemblyBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="cb973-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb973-104">Syntax</span></span>  
  
```xml  
      <assemblyBinding
   xmlns="urn:schemas-microsoft-com:asm.v1" appliesTo="v1.0.3705">  
</assemblyBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cb973-105">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="cb973-105">Attributes and Elements</span></span>  
 <span data-ttu-id="cb973-106">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cb973-107">특성</span><span class="sxs-lookup"><span data-stu-id="cb973-107">Attributes</span></span>  
  
|<span data-ttu-id="cb973-108">attribute</span><span class="sxs-lookup"><span data-stu-id="cb973-108">Attribute</span></span>|<span data-ttu-id="cb973-109">Description</span><span class="sxs-lookup"><span data-stu-id="cb973-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="cb973-110">**xmlns**</span><span class="sxs-lookup"><span data-stu-id="cb973-110">**xmlns**</span></span>|<span data-ttu-id="cb973-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="cb973-112">어셈블리 바인딩에 필요한 XML 네임스페이스를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-112">Specifies the XML namespace required for assembly binding.</span></span> <span data-ttu-id="cb973-113">문자열 string "urn:schemas-microsoft-com:asm.v1"을 값으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-113">Use the string "urn:schemas-microsoft-com:asm.v1" as the value.</span></span>|  
|<span data-ttu-id="cb973-114">**appliesTo**</span><span class="sxs-lookup"><span data-stu-id="cb973-114">**appliesTo**</span></span>|<span data-ttu-id="cb973-115">.NET Framework 어셈블리 리디렉션이 적용되는 런타임 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-115">Specifies the runtime version the .NET Framework assembly redirection applies to.</span></span> <span data-ttu-id="cb973-116">이 선택적 특성은 .NET Framework 버전 번호를 사용하여 특성이 적용되는 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-116">This optional attribute uses a .NET Framework version number to indicate what version it applies to.</span></span> <span data-ttu-id="cb973-117">**AppliesTo** 특성이 지정 되지 않은 경우 요소는 **\<assemblyBinding>** .NET Framework 모든 버전에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-117">If no **appliesTo** attribute is specified, the **\<assemblyBinding>** element applies to all versions of the .NET Framework.</span></span> <span data-ttu-id="cb973-118">**AppliesTo** 특성은 .NET Framework 버전 1.1에서 도입 되었습니다. .NET Framework 버전 1.0에서 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-118">The **appliesTo** attribute was introduced in .NET Framework version 1.1; it is ignored by the .NET Framework version 1.0.</span></span> <span data-ttu-id="cb973-119">이는 **\<assemblyBinding>** **appliesTo** 특성이 지정 된 경우에도 .NET Framework 버전 1.0을 사용 하는 경우 모든 요소가 적용 됨을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-119">This means that all **\<assemblyBinding>** elements are applied when using the .NET Framework version 1.0, even if an **appliesTo** attribute is specified.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="cb973-120">자식 요소</span><span class="sxs-lookup"><span data-stu-id="cb973-120">Child Elements</span></span>  
  
|<span data-ttu-id="cb973-121">요소</span><span class="sxs-lookup"><span data-stu-id="cb973-121">Element</span></span>|<span data-ttu-id="cb973-122">Description</span><span class="sxs-lookup"><span data-stu-id="cb973-122">Description</span></span>|  
|-------------|-----------------|  
|[\<dependentAssembly>](dependentassembly-element.md)|<span data-ttu-id="cb973-123">어셈블리에 대한 바인딩 정책 및 어셈블리 위치를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-123">Encapsulates binding policy and assembly location for an assembly.</span></span> <span data-ttu-id="cb973-124">**\<dependentAssembly>** 각 어셈블리에 대해 하나의 태그를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-124">Use one **\<dependentAssembly>** tag for each assembly.</span></span>|  
|[\<probing>](probing-element.md)|<span data-ttu-id="cb973-125">어셈블리를 로드할 때 공용 언어 런타임이 검색하는 하위 디렉터리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-125">Specifies subdirectories the common language runtime searches when loading assemblies.</span></span>|  
|[\<publisherPolicy>](publisherpolicy-element.md)|<span data-ttu-id="cb973-126">런타임이 게시자 정책을 적용할지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-126">Specifies whether the runtime applies publisher policy.</span></span>|  
|[\<qualifyAssembly>](qualifyassembly-element.md)|<span data-ttu-id="cb973-127">부분 이름이 사용될 때 동적으로 로드되어야 하는 어셈블리의 전체 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-127">Specifies the full name of the assembly that should be dynamically loaded when a partial name is used.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cb973-128">부모 요소</span><span class="sxs-lookup"><span data-stu-id="cb973-128">Parent Elements</span></span>  
  
|<span data-ttu-id="cb973-129">요소</span><span class="sxs-lookup"><span data-stu-id="cb973-129">Element</span></span>|<span data-ttu-id="cb973-130">Description</span><span class="sxs-lookup"><span data-stu-id="cb973-130">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cb973-131">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-131">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="cb973-132">어셈블리 바인딩 및 가비지 컬렉션에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-132">Contains information about assembly binding and garbage collection.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="cb973-133">예제</span><span class="sxs-lookup"><span data-stu-id="cb973-133">Example</span></span>  
 <span data-ttu-id="cb973-134">다음 예제에서는 어셈블리 버전을 다른 버전으로 리디렉션하는 방법을 보여 주고 Codebase를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-134">The following example shows how to redirect one assembly version to another and provide a codebase.</span></span>  
  
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
  
 <span data-ttu-id="cb973-135">다음 예제에서는 **appliesTo** 특성을 사용 하 여 .NET Framework 어셈블리의 바인딩을 리디렉션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb973-135">The following example shows how to use the **appliesTo** attribute to redirect binding of a .NET Framework assembly.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="cb973-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb973-136">See also</span></span>

- [<span data-ttu-id="cb973-137">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="cb973-137">Runtime Settings Schema</span></span>](index.md)
- [<span data-ttu-id="cb973-138">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="cb973-138">Configuration File Schema</span></span>](../index.md)
- [<span data-ttu-id="cb973-139">어셈블리 버전 리디렉션</span><span class="sxs-lookup"><span data-stu-id="cb973-139">Redirecting Assembly Versions</span></span>](../../redirect-assembly-versions.md)
