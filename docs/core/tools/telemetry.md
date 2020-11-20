---
title: .NET SDK 원격 분석
description: 어떤 데이터가 수집되고 수집 기능을 사용하지 않도록 설정하는 방법에 대한 분석을 위해 사용량 정보를 수집하는 .NET SDK 원격 분석 기능을 살펴봅니다.
author: KathleenDollard
ms.date: 08/27/2019
ms.openlocfilehash: 4f137822c61e1a04eccd28ebd0cd56c04f4a85e2
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2020
ms.locfileid: "94633871"
---
# <a name="net-sdk-telemetry"></a><span data-ttu-id="79c43-103">.NET SDK 원격 분석</span><span class="sxs-lookup"><span data-stu-id="79c43-103">.NET SDK telemetry</span></span>

<span data-ttu-id="79c43-104">[.NET SDK](index.md)에는 .NET CLI에서 크래시가 발생할 때 사용량 현황 데이터 및 예외 정보를 수집하는 원격 분석 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-104">The [.NET SDK](index.md) includes a telemetry feature that collects usage data and exception information when the .NET CLI crashes.</span></span> <span data-ttu-id="79c43-105">.NET CLI는 .NET SDK와 함께 제공되며 .NET 앱을 빌드, 테스트 및 게시하는 데 사용할 수 있는 동사 세트입니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-105">The .NET CLI comes with the .NET SDK and is the set of verbs that enable you to build, test, and publish your .NET apps.</span></span> <span data-ttu-id="79c43-106">.NET 팀이 이 도구를 개선하려면 이 도구가 어떻게 사용되는지 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-106">It's important that the .NET team understands how the tools are used so they can be improved.</span></span> <span data-ttu-id="79c43-107">오류에 대한 정보는 팀이 문제를 해결하고 버그를 수정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-107">Information on failures helps the team resolve problems and fix bugs.</span></span>

