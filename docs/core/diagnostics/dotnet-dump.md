---
title: dotnet-dump - .NET Core
description: dotnet-dump 명령줄 도구를 설치하고 사용합니다.
ms.date: 10/14/2019
ms.openlocfilehash: c78ddb6447021f61f2452c075733b7d33e051ca0
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888204"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a><span data-ttu-id="54ea8-103">덤프 수집 및 분석 유틸리티(`dotnet-dump`)</span><span class="sxs-lookup"><span data-stu-id="54ea8-103">Dump collection and analysis utility (`dotnet-dump`)</span></span>

<span data-ttu-id="54ea8-104">**이 문서의 적용 대상:**  ✔️ .NET Core 3.0 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="54ea8-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

> [!NOTE]
> <span data-ttu-id="54ea8-105">`dotnet-dump`는 macOS에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-105">`dotnet-dump` isn't supported on macOS.</span></span>

## <a name="installing-dotnet-dump"></a><span data-ttu-id="54ea8-106">`dotnet-dump` 설치</span><span class="sxs-lookup"><span data-stu-id="54ea8-106">Installing `dotnet-dump`</span></span>

<span data-ttu-id="54ea8-107">`dotnet-dump` [NuGet 패키지](https://www.nuget.org/packages/dotnet-dump)의 최신 릴리스 버전을 설치하려면 [dotnet tool install](../tools/dotnet-tool-install.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-107">To install the latest release version of the `dotnet-dump` [NuGet package](https://www.nuget.org/packages/dotnet-dump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-dump
```

## <a name="synopsis"></a><span data-ttu-id="54ea8-108">개요</span><span class="sxs-lookup"><span data-stu-id="54ea8-108">Synopsis</span></span>

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="54ea8-109">설명</span><span class="sxs-lookup"><span data-stu-id="54ea8-109">Description</span></span>

<span data-ttu-id="54ea8-110">`dotnet-dump` 글로벌 도구는 Linux에서 `lldb`와 같은 네이티브 디버거 없이 Windows 및 Linux 덤프를 수집하고 분석하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-110">The `dotnet-dump` global tool is a way to collect and analyze Windows and Linux dumps without any native debugger involved like `lldb` on Linux.</span></span> <span data-ttu-id="54ea8-111">이 도구는 완벽하게 작동하는 `lldb`를 사용할 수 없는 Alpine Linux와 같은 플랫폼에서 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-111">This tool is important on platforms like Alpine Linux where a fully working `lldb` isn't available.</span></span> <span data-ttu-id="54ea8-112">`dotnet-dump` 도구를 사용하면 충돌 및 GC(가비지 수집기)를 분석하기 위해 SOS 명령을 실행할 수 있지만 네이티브 디버거가 아니므로 네이티브 스택 프레임 표시와 같은 기능은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-112">The `dotnet-dump` tool allows you to run SOS commands to analyze crashes and the garbage collector (GC), but it isn't a native debugger so things like displaying native stack frames aren't supported.</span></span>

## <a name="options"></a><span data-ttu-id="54ea8-113">옵션</span><span class="sxs-lookup"><span data-stu-id="54ea8-113">Options</span></span>

- **`--version`**

  <span data-ttu-id="54ea8-114">dotnet-dump 유틸리티의 버전을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-114">Displays the version of the dotnet-dump utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="54ea8-115">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-115">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="54ea8-116">명령</span><span class="sxs-lookup"><span data-stu-id="54ea8-116">Commands</span></span>

| <span data-ttu-id="54ea8-117">명령</span><span class="sxs-lookup"><span data-stu-id="54ea8-117">Command</span></span>                                     |
| ------------------------------------------- |
| [<span data-ttu-id="54ea8-118">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="54ea8-118">dotnet-dump collect</span></span>](#dotnet-dump-collect) |
| [<span data-ttu-id="54ea8-119">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="54ea8-119">dotnet-dump analyze</span></span>](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a><span data-ttu-id="54ea8-120">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="54ea8-120">dotnet-dump collect</span></span>

<span data-ttu-id="54ea8-121">프로세스에서 덤프를 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-121">Captures a dump from a process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="54ea8-122">개요</span><span class="sxs-lookup"><span data-stu-id="54ea8-122">Synopsis</span></span>

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [--type] [-o|--output] [--diag]
```

### <a name="options"></a><span data-ttu-id="54ea8-123">옵션</span><span class="sxs-lookup"><span data-stu-id="54ea8-123">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="54ea8-124">명령줄 도움말을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-124">Shows command-line help.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="54ea8-125">메모리 덤프를 수집할 프로세스 ID 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-125">Specifies the process ID number to collect a memory dump from.</span></span>

- **`--type <Heap|Mini>`**

  <span data-ttu-id="54ea8-126">프로세스에서 수집되는 정보의 종류를 결정하는 덤프 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-126">Specifies the dump type, which determines the kinds of information that are collected from the process.</span></span> <span data-ttu-id="54ea8-127">다음과 같은 두 가지 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-127">There are two types:</span></span>

  - <span data-ttu-id="54ea8-128">`Heap` - 모듈 목록, 스레드 목록, 모든 스택, 예외 정보, 핸들 정보 및 매핑된 이미지를 제외한 모든 메모리를 포함하는 크고 비교적 포괄적인 덤프입니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-128">`Heap` - A large and relatively comprehensive dump containing module lists, thread lists, all stacks, exception information, handle information, and all memory except for mapped images.</span></span>
  - <span data-ttu-id="54ea8-129">`Mini` - 모듈 목록, 스레드 목록, 예외 정보 및 모든 스택을 포함하는 작은 덤프입니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-129">`Mini` - A small dump containing module lists, thread lists, exception information, and all stacks.</span></span>

  <span data-ttu-id="54ea8-130">지정하지 않으면 `Heap`이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-130">If not specified, `Heap` is the default.</span></span>

- **`-o|--output <output_dump_path>`**

  <span data-ttu-id="54ea8-131">수집된 덤프를 기록해야 하는 전체 경로 및 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-131">The full path and file name where the collected dump should be written.</span></span>

  <span data-ttu-id="54ea8-132">지정하지 않으면 다음과 같이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-132">If not specified:</span></span>

  - <span data-ttu-id="54ea8-133">Windows의 경우 기본적으로 *.\dump_YYYYMMDD_HHMMSS.dmp*로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-133">Defaults to *.\dump_YYYYMMDD_HHMMSS.dmp* on Windows.</span></span>
  - <span data-ttu-id="54ea8-134">Linux의 경우 기본적으로 *./core_YYYYMMDD_HHMMSS*로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-134">Defaults to *./core_YYYYMMDD_HHMMSS* on Linux.</span></span>

  <span data-ttu-id="54ea8-135">YYYYMMDD는 년/월/일이고, HHMMSS는 시간/분/초입니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-135">YYYYMMDD is Year/Month/Day and HHMMSS is Hour/Minute/Second.</span></span>

- **`--diag`**

  <span data-ttu-id="54ea8-136">덤프 수집 진단 로깅을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-136">Enables dump collection diagnostic logging.</span></span>

## <a name="dotnet-dump-analyze"></a><span data-ttu-id="54ea8-137">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="54ea8-137">dotnet-dump analyze</span></span>

<span data-ttu-id="54ea8-138">덤프를 검색하기 위해 대화형 셸을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-138">Starts an interactive shell to explore a dump.</span></span> <span data-ttu-id="54ea8-139">셸에는 다양한 [SOS 명령](#analyze-sos-commands)이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-139">The shell accepts various [SOS commands](#analyze-sos-commands).</span></span>

### <a name="synopsis"></a><span data-ttu-id="54ea8-140">개요</span><span class="sxs-lookup"><span data-stu-id="54ea8-140">Synopsis</span></span>

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a><span data-ttu-id="54ea8-141">인수</span><span class="sxs-lookup"><span data-stu-id="54ea8-141">Arguments</span></span>

- **`<dump_path>`**

  <span data-ttu-id="54ea8-142">분석할 덤프 파일의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-142">Specifies the path to the dump file to analyze.</span></span>

### <a name="options"></a><span data-ttu-id="54ea8-143">옵션</span><span class="sxs-lookup"><span data-stu-id="54ea8-143">Options</span></span>

- **`-c|--command <debug_command>`**

  <span data-ttu-id="54ea8-144">시작할 때 셸에서 실행할 [명령](#analyze-sos-commands)을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-144">Specifies the [command](#analyze-sos-commands) to run in the shell on start.</span></span>

### <a name="analyze-sos-commands"></a><span data-ttu-id="54ea8-145">SOS 명령 분석</span><span class="sxs-lookup"><span data-stu-id="54ea8-145">Analyze SOS commands</span></span>

| <span data-ttu-id="54ea8-146">명령</span><span class="sxs-lookup"><span data-stu-id="54ea8-146">Command</span></span>                             | <span data-ttu-id="54ea8-147">기능</span><span class="sxs-lookup"><span data-stu-id="54ea8-147">Function</span></span>                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | <span data-ttu-id="54ea8-148">사용 가능한 모든 명령을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-148">Displays all available commands</span></span>                                                               |
| `soshelp|help <command>`            | <span data-ttu-id="54ea8-149">지정된 명령을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-149">Displays the specified command.</span></span>                                                               |
| `exit|quit`                         | <span data-ttu-id="54ea8-150">대화형 모드를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-150">Exits interactive mode.</span></span>                                                                       |
| `clrstack <arguments>`              | <span data-ttu-id="54ea8-151">관리 코드의 스택 추적만 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-151">Provides a stack trace of managed code only.</span></span>                                                  |
| `clrthreads <arguments>`            | <span data-ttu-id="54ea8-152">실행 중인 관리형 스레드를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-152">Lists the managed threads running.</span></span>                                                            |
| `dumpasync <arguments>`             | <span data-ttu-id="54ea8-153">가비지가 수집된 힙의 비동기 상태 머신에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-153">Displays information about async state machines on the garbage-collected heap.</span></span>                |
| `dumpassembly <arguments>`          | <span data-ttu-id="54ea8-154">어셈블리에 대한 세부 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-154">Displays details about an assembly.</span></span>                                                           |
| `dumpclass <arguments>`             | <span data-ttu-id="54ea8-155">지정된 주소의 EE 클래스 구조체에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-155">Displays information about a EE class structure at the specified address.</span></span>                     |
| `dumpdelegate <arguments>`          | <span data-ttu-id="54ea8-156">대리자에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-156">Displays information about a delegate.</span></span>                                                        |
| `dumpdomain <arguments>`            | <span data-ttu-id="54ea8-157">모든 AppDomains 및 도메인 내의 모든 어셈블리에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-157">Displays information all the AppDomains and all assemblies within the domains.</span></span>                |
| `dumpheap <arguments>`              | <span data-ttu-id="54ea8-158">가비지가 수집된 힙에 대한 정보와 개체에 대한 수집 통계를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-158">Displays info about the garbage-collected heap and collection statistics about objects.</span></span>       |
| `dumpil <arguments>`                | <span data-ttu-id="54ea8-159">관리되는 메서드와 연관된 MSIL(Microsoft intermediate language)을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-159">Displays the Microsoft intermediate language (MSIL) that is associated with a managed method.</span></span> |
| `dumplog <arguments>`               | <span data-ttu-id="54ea8-160">메모리 내 스트레스 로그의 내용을 지정된 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-160">Writes the contents of an in-memory stress log to the specified file.</span></span>                         |
| `dumpmd <arguments>`                | <span data-ttu-id="54ea8-161">지정된 주소의 MethodDesc 구조체에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-161">Displays information about a MethodDesc structure at the specified address.</span></span>                   |
| `dumpmodule <arguments>`            | <span data-ttu-id="54ea8-162">지정된 주소의 EE 모듈 구조체에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-162">Displays information about a EE module structure at the specified address.</span></span>                    |
| `dumpmt <arguments>`                | <span data-ttu-id="54ea8-163">지정된 주소의 메서드 테이블에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-163">Displays information about a method table at the specified address.</span></span>                           |
| `dumpobj <arguments>`               | <span data-ttu-id="54ea8-164">지정된 주소의 개체에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-164">Displays info about an object at the specified address.</span></span>                                       |
| `dso|dumpstackobjects <arguments>`  | <span data-ttu-id="54ea8-165">현재 스택의 범위 내에 있는 관리되는 모든 개체를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-165">Displays all managed objects found within the bounds of the current stack.</span></span>                    |
| `eeheap <arguments>`                | <span data-ttu-id="54ea8-166">내부 런타임 데이터 구조에서 사용하는 프로세스 메모리에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-166">Displays info about process memory consumed by internal runtime data structures.</span></span>              |
| `finalizequeue <arguments>`         | <span data-ttu-id="54ea8-167">종료하도록 등록된 모든 개체를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-167">Displays all objects registered for finalization.</span></span>                                             |
| `gcroot <arguments>`                | <span data-ttu-id="54ea8-168">지정된 주소의 개체에 대한 참조(또는 루트)에 대한 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-168">Displays info about references (or roots) to an object at the specified address.</span></span>              |
| `gcwhere <arguments>`               | <span data-ttu-id="54ea8-169">전달된 인수의 GC 힙에 있는 위치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-169">Displays the location in the GC heap of the argument passed in.</span></span>                               |
| `ip2md <arguments>`                 | <span data-ttu-id="54ea8-170">JIT 코드의 지정된 주소에 있는 MethodDesc 구조체를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-170">Displays the MethodDesc structure at the specified address in JIT code.</span></span>                       |
| `histclear <arguments>`             | <span data-ttu-id="54ea8-171">`hist*` 명령의 패밀리에서 사용하는 모든 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-171">Releases any resources used by the family of `hist*` commands.</span></span>                                |
| `histinit <arguments>`              | <span data-ttu-id="54ea8-172">디버기에 저장된 스트레스 로그에서 SOS 구조를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-172">Initializes the SOS structures from the stress log saved in the debuggee.</span></span>                     |
| `histobj <arguments>`               | <span data-ttu-id="54ea8-173">`<arguments>`와 관련된 가비지 수집 스트레스 로그 재배치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-173">Displays the garbage collection stress log relocations related to `<arguments>`.</span></span>              |
| `histobjfind <arguments>`           | <span data-ttu-id="54ea8-174">지정된 주소의 개체를 참조하는 모든 로그 항목을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-174">Displays all the log entries that reference an object at the specified address.</span></span>               |
| `histroot <arguments>`              | <span data-ttu-id="54ea8-175">지정된 루트의 승격 및 재배치와 관련된 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-175">Displays information related to both promotions and relocations of the specified root.</span></span>        |
| `lm|modules`                        | <span data-ttu-id="54ea8-176">프로세스의 네이티브 모듈을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-176">Displays the native modules in the process.</span></span>                                                   |
| `name2ee <arguments>`               | <span data-ttu-id="54ea8-177">`<argument>`에 대한 MethodTable 구조체와 EEClass 구조체를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-177">Displays the MethodTable structure and EEClass structure for the `<argument>`.</span></span>                |
| `pe|printexception <arguments>`     | <span data-ttu-id="54ea8-178">`<argument>` 주소의 Exception 클래스에서 파생된 개체를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-178">Displays any object derived from the Exception class at the address `<argument>`.</span></span>             |
| `setsymbolserver <arguments>`       | <span data-ttu-id="54ea8-179">기호 서버 지원을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-179">Enables the symbol server support</span></span>                                                             |
| `syncblk <arguments>`               | <span data-ttu-id="54ea8-180">SyncBlock 표시자 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-180">Displays the SyncBlock holder info.</span></span>                                                           |
| `threads|setthread <threadid>`      | <span data-ttu-id="54ea8-181">SOS 명령의 현재 스레드 ID를 설정하거나 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-181">Sets or displays the current thread ID for the SOS commands.</span></span>                                  |

## <a name="using-dotnet-dump"></a><span data-ttu-id="54ea8-182">`dotnet-dump` 사용</span><span class="sxs-lookup"><span data-stu-id="54ea8-182">Using `dotnet-dump`</span></span>

<span data-ttu-id="54ea8-183">첫 번째 단계는 덤프를 수집하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-183">The first step is to collect a dump.</span></span> <span data-ttu-id="54ea8-184">코어 덤프가 이미 생성된 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-184">This step can be skipped if a core dump has already been generated.</span></span> <span data-ttu-id="54ea8-185">운영 체제 또는 .NET Core 런타임의 기본 제공 [dump 생성 기능](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md)은 각각 코어 덤프를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-185">The operating system or the .NET Core runtime's built-in [dump generation feature](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) can each create core dumps.</span></span>

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

<span data-ttu-id="54ea8-186">이제 `analyze` 명령을 사용하여 코어 덤프를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-186">Now analyze the core dump with the `analyze` command:</span></span>

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

<span data-ttu-id="54ea8-187">이 작업을 수행하면 다음과 같은 명령을 허용하는 대화형 세션이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-187">This action brings up an interactive session that accepts commands like:</span></span>

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

<span data-ttu-id="54ea8-188">앱을 종료한 처리되지 않은 예외를 보려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-188">To see an unhandled exception that killed your app:</span></span>

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a><span data-ttu-id="54ea8-189">Docker에 대한 특별 지침</span><span class="sxs-lookup"><span data-stu-id="54ea8-189">Special instructions for Docker</span></span>

<span data-ttu-id="54ea8-190">Docker에서 실행되는 경우 덤프 수집에 `SYS_PTRACE` 기능(`--cap-add=SYS_PTRACE` 또는 `--privileged`)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-190">If you're running under Docker, dump collection requires `SYS_PTRACE` capabilities (`--cap-add=SYS_PTRACE` or `--privileged`).</span></span>

<span data-ttu-id="54ea8-191">Microsoft .NET Core SDK Linux Docker 이미지에서 일부 `dotnet-dump` 명령은 다음과 같은 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-191">On Microsoft .NET Core SDK Linux Docker images, some `dotnet-dump` commands can throw the following exception:</span></span>

> <span data-ttu-id="54ea8-192">처리되지 않은 예외: System.DllNotFoundException: 'libdl.so' 공유 라이브러리 또는 해당 종속성 예외 중 하나를 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54ea8-192">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception.</span></span>

<span data-ttu-id="54ea8-193">이 문제를 해결하려면 "libc6-dev" 패키지를 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="54ea8-193">To work around this problem, install the "libc6-dev" package.</span></span>
