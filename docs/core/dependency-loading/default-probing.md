---
title: 기본 검색 - .NET Core
description: 종속성을 찾기 위한 .NET Core의 System.Runtime.Loader.AssemblyLoadContext.Default 검색 논리 개요입니다.
ms.date: 08/09/2019
author: sdmaclea
ms.author: stmaclea
ms.openlocfilehash: 13ce4c7de5f6ce1b76b2e61db810c0f19717540f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608418"
---
# <a name="default-probing"></a><span data-ttu-id="f3d56-103">기본 검색</span><span class="sxs-lookup"><span data-stu-id="f3d56-103">Default probing</span></span>

<span data-ttu-id="f3d56-104"><xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 인스턴스는 어셈블리의 종속성을 찾는 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-104">The <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance is responsible for locating an assembly's dependencies.</span></span> <span data-ttu-id="f3d56-105">이 문서에서는 <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 인스턴스의 검색 논리를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-105">This article describes the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> instance's probing logic.</span></span>

## <a name="host-configured-probing-properties"></a><span data-ttu-id="f3d56-106">호스트 구성 검색 속성</span><span class="sxs-lookup"><span data-stu-id="f3d56-106">Host configured probing properties</span></span>

<span data-ttu-id="f3d56-107">런타임이 시작되면 런타임 호스트는 <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> 프로브 경로를 구성하는 명명된 검색 속성 세트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-107">When the runtime is started, the runtime host provides a set of named probing properties that configure <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> probe paths.</span></span>

<span data-ttu-id="f3d56-108">각 검색 속성은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-108">Each probing property is optional.</span></span> <span data-ttu-id="f3d56-109">있는 경우 각 속성은 구분 기호로 분리된 절대 경로 목록을 포함하는 문자열 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-109">If present, each property is a string value that contains a delimited list of absolute paths.</span></span> <span data-ttu-id="f3d56-110">구분 기호는 Windows의 경우 ';'이고 다른 모든 플랫폼의 경우 ':'입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-110">The delimiter is ';' on Windows and ':' on all other platforms.</span></span>

|<span data-ttu-id="f3d56-111">속성 이름</span><span class="sxs-lookup"><span data-stu-id="f3d56-111">Property Name</span></span>                 |<span data-ttu-id="f3d56-112">설명</span><span class="sxs-lookup"><span data-stu-id="f3d56-112">Description</span></span>  |
|------------------------------|---------|
|`TRUSTED_PLATFORM_ASSEMBLIES`   | <span data-ttu-id="f3d56-113">플랫폼 및 애플리케이션 어셈블리 파일 경로의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-113">List of platform and application assembly file paths.</span></span> |
|`PLATFORM_RESOURCE_ROOTS`       | <span data-ttu-id="f3d56-114">위성 리소스 어셈블리를 검색할 디렉터리 경로 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-114">List of directory paths to search for satellite resource assemblies.</span></span> |
|`NATIVE_DLL_SEARCH_DIRECTORIES` | <span data-ttu-id="f3d56-115">관리되지 않는(네이티브) 라이브러리를 검색할 디렉터리 경로 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-115">List of directory paths to search for unmanaged (native) libraries.</span></span>        |
|`APP_PATHS`                     | <span data-ttu-id="f3d56-116">관리 어셈블리를 검색할 디렉터리 경로 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-116">List of directory paths to search for managed assemblies.</span></span> |
|`APP_NI_PATHS`                  | <span data-ttu-id="f3d56-117">관리 어셈블리의 네이티브 이미지를 검색할 디렉터리 경로 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-117">List of directory paths to search for native images of managed assemblies.</span></span> |

### <a name="how-are-the-properties-populated"></a><span data-ttu-id="f3d56-118">속성이 채워지는 방법</span><span class="sxs-lookup"><span data-stu-id="f3d56-118">How are the properties populated?</span></span>

<span data-ttu-id="f3d56-119">*\<myapp>.deps.json* 파일이 있는지 여부에 따라 속성을 채우는 두 가지 주요 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-119">There are two main scenarios for populating the properties depending on whether the *\<myapp>.deps.json* file exists.</span></span>

- <span data-ttu-id="f3d56-120">*\*.deps.json* 파일이 있으면 검색 속성을 채우도록 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-120">When the *\*.deps.json* file is present, it's parsed to populate the probing properties.</span></span>
- <span data-ttu-id="f3d56-121">*\*.deps.json* 파일이 없으면 애플리케이션의 디렉터리에 모든 종속성이 포함된 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-121">When the *\*.deps.json* file isn't present, the application's directory is assumed to contain all the dependencies.</span></span> <span data-ttu-id="f3d56-122">디렉터리의 콘텐츠는 검색 속성을 채우는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-122">The directory's contents are used to populate the probing properties.</span></span>

<span data-ttu-id="f3d56-123">또한 참조된 프레임워크의 *\*.deps.json* 파일도 유사하게 구문 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-123">Additionally, the *\*.deps.json* files for any referenced frameworks are similarly parsed.</span></span>

<span data-ttu-id="f3d56-124">마지막으로 `ADDITIONAL_DEPS` 환경 변수를 사용하여 추가 종속성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-124">Finally the environment variable `ADDITIONAL_DEPS` can be used to add additional dependencies.</span></span>  <span data-ttu-id="f3d56-125">`dotnet.exe`에는 애플리케이션을 시작할 때 이 값을 설정하는 선택적 매개 변수 `--additional-deps`도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-125">`dotnet.exe` also contains an `--additional-deps` optional parameter to set this value on application startup.</span></span>

