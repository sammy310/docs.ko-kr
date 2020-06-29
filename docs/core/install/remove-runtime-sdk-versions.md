---
title: .NET Core 런타임 및 SDK 제거
description: 이 문서에서는 현재 설치된 .NET Core 런타임 및 SDK 버전을 확인하는 방법 및 Windows, Mac 및 Linux에서 제거하는 방법을 설명합니다.
author: adegeo
ms.author: adegeo
ms.date: 04/28/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 1e4a846cf5e3d0209f5ade873520ef64abc12e7c
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324649"
---
# <a name="how-to-remove-the-net-core-runtime-and-sdk"></a><span data-ttu-id="6e800-103">.NET Core 런타임 및 SDK를 제거하는 방법</span><span class="sxs-lookup"><span data-stu-id="6e800-103">How to remove the .NET Core Runtime and SDK</span></span>

<span data-ttu-id="6e800-104">시간이 지남에 따라 .NET Core 런타임 및 SDK의 업데이트된 버전을 설치할 때 머신에서 .NET Core의 오래된 버전을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-104">Over time, as you install updated versions of the .NET Core runtime and SDK, you may want to remove outdated versions of .NET Core from your machine.</span></span> <span data-ttu-id="6e800-105">이전 버전의 런타임을 제거하면 [.NET Core 버전 선택](../versions/selection.md)의 문서에서 설명한 대로 공유 프레임워크 애플리케이션을 실행하기 위해 선택한 런타임이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-105">Removing older versions of the runtime may change the runtime chosen to run shared framework applications, as detailed in the article on [.NET Core version selection](../versions/selection.md).</span></span>

## <a name="should-i-remove-a-version"></a><span data-ttu-id="6e800-106">버전을 제거해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="6e800-106">Should I remove a version?</span></span>

<span data-ttu-id="6e800-107">[.NET Core 버전 선택](../versions/selection.md) 동작 및 .NET Core의 런타임 호환성을 업데이트하여 이전 버전을 안전하게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-107">The [.NET Core version selection](../versions/selection.md) behaviors and the runtime compatibility of .NET Core across updates enables safe removal of previous versions.</span></span> <span data-ttu-id="6e800-108">.NET Core 런타임 업데이트는 1.x 및 2.x와 같은 주 버전 '대역' 내에서 호환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-108">.NET Core runtime updates are compatible within a major version 'band' such as 1.x and 2.x.</span></span> <span data-ttu-id="6e800-109">또한 .NET Core SDK의 최신 릴리스는 호환 가능한 방식으로 이전 버전의 런타임을 대상으로 하는 애플리케이션을 빌드하는 기능을 일반적으로 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-109">Additionally, newer releases of the .NET Core SDK generally maintain the ability to build applications that target previous versions of the runtime in a compatible manner.</span></span>

<span data-ttu-id="6e800-110">일반적으로 애플리케이션에 필요한 최신 SDK 및 런타임의 최신 패치 버전만 있으면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-110">In general, you only need the latest SDK and latest patch version of the runtimes required for your application.</span></span> <span data-ttu-id="6e800-111">이전 SDK 또는 런타임 버전을 유지하려는 인스턴스에는 *project.json* 기반 애플리케이션 유지 관리가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-111">Instances where you might want to keep older SDK or runtime versions include maintaining *project.json*-based applications.</span></span> <span data-ttu-id="6e800-112">애플리케이션에 이전 SDK 또는 런타임에 대한 특정 이유가 없는 경우 이전 버전을 안전하게 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-112">Unless your application has specific reasons for earlier SDKs or runtimes, you may safely remove older versions.</span></span>

## <a name="determine-what-is-installed"></a><span data-ttu-id="6e800-113">설치된 버전 확인</span><span class="sxs-lookup"><span data-stu-id="6e800-113">Determine what is installed</span></span>

