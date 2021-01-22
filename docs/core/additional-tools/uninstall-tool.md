---
title: 제거 도구
description: .NET Core SDK 및 런타임의 제어된 정리를 사용 설정하는 단계별 도구인 .NET Core 제거 도구에 대한 개요입니다.
author: sfoslund
ms.date: 05/27/2020
ms.openlocfilehash: ed43b4ec8437ae0ccaf5f1234758dda9f16bd51e
ms.sourcegitcommit: 4f5f1855849cb02c3b610c7006ac21d7429f3348
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98235354"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="f7212-103">.NET Core 제거 도구</span><span class="sxs-lookup"><span data-stu-id="f7212-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="f7212-104">[.NET Core 제거 도구](https://aka.ms/dotnet-core-uninstall-tool)(`dotnet-core-uninstall`)를 사용하면 시스템에서 .NET Core SDK 및 런타임을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="f7212-105">제거하고자 하는 버전을 지정할 수 있는 옵션 컬렉션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="f7212-106">도구는 Windows 및 macOS를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="f7212-107">Linux는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-107">Linux is currently not supported.</span></span>

<span data-ttu-id="f7212-108">Windows에서 도구는 다음 설치 관리자 중 하나를 사용하여 설치된 SDK 및 런타임만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="f7212-109">.NET Core SDK 및 런타임 설치 관리자.</span><span class="sxs-lookup"><span data-stu-id="f7212-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="f7212-110">Visual Studio 2019 버전 16.3 이전 버전의 Visual studio 설치 관리자.</span><span class="sxs-lookup"><span data-stu-id="f7212-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="f7212-111">macOS에서 도구는 */usr/local/share/dotnet* 폴더에 있는 SDK 및 런타임만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="f7212-112">이러한 제한 사항으로 인해 도구는 컴퓨터에서 모든 .NET Core SDK 및 런타임을 제거하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="f7212-113">`dotnet --info` 명령을 사용하여 이 도구에서 제거할 수 없는 SDK 및 런타임을 포함하여 설치된 모든 .NET Core SDK 및 런타임을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="f7212-114">`dotnet-core-uninstall list` 명령을 사용하면 도구를 사용하여 제거할 수 있는 SDK가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span> <span data-ttu-id="f7212-115">버전 1.2 이상은 버전 5.0 이하의 SDK 및 런타임을 제거할 수 있으며 이전 버전의 도구는 3.1 이하를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-115">Versions 1.2 and later can uninstall SDKs and runtimes with version 5.0 or earlier, and previous versions of the tool can uninstall 3.1 and earlier.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="f7212-116">도구 설치</span><span class="sxs-lookup"><span data-stu-id="f7212-116">Install the tool</span></span>

<span data-ttu-id="f7212-117">.NET Core 제거 도구를 [도구의 릴리스 페이지](https://aka.ms/dotnet-core-uninstall-tool)에서 다운로드할 수 있으며 [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub 리포지토리에서 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-117">You can download the .NET Core Uninstall Tool from [the tool's releases page](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="f7212-118">이 도구에는 .NET Core SDK 및 런타임 제거를 위한 권한 상승이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-118">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="f7212-119">따라서 Windows의 경우 *C:\Program Files*, 또는 macOS의 경우 */usr/local/bin* 과 같이 쓰기 보호된 디렉터리에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-119">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="f7212-120">[dotnet 명령에 대한 상승된 액세스 권한](../tools/elevated-access.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7212-120">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="f7212-121">자세한 내용은 [자세한 설치 지침](https://aka.ms/dotnet-core-uninstall-tool)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7212-121">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="f7212-122">도구 실행</span><span class="sxs-lookup"><span data-stu-id="f7212-122">Run the tool</span></span>

<span data-ttu-id="f7212-123">다음 단계는 제거 도구 실행을 위한 권장 접근 방식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-123">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="f7212-124">1단계 - 설치된 .NET Core SDK 및 런타임 표시</span><span class="sxs-lookup"><span data-stu-id="f7212-124">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="f7212-125">2단계- 시험 실행 실시</span><span class="sxs-lookup"><span data-stu-id="f7212-125">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="f7212-126">3단계 - .NET Core SDK 및 런타임 제거</span><span class="sxs-lookup"><span data-stu-id="f7212-126">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="f7212-127">4단계 - NuGet 대체 폴더 삭제(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="f7212-127">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="f7212-128">1단계 - 설치된 .NET Core SDK 및 런타임 표시</span><span class="sxs-lookup"><span data-stu-id="f7212-128">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="f7212-129">`dotnet-core-uninstall list` 명령은 이 도구를 사용하여 제거할 수 있는 설치된 .NET Core SDK 및 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-129">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="f7212-130">일부 SDK 및 런타임은 Visual Studio에 필요할 수 있으며, 제거를 권장하지 않는 이유를 포함하여 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-130">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

> [!NOTE]
> <span data-ttu-id="f7212-131">대부분의 경우 `dotnet-core-uninstall list` 명령의 출력이 `dotnet --info`의 출력에서 설치된 버전 목록과 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-131">The output of the `dotnet-core-uninstall list` command will not match the list of installed versions in the output of `dotnet --info` in most cases.</span></span> <span data-ttu-id="f7212-132">특히 이 도구는 zip 파일로 설치되거나 Visual Studio에서 관리하는 버전을 표시하지 않습니다(Visual Studio 2019 16.3 이상에 설치된 모든 버전).</span><span class="sxs-lookup"><span data-stu-id="f7212-132">Specifically, this tool will not display versions installed by zip files or managed by Visual Studio (any version installed with Visual Studio 2019 16.3 or later).</span></span> <span data-ttu-id="f7212-133">Visual Studio에서 버전을 관리하는지 확인하는 한 가지 방법은 Visual Studio 관리되는 버전이 표시 이름에 표시되는 `Add or Remove Programs`에서 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-133">One way to check if a version is managed by Visual Studio is to view it in `Add or Remove Programs`, where Visual Studio managed versions are marked as such in their display names.</span></span>

<span data-ttu-id="f7212-134">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="f7212-134">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="f7212-135">개요</span><span class="sxs-lookup"><span data-stu-id="f7212-135">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="f7212-136">옵션</span><span class="sxs-lookup"><span data-stu-id="f7212-136">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="f7212-137">Windows</span><span class="sxs-lookup"><span data-stu-id="f7212-137">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="f7212-138">이 도구를 사용하여 제거할 수 있는 모든 ASP.NET Core 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-138">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="f7212-139">이 도구를 사용하여 제거할 수 있는 모든 .NET Core 호스팅 번들을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-139">Lists all the .NET Core hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="f7212-140">이 도구를 사용하여 제거할 수 있는 모든 .NET Core 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-140">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="f7212-141">이 도구를 사용하여 제거할 수 있는 모든 .NET Core SDK를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-141">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f7212-142">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-142">Sets the verbosity level.</span></span> <span data-ttu-id="f7212-143">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-143">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f7212-144">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-144">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="f7212-145">이 도구를 사용하여 제거할 수 있는 모든 x64 .NET Core SDK 및 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-145">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="f7212-146">이 도구를 사용하여 제거할 수 있는 모든 x86 .NET Core SDK 및 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-146">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f7212-147">macOS</span><span class="sxs-lookup"><span data-stu-id="f7212-147">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="f7212-148">이 도구를 사용하여 제거할 수 있는 모든 .NET Core 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-148">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="f7212-149">이 도구를 사용하여 제거할 수 있는 모든 .NET Core SDK를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-149">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f7212-150">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-150">Sets the verbosity level.</span></span> <span data-ttu-id="f7212-151">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f7212-152">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-152">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="f7212-153">예</span><span class="sxs-lookup"><span data-stu-id="f7212-153">Examples</span></span>

* <span data-ttu-id="f7212-154">이 도구를 사용하여 제거할 수 있는 모든 .NET Core SDK 및 런타임 나열:</span><span class="sxs-lookup"><span data-stu-id="f7212-154">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="f7212-155">모든 x64 .NET Core SDK 및 런타임 나열:</span><span class="sxs-lookup"><span data-stu-id="f7212-155">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="f7212-156">모든 x86 .NET Core SDK 나열:</span><span class="sxs-lookup"><span data-stu-id="f7212-156">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="f7212-157">2단계- 시험 실행 실시</span><span class="sxs-lookup"><span data-stu-id="f7212-157">Step 2 - Do a dry run</span></span>

<span data-ttu-id="f7212-158">`dotnet-core-uninstall dry-run` 및 `dotnet-core-uninstall whatif` 명령은 제거를 수행하지 않고 입력한 옵션에 따라 제거할 .NET Core SDK 및 런타임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-158">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="f7212-159">이 명령은 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-159">These commands are synonyms.</span></span>

<span data-ttu-id="f7212-160">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="f7212-160">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="f7212-161">개요</span><span class="sxs-lookup"><span data-stu-id="f7212-161">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="f7212-162">인수</span><span class="sxs-lookup"><span data-stu-id="f7212-162">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="f7212-163">제거할 지정된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-163">The specified version to uninstall.</span></span> <span data-ttu-id="f7212-164">공백으로 구분하여 여러 버전을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-164">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="f7212-165">지시 파일도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-165">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="f7212-166">지시 파일은 명령줄에 모든 버전을 배치하는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-166">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="f7212-167">지시 파일은 \*.rsp 확장명을 사용하는 텍스트 파일이며, 각 버전은 별도의 줄에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-167">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="f7212-168">`VERSION` 인수에 대한 지시 파일을 지정하려면 지시 파일 이름 바로 뒤에 \@ 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-168">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="f7212-169">옵션</span><span class="sxs-lookup"><span data-stu-id="f7212-169">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="f7212-170">Windows</span><span class="sxs-lookup"><span data-stu-id="f7212-170">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="f7212-171">모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-171">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="f7212-172">지정된 버전보다 이전 버전의 .NET Core SDK 및 런타임만을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-172">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="f7212-173">지정된 버전은 설치된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-173">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="f7212-174">지정된 버전을 제외한 모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-174">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f7212-175">최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-175">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f7212-176">상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-176">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f7212-177">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-177">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f7212-178">미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-178">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f7212-179">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-179">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="f7212-180">ASP.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-180">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="f7212-181">.NET Core 런타임 및 호스팅 번들만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-181">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f7212-182">지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-182">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f7212-183">.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-183">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f7212-184">.NET Core SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-184">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f7212-185">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-185">Sets the verbosity level.</span></span> <span data-ttu-id="f7212-186">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-186">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f7212-187">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-187">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="f7212-188">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x64 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-188">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="f7212-189">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x86 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-189">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="f7212-190">**`--force`** 는 Visual Studio에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-190">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="f7212-191">메모:</span><span class="sxs-lookup"><span data-stu-id="f7212-191">Notes:</span></span>

1. <span data-ttu-id="f7212-192">정확히 `--sdk`, `--runtime`, `--aspnet-runtime` 및 `--hosting-bundle` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-192">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="f7212-193">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-193">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="f7212-194">`--x64` 또는 `--x86`이 지정되지 않은 경우 x64와 x86 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-194">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f7212-195">macOS</span><span class="sxs-lookup"><span data-stu-id="f7212-195">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="f7212-196">모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-196">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="f7212-197">지정된 버전보다 낮은 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-197">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="f7212-198">지정된 버전은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-198">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="f7212-199">지정된 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-199">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f7212-200">최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-200">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f7212-201">상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-201">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f7212-202">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-202">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f7212-203">미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-203">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f7212-204">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-204">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f7212-205">지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-205">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f7212-206">.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-206">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f7212-207">.NET Core SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-207">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f7212-208">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-208">Sets the verbosity level.</span></span> <span data-ttu-id="f7212-209">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-209">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f7212-210">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-210">The default value is `normal`.</span></span>
  
* <span data-ttu-id="f7212-211">**`--force`** 는 Visual Studio 또는 SDK에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-211">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="f7212-212">메모:</span><span class="sxs-lookup"><span data-stu-id="f7212-212">Notes:</span></span>

1. <span data-ttu-id="f7212-213">정확히 `--sdk` 및 `--runtime` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-213">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="f7212-214">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-214">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="f7212-215">예</span><span class="sxs-lookup"><span data-stu-id="f7212-215">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="f7212-216">기본적으로 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET Core SDK 및 런타임은 `dotnet-core-uninstall dry-run` 출력에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-216">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="f7212-217">다음 예에서는 컴퓨터의 상태에 따라 지정된 SDK 및 런타임 중 일부가 출력에 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-217">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="f7212-218">모든 SDK 및 런타임을 포함하려면 이를 명시적으로 인수로 나열하거나 `--force` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-218">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="f7212-219">상위 패치로 대체된 모든 .NET Core 런타임 제거를 시험 실행:</span><span class="sxs-lookup"><span data-stu-id="f7212-219">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="f7212-220">버전 `2.2.301` 이하의 모든 .NET Core SDK 제거를 시험 실행:</span><span class="sxs-lookup"><span data-stu-id="f7212-220">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="f7212-221">3단계 - .NET Core SDK 및 런타임 제거</span><span class="sxs-lookup"><span data-stu-id="f7212-221">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="f7212-222">`dotnet-core-uninstall remove`는 옵션 컬렉션에서 지정한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-222">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="f7212-223">버전 1.2 이상은 버전 5.0 이하의 SDK 및 런타임을 제거할 수 있으며 이전 버전의 도구는 3.1 이하를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-223">Versions 1.2 and later can uninstall SDKs and runtimes with version 5.0 or earlier, and previous versions of the tool can uninstall 3.1 and earlier.</span></span>

<span data-ttu-id="f7212-224">이 도구는 파괴적인 동작을 포함하므로 제거 명령을 실행하기 전에 시험 실행을 실시하는 것을 **적극** 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-224">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="f7212-225">시험 실행에서 `remove` 명령을 사용하면 어떤 .NET Core SDK 및 런타임이 제거되는지 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-225">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="f7212-226">어떤 SDK 및 런타임을 안전하게 제거할 수 있는지 알아보려면 [버전을 제거해야 하나요?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7212-226">Refer to [Should I remove a version?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="f7212-227">다음 사항에 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="f7212-227">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="f7212-228">이 도구는 컴퓨터의 `global.json` 파일에 필요한 .NET Core SDK 버전을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-228">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="f7212-229">[.NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core) 페이지에서 .NET Core SDK를 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-229">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="f7212-230">이 도구는 컴퓨터의 프레임워크 종속 애플리케이션에 필요한 .NET Core 런타임 버전을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-230">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="f7212-231">[.NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core) 페이지에서 .NET Core 런타임을 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-231">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="f7212-232">이 도구는 Visual Studio에서 사용하는 .NET Core SDK 및 런타임 버전을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-232">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="f7212-233">Visual Studio 설치를 중단하는 경우 Visual Studio 설치 관리자에서 "복구"를 실행하여 작업 상태로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-233">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="f7212-234">기본적으로 모든 명령은 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET Core SDK 및 런타임을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-234">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="f7212-235">이러한 SDK 및 런타임은 명시적으로 인수로 나열하거나 `--force` 옵션을 사용하여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-235">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="f7212-236">이 도구에는 .NET Core SDK 및 런타임 제거를 위한 권한 상승이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-236">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="f7212-237">Windows의 관리자 명령 프롬프트에서 및 macOS의 `sudo`를 사용하여 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-237">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="f7212-238">`dry-run` 및 `whatif` 명령에는 권한 상승이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-238">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="f7212-239">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="f7212-239">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="f7212-240">개요</span><span class="sxs-lookup"><span data-stu-id="f7212-240">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="f7212-241">인수</span><span class="sxs-lookup"><span data-stu-id="f7212-241">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="f7212-242">제거할 지정된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-242">The specified version to uninstall.</span></span> <span data-ttu-id="f7212-243">공백으로 구분하여 여러 버전을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-243">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="f7212-244">지시 파일도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-244">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="f7212-245">지시 파일은 명령줄에 모든 버전을 배치하는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-245">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="f7212-246">지시 파일은 \*.rsp 확장명을 사용하는 텍스트 파일이며, 각 버전은 별도의 줄에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-246">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="f7212-247">`VERSION` 인수에 대한 지시 파일을 지정하려면 지시 파일 이름 바로 뒤에 \@ 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-247">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="f7212-248">옵션</span><span class="sxs-lookup"><span data-stu-id="f7212-248">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="f7212-249">Windows</span><span class="sxs-lookup"><span data-stu-id="f7212-249">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="f7212-250">모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-250">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="f7212-251">지정된 버전보다 이전 버전의 .NET Core SDK 및 런타임만을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-251">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="f7212-252">지정된 버전은 설치된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-252">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="f7212-253">지정된 버전을 제외한 모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-253">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f7212-254">최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-254">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f7212-255">상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-255">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f7212-256">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-256">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f7212-257">미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-257">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f7212-258">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-258">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="f7212-259">ASP.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-259">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="f7212-260">.NET Core 호스팅 번들만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-260">Removes .NET Core hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f7212-261">지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-261">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f7212-262">.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-262">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f7212-263">.NET Core SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-263">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f7212-264">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-264">Sets the verbosity level.</span></span> <span data-ttu-id="f7212-265">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-265">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f7212-266">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-266">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="f7212-267">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x64 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-267">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="f7212-268">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x86 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-268">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="f7212-269">**`-y, --yes`** 예 또는 아니요를 확인하지 않고 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-269">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="f7212-270">**`--force`** 는 Visual Studio에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-270">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="f7212-271">메모:</span><span class="sxs-lookup"><span data-stu-id="f7212-271">Notes:</span></span>

1. <span data-ttu-id="f7212-272">정확히 `--sdk`, `--runtime`, `--aspnet-runtime` 및 `--hosting-bundle` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-272">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="f7212-273">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-273">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="f7212-274">`--x64` 또는 `--x86`이 지정되지 않은 경우 x64와 x86 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-274">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f7212-275">macOS</span><span class="sxs-lookup"><span data-stu-id="f7212-275">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="f7212-276">모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-276">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="f7212-277">지정된 버전보다 낮은 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-277">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="f7212-278">지정된 버전은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-278">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="f7212-279">지정된 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-279">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="f7212-280">최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-280">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="f7212-281">상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-281">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="f7212-282">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-282">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="f7212-283">미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-283">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="f7212-284">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-284">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="f7212-285">지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-285">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="f7212-286">.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-286">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="f7212-287">.NET Core SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-287">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="f7212-288">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-288">Sets the verbosity level.</span></span> <span data-ttu-id="f7212-289">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-289">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="f7212-290">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-290">The default value is `normal`.</span></span>

* <span data-ttu-id="f7212-291">**`-y, --yes`** 예 또는 아니요를 확인하지 않고 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-291">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="f7212-292">**`--force`** 는 Visual Studio 또는 SDK에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-292">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="f7212-293">메모:</span><span class="sxs-lookup"><span data-stu-id="f7212-293">Notes:</span></span>

1. <span data-ttu-id="f7212-294">정확히 `--sdk` 및 `--runtime` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-294">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="f7212-295">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-295">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="f7212-296">예</span><span class="sxs-lookup"><span data-stu-id="f7212-296">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="f7212-297">기본적으로 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET Core SDK 및 런타임은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-297">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="f7212-298">다음 예에서는 컴퓨터의 상태에 따라 지정된 SDK 및 런타임 중 일부가 그대로 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-298">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="f7212-299">모든 SDK 및 런타임을 제거하려면 이를 명시적으로 인수로 나열하거나 `--force` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-299">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="f7212-300">`3.0.0-preview6-27804-01` 버전을 제외한 모든 .NET Core 런타임을 예 또는 아니요 확인 없이 제거:</span><span class="sxs-lookup"><span data-stu-id="f7212-300">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="f7212-301">모든 .NET Core 1.1 SDK를 예 또는 아니요 확인 없이 제거:</span><span class="sxs-lookup"><span data-stu-id="f7212-301">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="f7212-302">콘솔 출력이 없는 .NET Core 1.1.11 SDK 제거:</span><span class="sxs-lookup"><span data-stu-id="f7212-302">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="f7212-303">이 도구로 안전하게 제거할 수 있는 모든 .NET Core SDK 제거:</span><span class="sxs-lookup"><span data-stu-id="f7212-303">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="f7212-304">Visual Studio에서 필요할 수 있는 SDK를 포함하여 이 도구로 제거할 수 있는 모든 .NET Core SDK 제거(권장하지 않음):</span><span class="sxs-lookup"><span data-stu-id="f7212-304">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="f7212-305">지시 파일 `versions.rsp`에 지정된 모든 .NET Core SDK 제거</span><span class="sxs-lookup"><span data-stu-id="f7212-305">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="f7212-306">*versions.rsp* 의 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-306">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="f7212-307">4단계 - NuGet 대체 폴더 삭제(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="f7212-307">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="f7212-308">경우에 따라 더 이상 `NuGetFallbackFolder`가 필요하지 않아 이를 삭제하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-308">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="f7212-309">이 폴더를 삭제하는 방법에 대한 자세한 내용은 [NuGetFallbackFolder 제거](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7212-309">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="f7212-310">도구 제거</span><span class="sxs-lookup"><span data-stu-id="f7212-310">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="f7212-311">Windows</span><span class="sxs-lookup"><span data-stu-id="f7212-311">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="f7212-312">**프로그램 추가/제거** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-312">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="f7212-313">`Microsoft .NET Core SDK Uninstall Tool`을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-313">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="f7212-314">**제거** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-314">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="f7212-315">macOS</span><span class="sxs-lookup"><span data-stu-id="f7212-315">macOS</span></span>](#tab/macos)

<span data-ttu-id="f7212-316">설치된 디렉터리에서 다운로드한 *dotnet-core-uninstall.tar.gz* 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-316">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="f7212-317">이 파일의 압축을 다른 디렉터리에 푼 경우 파일 내용 또한 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7212-317">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
