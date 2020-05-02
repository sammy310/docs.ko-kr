---
title: Windows, Linux 및 macOS에서 설치된 .NET Core 버전 확인 - .NET Core
description: 컴퓨터에 설치된 .NET Core 버전을 확인하는 방법을 알아봅니다. 여기에는 .NET Core 런타임 및 SDK가 포함됩니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 3a78acee6cf427085e98f14353fc2c0ac65d3d80
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645343"
---
# <a name="how-to-check-that-net-core-is-already-installed"></a><span data-ttu-id="ce059-104">.NET Core가 설치되어 있는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="ce059-104">How to check that .NET Core is already installed</span></span>

<span data-ttu-id="ce059-105">이 문서에서는 컴퓨터에 설치된 .NET Core 런타임 및 SDK의 버전을 확인하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-105">This article teaches you how to check which versions of the .NET Core runtime and SDK are installed on your computer.</span></span> <span data-ttu-id="ce059-106">Visual Studio 또는 Mac용 Visual Studio와 같은 통합 개발 환경이 설치된 경우 .NET Core가 이미 설치되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-106">.NET core may have already been installed if you have an integrated development environment, such as Visual Studio or Visual Studio for Mac.</span></span>

<span data-ttu-id="ce059-107">SDK를 설치하면 그에 해당하는 런타임도 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-107">Installing an SDK installs the corresponding runtime.</span></span>

<span data-ttu-id="ce059-108">이 문서에서 안내하는 명령이 작동하지 않는다면 런타임 또는 SDK가 설치되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-108">If any command in this article fails, you don't have the runtime or SDK installed.</span></span> <span data-ttu-id="ce059-109">자세한 내용은 [.NET Core 다운로드 및 설치](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce059-109">For more information, see [Download and install .NET Core](index.md).</span></span>

## <a name="check-sdk-versions"></a><span data-ttu-id="ce059-110">SDK 버전 확인</span><span class="sxs-lookup"><span data-stu-id="ce059-110">Check SDK versions</span></span>

<span data-ttu-id="ce059-111">터미널을 사용하여 현재 설치된 .NET Core SDK의 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-111">You can see which versions of the .NET Core SDK are currently installed with a terminal.</span></span> <span data-ttu-id="ce059-112">터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-112">Open a terminal and run the following command.</span></span>

```dotnetcli
dotnet --list-sdks
```

<span data-ttu-id="ce059-113">그러면 다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-113">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
2.1.500 [C:\program files\dotnet\sdk]
2.1.502 [C:\program files\dotnet\sdk]
2.1.504 [C:\program files\dotnet\sdk]
2.1.600 [C:\program files\dotnet\sdk]
2.1.602 [C:\program files\dotnet\sdk]
2.2.101 [C:\program files\dotnet\sdk]
3.0.100 [C:\program files\dotnet\sdk]
3.1.100 [C:\program files\dotnet\sdk]
```

::: zone-end

::: zone pivot="os-linux"

```bash
2.1.500 [/home/user/dotnet/sdk]
2.1.502 [/home/user/dotnet/sdk]
2.1.504 [/home/user/dotnet/sdk]
2.1.600 [/home/user/dotnet/sdk]
2.1.602 [/home/user/dotnet/sdk]
2.2.101 [/home/user/dotnet/sdk]
3.0.100 [/home/user/dotnet/sdk]
3.1.100 [/home/user/dotnet/sdk]
```

::: zone-end

::: zone pivot="os-macos"

```bash
2.1.500 [/usr/local/share/dotnet/sdk]
2.1.502 [/usr/local/share/dotnet/sdk]
2.1.504 [/usr/local/share/dotnet/sdk]
2.1.600 [/usr/local/share/dotnet/sdk]
2.1.602 [/usr/local/share/dotnet/sdk]
2.2.101 [/usr/local/share/dotnet/sdk]
3.0.100 [/usr/local/share/dotnet/sdk]
3.1.100 [/usr/local/share/dotnet/sdk]
```

::: zone-end

## <a name="check-runtime-versions"></a><span data-ttu-id="ce059-114">런타임 버전 확인</span><span class="sxs-lookup"><span data-stu-id="ce059-114">Check runtime versions</span></span>

<span data-ttu-id="ce059-115">다음 명령을 사용하여 현재 설치된 .NET Core 런타임의 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-115">You can see which versions of the .NET Core runtime are currently installed with the following command.</span></span>

```dotnetcli
dotnet --list-runtimes
```

<span data-ttu-id="ce059-116">그러면 다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-116">You get output similar to the following.</span></span>

::: zone pivot="os-windows"

```console
Microsoft.AspNetCore.All 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.NETCore.App]
Microsoft.WindowsDesktop.App 3.0.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
Microsoft.WindowsDesktop.App 3.1.0 [c:\program files\dotnet\shared\Microsoft.WindowsDesktop.App]
```

::: zone-end

::: zone pivot="os-linux"

```bash
Microsoft.AspNetCore.All 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/home/user/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

::: zone pivot="os-macos"

```bash
Microsoft.AspNetCore.All 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.All 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.All]
Microsoft.AspNetCore.App 2.1.6 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.AspNetCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.AspNetCore.App]
Microsoft.NETCore.App 2.1.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.1.13 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.3 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 2.2.7 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.0.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
Microsoft.NETCore.App 3.1.0 [/usr/local/share/dotnet/shared/Microsoft.NETCore.App]
```

::: zone-end

## <a name="check-for-install-folders"></a><span data-ttu-id="ce059-117">설치 폴더 확인</span><span class="sxs-lookup"><span data-stu-id="ce059-117">Check for install folders</span></span>

