---
title: 제거 도구
description: .NET SDK 및 런타임의 제어된 정리를 사용하도록 설정하는 단계별 도구인 .NET 제거 도구에 대한 개요입니다.
author: sfoslund
ms.date: 01/28/2021
ms.openlocfilehash: a3819b11af94d4fec3ecb072ec3d5ddf6de706c9
ms.sourcegitcommit: 68c9d9d9a97aab3b59d388914004b5474cf1dbd7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "99216319"
---
# <a name="net-uninstall-tool"></a><span data-ttu-id="8b437-103">.NET 제거 도구</span><span class="sxs-lookup"><span data-stu-id="8b437-103">.NET Uninstall Tool</span></span>

<span data-ttu-id="8b437-104">[.NET 제거 도구](https://aka.ms/dotnet-core-uninstall-tool)(`dotnet-core-uninstall`)를 사용하면 시스템에서 .NET SDK 및 런타임을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-104">The [.NET Uninstall Tool](https://aka.ms/dotnet-core-uninstall-tool) (`dotnet-core-uninstall`) lets you remove .NET SDKs and Runtimes from a system.</span></span> <span data-ttu-id="8b437-105">제거하고자 하는 버전을 지정할 수 있는 옵션 컬렉션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-105">A collection of options is available to specify which versions you want to uninstall.</span></span>

<span data-ttu-id="8b437-106">도구는 Windows 및 macOS를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-106">The tool supports Windows and macOS.</span></span> <span data-ttu-id="8b437-107">Linux는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-107">Linux is currently not supported.</span></span>

<span data-ttu-id="8b437-108">Windows에서 도구는 다음 설치 관리자 중 하나를 사용하여 설치된 SDK 및 런타임만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-108">On Windows, the tool can only uninstall SDKs and Runtimes that were installed using one of the following installers:</span></span>

- <span data-ttu-id="8b437-109">.NET SDK 및 런타임 설치 관리자.</span><span class="sxs-lookup"><span data-stu-id="8b437-109">The .NET SDK and runtime installer.</span></span>
- <span data-ttu-id="8b437-110">Visual Studio 2019 버전 16.3 이전 버전의 Visual studio 설치 관리자.</span><span class="sxs-lookup"><span data-stu-id="8b437-110">The Visual Studio installer in versions earlier than Visual Studio 2019 version 16.3.</span></span>

<span data-ttu-id="8b437-111">macOS에서 도구는 */usr/local/share/dotnet* 폴더에 있는 SDK 및 런타임만 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-111">On macOS, the tool can only uninstall SDKs and runtimes located in the */usr/local/share/dotnet* folder.</span></span>

<span data-ttu-id="8b437-112">이러한 제한 사항으로 인해 도구가 머신에서 일부 .NET SDK 및 런타임을 제거하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-112">Because of these limitations, the tool may not be able to uninstall all of the .NET SDKs and runtimes on your machine.</span></span> <span data-ttu-id="8b437-113">`dotnet --info` 명령을 사용하여 이 도구에서 제거할 수 없는 SDK 및 런타임을 포함하여 설치된 모든 .NET SDK 및 런타임을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-113">You can use the `dotnet --info` command to find all of the .NET SDKs and runtimes installed, including those SDKs and runtimes that this tool can't remove.</span></span> <span data-ttu-id="8b437-114">`dotnet-core-uninstall list` 명령을 사용하면 도구를 사용하여 제거할 수 있는 SDK가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-114">The `dotnet-core-uninstall list` command displays which SDKs can be uninstalled with the tool.</span></span> <span data-ttu-id="8b437-115">버전 1.2 이상은 버전 5.0 이하의 SDK 및 런타임을 제거할 수 있으며 이전 버전의 도구는 3.1 이하를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-115">Versions 1.2 and later can uninstall SDKs and runtimes with version 5.0 or earlier, and previous versions of the tool can uninstall 3.1 and earlier.</span></span>

## <a name="install-the-tool"></a><span data-ttu-id="8b437-116">도구 설치</span><span class="sxs-lookup"><span data-stu-id="8b437-116">Install the tool</span></span>

<span data-ttu-id="8b437-117">.NET 제거 도구는 [도구의 릴리스 페이지](https://aka.ms/dotnet-core-uninstall-tool)에서 다운로드할 수 있으며 소스 코드는 [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub 리포지토리에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-117">You can download the .NET Uninstall Tool from [the tool's releases page](https://aka.ms/dotnet-core-uninstall-tool) and find the source code at the [dotnet/cli-lab](https://github.com/dotnet/cli-lab) GitHub repository.</span></span>

> [!NOTE]
> <span data-ttu-id="8b437-118">이 도구에서 .NET SDK 및 런타임을 제거하려면 권한 상승이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-118">The tool requires elevation to uninstall .NET SDKs and runtimes.</span></span> <span data-ttu-id="8b437-119">따라서 Windows의 경우 *C:\Program Files*, 또는 macOS의 경우 */usr/local/bin* 과 같이 쓰기 보호된 디렉터리에 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-119">Therefore, it should be installed in a write-protected directory such as *C:\Program Files* on Windows or */usr/local/bin* on macOS.</span></span> <span data-ttu-id="8b437-120">[dotnet 명령에 대한 상승된 액세스 권한](../tools/elevated-access.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b437-120">See also [Elevated access for dotnet commands](../tools/elevated-access.md).</span></span> <span data-ttu-id="8b437-121">자세한 내용은 [자세한 설치 지침](https://aka.ms/dotnet-core-uninstall-tool)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b437-121">For more information, see the [detailed installation instructions](https://aka.ms/dotnet-core-uninstall-tool).</span></span>

## <a name="run-the-tool"></a><span data-ttu-id="8b437-122">도구 실행</span><span class="sxs-lookup"><span data-stu-id="8b437-122">Run the tool</span></span>

<span data-ttu-id="8b437-123">다음 단계는 제거 도구 실행을 위한 권장 접근 방식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-123">The following steps show the recommended approach for running the uninstall tool:</span></span>

- [<span data-ttu-id="8b437-124">1단계 - 설치된 .NET SDK 및 런타임 표시</span><span class="sxs-lookup"><span data-stu-id="8b437-124">Step 1 - Display installed .NET SDKs and runtimes</span></span>](#step-1---display-installed-net-sdks-and-runtimes)
- [<span data-ttu-id="8b437-125">2단계- 시험 실행 실시</span><span class="sxs-lookup"><span data-stu-id="8b437-125">Step 2 - Do a dry run</span></span>](#step-2---do-a-dry-run)
- [<span data-ttu-id="8b437-126">3단계 - .NET SDK 및 런타임 제거</span><span class="sxs-lookup"><span data-stu-id="8b437-126">Step 3 - Uninstall .NET SDKs and Runtimes</span></span>](#step-3---uninstall-net-sdks-and-runtimes)
- [<span data-ttu-id="8b437-127">4단계 - NuGet 대체 폴더 삭제(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8b437-127">Step 4 - Delete the NuGet fallback folder (optional)</span></span>](#step-4---delete-the-nuget-fallback-folder-optional)

### <a name="step-1---display-installed-net-sdks-and-runtimes"></a><span data-ttu-id="8b437-128">1단계 - 설치된 .NET SDK 및 런타임 표시</span><span class="sxs-lookup"><span data-stu-id="8b437-128">Step 1 - Display installed .NET SDKs and runtimes</span></span>

<span data-ttu-id="8b437-129">`dotnet-core-uninstall list` 명령은 이 도구를 사용하여 제거할 수 있는 설치된 .NET SDK 및 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-129">The `dotnet-core-uninstall list` command lists the installed .NET SDKs and runtimes that can be removed with this tool.</span></span> <span data-ttu-id="8b437-130">일부 SDK 및 런타임은 Visual Studio에 필요할 수 있으며, 제거를 권장하지 않는 이유를 포함하여 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-130">Some SDKs and runtimes may be required by Visual Studio and they're displayed with a note of why it isn't recommended to uninstall them.</span></span>

> [!NOTE]
> <span data-ttu-id="8b437-131">대부분의 경우 `dotnet-core-uninstall list` 명령의 출력이 `dotnet --info`의 출력에서 설치된 버전 목록과 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-131">The output of the `dotnet-core-uninstall list` command will not match the list of installed versions in the output of `dotnet --info` in most cases.</span></span> <span data-ttu-id="8b437-132">특히 이 도구는 zip 파일로 설치되거나 Visual Studio에서 관리하는 버전을 표시하지 않습니다(Visual Studio 2019 16.3 이상에 설치된 모든 버전).</span><span class="sxs-lookup"><span data-stu-id="8b437-132">Specifically, this tool will not display versions installed by zip files or managed by Visual Studio (any version installed with Visual Studio 2019 16.3 or later).</span></span> <span data-ttu-id="8b437-133">Visual Studio에서 버전을 관리하는지 확인하는 한 가지 방법은 Visual Studio 관리되는 버전이 표시 이름에 표시되는 `Add or Remove Programs`에서 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-133">One way to check if a version is managed by Visual Studio is to view it in `Add or Remove Programs`, where Visual Studio managed versions are marked as such in their display names.</span></span>

<span data-ttu-id="8b437-134">**dotnet-core-uninstall list**</span><span class="sxs-lookup"><span data-stu-id="8b437-134">**dotnet-core-uninstall list**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="8b437-135">개요</span><span class="sxs-lookup"><span data-stu-id="8b437-135">Synopsis</span></span>

```console
dotnet-core-uninstall list [options]
```

#### <a name="options"></a><span data-ttu-id="8b437-136">옵션</span><span class="sxs-lookup"><span data-stu-id="8b437-136">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="8b437-137">Windows</span><span class="sxs-lookup"><span data-stu-id="8b437-137">Windows</span></span>](#tab/windows)

* **`--aspnet-runtime`**

  <span data-ttu-id="8b437-138">이 도구를 사용하여 제거할 수 있는 모든 ASP.NET 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-138">Lists all the ASP.NET Runtimes that can be uninstalled with this tool.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="8b437-139">이 도구를 사용하여 제거할 수 있는 모든 .NET 호스팅 번들을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-139">Lists all the .NET hosting bundles that can be uninstalled with this tool.</span></span>

* **`--runtime`**

  <span data-ttu-id="8b437-140">이 도구를 사용하여 제거할 수 있는 모든 .NET 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-140">Lists all .NET Runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="8b437-141">이 도구를 사용하여 제거할 수 있는 모든 .NET SDK를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-141">Lists all .NET SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="8b437-142">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-142">Sets the verbosity level.</span></span> <span data-ttu-id="8b437-143">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-143">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8b437-144">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-144">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="8b437-145">이 도구를 사용하여 제거할 수 있는 모든 x64 .NET SDK 및 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-145">Lists all x64 .NET SDKs and runtimes that can be uninstalled with this tool.</span></span>

* **`--x86`**

  <span data-ttu-id="8b437-146">이 도구를 사용하여 제거할 수 있는 모든 x86 .NET SDK 및 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-146">Lists all x86 .NET SDKs and runtimes that can be uninstalled with this tool.</span></span>

## <a name="macos"></a>[<span data-ttu-id="8b437-147">macOS</span><span class="sxs-lookup"><span data-stu-id="8b437-147">macOS</span></span>](#tab/macos)

* **`--runtime`**

  <span data-ttu-id="8b437-148">이 도구를 사용하여 제거할 수 있는 모든 .NET 런타임을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-148">Lists all .NET Runtimes that can be uninstalled with this tool.</span></span>

* **`--sdk`**

  <span data-ttu-id="8b437-149">이 도구를 사용하여 제거할 수 있는 모든 .NET SDK를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-149">Lists all .NET SDKs that can be uninstalled with this tool.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="8b437-150">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-150">Sets the verbosity level.</span></span> <span data-ttu-id="8b437-151">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-151">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8b437-152">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-152">The default value is `normal`.</span></span>
  
---

#### <a name="examples"></a><span data-ttu-id="8b437-153">예</span><span class="sxs-lookup"><span data-stu-id="8b437-153">Examples</span></span>

* <span data-ttu-id="8b437-154">이 도구를 사용하여 제거할 수 있는 모든 .NET SDK 및 런타임 나열:</span><span class="sxs-lookup"><span data-stu-id="8b437-154">List all .NET SDKs and runtimes that can be removed with this tool:</span></span>

  ```console
  dotnet-core-uninstall list
  ```

* <span data-ttu-id="8b437-155">모든 x64 .NET SDK 및 런타임 나열:</span><span class="sxs-lookup"><span data-stu-id="8b437-155">List all x64 .NET SDKs and runtimes:</span></span>

  ```console
  dotnet-core-uninstall list --x64
  ```

* <span data-ttu-id="8b437-156">모든 x86 .NET SDK 나열:</span><span class="sxs-lookup"><span data-stu-id="8b437-156">List all x86 .NET SDKs:</span></span>

  ```console
  dotnet-core-uninstall list --sdk --x86
  ```

### <a name="step-2---do-a-dry-run"></a><span data-ttu-id="8b437-157">2단계- 시험 실행 실시</span><span class="sxs-lookup"><span data-stu-id="8b437-157">Step 2 - Do a dry run</span></span>

<span data-ttu-id="8b437-158">`dotnet-core-uninstall dry-run` 및 `dotnet-core-uninstall whatif` 명령은 제거를 수행하지 않고 제공된 옵션에 따라 제거할 .NET SDK 및 런타임을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-158">The `dotnet-core-uninstall dry-run` and `dotnet-core-uninstall whatif` commands display the .NET SDKs and runtimes that will be removed based on the options provided without performing the uninstall.</span></span> <span data-ttu-id="8b437-159">이 명령은 동의어입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-159">These commands are synonyms.</span></span>

<span data-ttu-id="8b437-160">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span><span class="sxs-lookup"><span data-stu-id="8b437-160">**dotnet-core-uninstall dry-run and dotnet-core-uninstall whatif**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="8b437-161">개요</span><span class="sxs-lookup"><span data-stu-id="8b437-161">Synopsis</span></span>

```console
dotnet-core-uninstall dry-run [options] [<VERSION>...]

dotnet-core-uninstall whatif [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="8b437-162">인수</span><span class="sxs-lookup"><span data-stu-id="8b437-162">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="8b437-163">제거할 지정된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-163">The specified version to uninstall.</span></span> <span data-ttu-id="8b437-164">공백으로 구분하여 여러 버전을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-164">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="8b437-165">지시 파일도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-165">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="8b437-166">지시 파일은 명령줄에 모든 버전을 배치하는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-166">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="8b437-167">지시 파일은 \*.rsp 확장명을 사용하는 텍스트 파일이며, 각 버전은 별도의 줄에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-167">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="8b437-168">`VERSION` 인수에 대한 지시 파일을 지정하려면 지시 파일 이름 바로 뒤에 \@ 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-168">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="8b437-169">옵션</span><span class="sxs-lookup"><span data-stu-id="8b437-169">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="8b437-170">Windows</span><span class="sxs-lookup"><span data-stu-id="8b437-170">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="8b437-171">모든 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-171">Removes all .NET SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="8b437-172">지정된 버전보다 이전 버전의 .NET SDK 및 런타임만을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-172">Removes only the .NET SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="8b437-173">지정된 버전은 설치된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-173">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="8b437-174">지정된 버전을 제외한 모든 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-174">Removes all .NET SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="8b437-175">최상위 버전을 제외한 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-175">Removes .NET SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="8b437-176">상위 패치로 대체되는 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-176">Removes .NET SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="8b437-177">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-177">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="8b437-178">미리 보기로 표시된 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-178">Removes .NET SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="8b437-179">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-179">Removes .NET SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="8b437-180">ASP.NET 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-180">Removes ASP.NET Runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="8b437-181">.NET 런타임 및 호스팅 번들만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-181">Removes .NET Runtime and hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="8b437-182">지정된 `major.minor` 버전과 일치하는 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-182">Removes .NET SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="8b437-183">.NET 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-183">Removes .NET Runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="8b437-184">.NET SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-184">Removes .NET SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="8b437-185">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-185">Sets the verbosity level.</span></span> <span data-ttu-id="8b437-186">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-186">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8b437-187">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-187">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="8b437-188">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x64 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-188">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="8b437-189">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x86 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-189">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="8b437-190">**`--force`** 는 Visual Studio에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-190">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="8b437-191">메모:</span><span class="sxs-lookup"><span data-stu-id="8b437-191">Notes:</span></span>

1. <span data-ttu-id="8b437-192">정확히 `--sdk`, `--runtime`, `--aspnet-runtime` 및 `--hosting-bundle` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-192">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="8b437-193">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-193">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="8b437-194">`--x64` 또는 `--x86`이 지정되지 않은 경우 x64와 x86 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-194">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="8b437-195">macOS</span><span class="sxs-lookup"><span data-stu-id="8b437-195">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="8b437-196">모든 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-196">Removes all .NET SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="8b437-197">지정된 버전보다 낮은 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-197">Removes .NET SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="8b437-198">지정된 버전은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-198">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="8b437-199">지정된 버전을 제외한 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-199">Removes .NET SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="8b437-200">최상위 버전을 제외한 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-200">Removes .NET SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="8b437-201">상위 패치로 대체되는 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-201">Removes .NET SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="8b437-202">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-202">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="8b437-203">미리 보기로 표시된 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-203">Removes .NET SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="8b437-204">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-204">Removes .NET SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="8b437-205">지정된 `major.minor` 버전과 일치하는 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-205">Removes .NET SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="8b437-206">.NET 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-206">Removes .NET Runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="8b437-207">.NET SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-207">Removes .NET SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="8b437-208">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-208">Sets the verbosity level.</span></span> <span data-ttu-id="8b437-209">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-209">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8b437-210">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-210">The default value is `normal`.</span></span>
  
* <span data-ttu-id="8b437-211">**`--force`** 는 Visual Studio 또는 SDK에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-211">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="8b437-212">메모:</span><span class="sxs-lookup"><span data-stu-id="8b437-212">Notes:</span></span>

1. <span data-ttu-id="8b437-213">정확히 `--sdk` 및 `--runtime` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-213">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="8b437-214">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-214">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="8b437-215">예</span><span class="sxs-lookup"><span data-stu-id="8b437-215">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="8b437-216">기본적으로 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET SDK 및 런타임은 `dotnet-core-uninstall dry-run` 출력에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-216">By default, .NET SDKs and runtimes that may be required by Visual Studio or other SDKs are not included in `dotnet-core-uninstall dry-run` output.</span></span> <span data-ttu-id="8b437-217">다음 예에서는 컴퓨터의 상태에 따라 지정된 SDK 및 런타임 중 일부가 출력에 포함되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-217">In the following examples, some of the specified SDKs and runtimes may not be included in the output, depending on the state of the machine.</span></span> <span data-ttu-id="8b437-218">모든 SDK 및 런타임을 포함하려면 이를 명시적으로 인수로 나열하거나 `--force` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-218">To include all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="8b437-219">상위 패치로 대체된 모든 .NET 런타임 제거를 시험 실행:</span><span class="sxs-lookup"><span data-stu-id="8b437-219">Dry run of removing all .NET Runtimes that have been superseded by higher patches:</span></span>

  ```console
  dotnet-core-uninstall dry-run --all-lower-patches --runtime
  ```

* <span data-ttu-id="8b437-220">`2.2.301` 버전 이하의 모든 .NET SDK 제거를 시험 실행:</span><span class="sxs-lookup"><span data-stu-id="8b437-220">Dry run of removing all .NET SDKs below the version `2.2.301`:</span></span>

  ```console
  dotnet-core-uninstall whatif --all-below 2.2.301 --sdk
  ```

### <a name="step-3---uninstall-net-sdks-and-runtimes"></a><span data-ttu-id="8b437-221">3단계 - .NET SDK 및 런타임 제거</span><span class="sxs-lookup"><span data-stu-id="8b437-221">Step 3 - Uninstall .NET SDKs and Runtimes</span></span>

<span data-ttu-id="8b437-222">`dotnet-core-uninstall remove`는 옵션 컬렉션에서 지정한 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-222">`dotnet-core-uninstall remove` uninstalls .NET SDKs and Runtimes that are specified by a collection of options.</span></span> <span data-ttu-id="8b437-223">버전 1.2 이상은 버전 5.0 이하의 SDK 및 런타임을 제거할 수 있으며 이전 버전의 도구는 3.1 이하를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-223">Versions 1.2 and later can uninstall SDKs and runtimes with version 5.0 or earlier, and previous versions of the tool can uninstall 3.1 and earlier.</span></span>

<span data-ttu-id="8b437-224">이 도구는 파괴적인 동작을 포함하므로 제거 명령을 실행하기 전에 시험 실행을 실시하는 것을 **적극** 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-224">Since this tool has a destructive behavior, it's **highly** recommended that you do a dry run before running the remove command.</span></span> <span data-ttu-id="8b437-225">시험 실행에서는 `remove` 명령을 사용하는 경우 제거되는 .NET SDK 및 런타임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-225">The dry run will show you what .NET SDKs and runtimes will be removed when you use the `remove` command.</span></span> <span data-ttu-id="8b437-226">어떤 SDK 및 런타임을 안전하게 제거할 수 있는지 알아보려면 [버전을 제거해야 하나요?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b437-226">Refer to [Should I remove a version?](../install/remove-runtime-sdk-versions.md#should-i-remove-a-version) to learn which SDKs and runtimes are safe to remove.</span></span>

> [!CAUTION]
> <span data-ttu-id="8b437-227">다음 사항에 주의하세요.</span><span class="sxs-lookup"><span data-stu-id="8b437-227">Keep in mind the following caveats:</span></span>
>
>- <span data-ttu-id="8b437-228">이 도구는 머신의 `global.json` 파일에 필요한 .NET SDK 버전을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-228">This tool can uninstall versions of the .NET SDK that are required by `global.json` files on your machine.</span></span> <span data-ttu-id="8b437-229">.NET SDK는 [.NET 다운로드](https://dotnet.microsoft.com/download/dotnet-core) 페이지에서 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-229">You can reinstall .NET SDKs from the [Download .NET](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="8b437-230">이 도구는 머신의 프레임워크 종속 애플리케이션에 필요한 .NET 런타임 버전을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-230">This tool can uninstall versions of the .NET Runtime that are required by framework dependent applications on your machine.</span></span> <span data-ttu-id="8b437-231">.NET 런타임은 [.NET 다운로드](https://dotnet.microsoft.com/download/dotnet-core) 페이지에서 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-231">You can reinstall .NET Runtimes from the [Download .NET](https://dotnet.microsoft.com/download/dotnet-core) page.</span></span>
>- <span data-ttu-id="8b437-232">이 도구는 Visual Studio에서 사용하는 .NET SDK 및 런타임 버전을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-232">This tool can uninstall versions of the .NET SDK and runtime that Visual Studio relies on.</span></span> <span data-ttu-id="8b437-233">Visual Studio 설치를 중단하는 경우 Visual Studio 설치 관리자에서 "복구"를 실행하여 작업 상태로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-233">If you break your Visual Studio installation, run "Repair" in the Visual Studio installer to get back to a working state.</span></span>

<span data-ttu-id="8b437-234">기본적으로 모든 명령은 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET SDK 및 런타임을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-234">By default, all commands keep the .NET SDKs and runtimes that may be required by Visual Studio or other SDKs.</span></span> <span data-ttu-id="8b437-235">이러한 SDK 및 런타임은 명시적으로 인수로 나열하거나 `--force` 옵션을 사용하여 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-235">These SDKs and runtimes can be uninstalled by listing them explicitly as arguments or by using the `--force` option.</span></span>

<span data-ttu-id="8b437-236">이 도구에서 .NET SDK 및 런타임을 제거하려면 권한 상승이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-236">The tool requires elevation to uninstall .NET SDKs and runtimes.</span></span> <span data-ttu-id="8b437-237">Windows의 관리자 명령 프롬프트에서 및 macOS의 `sudo`를 사용하여 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-237">Run the tool in an Administrator command prompt on Windows and with `sudo` on macOS.</span></span> <span data-ttu-id="8b437-238">`dry-run` 및 `whatif` 명령에는 권한 상승이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-238">The `dry-run` and `whatif` commands don't require elevation.</span></span>

<span data-ttu-id="8b437-239">**dotnet-core-uninstall remove**</span><span class="sxs-lookup"><span data-stu-id="8b437-239">**dotnet-core-uninstall remove**</span></span>

#### <a name="synopsis"></a><span data-ttu-id="8b437-240">개요</span><span class="sxs-lookup"><span data-stu-id="8b437-240">Synopsis</span></span>

```console
dotnet-core-uninstall remove [options] [<VERSION>...]
```

#### <a name="arguments"></a><span data-ttu-id="8b437-241">인수</span><span class="sxs-lookup"><span data-stu-id="8b437-241">Arguments</span></span>

* **`VERSION`**

  <span data-ttu-id="8b437-242">제거할 지정된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-242">The specified version to uninstall.</span></span> <span data-ttu-id="8b437-243">공백으로 구분하여 여러 버전을 나열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-243">You may list several versions one after the other, separated by spaces.</span></span> <span data-ttu-id="8b437-244">지시 파일도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-244">Response files are also supported.</span></span>

  > [!TIP]
  > <span data-ttu-id="8b437-245">지시 파일은 명령줄에 모든 버전을 배치하는 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-245">Response files are an alternative to placing all the versions on the command line.</span></span>
  > <span data-ttu-id="8b437-246">지시 파일은 \*.rsp 확장명을 사용하는 텍스트 파일이며, 각 버전은 별도의 줄에 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-246">They're text files, typically with a \*.rsp extension, and each version is listed on a separate line.</span></span>
  > <span data-ttu-id="8b437-247">`VERSION` 인수에 대한 지시 파일을 지정하려면 지시 파일 이름 바로 뒤에 \@ 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-247">To specify a response file for the `VERSION` argument, use the \@ character immediately followed by the response file name.</span></span>

#### <a name="options"></a><span data-ttu-id="8b437-248">옵션</span><span class="sxs-lookup"><span data-stu-id="8b437-248">Options</span></span>

## <a name="windows"></a>[<span data-ttu-id="8b437-249">Windows</span><span class="sxs-lookup"><span data-stu-id="8b437-249">Windows</span></span>](#tab/windows)

* **`--all`**

  <span data-ttu-id="8b437-250">모든 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-250">Removes all .NET SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="8b437-251">지정된 버전보다 이전 버전의 .NET SDK 및 런타임만을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-251">Removes only the .NET SDKs and runtimes with a version smaller than the specified version.</span></span> <span data-ttu-id="8b437-252">지정된 버전은 설치된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-252">The specified version remains installed.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="8b437-253">지정된 버전을 제외한 모든 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-253">Removes all .NET SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="8b437-254">최상위 버전을 제외한 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-254">Removes .NET SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="8b437-255">상위 패치로 대체되는 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-255">Removes .NET SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="8b437-256">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-256">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="8b437-257">미리 보기로 표시된 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-257">Removes .NET SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="8b437-258">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-258">Removes .NET SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--aspnet-runtime`**

  <span data-ttu-id="8b437-259">ASP.NET 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-259">Removes ASP.NET Runtimes only.</span></span>

* **`--hosting-bundle`**

  <span data-ttu-id="8b437-260">.NET 호스팅 번들만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-260">Removes .NET hosting bundles only.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="8b437-261">지정된 `major.minor` 버전과 일치하는 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-261">Removes .NET SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="8b437-262">.NET 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-262">Removes .NET Runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="8b437-263">.NET SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-263">Removes .NET SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="8b437-264">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-264">Sets the verbosity level.</span></span> <span data-ttu-id="8b437-265">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-265">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8b437-266">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-266">The default value is `normal`.</span></span>

* **`--x64`**

  <span data-ttu-id="8b437-267">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x64 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-267">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x64 SDKs or runtimes.</span></span>

* **`--x86`**

  <span data-ttu-id="8b437-268">`--sdk`, `--runtime` 및 `--aspnet-runtime`을 사용하여 x86 SDK 또는 런타임을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-268">Must be used with `--sdk`, `--runtime`, and `--aspnet-runtime` to remove x86 SDKs or runtimes.</span></span>

* <span data-ttu-id="8b437-269">**`-y, --yes`** 예 또는 아니요를 확인하지 않고 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-269">**`-y, --yes`** Executes the command without requiring a yes or no confirmation.</span></span>

* <span data-ttu-id="8b437-270">**`--force`** 는 Visual Studio에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-270">**`--force`** Forces removal of versions that might be used by Visual Studio.</span></span>

<span data-ttu-id="8b437-271">메모:</span><span class="sxs-lookup"><span data-stu-id="8b437-271">Notes:</span></span>

1. <span data-ttu-id="8b437-272">정확히 `--sdk`, `--runtime`, `--aspnet-runtime` 및 `--hosting-bundle` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-272">Exactly one of `--sdk`, `--runtime`, `--aspnet-runtime`, and `--hosting-bundle` is required.</span></span>
2. <span data-ttu-id="8b437-273">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-273">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>
3. <span data-ttu-id="8b437-274">`--x64` 또는 `--x86`이 지정되지 않은 경우 x64와 x86 모두 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-274">If `--x64` or `--x86` aren't specified, then both x64 and x86 will be removed.</span></span>

## <a name="macos"></a>[<span data-ttu-id="8b437-275">macOS</span><span class="sxs-lookup"><span data-stu-id="8b437-275">macOS</span></span>](#tab/macos)

* **`--all`**

  <span data-ttu-id="8b437-276">모든 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-276">Removes all .NET SDKs and runtimes.</span></span>

* **`--all-below <VERSION>[ <VERSION>...]`**

  <span data-ttu-id="8b437-277">지정된 버전보다 낮은 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-277">Removes .NET SDKs and runtimes below the specified version.</span></span> <span data-ttu-id="8b437-278">지정된 버전은 그대로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-278">The specified version will remain.</span></span>

* **`--all-but <VERSIONS>[ <VERSION>...]`**

  <span data-ttu-id="8b437-279">지정된 버전을 제외한 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-279">Removes .NET SDKs and runtimes, except those versions specified.</span></span>

* **`--all-but-latest`**

  <span data-ttu-id="8b437-280">최상위 버전을 제외한 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-280">Removes .NET SDKs and runtimes, except the one highest version.</span></span>

* **`--all-lower-patches`**

  <span data-ttu-id="8b437-281">상위 패치로 대체되는 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-281">Removes .NET SDKs and runtimes superseded by higher patches.</span></span> <span data-ttu-id="8b437-282">이 옵션은 global.json을 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-282">This option protects global.json.</span></span>

* **`--all-previews`**

  <span data-ttu-id="8b437-283">미리 보기로 표시된 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-283">Removes .NET SDKs and runtimes marked as previews.</span></span>

* **`--all-previews-but-latest`**

  <span data-ttu-id="8b437-284">최상위 미리 보기를 제외하고 미리 보기로 표시된 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-284">Removes .NET SDKs and runtimes marked as previews except the one highest preview.</span></span>

* **`--major-minor <MAJOR_MINOR>`**

  <span data-ttu-id="8b437-285">지정된 `major.minor` 버전과 일치하는 .NET SDK 및 런타임을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-285">Removes .NET SDKs and runtimes that match the specified `major.minor` version.</span></span>

* **`--runtime`**

  <span data-ttu-id="8b437-286">.NET 런타임만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-286">Removes .NET Runtimes only.</span></span>

* **`--sdk`**

  <span data-ttu-id="8b437-287">.NET SDK만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-287">Removes .NET SDKs only.</span></span>

* **`-v, --verbosity <LEVEL>`**

  <span data-ttu-id="8b437-288">자세한 표시 수준을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-288">Sets the verbosity level.</span></span> <span data-ttu-id="8b437-289">허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-289">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span> <span data-ttu-id="8b437-290">기본값은 `normal`입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-290">The default value is `normal`.</span></span>

* <span data-ttu-id="8b437-291">**`-y, --yes`** 예 또는 아니요를 확인하지 않고 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-291">**`-y, --yes`** Executes the command without requiring Y/N confirmation.</span></span>
  
* <span data-ttu-id="8b437-292">**`--force`** 는 Visual Studio 또는 SDK에서 사용할 수 있는 버전을 강제로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-292">**`--force`** Forces removal of versions that might be used by Visual Studio or SDKs.</span></span>

<span data-ttu-id="8b437-293">메모:</span><span class="sxs-lookup"><span data-stu-id="8b437-293">Notes:</span></span>

1. <span data-ttu-id="8b437-294">정확히 `--sdk` 및 `--runtime` 중 하나가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-294">Exactly one of `--sdk` and `--runtime` is required.</span></span>
2. <span data-ttu-id="8b437-295">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor` 및 `[<VERSION>...]`은 배타적입니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-295">`--all`, `--all-below`, `--all-but`, `--all-but-latest`, `--all-lower-patches`, `--all-previews`, `--all-previews-but-latest`, `--major-minor`, and `[<VERSION>...]` are exclusive.</span></span>

---

#### <a name="examples"></a><span data-ttu-id="8b437-296">예</span><span class="sxs-lookup"><span data-stu-id="8b437-296">Examples</span></span>

> [!NOTE]
> <span data-ttu-id="8b437-297">기본적으로 Visual Studio 또는 기타 SDK에서 필요할 수 있는 .NET SDK 및 런타임은 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-297">By default, .NET SDKs and runtimes that may be required by Visual Studio or other SDKs are kept.</span></span> <span data-ttu-id="8b437-298">다음 예에서는 컴퓨터의 상태에 따라 지정된 SDK 및 런타임 중 일부가 그대로 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-298">In the following examples, some of the specified SDKs and runtimes may remain, depending on the state of the machine.</span></span> <span data-ttu-id="8b437-299">모든 SDK 및 런타임을 제거하려면 이를 명시적으로 인수로 나열하거나 `--force` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-299">To remove all SDKs and runtimes, list them explicitly as arguments or use the `--force` option.</span></span>

* <span data-ttu-id="8b437-300">예/아니요를 확인하지 않고 `3.0.0-preview6-27804-01` 버전을 제외한 모든 .NET 런타임 제거:</span><span class="sxs-lookup"><span data-stu-id="8b437-300">Remove all .NET Runtimes except the version `3.0.0-preview6-27804-01` without requiring Y/N confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --all-but 3.0.0-preview6-27804-01 --runtime --yes
  ```

* <span data-ttu-id="8b437-301">모든 .NET Core 1.1 SDK를 예 또는 아니요 확인 없이 제거:</span><span class="sxs-lookup"><span data-stu-id="8b437-301">Remove all .NET Core 1.1 SDKs without requiring Y/n confirmation:</span></span>

  ```console
  dotnet-core-uninstall remove --sdk --major-minor 1.1 -y
  ```

* <span data-ttu-id="8b437-302">콘솔 출력이 없는 .NET Core 1.1.11 SDK 제거:</span><span class="sxs-lookup"><span data-stu-id="8b437-302">Remove the .NET Core 1.1.11 SDK with no console output:</span></span>

  ```console
  dotnet-core-uninstall remove 1.1.11 --sdk --yes --verbosity q
  ```

* <span data-ttu-id="8b437-303">이 도구로 안전하게 제거할 수 있는 모든 .NET SDK 제거:</span><span class="sxs-lookup"><span data-stu-id="8b437-303">Remove all .NET SDKs that can safely be removed by this tool:</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk
  ```

* <span data-ttu-id="8b437-304">Visual Studio에서 필요할 수 있는 SDK를 포함하여 이 도구로 제거할 수 있는 모든 .NET SDK 제거(권장하지 않음):</span><span class="sxs-lookup"><span data-stu-id="8b437-304">Remove all .NET SDKs that can be removed by this tool, including those SDKs that may be required by Visual Studio (not recommended):</span></span>

  ```console
  dotnet-core-uninstall remove --all --sdk --force
  ```

* <span data-ttu-id="8b437-305">지시 파일 `versions.rsp`에 지정된 모든 .NET SDK 제거</span><span class="sxs-lookup"><span data-stu-id="8b437-305">Remove all .NET SDKs that are specified in the response file `versions.rsp`</span></span>

  ```console
  dotnet-core-uninstall remove --sdk @versions.rsp
  ```

  <span data-ttu-id="8b437-306">*versions.rsp* 의 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-306">The content of *versions.rsp* is as follows:</span></span>
  
  ```text
  2.2.300
  2.1.700
  ```

### <a name="step-4---delete-the-nuget-fallback-folder-optional"></a><span data-ttu-id="8b437-307">4단계 - NuGet 대체 폴더 삭제(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8b437-307">Step 4 - Delete the NuGet fallback folder (optional)</span></span>

<span data-ttu-id="8b437-308">경우에 따라 더 이상 `NuGetFallbackFolder`가 필요하지 않아 이를 삭제하고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-308">In some cases, you no longer need the `NuGetFallbackFolder` and may wish to delete it.</span></span> <span data-ttu-id="8b437-309">이 폴더를 삭제하는 방법에 대한 자세한 내용은 [NuGetFallbackFolder 제거](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8b437-309">For more information about deleting this folder, see [Remove the NuGetFallbackFolder](../install/remove-runtime-sdk-versions.md#remove-the-nuget-fallback-folder).</span></span>

## <a name="uninstall-the-tool"></a><span data-ttu-id="8b437-310">도구 제거</span><span class="sxs-lookup"><span data-stu-id="8b437-310">Uninstall the tool</span></span>

## <a name="windows"></a>[<span data-ttu-id="8b437-311">Windows</span><span class="sxs-lookup"><span data-stu-id="8b437-311">Windows</span></span>](#tab/windows)

1. <span data-ttu-id="8b437-312">**프로그램 추가/제거** 를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-312">Open **Add or Remove Programs**.</span></span>
2. <span data-ttu-id="8b437-313">`Microsoft .NET SDK Uninstall Tool`을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-313">Search for `Microsoft .NET SDK Uninstall Tool`.</span></span>
3. <span data-ttu-id="8b437-314">**제거** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-314">Select **Uninstall**.</span></span>

## <a name="macos"></a>[<span data-ttu-id="8b437-315">macOS</span><span class="sxs-lookup"><span data-stu-id="8b437-315">macOS</span></span>](#tab/macos)

<span data-ttu-id="8b437-316">설치된 디렉터리에서 다운로드한 *dotnet-core-uninstall.tar.gz* 파일을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-316">Delete the downloaded *dotnet-core-uninstall.tar.gz* file from the directory where it was installed.</span></span> <span data-ttu-id="8b437-317">이 파일의 압축을 다른 디렉터리에 푼 경우 파일 내용 또한 삭제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b437-317">If you unzipped the contents of this file into another directory, be sure to delete that content as well.</span></span>

---
