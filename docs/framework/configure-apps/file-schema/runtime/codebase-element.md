---
title: <codeBase> 요소
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#codeBase
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/runtime/assemblyBinding/dependentAssembly/codeBase
helpviewer_keywords:
- <codeBase> element
- container tags, <codeBase> element
- codeBase element
ms.assetid: d48a3983-2297-43ff-a14d-1f29d3995822
ms.openlocfilehash: b5825efcc613689e73fb56b6695fe7c75ff09136
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356613"
---
# <a name="codebase-element"></a><span data-ttu-id="78950-102">\<코드 베이스 > 요소</span><span class="sxs-lookup"><span data-stu-id="78950-102">\<codeBase> Element</span></span>

<span data-ttu-id="78950-103">공용 언어 런타임에서 어셈블리를 찾는 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-103">Specifies where the common language runtime can find an assembly.</span></span>

<span data-ttu-id="78950-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span><span class="sxs-lookup"><span data-stu-id="78950-104">\<configuration> \<runtime> \<assemblyBinding> \<dependentAssembly> \<codeBase></span></span>

## <a name="syntax"></a><span data-ttu-id="78950-105">구문</span><span class="sxs-lookup"><span data-stu-id="78950-105">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="78950-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="78950-106">Attributes and Elements</span></span>

<span data-ttu-id="78950-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="78950-108">특성</span><span class="sxs-lookup"><span data-stu-id="78950-108">Attributes</span></span>

|<span data-ttu-id="78950-109">특성</span><span class="sxs-lookup"><span data-stu-id="78950-109">Attribute</span></span>|<span data-ttu-id="78950-110">설명</span><span class="sxs-lookup"><span data-stu-id="78950-110">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="78950-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="78950-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="78950-112">런타임에서 어셈블리의 지정된 된 버전을 찾을 수 있는 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-112">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="78950-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="78950-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="78950-114">코드 베이스에 적용 하는 어셈블리의 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-114">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="78950-115">어셈블리 버전 번호의 형식은 *major.minor.build.revision*합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-115">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="78950-116">버전 특성</span><span class="sxs-lookup"><span data-stu-id="78950-116">version Attribute</span></span>

|<span data-ttu-id="78950-117">값</span><span class="sxs-lookup"><span data-stu-id="78950-117">Value</span></span>|<span data-ttu-id="78950-118">설명</span><span class="sxs-lookup"><span data-stu-id="78950-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="78950-119">버전 번호의 각 부분에 대 한 유효한 값은 0부터 65535 까지입니다.</span><span class="sxs-lookup"><span data-stu-id="78950-119">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="78950-120">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="78950-120">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="78950-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="78950-121">Child Elements</span></span>

<span data-ttu-id="78950-122">없음</span><span class="sxs-lookup"><span data-stu-id="78950-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="78950-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="78950-123">Parent Elements</span></span>

|<span data-ttu-id="78950-124">요소</span><span class="sxs-lookup"><span data-stu-id="78950-124">Element</span></span>|<span data-ttu-id="78950-125">설명</span><span class="sxs-lookup"><span data-stu-id="78950-125">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="78950-126">사용자 지정 리소스 파일의 컴파일에 사용되는 빌드 공급자의 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-126">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="78950-127">빌드 공급자 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78950-127">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="78950-128">ASP.NET을 사용 하는 모든 컴파일 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-128">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="78950-129">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="78950-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="78950-130">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-130">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="78950-131">설명</span><span class="sxs-lookup"><span data-stu-id="78950-131">Remarks</span></span>

<span data-ttu-id="78950-132">사용에 런타임에 대 한 합니다  **\<codeBase >** 컴퓨터 구성 파일 또는 게시자 정책 파일에서 설정 파일을 리디렉션해야 어셈블리 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="78950-132">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="78950-133">응용 프로그램 구성 파일에는 어셈블리 버전 리디렉션 없이 코드 베이스 설정이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78950-133">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="78950-134">사용 하는 어셈블리 버전을 결정 한 후 런타임 버전을 결정 하는 파일의 코드 베이스 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-134">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="78950-135">없는 코드 베이스를 지정 하는 경우 런타임은 일반적인 방법으로 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-135">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="78950-136">어셈블리에 강력한 이름을 하는 경우 코드 베이스 설정을 로컬 인트라넷 또는 인터넷에서 아무 곳 이나 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78950-136">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="78950-137">전용 어셈블리를 어셈블리가 있는 경우 코드 베이스 설정을 응용 프로그램의 디렉터리에 상대적인 경로 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78950-137">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="78950-138">강력한 이름이 없는 어셈블리의 경우 버전이 무시 되 고 로더는 첫 번째 모양의 \<codebase > 내에서 \<dependentAssembly >.</span><span class="sxs-lookup"><span data-stu-id="78950-138">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="78950-139">다른 어셈블리 바인딩을 리디렉션하는 응용 프로그램 구성 파일에 항목이 있으면 리디렉션 어셈블리 버전 바인딩 요청과 일치 하지 않습니다 하는 경우에 우선을 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78950-139">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="78950-140">예제</span><span class="sxs-lookup"><span data-stu-id="78950-140">Example</span></span>

<span data-ttu-id="78950-141">다음 예제에서는 런타임에 어셈블리를 찾을 수 있습니다 위치를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78950-141">The following example shows how to specify where the runtime can find an assembly.</span></span>

```xml
<configuration>
   <runtime>
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">
         <dependentAssembly>
            <assemblyIdentity name="myAssembly"
                              publicKeyToken="32ab4ba45e0a69a1"
                              culture="neutral" />
            <codeBase version="2.0.0.0"
                      href="http://www.litwareinc.com/myAssembly.dll"/>
         </dependentAssembly>
      </assemblyBinding>
   </runtime>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="78950-142">참고자료</span><span class="sxs-lookup"><span data-stu-id="78950-142">See also</span></span>

- [<span data-ttu-id="78950-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="78950-143">Runtime Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/index.md)
- [<span data-ttu-id="78950-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="78950-144">Configuration File Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [<span data-ttu-id="78950-145">어셈블리 위치 지정</span><span class="sxs-lookup"><span data-stu-id="78950-145">Specifying an Assembly's Location</span></span>](../../../../../docs/framework/configure-apps/specify-assembly-location.md)
- [<span data-ttu-id="78950-146">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="78950-146">How the Runtime Locates Assemblies</span></span>](../../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
