---
title: 'NETSDK1045: 현재 .NET SDK는 대상으로 ‘최신 버전’을 지원하지 않습니다.'
description: 빌드 도구가 요청된 .NET SDK 버전을 찾을 수 없을 때 발생하는 .NET SDK 오류 NETSDK1045에 관해 알아봅니다.
ms.topic: error-reference
ms.date: 02/12/2021
f1_keywords:
- NETSDK1045
ms.openlocfilehash: 7f21270fdc7c2db862a49302a302bf8121fc86a5
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102104104"
---
# <a name="netsdk1045-the-current-net-sdk-does-not-support-newer-version-as-a-target"></a><span data-ttu-id="a6b4e-103">NETSDK1045: 현재 .NET SDK는 대상으로 ‘최신 버전’을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-103">NETSDK1045: The current .NET SDK does not support 'newer version' as a target.</span></span>

<span data-ttu-id="a6b4e-104">**이 문서의 적용 대상:** ✔️ .NET Core 2.1.100 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="a6b4e-104">**This article applies to:** ✔️ .NET Core 2.1.100 SDK and later versions</span></span>

<span data-ttu-id="a6b4e-105">이 오류는 빌드 도구가 프로젝트를 빌드하는 데 필요한 .NET SDK 버전을 찾을 수 없을 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-105">This error occurs when the build tools can't find the version of the .NET SDK that's needed to build a project.</span></span> <span data-ttu-id="a6b4e-106">이는 일반적으로 .NET Core SDK 설치 또는 구성 문제로 인해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-106">This is typically due to a .NET Core SDK installation or configuration issue.</span></span> <span data-ttu-id="a6b4e-107">전체 오류 메시지는 다음 예제와 유사하게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-107">The full error message is similar to the following example:</span></span>

> <span data-ttu-id="a6b4e-108">NETSDK1045: 현재 .NET SDK는 대상으로 ‘최신 버전’을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-108">NETSDK1045: The current .NET SDK does not support 'newer version' as a target.</span></span> <span data-ttu-id="a6b4e-109">‘이전 버전’ 이하를 대상으로 하거나 ‘최신 버전’을 지원하는 .NET SDK 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-109">Either target 'older version' or lower, or use a .NET SDK version that supports 'newer version'.</span></span>

<span data-ttu-id="a6b4e-110">다음 섹션에서는 이 오류의 가능한 몇 가지 원인을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-110">The following sections describe some of the possible reasons for this error.</span></span> <span data-ttu-id="a6b4e-111">각 원인을 확인하고 어떤 원인이 적용되는지 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-111">Check each one and see which one applies to you.</span></span> <span data-ttu-id="a6b4e-112">환경 또는 구성 파일을 변경할 때 변경 내용을 적용하려면 명령 창을 다시 시작하거나, Visual Studio를 다시 시작하거나, 머신을 다시 부팅해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-112">Keep in mind that when making changes to the environment or the configuration files, you might have to restart command windows, restart Visual Studio, or reboot your machine, for your changes to take effect.</span></span>

## <a name="net-sdk-version"></a><span data-ttu-id="a6b4e-113">.NET SDK 버전</span><span class="sxs-lookup"><span data-stu-id="a6b4e-113">.NET SDK version</span></span>

<span data-ttu-id="a6b4e-114">프로젝트 파일(.csproj, .vbproj 또는 .fsproj)을 열고 대상 프레임워크를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-114">Open the project file (.csproj, .vbproj, or .fsproj) and check the target framework.</span></span> <span data-ttu-id="a6b4e-115">앱에서 사용하려는 프레임워크의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-115">This is the version of the framework that your app is trying to use.</span></span>

```xml
<TargetFramework>netcoreapp3.0</TargetFramework>
```

<span data-ttu-id="a6b4e-116">나열된 .NET 버전이 머신에 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-116">Make sure that the version of .NET listed is installed on the machine.</span></span> <span data-ttu-id="a6b4e-117">다음 명령을 사용하여 설치된 버전을 나열할 수 있습니다(개발자 명령 프롬프트를 열고 이 명령을 실행).</span><span class="sxs-lookup"><span data-stu-id="a6b4e-117">You can list the installed versions by using the following command (open a Developer Command Prompt and run this command):</span></span>

```dotnetcli
dotnet --list-sdks
```

### <a name="x86-or-x64-architecture"></a><span data-ttu-id="a6b4e-118">x86 또는 x64 아키텍처</span><span class="sxs-lookup"><span data-stu-id="a6b4e-118">x86 or x64 architecture</span></span>

