---
title: Windows, Linux 및 macOS에서 설치된 .NET Core 버전 확인 - .NET Core
description: 컴퓨터에 설치된 .NET Core 버전을 확인하는 방법을 알아봅니다. 여기에는 .NET Core 런타임 및 SDK가 포함됩니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a91a648f4b3d3fd36c43b22ad81f00b2ad55f3c4
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74999004"
---
# <a name="how-to-check-that-net-core-is-already-installed"></a><span data-ttu-id="4988c-104">.NET Core가 설치되어 있는지 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="4988c-104">How to check that .NET Core is already installed</span></span>

<span data-ttu-id="4988c-105">이 문서에서는 컴퓨터에 설치된 .NET Core 런타임 및 SDK의 버전을 확인하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4988c-105">This article teaches you how to check which versions of the .NET Core runtime and SDK are installed on your computer.</span></span> <span data-ttu-id="4988c-106">Visual Studio 또는 Mac용 Visual Studio와 같은 통합 개발 환경이 설치된 경우 .NET Core가 이미 설치되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4988c-106">.NET core may have already been installed if you have an integrated development environment, such as Visual Studio or Visual Studio for Mac.</span></span>

<span data-ttu-id="4988c-107">SDK를 설치하면 그에 해당하는 런타임도 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="4988c-107">Installing an SDK installs the corresponding runtime.</span></span>

<span data-ttu-id="4988c-108">이 문서에서 안내하는 명령이 작동하지 않는다면 런타임 또는 SDK가 설치되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4988c-108">If any command in this article fails, you don't have the runtime or SDK installed.</span></span> <span data-ttu-id="4988c-109">자세한 내용은 [.NET Core 다운로드 및 설치](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4988c-109">For more information, see [Download and install .NET Core](index.md).</span></span>

## <a name="check-sdk-versions"></a><span data-ttu-id="4988c-110">SDK 버전 확인</span><span class="sxs-lookup"><span data-stu-id="4988c-110">Check SDK versions</span></span>

<span data-ttu-id="4988c-111">터미널을 사용하여 현재 설치된 .NET Core SDK의 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4988c-111">You can see which versions of the .NET Core SDK are currently installed with a terminal.</span></span> <span data-ttu-id="4988c-112">터미널을 열고 `dotnet --list-sdks` 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4988c-112">Open a terminal and run the `dotnet --list-sdks` command.</span></span>

::: zone pivot="os-windows"

```console
dotnet --list-sdks

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
dotnet --list-sdks

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
dotnet --list-sdks

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

## <a name="check-runtime-versions"></a><span data-ttu-id="4988c-113">런타임 버전 확인</span><span class="sxs-lookup"><span data-stu-id="4988c-113">Check runtime versions</span></span>

<span data-ttu-id="4988c-114">`dotnet --list-runtimes` 명령을 사용하여 현재 설치된 .NET Core 런타임의 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4988c-114">You can see which versions of the .NET Core runtime are currently installed with the `dotnet --list-runtimes` command.</span></span>

::: zone pivot="os-windows"

```console
dotnet --list-runtimes

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
dotnet --list-runtimes

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
dotnet --list-sdks

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

## <a name="more-information"></a><span data-ttu-id="4988c-115">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4988c-115">More information</span></span>

<span data-ttu-id="4988c-116">`dotnet --info` 명령을 사용하여 SDK의 버전과 런타임의 버전을 모두 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4988c-116">You can see both the SDK versions and runtime versions with the command `dotnet --info`.</span></span> <span data-ttu-id="4988c-117">그 밖에도 운영 체제 버전, 런타임 식별자(RID)와 같은 다른 환경 관련 정보도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4988c-117">You'll also get other environmental related information, such as the operating system version and runtime identifier (RID).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4988c-118">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4988c-118">Next steps</span></span>

- <span data-ttu-id="4988c-119">[Install the .NET Core Runtime](runtime.md)(.NET Core 런타임 설치)</span><span class="sxs-lookup"><span data-stu-id="4988c-119">[Install the .NET Core Runtime](runtime.md).</span></span>
- <span data-ttu-id="4988c-120">[Install the .NET Core SDK](sdk.md)(.NET Core SDK 설치)</span><span class="sxs-lookup"><span data-stu-id="4988c-120">[Install the .NET Core SDK](sdk.md).</span></span>
