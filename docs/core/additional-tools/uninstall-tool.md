---
title: 제거 도구
description: .NET Core SDK 및 런타임의 제어된 정리를 사용 설정하는 단계별 도구인 .NET Core 제거 도구에 대한 개요입니다.
author: sfoslund
ms.date: 01/06/2020
ms.openlocfilehash: bd20cba133cbb754dcca48e48b76a391a9efacba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847072"
---
# <a name="net-core-uninstall-tool"></a><span data-ttu-id="d93c8-103">.NET Core 제거 도구</span><span class="sxs-lookup"><span data-stu-id="d93c8-103">.NET Core Uninstall Tool</span></span>

<span data-ttu-id="d93c8-104">[.NET Core 제거 도구](https://aka.ms/dotnet-core-uninstall-tool)(`dotnet-core-uninstall`)를 사용하면 시스템에서 .NET Core SDK 및 런타임을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-104">The [.NET Core Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET Core SDKs and Runtimes from a system.</span></span> <span data-ttu-id="d93c8-105">제거하고자 하는 버전을 지정할 수 있는 옵션 컬렉션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="d93c8-106">도구는 Windows 및 macOS를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="d93c8-107">Linux는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-107">Linux is currently not supported.</span></span>

<span data-ttu-id="d93c8-108">Windows에서 도구는 다음 설치 관리자 중 하나를 사용하여 설치된 SDK 및 런타임만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="d93c8-109">.NET Core SDK 및 런타임 설치 관리자.</span><span class="sxs-lookup"><span data-stu-id="d93c8-109">The .NET Core SDK and runtime installer.</span></span>
- <span data-ttu-id="d93c8-110">Visual Studio 2019 버전 16.3 이전 버전의 Visual studio 설치 관리자.</span><span class="sxs-lookup"><span data-stu-id="d93c8-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="d93c8-111">macOS에서 도구는 */usr/local/share/dotnet* 폴더에 있는 SDK 및 런타임만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="d93c8-112">이러한 제한 사항으로 인해 도구는 컴퓨터에서 모든 .NET Core SDK 및 런타임을 제거하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-112">Because of these limitations, the tool may not be able to uninstall all of the .NET Core SDKs and runtimes on your machine.</span></span> <span data-ttu-id="d93c8-113">`dotnet --info` 명령을 사용하여 이 도구에서 제거할 수 없는 SDK 및 런타임을 포함하여 설치된 모든 .NET Core SDK 및 런타임을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-113">You can use the `dotnet --info` command to find all of the .NET Core SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="d93c8-114">`dotnet-core-uninstall list` 명령을 사용하면 도구를 사용하여 제거할 수 있는 SDK가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="d93c8-115">도구 설치</span><span class="sxs-lookup"><span data-stu-id="d93c8-115">Install the tool</span></span>

<span data-ttu-id="d93c8-116">.NET Core 제거 도구를 [여기](https://aka.ms/dotnet-core-uninstall-tool)에서 다운로드할 수 있으며 [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub 리포지토리에서 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-116">You can download the .NET Core Uninstall Tool from [here](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="d93c8-117">이 도구에는 .NET Core SDK 및 런타임 제거를 위한 권한 상승이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-117">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="d93c8-118">따라서 Windows의 경우 *C:\Program Files*, 또는 macOS의 경우 */usr/local/bin*과 같이 쓰기 보호된 디렉터리에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-118">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="d93c8-119">[dotnet 명령에 대한 상승된 액세스 권한](../tools/elevated-access.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d93c8-119">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="d93c8-120">자세한 내용은 [자세한 설치 지침](https://aka.ms/dotnet-core-uninstall-tool)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d93c8-120">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="d93c8-121">도구 실행</span><span class="sxs-lookup"><span data-stu-id="d93c8-121">Run the tool</span></span>

<span data-ttu-id="d93c8-122">다음 단계는 제거 도구 실행을 위한 권장 접근 방식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-122">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="d93c8-123">1단계 - 설치된 .NET Core SDK 및 런타임 표시</span><span class="sxs-lookup"><span data-stu-id="d93c8-123">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>](#step-1---display-installed-net-core-sdks-and-runtimes)
- [<span data-ttu-id="d93c8-124">2단계- 시험 실행 실시</span><span class="sxs-lookup"><span data-stu-id="d93c8-124">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="d93c8-125">3단계 - .NET Core SDK 및 런타임 제거</span><span class="sxs-lookup"><span data-stu-id="d93c8-125">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>](#step-3---uninstall-net-core-sdks-and-runtimes)
- [<span data-ttu-id="d93c8-126">4단계 - NuGet 대체 폴더 삭제(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="d93c8-126">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-core-sdks-and-runtimes"></a><span data-ttu-id="d93c8-127">1단계 - 설치된 .NET Core SDK 및 런타임 표시</span><span class="sxs-lookup"><span data-stu-id="d93c8-127">Step 1 - Display installed .NET Core SDKs and runtimes</span></span>

<span data-ttu-id="d93c8-128">`dotnet-core-uninstall list` 명령은 이 도구를 사용하여 제거할 수 있는 설치된 .NET Core SDK 및 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-128">The `dotnet-core-uninstall list` command lists the installed .NET Core SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="d93c8-129">일부 SDK 및 런타임은 Visual Studio에 필요할 수 있으며, 제거를 권장하지 않는 이유를 포함하여 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-129">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

<span data-ttu-id="d93c8-130">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="d93c8-130">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d93c8-131">개요</span><span class="sxs-lookup"><span data-stu-id="d93c8-131">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="d93c8-132">옵션</span><span class="sxs-lookup"><span data-stu-id="d93c8-132">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="d93c8-133">Windows</span><span class="sxs-lookup"><span data-stu-id="d93c8-133">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="d93c8-134">이 도구를 사용하여 제거할 수 있는 모든 ASP.NET Core 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-134">Lists all the ASP.NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="d93c8-135">이 도구를 사용하여 제거할 수 있는 모든 .NET Core 런타임 및 호스팅 번들을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-135">Lists all the .NET Core runtime and hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="d93c8-136">이 도구를 사용하여 제거할 수 있는 모든 .NET Core 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-136">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="d93c8-137">이 도구를 사용하여 제거할 수 있는 모든 .NET Core SDK를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-137">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d93c8-138">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-138">Sets the verbosity level.</span></span> <span data-ttu-id="d93c8-139">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-139">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d93c8-140">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-140">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="d93c8-141">이 도구를 사용하여 제거할 수 있는 모든 x64 .NET Core SDK 및 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-141">Lists all x64 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="d93c8-142">이 도구를 사용하여 제거할 수 있는 모든 x86 .NET Core SDK 및 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-142">Lists all x86 .NET Core SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="d93c8-143">macOS</span><span class="sxs-lookup"><span data-stu-id="d93c8-143">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="d93c8-144">이 도구를 사용하여 제거할 수 있는 모든 .NET Core 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-144">Lists all .NET Core runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="d93c8-145">이 도구를 사용하여 제거할 수 있는 모든 .NET Core SDK를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-145">Lists all .NET Core SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d93c8-146">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-146">Sets the verbosity level.</span></span> <span data-ttu-id="d93c8-147">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-147">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d93c8-148">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-148">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="d93c8-149">예</span><span class="sxs-lookup"><span data-stu-id="d93c8-149">Examples</span></span>

* <span data-ttu-id="d93c8-150">이 도구를 사용하여 제거할 수 있는 모든 .NET Core SDK 및 런타임 나열:</span><span class="sxs-lookup"><span data-stu-id="d93c8-150">List all .NET Core SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="d93c8-151">모든 x64 .NET Core SDK 및 런타임 나열:</span><span class="sxs-lookup"><span data-stu-id="d93c8-151">List all x64 .NET Core SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="d93c8-152">모든 x86 .NET Core SDK 나열:</span><span class="sxs-lookup"><span data-stu-id="d93c8-152">List all x86 .NET Core SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="d93c8-153">2단계- 시험 실행 실시</span><span class="sxs-lookup"><span data-stu-id="d93c8-153">Step 2 - Do a dry run</span></span>

<span data-ttu-id="d93c8-154">`dotnet-core-uninstall dry-run` 및 `dotnet-core-uninstall whatif` 명령은 제거를 수행하지 않고 입력한 옵션에 따라 제거할 .NET Core SDK 및 런타임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-154">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET Core SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="d93c8-155">이 명령은 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-155">These commands are synonyms.</span></span>

<span data-ttu-id="d93c8-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="d93c8-156">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d93c8-157">개요</span><span class="sxs-lookup"><span data-stu-id="d93c8-157">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="d93c8-158">인수</span><span class="sxs-lookup"><span data-stu-id="d93c8-158">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="d93c8-159">제거할 지정된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-159">The specified version to uninstall.</span></span> <span data-ttu-id="d93c8-160">공백으로 구분하여 여러 버전을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-160">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="d93c8-161">지시 파일도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-161">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="d93c8-162">지시 파일은 명령줄에 모든 버전을 배치하는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-162">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="d93c8-163">지시 파일은 \*.rsp 확장명을 사용하는 텍스트 파일이며, 각 버전은 별도의 줄에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-163">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="d93c8-164">`VERSION` 인수에 대한 지시 파일을 지정하려면 지시 파일 이름 바로 뒤에 \@ 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-164">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="d93c8-165">옵션</span><span class="sxs-lookup"><span data-stu-id="d93c8-165">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="d93c8-166">Windows</span><span class="sxs-lookup"><span data-stu-id="d93c8-166">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="d93c8-167">모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-167">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="d93c8-168">지정된 버전보다 이전 버전의 .NET Core SDK 및 런타임만을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-168">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="d93c8-169">지정된 버전은 설치된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-169">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="d93c8-170">지정된 버전을 제외한 모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-170">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="d93c8-171">최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-171">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="d93c8-172">상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-172">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="d93c8-173">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-173">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="d93c8-174">미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-174">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="d93c8-175">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-175">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="d93c8-176">ASP.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-176">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="d93c8-177">.NET Core 런타임 및 호스팅 번들만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-177">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="d93c8-178">지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-178">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="d93c8-179">.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-179">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="d93c8-180">.NET Core SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-180">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d93c8-181">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-181">Sets the verbosity level.</span></span> <span data-ttu-id="d93c8-182">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-182">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d93c8-183">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-183">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="d93c8-184">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x64 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-184">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="d93c8-185">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x86 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-185">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="d93c8-186">**`--force`** 는 Visual Studio에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-186">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="d93c8-187">메모:</span><span class="sxs-lookup"><span data-stu-id="d93c8-187">Notes:</span></span>

1. <span data-ttu-id="d93c8-188">정확히 `--sdk`, `--runtime`, `--aspnet-runtime` 및 `--hosting-bundle` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-188">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="d93c8-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-189">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="d93c8-190">`--x64` 또는 `--x86`이 지정되지 않은 경우 x64와 x86 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-190">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="d93c8-191">macOS</span><span class="sxs-lookup"><span data-stu-id="d93c8-191">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="d93c8-192">모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-192">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="d93c8-193">지정된 버전보다 낮은 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-193">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="d93c8-194">지정된 버전은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-194">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="d93c8-195">지정된 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-195">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="d93c8-196">최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-196">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="d93c8-197">상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-197">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="d93c8-198">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-198">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="d93c8-199">미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-199">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="d93c8-200">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-200">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="d93c8-201">지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-201">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="d93c8-202">.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-202">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="d93c8-203">.NET Core SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-203">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d93c8-204">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-204">Sets the verbosity level.</span></span> <span data-ttu-id="d93c8-205">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-205">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d93c8-206">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-206">The default value is `normal`.</span></span>
  
* <span data-ttu-id="d93c8-207">**`--force`** 는 Visual Studio 또는 SDK에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-207">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="d93c8-208">메모:</span><span class="sxs-lookup"><span data-stu-id="d93c8-208">Notes:</span></span>

1. <span data-ttu-id="d93c8-209">정확히 `--sdk` 및 `--runtime` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-209">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="d93c8-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-210">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="d93c8-211">예</span><span class="sxs-lookup"><span data-stu-id="d93c8-211">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="d93c8-212">기본적으로 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET Core SDK 및 런타임은 `dotnet-core-uninstall dry-run` 출력에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-212">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="d93c8-213">다음 예에서는 컴퓨터의 상태에 따라 지정된 SDK 및 런타임 중 일부가 출력에 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-213">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="d93c8-214">모든 SDK 및 런타임을 포함하려면 이를 명시적으로 인수로 나열하거나 `--force` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-214">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="d93c8-215">상위 패치로 대체된 모든 .NET Core 런타임 제거를 시험 실행:</span><span class="sxs-lookup"><span data-stu-id="d93c8-215">Dry run of removing all .NET Core runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="d93c8-216">버전 `2.2.301` 이하의 모든 .NET Core SDK 제거를 시험 실행:</span><span class="sxs-lookup"><span data-stu-id="d93c8-216">Dry run of removing all .NET Core SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-core-sdks-and-runtimes"></a><span data-ttu-id="d93c8-217">3단계 - .NET Core SDK 및 런타임 제거</span><span class="sxs-lookup"><span data-stu-id="d93c8-217">Step 3 - Uninstall .NET Core SDKs and Runtimes</span></span>

<span data-ttu-id="d93c8-218">`dotnet-core-uninstall remove`는 옵션 컬렉션에서 지정한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-218">`dotnet-core-uninstall remove` uninstalls .NET Core SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="d93c8-219">이 도구는 버전 5.0 이상의 SDK 및 런타임 제거에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-219">The tool can't be used to uninstall SDKs and Runtimes with version 5.0 or above.</span></span>

<span data-ttu-id="d93c8-220">이 도구는 파괴적인 동작을 포함하므로 제거 명령을 실행하기 전에 시험 실행을 실시하는 것을 **적극** 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-220">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="d93c8-221">시험 실행에서 `remove` 명령을 사용하면 어떤 .NET Core SDK 및 런타임이 제거되는지 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-221">The dry run will show you what .NET Core SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="d93c8-222">어떤 SDK 및 런타임을 안전하게 제거할 수 있는지 알아보려면 [버전을 제거해야 하나요?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d93c8-222">Refer to [Should I remove a version?](../versions/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="d93c8-223">다음 사항에 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="d93c8-223">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="d93c8-224">이 도구는 컴퓨터의 `global.json` 파일에 필요한 .NET Core SDK 버전을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-224">This tool can uninstall versions of the .NET Core SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="d93c8-225">[.NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core) 페이지에서 .NET Core SDK를 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-225">You can reinstall .NET Core SDKs from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="d93c8-226">이 도구는 컴퓨터의 프레임워크 종속 애플리케이션에 필요한 .NET Core 런타임 버전을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-226">This tool can uninstall versions of the .NET Core runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="d93c8-227">[.NET Core 다운로드](https://dotnet.microsoft.com/download/dotnet-core) 페이지에서 .NET Core 런타임을 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-227">You can reinstall .NET Core runtimes from the [Download .NET Core](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="d93c8-228">이 도구는 Visual Studio에서 사용하는 .NET Core SDK 및 런타임 버전을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-228">This tool can uninstall versions of the .NET Core SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="d93c8-229">Visual Studio 설치를 중단하는 경우 Visual Studio 설치 관리자에서 "복구"를 실행하여 작업 상태로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-229">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="d93c8-230">기본적으로 모든 명령은 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET Core SDK 및 런타임을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-230">By default, all commands keep the .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="d93c8-231">이러한 SDK 및 런타임은 명시적으로 인수로 나열하거나 `--force` 옵션을 사용하여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-231">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="d93c8-232">이 도구에는 .NET Core SDK 및 런타임 제거를 위한 권한 상승이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-232">The tool requires elevation to uninstall .NET Core SDKs and runtimes.</span></span> <span data-ttu-id="d93c8-233">Windows의 관리자 명령 프롬프트에서 및 macOS의 `sudo`를 사용하여 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-233">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="d93c8-234">`dry-run` 및 `whatif` 명령에는 권한 상승이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-234">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="d93c8-235">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="d93c8-235">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="d93c8-236">개요</span><span class="sxs-lookup"><span data-stu-id="d93c8-236">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="d93c8-237">인수</span><span class="sxs-lookup"><span data-stu-id="d93c8-237">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="d93c8-238">제거할 지정된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-238">The specified version to uninstall.</span></span> <span data-ttu-id="d93c8-239">공백으로 구분하여 여러 버전을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-239">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="d93c8-240">지시 파일도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-240">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="d93c8-241">지시 파일은 명령줄에 모든 버전을 배치하는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-241">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="d93c8-242">지시 파일은 \*.rsp 확장명을 사용하는 텍스트 파일이며, 각 버전은 별도의 줄에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-242">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="d93c8-243">`VERSION` 인수에 대한 지시 파일을 지정하려면 지시 파일 이름 바로 뒤에 \@ 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-243">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="d93c8-244">옵션</span><span class="sxs-lookup"><span data-stu-id="d93c8-244">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="d93c8-245">Windows</span><span class="sxs-lookup"><span data-stu-id="d93c8-245">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="d93c8-246">모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-246">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="d93c8-247">지정된 버전보다 이전 버전의 .NET Core SDK 및 런타임만을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-247">Removes only the .NET Core SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="d93c8-248">지정된 버전은 설치된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-248">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="d93c8-249">지정된 버전을 제외한 모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-249">Removes all .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="d93c8-250">최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-250">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="d93c8-251">상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-251">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="d93c8-252">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-252">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="d93c8-253">미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-253">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="d93c8-254">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-254">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="d93c8-255">ASP.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-255">Removes ASP.NET Core runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="d93c8-256">.NET Core 런타임 및 호스팅 번들만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-256">Removes .NET Core runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="d93c8-257">지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-257">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="d93c8-258">.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-258">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="d93c8-259">.NET Core SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-259">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d93c8-260">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-260">Sets the verbosity level.</span></span> <span data-ttu-id="d93c8-261">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-261">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d93c8-262">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-262">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="d93c8-263">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x64 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-263">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="d93c8-264">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x86 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-264">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="d93c8-265">**`-y, --yes`** 예 또는 아니요를 확인하지 않고 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-265">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="d93c8-266">**`--force`** 는 Visual Studio에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-266">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="d93c8-267">메모:</span><span class="sxs-lookup"><span data-stu-id="d93c8-267">Notes:</span></span>

1. <span data-ttu-id="d93c8-268">정확히 `--sdk`, `--runtime`, `--aspnet-runtime` 및 `--hosting-bundle` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-268">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="d93c8-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-269">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="d93c8-270">`--x64` 또는 `--x86`이 지정되지 않은 경우 x64와 x86 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-270">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="d93c8-271">macOS</span><span class="sxs-lookup"><span data-stu-id="d93c8-271">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="d93c8-272">모든 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-272">Removes all .NET Core SDKs and runtimes.</span></span>

* **`--all-below <VERSION>`**

  <span data-ttu-id="d93c8-273">지정된 버전보다 낮은 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-273">Removes .NET Core SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="d93c8-274">지정된 버전은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-274">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>`**

  <span data-ttu-id="d93c8-275">지정된 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-275">Removes .NET Core SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="d93c8-276">최상위 버전을 제외한 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-276">Removes .NET Core SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="d93c8-277">상위 패치로 대체되는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-277">Removes .NET Core SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="d93c8-278">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-278">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="d93c8-279">미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-279">Removes .NET Core SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="d93c8-280">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-280">Removes .NET Core SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="d93c8-281">지정된 `major.minor` 버전과 일치하는 .NET Core SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-281">Removes .NET Core SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="d93c8-282">.NET Core 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-282">Removes .NET Core runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="d93c8-283">.NET Core SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-283">Removes .NET Core SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="d93c8-284">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-284">Sets the verbosity level.</span></span> <span data-ttu-id="d93c8-285">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-285">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="d93c8-286">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-286">The default value is `normal`.</span></span>

* <span data-ttu-id="d93c8-287">**`-y, --yes`** 예 또는 아니요를 확인하지 않고 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-287">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="d93c8-288">**`--force`** 는 Visual Studio 또는 SDK에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-288">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="d93c8-289">메모:</span><span class="sxs-lookup"><span data-stu-id="d93c8-289">Notes:</span></span>

1. <span data-ttu-id="d93c8-290">정확히 `--sdk` 및 `--runtime` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-290">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="d93c8-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-291">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="d93c8-292">예</span><span class="sxs-lookup"><span data-stu-id="d93c8-292">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="d93c8-293">기본적으로 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET Core SDK 및 런타임은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-293">By default, .NET Core SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="d93c8-294">다음 예에서는 컴퓨터의 상태에 따라 지정된 SDK 및 런타임 중 일부가 그대로 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-294">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="d93c8-295">모든 SDK 및 런타임을 제거하려면 이를 명시적으로 인수로 나열하거나 `--force` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-295">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="d93c8-296">`3.0.0-preview6-27804-01` 버전을 제외한 모든 .NET Core 런타임을 예 또는 아니요 확인 없이 제거:</span><span class="sxs-lookup"><span data-stu-id="d93c8-296">Remove all .NET Core runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="d93c8-297">모든 .NET Core 1.1 SDK를 예 또는 아니요 확인 없이 제거:</span><span class="sxs-lookup"><span data-stu-id="d93c8-297">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="d93c8-298">콘솔 출력이 없는 .NET Core 1.1.11 SDK 제거:</span><span class="sxs-lookup"><span data-stu-id="d93c8-298">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="d93c8-299">이 도구로 안전하게 제거할 수 있는 모든 .NET Core SDK 제거:</span><span class="sxs-lookup"><span data-stu-id="d93c8-299">Remove all .NET Core SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="d93c8-300">Visual Studio에서 필요할 수 있는 SDK를 포함하여 이 도구로 제거할 수 있는 모든 .NET Core SDK 제거(권장하지 않음):</span><span class="sxs-lookup"><span data-stu-id="d93c8-300">Remove all .NET Core SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="d93c8-301">지시 파일 `versions.rsp`에 지정된 모든 .NET Core SDK 제거</span><span class="sxs-lookup"><span data-stu-id="d93c8-301">Remove all .NET Core SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="d93c8-302">*versions.rsp*의 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-302">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="d93c8-303">4단계 - NuGet 대체 폴더 삭제(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="d93c8-303">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="d93c8-304">경우에 따라 더 이상 `NuGetFallbackFolder`가 필요하지 않아 이를 삭제하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-304">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="d93c8-305">이 폴더를 삭제하는 방법에 대한 자세한 내용은 [NuGetFallbackFolder 제거](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d93c8-305">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../versions/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="d93c8-306">도구 제거</span><span class="sxs-lookup"><span data-stu-id="d93c8-306">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="d93c8-307">Windows</span><span class="sxs-lookup"><span data-stu-id="d93c8-307">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="d93c8-308">**프로그램 추가/제거**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-308">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="d93c8-309">`Microsoft .NET Core SDK Uninstall Tool`을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-309">Search for `Microsoft .NET Core SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="d93c8-310">**제거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-310">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="d93c8-311">macOS</span><span class="sxs-lookup"><span data-stu-id="d93c8-311">macOS</span></span>](#tab/macos)

<span data-ttu-id="d93c8-312">설치된 디렉터리에서 다운로드한 *dotnet-core-uninstall.tar.gz* 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-312">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="d93c8-313">이 파일의 압축을 다른 디렉터리에 푼 경우 파일 내용 또한 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d93c8-313">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