<span data-ttu-id="6e800-114">.NET Core 2.1부터 .NET CLI에는 머신에 설치된 SDK 및 런타임 버전을 나열하는 데 사용할 수 있는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-114">Starting with .NET Core 2.1, the .NET CLI has options you can use to list the versions of the SDK and runtime that are installed on your machine.</span></span>  <span data-ttu-id="6e800-115">[`dotnet --list-sdks`](../tools/dotnet.md#options)를 사용하여 머신에 설치된 SDK의 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-115">Use [`dotnet --list-sdks`](../tools/dotnet.md#options) to see the list of SDKs installed on your machine.</span></span> <span data-ttu-id="6e800-116">[`dotnet --list-runtimes`](../tools/dotnet.md#options)을 사용하여 머신에 설치된 런타임의 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-116">Use [`dotnet --list-runtimes`](../tools/dotnet.md#options) to see the list of runtimes installed on your machine.</span></span> <span data-ttu-id="6e800-117">자세한 내용은 [.NET Core가 이미 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e800-117">For more information, see [How to check that .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>

## <a name="uninstall-net-core"></a><span data-ttu-id="6e800-118">.NET Core 제거</span><span class="sxs-lookup"><span data-stu-id="6e800-118">Uninstall .NET Core</span></span>

::: zone pivot="os-windows"

<span data-ttu-id="6e800-119">.NET Core는 Windows **앱 및 기능** 대화 상자를 사용하여 .NET Core 런타임 및 SDK의 버전을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-119">.NET Core uses the Windows **Apps & features** dialog to remove versions of the .NET Core runtime and SDK.</span></span> <span data-ttu-id="6e800-120">다음 그림은 **앱 및 기능** 대화 상자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-120">The following figure shows the **Apps & features** dialog.</span></span> <span data-ttu-id="6e800-121">**core sdk**를 검색하여 설치된 .NET Core 버전을 필터링하고 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-121">You can search for **core sdk** to filter and show installed versions of .NET Core.</span></span>

![.NET Core 제거를 위한 프로그램 추가/제거](./media/remove-runtime-sdk-versions/programs-and-features.png)

<span data-ttu-id="6e800-123">머신에서 제거할 버전을 선택하고 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-123">Select any versions you want to remove from your machine and click **Uninstall**.</span></span>

::: zone-end

::: zone pivot="os-linux"

<span data-ttu-id="6e800-124">Linux에서 .NET Core(SDK 또는 런타임)를 제거하는 옵션이 더 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-124">There are more options to uninstall .NET Core (either SDK or runtime) on Linux.</span></span> <span data-ttu-id="6e800-125">.NET Core를 제거하는 가장 좋은 방법은 .NET Core 설치에 사용한 작업을 미러링하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-125">The best way for you to uninstall .NET Core is to mirror the action you used to install .NET Core.</span></span> <span data-ttu-id="6e800-126">세부 정보는 선택한 배포 및 설치 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-126">The specifics depend on your chosen distribution and the installation method.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e800-127">Red Hat 설치의 경우 .NET Core 설치 및 제거에 대한 정보는 [Red Hat 시작 가이드](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e800-127">For Red Hat installations, consult the [Red Hat Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/gs_install_dotnet#install_register_rehel) for information on installing and uninstalling .NET Core.</span></span>

<span data-ttu-id="6e800-128">.NET Core 2.1부터 패키지 관리자를 사용하여 업그레이드할 때 .NET Core SDK를 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-128">Starting with .NET Core 2.1, there's no need to uninstall the .NET Core SDK when upgrading it using a package manager.</span></span> <span data-ttu-id="6e800-129">패키지 관리자 `update` 또는 `refresh` 명령은 최신 버전을 성공적으로 설치하면 이전 버전을 자동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-129">The package manager `update` or `refresh` commands will automatically remove the older version upon the successful installation of a newer version.</span></span>

<span data-ttu-id="6e800-130">패키지 관리자를 사용하여 .NET Core를 설치한 경우 동일한 패키지 관리자를 사용하여 .NET SDK 또는 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-130">If you installed .NET Core using a package manager, you use that same package manager to uninstall .NET SDK or runtime.</span></span> <span data-ttu-id="6e800-131">.NET core 설치는 가장 인기 있는 패키지 관리자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-131">.NET Core installations support most popular package managers.</span></span> <span data-ttu-id="6e800-132">환경의 정확한 구문은 배포의 패키지 관리자에 관한 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6e800-132">Consult the documentation for your distribution's package manager for the precise syntax in your environment:</span></span>

- <span data-ttu-id="6e800-133">[apt-get(8)](https://linux.die.net/man/8/apt-get)은 Debian 기반 시스템(Ubuntu 포함)에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-133">[apt-get(8)](https://linux.die.net/man/8/apt-get) is used by Debian based systems, including Ubuntu.</span></span>
- <span data-ttu-id="6e800-134">[yum(8)](https://linux.die.net/man/8/yum)은 Fedora, CentOS 및 Oracle Linux에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-134">[yum(8)](https://linux.die.net/man/8/yum) is used on Fedora, CentOS, and Oracle Linux.</span></span>
- <span data-ttu-id="6e800-135">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain))는 openSUSE 및 SLES(SUSE Linux Enterprise 시스템)에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-135">[zypper(8)](https://en.opensuse.org/SDB:Zypper_manual_(plain)) is used on openSUSE and SUSE Linux Enterprise System (SLES).</span></span>
- <span data-ttu-id="6e800-136">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html)는 Fedora에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-136">[dnf(8)](https://dnf.readthedocs.io/en/latest/command_ref.html) is used on Fedora.</span></span>

<span data-ttu-id="6e800-137">대부분의 경우 패키지를 제거하는 명령은 `remove`입니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-137">In almost all cases, the command to remove a package is `remove`.</span></span>

<span data-ttu-id="6e800-138">대부분의 패키지 관리자에 대한 .NET Core SDK 설치의 패키지 이름은 `dotnet-sdk`이며, 그 뒤에 버전 번호가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-138">The package name for the .NET Core SDK installation for most package managers is `dotnet-sdk`, followed by the version number.</span></span> <span data-ttu-id="6e800-139">.NET Core SDK의 버전 2.1.300 및 런타임의 버전 `2.1`부터는 주 및 부 버전 번호만 필요합니다. 예를 들어 .NET Core SDK 버전 2.1.300은 `dotnet-sdk-2.1` 패키지로 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-139">Starting with the version 2.1.300 of the .NET Core SDK and version `2.1` of the runtime, only the major and minor version numbers are necessary: for example, the .NET Core SDK version 2.1.300 can be referenced as the package `dotnet-sdk-2.1`.</span></span> <span data-ttu-id="6e800-140">이전 버전에는 전체 버전 문자열이 필요합니다. 예를 들어 .NET Core SDK의 버전 2.1.200에는 `dotnet-sdk-2.1.200`이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-140">Prior versions require the entire version string: for example, `dotnet-sdk-2.1.200` would be required for version 2.1.200 of the .NET Core SDK.</span></span>

<span data-ttu-id="6e800-141">SDK가 아닌 런타임만 설치한 머신의 경우, 패키지 이름은 .NET Core 런타임의 경우에는 `dotnet-runtime-<version>`이고 전체 런타임 스택의 경우에는 `aspnetcore-runtime-<version>`입니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-141">For machines that have installed only the runtime, and not the SDK, the package name is `dotnet-runtime-<version>` for the .NET Core runtime, and `aspnetcore-runtime-<version>` for the entire runtime stack.</span></span>

<span data-ttu-id="6e800-142">2\.0 이전의 .NET Core 설치는 패키지 관리자를 사용하여 SDK를 제거할 때 호스트 애플리케이션을 제거하지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-142">.NET Core installations earlier than 2.0 didn't uninstall the host application when the SDK was uninstalled using the package manager.</span></span> <span data-ttu-id="6e800-143">`apt-get`을 사용하는 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-143">Using `apt-get`, the command is:</span></span>

```bash
apt-get remove dotnet-host
```

<span data-ttu-id="6e800-144">`dotnet-host`에 연결된 버전이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-144">Note that there's no version attached to `dotnet-host`.</span></span>

<span data-ttu-id="6e800-145">tarball을 사용하여 설치한 경우 수동 메서드를 사용하여 .NET Core를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-145">If you installed using a tarball, you must remove .NET Core using the manual method.</span></span>

<span data-ttu-id="6e800-146">Linux에서는 버전이 지정된 디렉터리를 제거하여 SDK와 런타임을 별도로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-146">On Linux, you must remove the SDKs and runtimes separately, by removing the versioned directories.</span></span> <span data-ttu-id="6e800-147">디렉터리를 제거하면 디스크에서 SDK 및 런타임이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-147">Removing them deletes the SDK and runtime from disk.</span></span> <span data-ttu-id="6e800-148">예는 들어 1.0.1 SDK 및 런타임을 제거하려면 다음 bash 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-148">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

<span data-ttu-id="6e800-149">SDK 및 런타임에 대한 부모 디렉터리는 이전 표에 표시된 것처럼 `dotnet --list-sdks` 및 `dotnet --list-runtimes` 명령의 출력에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-149">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="6e800-150">Mac에서는 버전이 지정된 디렉터리를 제거하여 SDK와 런타임을 별도로 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-150">On Mac, you must remove the SDKs and runtimes separately, by removing the versioned directories.</span></span> <span data-ttu-id="6e800-151">디렉터리를 제거하면 디스크에서 SDK 및 런타임이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-151">Removing them deletes the SDK and runtime from disk.</span></span> <span data-ttu-id="6e800-152">예는 들어 1.0.1 SDK 및 런타임을 제거하려면 다음 bash 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-152">For example, to remove the 1.0.1 SDK and runtime, you would use the following bash commands:</span></span>

```bash
version="1.0.1"
sudo rm -rf /usr/local/share/dotnet/sdk/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.NETCore.App/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.All/$version
sudo rm -rf /usr/local/share/dotnet/shared/Microsoft.AspNetCore.App/$version
sudo rm -rf /usr/local/share/dotnet/host/fxr/$version
```

<span data-ttu-id="6e800-153">SDK 및 런타임에 대한 부모 디렉터리는 이전 표에 표시된 것처럼 `dotnet --list-sdks` 및 `dotnet --list-runtimes` 명령의 출력에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-153">The parent directories for the SDK and runtime are listed in the output from the `dotnet --list-sdks` and `dotnet --list-runtimes` command, as shown in the earlier table.</span></span>

::: zone-end

## <a name="net-core-uninstall-tool"></a><span data-ttu-id="6e800-154">.NET Core 제거 도구</span><span class="sxs-lookup"><span data-stu-id="6e800-154">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="6e800-155">[.NET Core 제거 도구](../additional-tools/uninstall-tool.md)(`dotnet-core-uninstall`)를 사용하면 시스템에서 .NET Core SDK 및 런타임을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-155">The [.NET Core Uninstall Tool](../additional-tools/uninstall-tool.md) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and runtimes from a system.</span></span> <span data-ttu-id="6e800-156">제거해야 하는 버전을 지정할 수 있는 옵션 컬렉션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-156">A collection of options is available to specify which versions should be uninstalled.</span></span>

## <a name="visual-studio-dependency-on-net-core-sdk-versions"></a><span data-ttu-id="6e800-157">.NET Core SDK 버전에 대한 Visual Studio 종속성</span><span class="sxs-lookup"><span data-stu-id="6e800-157">Visual Studio dependency on .NET Core SDK versions</span></span>

<span data-ttu-id="6e800-158">Visual Studio 2019 버전 16.3 이전에는 Visual Studio 설치 관리자가 독립 실행형 .NET Core SDK 설치 관리자를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-158">Before Visual Studio 2019 version 16.3, Visual Studio installers called the standalone .NET Core SDK installer.</span></span> <span data-ttu-id="6e800-159">따라서 SDK 버전은 Windows **앱 및 기능** 대화 상자에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-159">As a result, the SDK versions appear in the Windows **Apps & features** dialog.</span></span> <span data-ttu-id="6e800-160">독립 실행형 설치 관리자를 사용하여 Visual Studio에서 설치한 .NET Core SDK를 제거하면 Visual Studio가 중단될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-160">Removing .NET Core SDKs that were installed by Visual Studio using the standalone installer may break Visual Studio.</span></span> <span data-ttu-id="6e800-161">SDK를 제거한 후 Visual Studio에서 문제가 발생하는 경우 해당 특정 버전의 Visual Studio에서 복구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-161">If Visual Studio has problems after you uninstall SDKs, run Repair on that specific version of Visual Studio.</span></span> <span data-ttu-id="6e800-162">다음 표에서는 .NET Core SDK 버전에 대한 몇 가지 Visual Studio 종속성을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-162">The following table shows some of the Visual Studio dependencies on .NET Core SDK versions:</span></span>

| <span data-ttu-id="6e800-163">Visual Studio 버전</span><span class="sxs-lookup"><span data-stu-id="6e800-163">Visual Studio version</span></span>           | <span data-ttu-id="6e800-164">.NET Core SDK 버전</span><span class="sxs-lookup"><span data-stu-id="6e800-164">.NET Core SDK version</span></span>          |
|---------------------------------|--------------------------------|
| <span data-ttu-id="6e800-165">Visual Studio 2019 버전 16.2</span><span class="sxs-lookup"><span data-stu-id="6e800-165">Visual Studio 2019 version 16.2</span></span> | <span data-ttu-id="6e800-166">.NET Core SDK 2.2.4xx, 2.1.8xx</span><span class="sxs-lookup"><span data-stu-id="6e800-166">.NET Core SDK 2.2.4xx, 2.1.8xx</span></span> |
| <span data-ttu-id="6e800-167">Visual Studio 2019 버전 16.1</span><span class="sxs-lookup"><span data-stu-id="6e800-167">Visual Studio 2019 version 16.1</span></span> | <span data-ttu-id="6e800-168">.NET Core SDK 2.2.3xx, 2.1.7xx</span><span class="sxs-lookup"><span data-stu-id="6e800-168">.NET Core SDK 2.2.3xx, 2.1.7xx</span></span> |
| <span data-ttu-id="6e800-169">Visual Studio 2019 버전 16.0</span><span class="sxs-lookup"><span data-stu-id="6e800-169">Visual Studio 2019 version 16.0</span></span> | <span data-ttu-id="6e800-170">.NET Core SDK 2.2.2xx, 2.1.6xx</span><span class="sxs-lookup"><span data-stu-id="6e800-170">.NET Core SDK 2.2.2xx, 2.1.6xx</span></span> |
| <span data-ttu-id="6e800-171">Visual Studio 2017 버전 15.9</span><span class="sxs-lookup"><span data-stu-id="6e800-171">Visual Studio 2017 version 15.9</span></span> | <span data-ttu-id="6e800-172">.NET Core SDK 2.2.1xx, 2.1.5xx</span><span class="sxs-lookup"><span data-stu-id="6e800-172">.NET Core SDK 2.2.1xx, 2.1.5xx</span></span> |
| <span data-ttu-id="6e800-173">Visual Studio 2017 버전 15.8</span><span class="sxs-lookup"><span data-stu-id="6e800-173">Visual Studio 2017 version 15.8</span></span> | <span data-ttu-id="6e800-174">.NET Core SDK 2.1.4xx</span><span class="sxs-lookup"><span data-stu-id="6e800-174">.NET Core SDK 2.1.4xx</span></span>          |

<span data-ttu-id="6e800-175">Visual Studio 2019 버전 16.3부터 Visual Studio는 .NET Core SDK의 자체 복사본을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-175">Starting with Visual Studio 2019 version 16.3, Visual Studio is in charge of its own copy of the .NET Core SDK.</span></span> <span data-ttu-id="6e800-176">그런 이유로 **앱 및 기능** 대화 상자에 해당 SDK 버전이 더 이상 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-176">For that reason, you no longer see those SDK versions in the **Apps & features** dialog.</span></span>

## <a name="remove-the-nuget-fallback-folder"></a><span data-ttu-id="6e800-177">NuGet 대체 폴더 제거</span><span class="sxs-lookup"><span data-stu-id="6e800-177">Remove the NuGet fallback folder</span></span>

<span data-ttu-id="6e800-178">.NET Core 3.0 SDK 이전에 .NET Core SDK 설치 프로그램은 *NuGetFallbackFolder* 폴더를 사용하여 NuGet 패키지의 캐시를 저장했습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-178">Before .NET Core 3.0 SDK, the .NET Core SDK installers used a folder named *NuGetFallbackFolder* to store a cache of NuGet packages.</span></span> <span data-ttu-id="6e800-179">이 캐시는 `dotnet restore`나 `dotnet build /t:Restore` 같은 작업 중에 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-179">This cache was used during operations such as `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="6e800-180">*NuGetFallbackFolder*는 Windows의 *C:\Program Files\dotnet\sdk*에 있고 macOS의 */usr/local/share/dotnet/sdk*에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-180">The *NuGetFallbackFolder* is located at *C:\Program Files\dotnet\sdk* on Windows and at */usr/local/share/dotnet/sdk* on macOS.</span></span>

<span data-ttu-id="6e800-181">다음 경우에는 이 폴더를 제거하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-181">You may want to remove this folder, if:</span></span>

- <span data-ttu-id="6e800-182">.NET Core 3.0 SDK 이후 버전을 사용하여 개발 중인 경우.</span><span class="sxs-lookup"><span data-stu-id="6e800-182">You're only developing using .NET Core 3.0 SDK or later versions.</span></span>
- <span data-ttu-id="6e800-183">3\.0 이전의 .NET Core SDK 버전을 사용하여 개발하고 있지만 온라인으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-183">You're developing using .NET Core SDK versions earlier than 3.0, but you can work online.</span></span>

<span data-ttu-id="6e800-184">NuGet 대체 폴더를 제거하고자 하는 경우 삭제할 수 있지만 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-184">If you want to remove the NuGet fallback folder, you can delete it, but you'll need admin privileges to do so.</span></span>

<span data-ttu-id="6e800-185">*dotnet* 폴더는 삭제하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-185">It's not recommended to delete the *dotnet* folder.</span></span> <span data-ttu-id="6e800-186">이렇게 하면 이전에 설치한 모든 전역 도구가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-186">Doing so would remove any global tools you've previously installed.</span></span> <span data-ttu-id="6e800-187">또한 Windows에서</span><span class="sxs-lookup"><span data-stu-id="6e800-187">Also, on Windows:</span></span>

- <span data-ttu-id="6e800-188">Visual Studio 2019 버전 16.3 이상 버전의 호환성이 손상됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-188">You'll break Visual Studio 2019 version 16.3 and later versions.</span></span> <span data-ttu-id="6e800-189">**복구**를 실행하여 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-189">You can run **Repair** to recover.</span></span>
- <span data-ttu-id="6e800-190">**앱 및 기능** 대화 상자에 있는 .NET Core SDK 항목은 분리됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e800-190">If there are .NET Core SDK entries in the **Apps & features** dialog, they'll be orphaned.</span></span>