<span data-ttu-id="a6b4e-119">각 버전의 .NET SDK는 x86 및 x64 아키텍처에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-119">Each version of the .NET SDK is available in both x86 and x64 architecture.</span></span> <span data-ttu-id="a6b4e-120">프로젝트가 잘못된 아키텍처용 .NET SDK를 찾으려고 하거나 프로젝트에 필요한 아키텍처용 .NET SDK가 설치되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-120">The project might be trying to find the .NET SDK for the wrong architecture, or the .NET SDK for the architecture your project needs might not be installed.</span></span> <span data-ttu-id="a6b4e-121">필요한 아키텍처의 설치 폴더를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-121">Check the installation folders for the architecture you need.</span></span> <span data-ttu-id="a6b4e-122">예를 들어 Windows에서 x86 버전의 .NET SDK는 *C:\Program Files (x86)\dotnet* 에 설치되고 x64 버전은 *C:\Program Files\dotnet* 에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-122">For example, on Windows, the x86 version of the .NET SDK is installed in *C:\Program Files (x86)\dotnet* and the x64 version is installed in *C:\Program Files\dotnet*.</span></span> <span data-ttu-id="a6b4e-123">[.NET이 이미 설치되어 있는지 확인하는 방법](../../install/how-to-detect-installed-versions.md)을 참조하고 운영 체제를 선택하여 머신에 설치된 항목을 검색하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-123">See [How to check that .NET is already installed](../../install/how-to-detect-installed-versions.md) and choose your operating system to find out how to detect what's installed on your machine.</span></span>