<span data-ttu-id="f3d56-126">`APP_PATHS` 및 `APP_NI_PATHS` 속성은 기본적으로 채워지지 않으며 대부분의 애플리케이션에서 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-126">The `APP_PATHS` and `APP_NI_PATHS` properties are not populated by default and are omitted for most applications.</span></span>

<span data-ttu-id="f3d56-127">애플리케이션에서 사용되는 모든 *\*.deps.json* 파일 목록은 `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")`를 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-127">The list of all *\*.deps.json* files used by the application can be accessed via `System.AppContext.GetData("APP_CONTEXT_DEPS_FILES")`.</span></span>

### <a name="how-do-i-see-the-probing-properties-from-managed-code"></a><span data-ttu-id="f3d56-128">관리 코드에서 검색 속성을 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="f3d56-128">How do I see the probing properties from managed code?</span></span>

<span data-ttu-id="f3d56-129">각 속성은 위의 표에서 속성 이름으로 <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> 함수를 호출하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-129">Each property is available by calling the <xref:System.AppContext.GetData(System.String)?displayProperty=nameWithType> function with the property name from the table above.</span></span>

### <a name="how-do-i-debug-the-probing-properties-construction"></a><span data-ttu-id="f3d56-130">검색 속성 생성의 구성을 디버깅하는 방법</span><span class="sxs-lookup"><span data-stu-id="f3d56-130">How do I debug the probing properties' construction?</span></span>

<span data-ttu-id="f3d56-131">특정 환경 변수가 활성화되면 .NET Core 런타임 호스트가 유용한 추적 메시지를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-131">The .NET Core runtime host will output useful trace messages when certain environment variables are enabled:</span></span>

|<span data-ttu-id="f3d56-132">환경 변수</span><span class="sxs-lookup"><span data-stu-id="f3d56-132">Environment Variable</span></span>        |<span data-ttu-id="f3d56-133">설명</span><span class="sxs-lookup"><span data-stu-id="f3d56-133">Description</span></span>  |
|----------------------------|---------|
|`COREHOST_TRACE=1`          |<span data-ttu-id="f3d56-134">추적을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-134">Enables tracing.</span></span>|
|`COREHOST_TRACEFILE=<path>` |<span data-ttu-id="f3d56-135">기본 `stderr` 대신 파일 경로를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-135">Traces to a file path instead of the default `stderr`.</span></span>|
|`COREHOST_TRACE_VERBOSITY`  |<span data-ttu-id="f3d56-136">자세한 정도를 1(가장 낮음)에서 4(가장 높음)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-136">Sets the verbosity from 1 (lowest) to 4 (highest).</span></span>|

## <a name="managed-assembly-default-probing"></a><span data-ttu-id="f3d56-137">관리 어셈블리 기본 검색</span><span class="sxs-lookup"><span data-stu-id="f3d56-137">Managed assembly default probing</span></span>

<span data-ttu-id="f3d56-138">관리 어셈블리를 찾기 위해 검색할 때 <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType>은 다음을 순서대로 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-138">When probing to locate a managed assembly, the <xref:System.Runtime.Loader.AssemblyLoadContext.Default%2A?displayProperty=nameWithType> looks in order at:</span></span>

- <span data-ttu-id="f3d56-139">파일 확장명을 제거한 후 `TRUSTED_PLATFORM_ASSEMBLIES`에서 <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType>과 일치하는 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-139">Files matching the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> in `TRUSTED_PLATFORM_ASSEMBLIES` (after removing file extensions).</span></span>
- <span data-ttu-id="f3d56-140">일반 파일 확장자가 있는 `APP_NI_PATHS`의 네이티브 이미지 어셈블리 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-140">Native image assembly files in `APP_NI_PATHS` with common file extensions.</span></span>
- <span data-ttu-id="f3d56-141">일반 파일 확장자가 있는 `APP_PATHS`의 어셈블리 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-141">Assembly files in `APP_PATHS` with common file extensions.</span></span>

## <a name="satellite-resource-assembly-probing"></a><span data-ttu-id="f3d56-142">위성(리소스) 어셈블리 검색</span><span class="sxs-lookup"><span data-stu-id="f3d56-142">Satellite (resource) assembly probing</span></span>

<span data-ttu-id="f3d56-143">특정 문화권에 대한 위성 어셈블리를 찾으려면 파일 경로 세트를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-143">To find a satellite assembly for a specific culture, construct a set of file paths.</span></span>

<span data-ttu-id="f3d56-144">`PLATFORM_RESOURCE_ROOTS` 및 `APP_PATHS`의 각 경로에 대해 <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> 문자열, 디렉터리 구분 기호, <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> 문자열 및 확장명 '.dll'을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-144">For each path in `PLATFORM_RESOURCE_ROOTS` and then `APP_PATHS`, append the <xref:System.Globalization.CultureInfo.Name?displayProperty=nameWithType> string, a directory separator, the <xref:System.Reflection.AssemblyName.Name?displayProperty=nameWithType> string, and the extension '.dll'.</span></span>

<span data-ttu-id="f3d56-145">일치하는 파일이 있는 경우 로드하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-145">If any matching file exists, attempt to load and return it.</span></span>

## <a name="unmanaged-native-library-probing"></a><span data-ttu-id="f3d56-146">관리되지 않는(네이티브) 라이브러리 검색</span><span class="sxs-lookup"><span data-stu-id="f3d56-146">Unmanaged (native) library probing</span></span>

<span data-ttu-id="f3d56-147">관리되지 않는 라이브러리를 찾기 위해 검색할 때 `NATIVE_DLL_SEARCH_DIRECTORIES`에서 일치하는 라이브러리를 찾아 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3d56-147">When probing to locate an unmanaged library, the `NATIVE_DLL_SEARCH_DIRECTORIES` are searched looking for a matching library.</span></span>
