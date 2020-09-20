---
title: Linux 덤프 디버그
description: 이 문서에서는 Linux 환경에서 덤프를 수집 및 분석하는 방법을 알아봅니다.
ms.date: 08/27/2020
ms.openlocfilehash: d62295e165f56e32ef73ab628ca9ebd77a4435d1
ms.sourcegitcommit: 43d5aca3fda42bad8843f6c4e72f6bd52daa55f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/09/2020
ms.locfileid: "89598304"
---
# <a name="debug-linux-dumps"></a><span data-ttu-id="7b613-103">Linux 덤프 디버그</span><span class="sxs-lookup"><span data-stu-id="7b613-103">Debug Linux dumps</span></span>

<span data-ttu-id="7b613-104">**이 문서의 적용 대상:** ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="7b613-104">**This article applies to: ✔️** .NET Core 3.0 SDK and later versions</span></span>

## <a name="collect-dumps-on-linux"></a><span data-ttu-id="7b613-105">Linux에서 덤프 수집</span><span class="sxs-lookup"><span data-stu-id="7b613-105">Collect dumps on Linux</span></span>

<span data-ttu-id="7b613-106">Linux에서 덤프를 수집하는 두 가지 권장 방법은 [`dotnet-dump`](dotnet-dump.md) 또는 [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-106">The two recommended ways of collecting dumps on Linux are the [`dotnet-dump`](dotnet-dump.md) or [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) tools.</span></span>

### <a name="managed-dumps-with-dotnet-dump"></a><span data-ttu-id="7b613-107">`dotnet-dump`를 사용한 관리형 덤프</span><span class="sxs-lookup"><span data-stu-id="7b613-107">Managed dumps with `dotnet-dump`</span></span>

<span data-ttu-id="7b613-108">[`dotnet-dump`](dotnet-dump.md) 도구는 간단하게 사용할 수 있으며 네이티브 디버거에 종속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-108">The [`dotnet-dump`](dotnet-dump.md) tool is simple to use, and does not have a dependency on any native debuggers.</span></span> <span data-ttu-id="7b613-109">`dotnet-dump`는 기존 디버깅 도구를 사용할 수 없는 다양한 Linux 플랫폼(예: Alpine 또는 ARM32/ARM64)에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-109">`dotnet-dump` works on a wide variety of Linux platforms (like Alpine or ARM32/ARM64) where traditional debugging tools may not be available.</span></span> <span data-ttu-id="7b613-110">그러나 `dotnet-dump`는 관리되는 상태만 캡처하므로 네이티브 코드에서 문제를 디버그하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-110">However, `dotnet-dump` only captures managed state so it can't be used for debugging issues in native code.</span></span> <span data-ttu-id="7b613-111">`dotnet-dump`가 수집한 덤프는 덤프가 생성된 동일한 OS 및 아키텍처를 사용하는 환경에서 분석됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-111">Dumps collected by `dotnet-dump` are analyzed in an environment with the the same OS and architecture the dump was created on.</span></span> <span data-ttu-id="7b613-112">[`dotnet-gcdump`](dotnet-gcdump.md) 도구는 GC 힙 정보를 캡처할 뿐 아니라 Windows에서 분석할 수 있는 덤프를 생성하는 대안으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-112">The [`dotnet-gcdump`](dotnet-gcdump.md) tool can be used as an alternative that only captures GC heap information but produces dumps that can be analyzed on Windows.</span></span>

### <a name="core-dumps-with-createdump"></a><span data-ttu-id="7b613-113">`createdump`를 사용한 코어 덤프</span><span class="sxs-lookup"><span data-stu-id="7b613-113">Core dumps with `createdump`</span></span>

<span data-ttu-id="7b613-114">관리형 전용 덤프를 만드는 `dotnet-dump`의 대안인 [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md)는 네이티브 정보와 관리형 정보를 둘 다 포함하는 코어 덤프를 Linux에서 만들 수 있는 권장 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-114">Alternative to `dotnet-dump` which creates managed-only dumps, [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) is the recommended tool for creating core dumps on Linux containing both native and managed information.</span></span> <span data-ttu-id="7b613-115">gdb 또는 gcore와 같은 다른 도구를 사용하여 코어 덤프를 만들 수도 있지만, 관리형 디버깅에 필요한 상태를 놓쳐서 분석 중에 “UNKNOWN” 형식 또는 함수 이름이 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-115">Other tools like gdb or gcore can also be used to create core dumps but may miss state needed for managed debugging, resulting in "UNKNOWN" type or function names during analysis.</span></span>

<span data-ttu-id="7b613-116">`createdump` 도구는 .NET Core 런타임과 함께 설치되며 libcoreclr.so 옆에(일반적으로 “/usr/share/dotnet/shared/Microsoft.NETCore.App/[version]”에) 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-116">The `createdump` tools is installed with the .NET Core runtime and can be found next to libcoreclr.so (typically in "/usr/share/dotnet/shared/Microsoft.NETCore.App/[version]").</span></span> <span data-ttu-id="7b613-117">해당 도구는 프로세스 ID를 사용하여 덤프를 기본 인수로 수집하며 수집할 덤프 종류를 지정하는 선택적 매개 변수를 사용할 수도 있습니다(힙이 있는 미니덤프가 기본값임).</span><span class="sxs-lookup"><span data-stu-id="7b613-117">The tool takes a process ID to collect a dump from as its primary argument and can also take optional parameters specifying what kind of dump to collect (a minidump with heap is the default).</span></span> <span data-ttu-id="7b613-118">다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-118">Options include:</span></span>

- **`<input-filename>`**

  <span data-ttu-id="7b613-119">변환할 입력 추적 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-119">Input trace file to be converted.</span></span> <span data-ttu-id="7b613-120">기본값은 *trace.nettrace*입니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-120">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="7b613-121">옵션</span><span class="sxs-lookup"><span data-stu-id="7b613-121">Options</span></span>

- **`-f|--name <output-filename>`**

  <span data-ttu-id="7b613-122">덤프를 쓸 대상 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-122">The file to write the dump to.</span></span> <span data-ttu-id="7b613-123">기본값은 ‘/tmp/coredump.%p’입니다. 여기서 %p는 대상 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-123">Default is '/tmp/coredump.%p' where %p is the process ID of the target process.</span></span>

- **`-n|--normal`**

  <span data-ttu-id="7b613-124">미니덤프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-124">Create a minidump.</span></span>

- **`-h|--withheap`**

  <span data-ttu-id="7b613-125">힙을 사용하여 미니덤프를 만듭니다(기본값).</span><span class="sxs-lookup"><span data-stu-id="7b613-125">Create a minidump with heap (default).</span></span>

- **`-t|--triage`**

  <span data-ttu-id="7b613-126">심사 미니덤프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-126">Create a triage minidump.</span></span>

- **`-u|--full`**

  <span data-ttu-id="7b613-127">전체 코어 덤프를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-127">Create a full core dump.</span></span>

- **`-d|--diag`**

  <span data-ttu-id="7b613-128">진단 메시지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-128">Enable diagnostic messages.</span></span>

<span data-ttu-id="7b613-129">코어 덤프를 수집하려면 `SYS_PTRACE` 기능이 있거나 sudo 또는 su를 사용하여 `createdump`를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-129">Note that collecting core dumps requires either the `SYS_PTRACE` capability or that `createdump` be run with sudo or su.</span></span>

## <a name="analyze-dumps-on-linux"></a><span data-ttu-id="7b613-130">Linux에서 덤프 분석</span><span class="sxs-lookup"><span data-stu-id="7b613-130">Analyze dumps on Linux</span></span>

<span data-ttu-id="7b613-131">`dotnet-dump`로 수집된 관리형 덤프와 `createdump`로 수집된 코어 덤프는 둘 다 `dotnet-dump analyze` 명령을 사용하여 `dotnet-dump` 도구로 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-131">Both managed dumps collected with `dotnet-dump` and core dumps collected with `createdump` can be analyzed with the `dotnet-dump` tool using the `dotnet-dump analyze` command.</span></span> <span data-ttu-id="7b613-132">`dotnet dump`를 사용하려면 덤프를 분석하는 환경의 OS 및 아키텍처가 덤프를 캡처한 환경과 동일해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-132">The `dotnet dump` requires that the environment analyzing the dump has the same OS and architecture as the environment the dump was captured in.</span></span>

<span data-ttu-id="7b613-133">또는 [LLDB](https://lldb.llvm.org/)를 사용하여 Linux에서 코어 덤프를 분석할 수 있습니다. 그러면 관리형 프레임과 네이티브 프레임을 둘 다 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-133">Alternatively, [LLDB](https://lldb.llvm.org/) can be used to analyze core dumps on Linux, which allows analysis of both managed and native frames.</span></span> <span data-ttu-id="7b613-134">LLDB는 SOS 확장을 사용하여 관리 코드를 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-134">LLDB uses the SOS extension to debug managed code.</span></span> <span data-ttu-id="7b613-135">[`dotnet-sos`](dotnet-sos.md) CLI 도구를 사용하여 관리 코드를 디버그하기 위한 [여러 유용한 명령](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md)이 포함된 SOS를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-135">The [`dotnet-sos`](dotnet-sos.md) CLI tool can be used to install SOS which has [many useful commands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) for debugging managed code.</span></span> <span data-ttu-id="7b613-136">.NET Core 덤프를 분석하려면 LLDB 및 SOS에는 덤프가 생성된 환경의 다음 .NET Core 이진 파일이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-136">In order to analyze .NET Core dumps, LLDB and SOS require the following .NET Core binaries from the environment the dump was created in:</span></span>

1. <span data-ttu-id="7b613-137">libmscordaccore.so</span><span class="sxs-lookup"><span data-stu-id="7b613-137">libmscordaccore.so</span></span>
2. <span data-ttu-id="7b613-138">libcoreclr.so</span><span class="sxs-lookup"><span data-stu-id="7b613-138">libcoreclr.so</span></span>
3. <span data-ttu-id="7b613-139">dotnet(앱을 시작하는 데 사용되는 호스트)</span><span class="sxs-lookup"><span data-stu-id="7b613-139">dotnet (the host used to launch the app)</span></span>

<span data-ttu-id="7b613-140">대부분의 경우 [`dotnet-symbol`](dotnet-symbol.md) 도구를 사용하여 해당 이진 파일을 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-140">In most cases, these binaries can be downloaded using the [`dotnet-symbol`](dotnet-symbol.md) tool.</span></span> <span data-ttu-id="7b613-141">`dotnet-symbol`을 사용하여 필요한 이진 파일을 다운로드할 수 없는 경우(예를 들어 소스에서 빌드된 프라이빗 버전의 .NET Core를 사용 중인 경우) 덤프가 생성된 환경에서 위에 나열된 파일을 복사해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-141">If the necessary binaries can't be downloaded with `dotnet-symbol` (for example, if a private version of .NET Core built from source was in use), it may be necessary to copy the files listed above from the environment the dump was created in.</span></span> <span data-ttu-id="7b613-142">파일이 덤프 파일 옆에 있지 않으면 LLDB/SOS 명령 `setclrpath <path>`를 사용하여 파일을 로드해야 하는 소스 경로를 설정하고 `setsymbolserver -directory <path>`를 사용하여 기호 파일을 확인할 경로를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-142">If the files aren't located next to the dump file, you can use the LLDB/SOS command `setclrpath <path>` to set the path they should be loaded from and `setsymbolserver -directory <path>` to set the path to look in for symbol files.</span></span>

<span data-ttu-id="7b613-143">필요한 파일을 사용할 수 있게 되면 디버그할 실행 파일로 dotnet 호스트를 지정하여 LLDB에서 덤프를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-143">Once the necessary files are available, the dump can be loaded in LLDB by specifying the dotnet host as the executable to debug:</span></span>

```console
lldb --core <dump-file> <host-program>
```

<span data-ttu-id="7b613-144">위 명령줄에서 `<dump-file>`은 분석할 덤프의 경로이며 `<host-program>`은 .NET Core 애플리케이션을 시작한 네이티브 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-144">In the above command line, `<dump-file>` is the path of the dump to analyze and `<host-program>` is the native program that started the .NET Core application.</span></span> <span data-ttu-id="7b613-145">앱이 자체 포함된 경우가 아니면 해당 프로그램은 일반적으로 `dotnet` 이진 파일이며, 이 경우 dll 확장명이 없는 애플리케이션의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-145">This is typically the `dotnet` binary unless the app is self-contained, in which case it is the name of the application without the dll extension.</span></span>

<span data-ttu-id="7b613-146">LLDB가 시작되면 `setsymbolserver` 명령을 사용하여 올바른 기호 위치를 가리켜야 할 수 있습니다(Microsoft의 기호 서버 또는 `setsymbolserver -directory <path>`를 사용하여 로컬 경로를 지정하려면 `setsymbolserver -ms`).</span><span class="sxs-lookup"><span data-stu-id="7b613-146">Once LLDB starts, it may be necessary to use the `setsymbolserver` command to point at the correct symbol location (`setsymbolserver -ms` to use Microsoft's symbol server or `setsymbolserver -directory <path>` to specify a local path).</span></span> <span data-ttu-id="7b613-147">네이티브 기호는 `loadsymbols`를 실행하여 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-147">Native symbols can be loaded by running `loadsymbols`.</span></span> <span data-ttu-id="7b613-148">이제 [SOS 명령](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md)을 사용하여 덤프를 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b613-148">At this point, [SOS commands](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md) can be used to analyze the dump.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b613-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b613-149">See also</span></span>

- <span data-ttu-id="7b613-150">SOS 확장 설치에 대한 자세한 내용은 [dotnet-sos](dotnet-sos.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b613-150">[dotnet-sos](dotnet-sos.md) for more details on installing the SOS extension.</span></span>
- <span data-ttu-id="7b613-151">기호 다운로드 도구 설치 및 사용에 대한 자세한 내용은 [dotnet-symbol](dotnet-symbol.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b613-151">[dotnet-symbol](dotnet-symbol.md) for more details on installing and using the symbol download tool.</span></span>
- <span data-ttu-id="7b613-152">유용한 FAQ를 포함하여 디버깅에 대한 자세한 내용은 [.NET Core 진단 리포지토리](https://github.com/dotnet/diagnostics/blob/master/documentation/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b613-152">[.NET Core diagnostics repo](https://github.com/dotnet/diagnostics/blob/master/documentation/) for more details on debugging, including a useful FAQ.</span></span>
- <span data-ttu-id="7b613-153">Linux 또는 Mac에 LLDB를 설치하는 방법에 관한 지침은 [LLDB 설치](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7b613-153">[Installing LLDB](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb) for instructions on installing LLDB on Linux or Mac.</span></span>