<span data-ttu-id="ce059-118">.NET Core가 설치되어 있지만 운영 체제 또는 사용자 프로필의 `PATH` 변수에 추가되지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-118">It's possible that .NET Core is installed but not added to the `PATH` variable for your operating system or user profile.</span></span> <span data-ttu-id="ce059-119">이전 섹션에서 명령을 실행하면 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-119">Running the commands from the previous sections may not work.</span></span> <span data-ttu-id="ce059-120">대안으로 .NET Core 설치 폴더가 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-120">As an alternative, you can check that the .NET Core install folders exist.</span></span>

<span data-ttu-id="ce059-121">설치 관리자 또는 스크립트에서 .NET Core를 설치하면 표준 폴더에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-121">When you install .NET Core from an installer or script, it's installed to a standard folder.</span></span> <span data-ttu-id="ce059-122">대부분의 경우 .NET Core를 설치하는 데 사용하는 설치 관리자 또는 스크립트는 다른 폴더에 설치할 수 있는 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-122">Much of the time the installer or script you're using to install .NET Core gives you an option to install to a different folder.</span></span> <span data-ttu-id="ce059-123">다른 폴더에 설치하도록 선택한 경우 폴더 경로의 시작을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-123">If you choose to install to a different folder, adjust the start of the folder path.</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="ce059-124">**dotnet 실행 파일**</span><span class="sxs-lookup"><span data-stu-id="ce059-124">**dotnet executable**</span></span>\
<span data-ttu-id="ce059-125">_C:\\program files\\dotnet\\dotnet.exe_</span><span class="sxs-lookup"><span data-stu-id="ce059-125">_C:\\program files\\dotnet\\dotnet.exe_</span></span>

- <span data-ttu-id="ce059-126">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="ce059-126">**.NET SDK**</span></span>\
<span data-ttu-id="ce059-127">_C:\\program files\\dotnet\\sdk\\{version}\\_</span><span class="sxs-lookup"><span data-stu-id="ce059-127">_C:\\program files\\dotnet\\sdk\\{version}\\_</span></span>

- <span data-ttu-id="ce059-128">**.NET 런타임**</span><span class="sxs-lookup"><span data-stu-id="ce059-128">**.NET Runtime**</span></span>\
<span data-ttu-id="ce059-129">_C:\\program files\\dotnet\\shared\\{runtime-type}\\{version}\\_</span><span class="sxs-lookup"><span data-stu-id="ce059-129">_C:\\program files\\dotnet\\shared\\{runtime-type}\\{version}\\_</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="ce059-130">**dotnet 실행 파일**</span><span class="sxs-lookup"><span data-stu-id="ce059-130">**dotnet executable**</span></span>\
<span data-ttu-id="ce059-131">_/home/user/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="ce059-131">_/home/user/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="ce059-132">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="ce059-132">**.NET SDK**</span></span>\
<span data-ttu-id="ce059-133">_/home/user/share/dotnet/sdk/{version}/_</span><span class="sxs-lookup"><span data-stu-id="ce059-133">_/home/user/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="ce059-134">**.NET 런타임**</span><span class="sxs-lookup"><span data-stu-id="ce059-134">**.NET Runtime**</span></span>\
<span data-ttu-id="ce059-135">_/home/user/share/dotnet/shared/{runtime-type}/{version}/_</span><span class="sxs-lookup"><span data-stu-id="ce059-135">_/home/user/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="ce059-136">**dotnet 실행 파일**</span><span class="sxs-lookup"><span data-stu-id="ce059-136">**dotnet executable**</span></span>\
<span data-ttu-id="ce059-137">_/usr/local/share/dotnet/dotnet_</span><span class="sxs-lookup"><span data-stu-id="ce059-137">_/usr/local/share/dotnet/dotnet_</span></span>

- <span data-ttu-id="ce059-138">**.NET SDK**</span><span class="sxs-lookup"><span data-stu-id="ce059-138">**.NET SDK**</span></span>\
<span data-ttu-id="ce059-139">_/usr/local/share/dotnet/sdk/{version}/_</span><span class="sxs-lookup"><span data-stu-id="ce059-139">_/usr/local/share/dotnet/sdk/{version}/_</span></span>

- <span data-ttu-id="ce059-140">**.NET 런타임**</span><span class="sxs-lookup"><span data-stu-id="ce059-140">**.NET Runtime**</span></span>\
<span data-ttu-id="ce059-141">_/usr/local/share/dotnet/shared/{runtime-type}/{version}/_</span><span class="sxs-lookup"><span data-stu-id="ce059-141">_/usr/local/share/dotnet/shared/{runtime-type}/{version}/_</span></span>

::: zone-end

## <a name="more-information"></a><span data-ttu-id="ce059-142">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ce059-142">More information</span></span>

<span data-ttu-id="ce059-143">`dotnet --info` 명령을 사용하여 SDK의 버전과 런타임의 버전을 모두 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-143">You can see both the SDK versions and runtime versions with the command `dotnet --info`.</span></span> <span data-ttu-id="ce059-144">그 밖에도 운영 체제 버전, 런타임 식별자(RID)와 같은 다른 환경 관련 정보도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce059-144">You'll also get other environmental related information, such as the operating system version and runtime identifier (RID).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce059-145">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ce059-145">Next steps</span></span>

- <span data-ttu-id="ce059-146">[Install the .NET Core Runtime](runtime.md)(.NET Core 런타임 설치)</span><span class="sxs-lookup"><span data-stu-id="ce059-146">[Install the .NET Core Runtime](runtime.md).</span></span>
- <span data-ttu-id="ce059-147">[Install the .NET Core SDK](sdk.md)(.NET Core SDK 설치)</span><span class="sxs-lookup"><span data-stu-id="ce059-147">[Install the .NET Core SDK](sdk.md).</span></span>