<span data-ttu-id="79c43-108">수집된 데이터는 [Creative Commons Attribution 라이선스](https://creativecommons.org/licenses/by/4.0/)에 따라 모두 집계하여 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-108">The collected data is published in aggregate under the [Creative Commons Attribution License](https://creativecommons.org/licenses/by/4.0/).</span></span>

## <a name="scope"></a><span data-ttu-id="79c43-109">Scope</span><span class="sxs-lookup"><span data-stu-id="79c43-109">Scope</span></span>

<span data-ttu-id="79c43-110">`dotnet`에는 앱을 실행하고 CLI 명령을 실행하는 두 가지 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-110">`dotnet` has two functions: to run apps, and to execute CLI commands.</span></span> <span data-ttu-id="79c43-111">`dotnet`을 사용하여 다음 형식으로 애플리케이션을 시작하는 경우 원격 분석이 ‘수집되지 않습니다’.</span><span class="sxs-lookup"><span data-stu-id="79c43-111">Telemetry *isn't collected* when using `dotnet` to start an application in the following format:</span></span>

- `dotnet [path-to-app].dll`

<span data-ttu-id="79c43-112">다음과 같은 [.NET CLI 명령](index.md)을 사용하는 경우 원격 분석이 ‘수집됩니다’.</span><span class="sxs-lookup"><span data-stu-id="79c43-112">Telemetry *is collected* when using any of the [.NET CLI commands](index.md), such as:</span></span>

- `dotnet build`
- `dotnet pack`
- `dotnet run`

## <a name="how-to-opt-out"></a><span data-ttu-id="79c43-113">옵트아웃(opt out)하는 방법</span><span class="sxs-lookup"><span data-stu-id="79c43-113">How to opt out</span></span>

<span data-ttu-id="79c43-114">.NET SDK 원격 분석 기능은 기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-114">The .NET SDK telemetry feature is enabled by default.</span></span> <span data-ttu-id="79c43-115">원격 분석 기능을 옵트아웃하려면 `DOTNET_CLI_TELEMETRY_OPTOUT` 환경 변수를 `1` 또는 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-115">To opt out of the telemetry feature, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span>

<span data-ttu-id="79c43-116">설치에 성공하면 .NET SDK 설치 관리자에서 단일 원격 분석 항목도 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-116">A single telemetry entry is also sent by the .NET SDK installer when a successful installation happens.</span></span> <span data-ttu-id="79c43-117">옵트아웃하려면 .NET SDK를 설치하기 전에 `DOTNET_CLI_TELEMETRY_OPTOUT` 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-117">To opt out, set the `DOTNET_CLI_TELEMETRY_OPTOUT` environment variable before you install the .NET SDK.</span></span>

## <a name="disclosure"></a><span data-ttu-id="79c43-118">공개</span><span class="sxs-lookup"><span data-stu-id="79c43-118">Disclosure</span></span>

<span data-ttu-id="79c43-119">.NET SDK는 [.NET CLI 명령](index.md) 중 하나(예: `dotnet build`)를 처음 실행할 때 다음과 유사한 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-119">The .NET SDK displays text similar to the following when you first run one of the [.NET CLI commands](index.md) (for example, `dotnet build`).</span></span> <span data-ttu-id="79c43-120">실행 중인 SDK 버전에 따라 텍스트가 약간 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-120">Text may vary slightly depending on the version of the SDK you're running.</span></span> <span data-ttu-id="79c43-121">이 "첫 실행" 경험이 Microsoft가 사용자에게 데이터 수집에 대해 알리는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-121">This "first run" experience is how Microsoft notifies you about data collection.</span></span>

```console
Telemetry
---------
The .NET tools collect usage data in order to help us improve your experience. The data is collected by Microsoft and shared with the community. You can opt-out of telemetry by setting the DOTNET_CLI_TELEMETRY_OPTOUT environment variable to '1' or 'true' using your favorite shell.

Read more about .NET CLI Tools telemetry: https://aka.ms/dotnet-cli-telemetry
```

<span data-ttu-id="79c43-122">이 메시지와 .NET 시작 메시지를 사용하지 않도록 설정하려면 `DOTNET_NOLOGO` 환경 변수를 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-122">To disable this message and the .NET welcome message, set the `DOTNET_NOLOGO` environment variable to `true`.</span></span> <span data-ttu-id="79c43-123">이 변수는 원격 분석 옵트아웃에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-123">Note that this variable has no effect on telemetry opt out.</span></span>

## <a name="data-points"></a><span data-ttu-id="79c43-124">데이터 요소</span><span class="sxs-lookup"><span data-stu-id="79c43-124">Data points</span></span>

<span data-ttu-id="79c43-125">이 원격 분석 기능은 사용자 이름이나 전자 메일 주소 등의 개인 데이터를 수집하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-125">The telemetry feature doesn't collect personal data, such as usernames or email addresses.</span></span> <span data-ttu-id="79c43-126">코드를 검사하지 않고 이름, 리포지토리 또는 작성자와 같은 프로젝트 수준 데이터를 추출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-126">It doesn't scan your code and doesn't extract project-level data, such as name, repository, or author.</span></span> <span data-ttu-id="79c43-127">데이터는 [Azure Monitor](https://azure.microsoft.com/services/monitor/) 기술을 사용하여 Microsoft 서버로 안전하게 전송되고, 제한된 액세스를 기준으로 보관되고, 안전한 [Azure Storage](https://azure.microsoft.com/services/storage/) 시스템에서 엄격한 보안 제어에 따라 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-127">The data is sent securely to Microsoft servers using [Azure Monitor](https://azure.microsoft.com/services/monitor/) technology, held under restricted access, and published under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

<span data-ttu-id="79c43-128">개인 정보 보호는 Microsoft에 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-128">Protecting your privacy is important to us.</span></span> <span data-ttu-id="79c43-129">원격 분석이 중요한 데이터를 수집하고 있는지 또는 데이터가 안전하지 않거나 부적절한 방식으로 처리되고 있는지 의심스러운 경우 조사를 위해 [dotnet/sdk](https://github.com/dotnet/sdk/issues) 리포지토리에서 문제를 제출하거나 [dotnet@microsoft.com](mailto:dotnet@microsoft.com)에 전자 메일을 보내세요.</span><span class="sxs-lookup"><span data-stu-id="79c43-129">If you suspect the telemetry is collecting sensitive data or the data is being insecurely or inappropriately handled, file an issue in the [dotnet/sdk](https://github.com/dotnet/sdk/issues) repository or send an email to [dotnet@microsoft.com](mailto:dotnet@microsoft.com) for investigation.</span></span>

<span data-ttu-id="79c43-130">원격 분석 기능은 다음 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-130">The telemetry feature collects the following data:</span></span>

| <span data-ttu-id="79c43-131">SDK 버전</span><span class="sxs-lookup"><span data-stu-id="79c43-131">SDK versions</span></span> | <span data-ttu-id="79c43-132">데이터</span><span class="sxs-lookup"><span data-stu-id="79c43-132">Data</span></span> |
|--------------|------|
| <span data-ttu-id="79c43-133">모두</span><span class="sxs-lookup"><span data-stu-id="79c43-133">All</span></span>          | <span data-ttu-id="79c43-134">호출의 타임스탬프</span><span class="sxs-lookup"><span data-stu-id="79c43-134">Timestamp of invocation.</span></span> |
| <span data-ttu-id="79c43-135">모두</span><span class="sxs-lookup"><span data-stu-id="79c43-135">All</span></span>          | <span data-ttu-id="79c43-136">2\.1부터 해시된 호출된 명령(예: “build”)</span><span class="sxs-lookup"><span data-stu-id="79c43-136">Command invoked (for example, "build"), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="79c43-137">모두</span><span class="sxs-lookup"><span data-stu-id="79c43-137">All</span></span>          | <span data-ttu-id="79c43-138">지리적 위치를 확인하는 데 사용되는 8진수 IP 주소 3개</span><span class="sxs-lookup"><span data-stu-id="79c43-138">Three octet IP address used to determine the geographical location.</span></span> |
| <span data-ttu-id="79c43-139">모두</span><span class="sxs-lookup"><span data-stu-id="79c43-139">All</span></span>          | <span data-ttu-id="79c43-140">운영 체제 및 버전</span><span class="sxs-lookup"><span data-stu-id="79c43-140">Operating system and version.</span></span> |
| <span data-ttu-id="79c43-141">모두</span><span class="sxs-lookup"><span data-stu-id="79c43-141">All</span></span>          | <span data-ttu-id="79c43-142">SDK가 실행되고 있는 RID(런타임 ID)</span><span class="sxs-lookup"><span data-stu-id="79c43-142">Runtime ID (RID) the SDK is running on.</span></span> |
| <span data-ttu-id="79c43-143">모두</span><span class="sxs-lookup"><span data-stu-id="79c43-143">All</span></span>          | <span data-ttu-id="79c43-144">.NET SDK 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-144">.NET SDK version.</span></span> |
| <span data-ttu-id="79c43-145">모두</span><span class="sxs-lookup"><span data-stu-id="79c43-145">All</span></span>          | <span data-ttu-id="79c43-146">원격 분석 프로필: 명시적 사용자 옵트인과 함께 사용되고 Microsoft에서 내부적으로만 사용되는 선택적 값</span><span class="sxs-lookup"><span data-stu-id="79c43-146">Telemetry profile: an optional value only used with explicit user opt-in and used internally at Microsoft.</span></span> |
| <span data-ttu-id="79c43-147">2\.0 이상</span><span class="sxs-lookup"><span data-stu-id="79c43-147">>=2.0</span></span>        | <span data-ttu-id="79c43-148">명령 인수 및 옵션: 알려진 인수 및 옵션만 수집됩니다(임의 문자열이 아님).</span><span class="sxs-lookup"><span data-stu-id="79c43-148">Command arguments and options: several arguments and options are collected (not arbitrary strings).</span></span> <span data-ttu-id="79c43-149">[수집된 옵션](#collected-options)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79c43-149">See [collected options](#collected-options).</span></span> <span data-ttu-id="79c43-150">2\.1.300 이후에 해시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-150">Hashed after 2.1.300.</span></span> |
| <span data-ttu-id="79c43-151">2\.0 이상</span><span class="sxs-lookup"><span data-stu-id="79c43-151">>=2.0</span></span>         | <span data-ttu-id="79c43-152">SDK가 컨테이너에서 실행 중인지 여부.</span><span class="sxs-lookup"><span data-stu-id="79c43-152">Whether the SDK is running in a container.</span></span> |
| <span data-ttu-id="79c43-153">2\.0 이상</span><span class="sxs-lookup"><span data-stu-id="79c43-153">>=2.0</span></span>         | <span data-ttu-id="79c43-154">2\.1부터 해시된 `TargetFramework` 이벤트의 대상 프레임워크</span><span class="sxs-lookup"><span data-stu-id="79c43-154">Target frameworks (from the `TargetFramework` event), hashed starting in 2.1.</span></span> |
| <span data-ttu-id="79c43-155">2\.0 이상</span><span class="sxs-lookup"><span data-stu-id="79c43-155">>=2.0</span></span>         | <span data-ttu-id="79c43-156">해시된 MAC(미디어 액세스 제어) 주소(SHA256).</span><span class="sxs-lookup"><span data-stu-id="79c43-156">Hashed Media Access Control (MAC) address (SHA256).</span></span> |
| <span data-ttu-id="79c43-157">2\.0 이상</span><span class="sxs-lookup"><span data-stu-id="79c43-157">>=2.0</span></span>         | <span data-ttu-id="79c43-158">해시된 현재 작업 디렉터리.</span><span class="sxs-lookup"><span data-stu-id="79c43-158">Hashed current working directory.</span></span> |
| <span data-ttu-id="79c43-159">2\.0 이상</span><span class="sxs-lookup"><span data-stu-id="79c43-159">>=2.0</span></span>         | <span data-ttu-id="79c43-160">해시된 설치 관리자 exe 파일 이름을 사용하는 설치 성공 보고서</span><span class="sxs-lookup"><span data-stu-id="79c43-160">Install success report, with hashed installer exe filename.</span></span> |
| <span data-ttu-id="79c43-161">2\.1.300 이상</span><span class="sxs-lookup"><span data-stu-id="79c43-161">>=2.1.300</span></span>     | <span data-ttu-id="79c43-162">커널 버전</span><span class="sxs-lookup"><span data-stu-id="79c43-162">Kernel version.</span></span> |
| <span data-ttu-id="79c43-163">2\.1.300 이상</span><span class="sxs-lookup"><span data-stu-id="79c43-163">>=2.1.300</span></span>     | <span data-ttu-id="79c43-164">Libc 릴리스/버전</span><span class="sxs-lookup"><span data-stu-id="79c43-164">Libc release/version.</span></span> |
| <span data-ttu-id="79c43-165">3\.0.100 이상</span><span class="sxs-lookup"><span data-stu-id="79c43-165">>=3.0.100</span></span>     | <span data-ttu-id="79c43-166">출력이 리디렉션되었는지 여부(true 또는 false)</span><span class="sxs-lookup"><span data-stu-id="79c43-166">Whether the output was redirected (true or false).</span></span> |
| <span data-ttu-id="79c43-167">3\.0.100 이상</span><span class="sxs-lookup"><span data-stu-id="79c43-167">>=3.0.100</span></span>     | <span data-ttu-id="79c43-168">CLI/SDK 크래시 발생 시 예외 형식 및 해당 스택 추적(전송된 스택 추적에는 CLI/SDK 코드만 포함됨).</span><span class="sxs-lookup"><span data-stu-id="79c43-168">On a CLI/SDK crash, the exception type and its stack trace (only CLI/SDK code is included in the stack trace sent).</span></span> <span data-ttu-id="79c43-169">자세한 내용은 [수집된 .NET CLI/SDK 크래시 예외 원격 분석](#net-clisdk-crash-exception-telemetry-collected)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79c43-169">For more information, see [.NET CLI/SDK crash exception telemetry collected](#net-clisdk-crash-exception-telemetry-collected).</span></span> |

### <a name="collected-options"></a><span data-ttu-id="79c43-170">수집된 옵션</span><span class="sxs-lookup"><span data-stu-id="79c43-170">Collected options</span></span>

<span data-ttu-id="79c43-171">특정 명령은 추가 데이터를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-171">Certain commands send additional data.</span></span> <span data-ttu-id="79c43-172">명령의 하위 집합은 첫 번째 인수를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-172">A subset of commands sends the first argument:</span></span>

| <span data-ttu-id="79c43-173">명령</span><span class="sxs-lookup"><span data-stu-id="79c43-173">Command</span></span>               | <span data-ttu-id="79c43-174">전송된 첫 번째 인수 데이터</span><span class="sxs-lookup"><span data-stu-id="79c43-174">First argument data sent</span></span>                |
|-----------------------|-----------------------------------------|
| `dotnet help <arg>`   | <span data-ttu-id="79c43-175">명령 도움말이 쿼리됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-175">The command help is being queried for.</span></span>  |
| `dotnet new <arg>`    | <span data-ttu-id="79c43-176">템플릿 이름(해시)</span><span class="sxs-lookup"><span data-stu-id="79c43-176">The template name (hashed).</span></span>             |
| `dotnet add <arg>`    | <span data-ttu-id="79c43-177">단어 `package` 또는 `reference`</span><span class="sxs-lookup"><span data-stu-id="79c43-177">The word `package` or `reference`.</span></span>      |
| `dotnet remove <arg>` | <span data-ttu-id="79c43-178">단어 `package` 또는 `reference`</span><span class="sxs-lookup"><span data-stu-id="79c43-178">The word `package` or `reference`.</span></span>      |
| `dotnet list <arg>`   | <span data-ttu-id="79c43-179">단어 `package` 또는 `reference`</span><span class="sxs-lookup"><span data-stu-id="79c43-179">The word `package` or `reference`.</span></span>      |
| `dotnet sln <arg>`    | <span data-ttu-id="79c43-180">단어 `add`, `list` 또는 `remove`</span><span class="sxs-lookup"><span data-stu-id="79c43-180">The word `add`, `list`, or `remove`.</span></span>    |
| `dotnet nuget <arg>`  | <span data-ttu-id="79c43-181">단어 `delete`, `locals` 또는 `push`</span><span class="sxs-lookup"><span data-stu-id="79c43-181">The word `delete`, `locals`, or `push`.</span></span> |

<span data-ttu-id="79c43-182">명령 하위 집합은 해당 값과 함께 사용되는 경우 선택된 옵션을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-182">A subset of commands sends selected options if they're used, along with their values:</span></span>

| <span data-ttu-id="79c43-183">옵션</span><span class="sxs-lookup"><span data-stu-id="79c43-183">Option</span></span>                  | <span data-ttu-id="79c43-184">명령</span><span class="sxs-lookup"><span data-stu-id="79c43-184">Commands</span></span>                                                                                       |
|-------------------------|------------------------------------------------------------------------------------------------|
| `--verbosity`           | <span data-ttu-id="79c43-185">모든 명령</span><span class="sxs-lookup"><span data-stu-id="79c43-185">All commands</span></span>                                                                                   |
| `--language`            | `dotnet new`                                                                                   |
| `--configuration`       | <span data-ttu-id="79c43-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span><span class="sxs-lookup"><span data-stu-id="79c43-186">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`</span></span>                  |
| `--framework`           | <span data-ttu-id="79c43-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span><span class="sxs-lookup"><span data-stu-id="79c43-187">`dotnet build`, `dotnet clean`, `dotnet publish`, `dotnet run`, `dotnet test`, `dotnet vstest`</span></span> |
| `--runtime`             | <span data-ttu-id="79c43-188">`dotnet build`, `dotnet publish`</span><span class="sxs-lookup"><span data-stu-id="79c43-188">`dotnet build`,  `dotnet publish`</span></span>                                                              |
| `--platform`            | `dotnet vstest`                                                                                |
| `--logger`              | `dotnet vstest`                                                                                |
| `--sdk-package-version` | `dotnet migrate`                                                                               |

<span data-ttu-id="79c43-189">`--verbosity` 및 `--sdk-package-version`을 제외하면 다른 모든 값은 .NET Core 2.1.100 SDK부터 해시됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-189">Except for `--verbosity` and `--sdk-package-version`, all the other values are hashed starting with .NET Core 2.1.100 SDK.</span></span>

## <a name="net-clisdk-crash-exception-telemetry-collected"></a><span data-ttu-id="79c43-190">수집된 .NET CLI/SDK 크래시 예외 원격 분석</span><span class="sxs-lookup"><span data-stu-id="79c43-190">.NET CLI/SDK crash exception telemetry collected</span></span>

<span data-ttu-id="79c43-191">.NET CLI/SDK에서 크래시가 발생하면 CLI/SDK 코드의 예외 및 스택 추적 이름을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-191">If the .NET CLI/SDK crashes, it collects the name of the exception and stack trace of the CLI/SDK code.</span></span> <span data-ttu-id="79c43-192">이 정보는 문제를 평가하고 .NET SDK 및 CLI의 품질을 향상하기 위해 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-192">This information is collected to assess problems and improve the quality of the .NET SDK and CLI.</span></span> <span data-ttu-id="79c43-193">이 문서에서는 수집하는 데이터에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-193">This article provides information about the data we collect.</span></span> <span data-ttu-id="79c43-194">고유한 .NET SDK 버전을 빌드하는 사용자가 실수로 개인 정보나 중요한 정보를 공개하지 않도록 하는 방법에 대한 팁도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-194">It also provides tips on how users building their own version of the .NET SDK can avoid inadvertent disclosure of personal or sensitive information.</span></span>

### <a name="types-of-collected-data"></a><span data-ttu-id="79c43-195">수집되는 데이터의 유형</span><span class="sxs-lookup"><span data-stu-id="79c43-195">Types of collected data</span></span>

<span data-ttu-id="79c43-196">.NET CLI는 애플리케이션의 예외가 아닌 CLI/SDK 예외용 정보만 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-196">.NET CLI collects information for CLI/SDK exceptions only, not exceptions in your application.</span></span> <span data-ttu-id="79c43-197">수집된 데이터에는 예외 및 스택 추적의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-197">The collected data contains the name of the exception and the stack trace.</span></span> <span data-ttu-id="79c43-198">이 스택 추적은 CLI/SDK 코드와 관련됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-198">This stack trace is of CLI/SDK code.</span></span>

<span data-ttu-id="79c43-199">다음 예제는 수집되는 데이터의 종류를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-199">The following example shows the kind of data that is collected:</span></span>

```console
System.IO.IOException
at System.ConsolePal.WindowsConsoleStream.Write(Byte[] buffer, Int32 offset, Int32 count)
at System.IO.StreamWriter.Flush(Boolean flushStream, Boolean flushEncoder)
at System.IO.StreamWriter.Write(Char[] buffer)
at System.IO.TextWriter.WriteLine()
at System.IO.TextWriter.SyncTextWriter.WriteLine()
at Microsoft.DotNet.Cli.Utils.Reporter.WriteLine()
at Microsoft.DotNet.Tools.Run.RunCommand.EnsureProjectIsBuilt()
at Microsoft.DotNet.Tools.Run.RunCommand.Execute()
at Microsoft.DotNet.Tools.Run.RunCommand.Run(String[] args)
at Microsoft.DotNet.Cli.Program.ProcessArgs(String[] args, ITelemetry telemetryClient)
at Microsoft.DotNet.Cli.Program.Main(String[] args)
```

### <a name="avoid-inadvertent-disclosure-of-information"></a><span data-ttu-id="79c43-200">의도하지 않은 정보 공개 방지</span><span class="sxs-lookup"><span data-stu-id="79c43-200">Avoid inadvertent disclosure of information</span></span>

<span data-ttu-id="79c43-201">.NET 기여자 및 자체적으로 빌드한 .NET SDK 버전을 실행하는 다른 모든 사용자는 SDK 소스 코드의 경로를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-201">.NET contributors and anyone else running a version of the .NET SDK that they built themselves should consider the path to their SDK source code.</span></span> <span data-ttu-id="79c43-202">사용자 지정 디버그 빌드이거나 사용자 지정 빌드 기호 파일로 구성된 .NET SDK를 사용하는 동안 크래시가 발생하면 빌드 머신의 SDK 소스 파일 경로는 스택 추적의 일부로 수집되며 해시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-202">If a crash occurs while using a .NET SDK that is a custom debug build or configured with custom build symbol files, the SDK source file path from the build machine is collected as part of the stack trace and isn't hashed.</span></span>

<span data-ttu-id="79c43-203">따라서 .NET SDK의 사용자 지정 빌드는 경로 이름이 개인 정보나 중요한 정보를 노출하는 디렉터리에 있으면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79c43-203">Because of this, custom builds of the .NET SDK shouldn't be located in directories whose path names expose personal or sensitive information.</span></span>

## <a name="see-also"></a><span data-ttu-id="79c43-204">참조</span><span class="sxs-lookup"><span data-stu-id="79c43-204">See also</span></span>

- [<span data-ttu-id="79c43-205">.NET CLI 원격 분석 데이터</span><span class="sxs-lookup"><span data-stu-id="79c43-205">.NET CLI Telemetry Data</span></span>](https://dotnet.microsoft.com/platform/telemetry)
- [<span data-ttu-id="79c43-206">원격 분석 참조 소스(dotnet/sdk 리포지토리)</span><span class="sxs-lookup"><span data-stu-id="79c43-206">Telemetry reference source (dotnet/sdk repository)</span></span>](https://github.com/dotnet/sdk/tree/master/src/Cli/dotnet/Telemetry)