<span data-ttu-id="a6b4e-124">필요한 버전이 설치되어 있지 않으면 [.NET 다운로드](https://dotnet.microsoft.com/download/dotnet) 페이지에서 필요한 버전을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-124">If the version you need isn't installed, find the one you need at the [.NET Downloads](https://dotnet.microsoft.com/download/dotnet) page.</span></span>

## <a name="preview-not-enabled"></a><span data-ttu-id="a6b4e-125">미리 보기가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="a6b4e-125">Preview not enabled</span></span>

<span data-ttu-id="a6b4e-126">요청된 .NET SDK 버전의 미리 보기를 설치한 경우 Visual Studio에서 미리 보기를 사용하도록 설정하는 옵션도 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-126">If you have a preview installed of the requested .NET SDK version, you also need to set the option to enable previews in Visual Studio.</span></span> <span data-ttu-id="a6b4e-127">**도구** > **옵션** > **환경** > **미리 보기 기능** 으로 이동하고 **.NET Core SDK의 미리 보기 사용** 이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-127">Go to **Tools** > **Options** > **Environment** > **Preview Features**, and make sure that **Use previews of the .NET Core SDK** is checked.</span></span>

## <a name="visual-studio-version"></a><span data-ttu-id="a6b4e-128">Visual Studio 버전</span><span class="sxs-lookup"><span data-stu-id="a6b4e-128">Visual Studio version</span></span>

<span data-ttu-id="a6b4e-129">예를 들어 .NET Core 3.0 이상에는 Visual Studio 2019가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-129">For example, .NET Core 3.0 and later require Visual Studio 2019.</span></span> <span data-ttu-id="a6b4e-130">프로젝트를 빌드하려면 [Visual Studio 2019 버전 16.3](https://visualstudio.microsoft.com/downloads) 이상으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-130">Upgrade to [Visual Studio 2019 version 16.3](https://visualstudio.microsoft.com/downloads) or later to build your project.</span></span>

## <a name="path-environment-variable"></a><span data-ttu-id="a6b4e-131">PATH 환경 변수</span><span class="sxs-lookup"><span data-stu-id="a6b4e-131">PATH environment variable</span></span>

<span data-ttu-id="a6b4e-132">빌드 도구는 PATH 환경 변수를 사용하여 .NET 빌드 도구의 적합한 버전을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-132">The build tools use the PATH environment variable to find the right version of the .NET build tools.</span></span> <span data-ttu-id="a6b4e-133">PATH 환경 변수에 이전 빌드 도구의 직접 경로가 포함된 경우 이 오류 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-133">If the PATH environment variable contains direct paths to older build tools, this error message could appear.</span></span> <span data-ttu-id="a6b4e-134">PATH 환경 변수에서 .NET 도구의 유일한 경로가 최상위 *dotnet* 폴더(예: *C:\Program Files\dotnet*)에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-134">Make sure the only path to the .NET tools in the PATH environment variable is to the top-level *dotnet* folder, for example, *C:\Program Files\dotnet*.</span></span> <span data-ttu-id="a6b4e-135">*C:\Program Files\dotnet\2.1.0\sdks* 같은 경로는 잘못된 PATH의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-135">An example of an incorrect PATH would be something like *C:\Program Files\dotnet\2.1.0\sdks*.</span></span>

## <a name="msbuildsdkpath-environment-variable"></a><span data-ttu-id="a6b4e-136">MSBuildSDKPath 환경 변수</span><span class="sxs-lookup"><span data-stu-id="a6b4e-136">MSBuildSDKPath environment variable</span></span>

<span data-ttu-id="a6b4e-137">MSBuildSDKPath 환경 변수를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-137">Check the MSBuildSDKPath environment variable.</span></span> <span data-ttu-id="a6b4e-138">이 선택적 환경 변수는 MSBuild에서 인식되며 설정된 경우 기본값을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-138">This optional environment variable is recognized by MSBuild and if set, overrides the default value.</span></span> <span data-ttu-id="a6b4e-139">특정 이전 버전의 .NET SDK로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-139">It might be set to a specific older version of the .NET SDK.</span></span> <span data-ttu-id="a6b4e-140">설정된 경우 환경 변수를 삭제하고 프로젝트를 다시 빌드해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-140">If it's set, try deleting it and rebuilding your project.</span></span>

## <a name="globaljson-file"></a><span data-ttu-id="a6b4e-141">global.json 파일</span><span class="sxs-lookup"><span data-stu-id="a6b4e-141">global.json file</span></span>

<span data-ttu-id="a6b4e-142">프로젝트의 루트 폴더에 있는 *global.json* 파일을 확인하고 파일이 폴더 구조의 어디에나 있을 수 있으므로 디렉터리 위로 볼륨의 루트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-142">Check for a *global.json* file in the root folder in your project and up the directory chain to the root of the volume, since it can be anywhere in the folder structure.</span></span> <span data-ttu-id="a6b4e-143">SDK 버전을 포함하는 경우 `sdk` 노드와 모든 자식을 삭제하거나 원하는 최신 .NET Core 버전으로 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-143">If it contains an SDK version, delete the `sdk` node and all its children, or update it to the desired newer .NET Core version.</span></span>

```json
{
  "sdk": {
    "version": "2.1.0"
  }
}
```

<span data-ttu-id="a6b4e-144">*global.json* 파일은 필요하지 않으므로 `sdk` 노드 이외의 항목을 포함하지 않는 경우 전체 파일을 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-144">The *global.json* file is not required, so if it doesn't contain anything other than the `sdk` node, you can delete the whole file.</span></span>

## <a name="directorybuildprops-file"></a><span data-ttu-id="a6b4e-145">Directory.build.props 파일</span><span class="sxs-lookup"><span data-stu-id="a6b4e-145">Directory.build.props file</span></span>

<span data-ttu-id="a6b4e-146">*Directory.build.props* 파일은 전역 속성을 설정할 수 있는 선택적 MSBuild 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-146">The *Directory.build.props* file is an optional MSBuild file that can set global properties.</span></span> <span data-ttu-id="a6b4e-147">솔루션 폴더에 있는 해당 파일을 확인하고 파일이 폴더 구조의 어디에나 있을 수 있으므로 디렉터리 위로 볼륨의 루트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-147">Check for these files in the solution folder and up the directory chain to the root of the volume, since they can be anywhere in the folder structure.</span></span> <span data-ttu-id="a6b4e-148">원하는 설정을 재정의할 수 있는 `MSBuildSDKPath`의 설정 또는 `TargetFramework` 요소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="a6b4e-148">Look for `TargetFramework` elements, or settings of `MSBuildSDKPath` that could override your desired settings.</span></span>

## <a name="see-also"></a><span data-ttu-id="a6b4e-149">참조</span><span class="sxs-lookup"><span data-stu-id="a6b4e-149">See also</span></span>

- [<span data-ttu-id="a6b4e-150">현재 .NET SDK가 .NET Core 3.0을 지원하지 않음 – 수정</span><span class="sxs-lookup"><span data-stu-id="a6b4e-150">The Current .NET SDK does not support targeting .NET Core 3.0 – Fix</span></span>](https://www.ryadel.com/current-net-sdk-not-support-net-core-3-0-fix/)
