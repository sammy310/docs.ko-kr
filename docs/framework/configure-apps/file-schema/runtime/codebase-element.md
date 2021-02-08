---
description: '다음에 대 한 자세한 정보: <codeBase> 요소'
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
ms.openlocfilehash: 714392444d3ee3db9126e9fe67832cb5f0bf5e3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795120"
---
# <a name="codebase-element"></a><span data-ttu-id="45654-103">\<codeBase> 요소</span><span class="sxs-lookup"><span data-stu-id="45654-103">\<codeBase> Element</span></span>

<span data-ttu-id="45654-104">공용 언어 런타임에서 어셈블리를 찾을 수 있는 위치를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-104">Specifies where the common language runtime can find an assembly.</span></span>

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<assemblyBinding>**](assemblybinding-element-for-runtime.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<dependentAssembly>**](dependentassembly-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<codeBase>**

## <a name="syntax"></a><span data-ttu-id="45654-105">구문</span><span class="sxs-lookup"><span data-stu-id="45654-105">Syntax</span></span>

```xml
   <codeBase
        version="Assembly version"
        href="URL of assembly"/>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="45654-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="45654-106">Attributes and Elements</span></span>

<span data-ttu-id="45654-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-107">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="45654-108">특성</span><span class="sxs-lookup"><span data-stu-id="45654-108">Attributes</span></span>

|<span data-ttu-id="45654-109">attribute</span><span class="sxs-lookup"><span data-stu-id="45654-109">Attribute</span></span>|<span data-ttu-id="45654-110">설명</span><span class="sxs-lookup"><span data-stu-id="45654-110">Description</span></span>|
|---------------|-----------------|
|`href`|<span data-ttu-id="45654-111">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="45654-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="45654-112">런타임이 지정 된 버전의 어셈블리를 찾을 수 있는 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-112">Specifies the URL where the runtime can find the specified version of the assembly.</span></span>|
|`version`|<span data-ttu-id="45654-113">필수 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="45654-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="45654-114">코드 베이스가 적용 되는 어셈블리의 버전을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-114">Specifies the version of the assembly the codebase applies to.</span></span> <span data-ttu-id="45654-115">어셈블리 버전 번호의 형식은 주 버전. *부 버전. 빌드. 수정 버전* 입니다.</span><span class="sxs-lookup"><span data-stu-id="45654-115">The format of an assembly version number is *major.minor.build.revision*.</span></span>|

## <a name="version-attribute"></a><span data-ttu-id="45654-116">version 특성</span><span class="sxs-lookup"><span data-stu-id="45654-116">version Attribute</span></span>

|<span data-ttu-id="45654-117">값</span><span class="sxs-lookup"><span data-stu-id="45654-117">Value</span></span>|<span data-ttu-id="45654-118">설명</span><span class="sxs-lookup"><span data-stu-id="45654-118">Description</span></span>|
|-----------|-----------------|
|<span data-ttu-id="45654-119">버전 번호의 각 부분에 대해 유효한 값은 0에서 65535입니다.</span><span class="sxs-lookup"><span data-stu-id="45654-119">Valid values for each part of the version number are 0 to 65535.</span></span>|<span data-ttu-id="45654-120">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="45654-120">Not applicable.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="45654-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="45654-121">Child Elements</span></span>

<span data-ttu-id="45654-122">없음</span><span class="sxs-lookup"><span data-stu-id="45654-122">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="45654-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="45654-123">Parent Elements</span></span>

|<span data-ttu-id="45654-124">요소</span><span class="sxs-lookup"><span data-stu-id="45654-124">Element</span></span>|<span data-ttu-id="45654-125">설명</span><span class="sxs-lookup"><span data-stu-id="45654-125">Description</span></span>|
|-------------|-----------------|
|`buildproviders`|<span data-ttu-id="45654-126">사용자 지정 리소스 파일의 컴파일에 사용되는 빌드 공급자의 컬렉션을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-126">Defines a collection of build providers used to compile custom resource files.</span></span> <span data-ttu-id="45654-127">빌드 공급자 수에는 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="45654-127">You can have any number of build providers.</span></span>|
|`compilation`|<span data-ttu-id="45654-128">ASP.NET에서 사용 하는 모든 컴파일 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-128">Configures all the compilation settings that ASP.NET uses.</span></span>|
|`configuration`|<span data-ttu-id="45654-129">공용 언어 런타임 및 .NET Framework 애플리케이션에서 사용하는 모든 구성 파일의 루트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="45654-129">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|
|`System.web`|<span data-ttu-id="45654-130">ASP.NET 구성 섹션의 루트 요소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-130">Specifies the root element for the ASP.NET configuration section.</span></span>|

## <a name="remarks"></a><span data-ttu-id="45654-131">설명</span><span class="sxs-lookup"><span data-stu-id="45654-131">Remarks</span></span>

<span data-ttu-id="45654-132">런타임에서 **\<codeBase>** 컴퓨터 구성 파일 또는 게시자 정책 파일의 설정을 사용 하려면 파일도 어셈블리 버전을 리디렉션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-132">For the runtime to use the **\<codeBase>** setting in a machine configuration file or publisher policy file, the file must also redirect the assembly version.</span></span> <span data-ttu-id="45654-133">응용 프로그램 구성 파일에는 어셈블리 버전을 리디렉션하지 않고 codebase 설정이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45654-133">Application configuration files can have a codebase setting without redirecting the assembly version.</span></span> <span data-ttu-id="45654-134">사용할 어셈블리 버전을 확인 한 후 런타임은 버전을 결정 하는 파일의 codebase 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-134">After determining which assembly version to use, the runtime applies the codebase setting from the file that determines the version.</span></span> <span data-ttu-id="45654-135">코드 베이스가 표시 되지 않는 경우 런타임은 일반적인 방법으로 어셈블리를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-135">If no codebase is indicated, the runtime probes for the assembly in the usual way.</span></span>

<span data-ttu-id="45654-136">어셈블리에 강력한 이름이 있는 경우 코드 베이스 설정은 로컬 인트라넷 또는 인터넷의 어디에 나 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="45654-136">If the assembly has a strong name, the codebase setting can be anywhere on the local intranet or the Internet.</span></span> <span data-ttu-id="45654-137">어셈블리가 전용 어셈블리인 경우 codebase 설정은 응용 프로그램 디렉터리에 대 한 상대 경로 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-137">If the assembly is a private assembly, the codebase setting must be a path relative to the application's directory.</span></span>

<span data-ttu-id="45654-138">강력한 이름이 없는 어셈블리의 경우 버전은 무시 되 고 로더는 내부의 첫 번째 모양을 사용 \<codebase> \<dependentAssembly> 합니다.</span><span class="sxs-lookup"><span data-stu-id="45654-138">For assemblies without a strong name, version is ignored and the loader uses the first appearance of \<codebase> inside \<dependentAssembly>.</span></span> <span data-ttu-id="45654-139">응용 프로그램 구성 파일에 바인딩을 다른 어셈블리로 리디렉션하는 항목이 있는 경우 어셈블리 버전이 바인딩 요청과 일치 하지 않는 경우에도 리디렉션이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="45654-139">If there is an entry in the application configuration file that redirects binding to another assembly, the redirection will take precedence even if the assembly version doesn't match the binding request.</span></span>

## <a name="example"></a><span data-ttu-id="45654-140">예제</span><span class="sxs-lookup"><span data-stu-id="45654-140">Example</span></span>

<span data-ttu-id="45654-141">다음 예제에서는 런타임에서 어셈블리를 찾을 수 있는 위치를 지정 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="45654-141">The following example shows how to specify where the runtime can find an assembly.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="45654-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45654-142">See also</span></span>

- [<span data-ttu-id="45654-143">런타임 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="45654-143">Runtime settings schema</span></span>](index.md)
- [<span data-ttu-id="45654-144">구성 파일 스키마</span><span class="sxs-lookup"><span data-stu-id="45654-144">Configuration file schema</span></span>](../index.md)
- [<span data-ttu-id="45654-145">어셈블리 위치 지정</span><span class="sxs-lookup"><span data-stu-id="45654-145">Specify an assembly's location</span></span>](../../../../standard/assembly/location.md)
- [<span data-ttu-id="45654-146">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="45654-146">How the runtime locates assemblies</span></span>](../../../deployment/how-the-runtime-locates-assemblies.md)
