---
title: ML.NET CLI의 원격 분석 수집
description: 어떤 데이터가 수집되고 수집 기능을 사용하지 않도록 설정하는 방법에 대한 분석을 위해 사용 정보를 수집하는 ML.NET CLI 원격 분석 기능을 살펴봅니다. 또한 Microsoft의 GDPR 규정 준수에 대한 정보와 .NET 라이선스 링크를 확인합니다.
ms.topic: conceptual
ms.date: 09/03/2019
ms.custom: mlnet-tooling
ms.openlocfilehash: 99e11acba343cc689c3219ca9316144fc62cd618
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "78849746"
---
# <a name="telemetry-collection-by-the-mlnet-cli"></a><span data-ttu-id="b2773-104">ML.NET CLI의 원격 분석 수집</span><span class="sxs-lookup"><span data-stu-id="b2773-104">Telemetry collection by the ML.NET CLI</span></span>

<span data-ttu-id="b2773-105">[ML.NET CLI](https://aka.ms/mlnet-cli)는 Microsoft에서 사용하기 위해 집계한 익명 사용량 현황 데이터를 수집하는 원격 분석 기능을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-105">The [ML.NET CLI](https://aka.ms/mlnet-cli) includes a telemetry feature that collects anonymous usage data that is aggregated for use by Microsoft.</span></span>

## <a name="how-microsoft-uses-the-data"></a><span data-ttu-id="b2773-106">Microsoft가 데이터를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="b2773-106">How Microsoft uses the data</span></span>

<span data-ttu-id="b2773-107">제품 팀에서는 ML.NET CLI 원격 분석 데이터를 사용하여 도구의 개선 방법을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-107">The product team uses ML.NET CLI telemetry data to help understand how to improve the tools.</span></span> <span data-ttu-id="b2773-108">예를 들어, 고객이 드물게 특정 기계 학습 작업을 사용할 경우 제품 팀은 그 원인을 조사하고 결과에 따라 기능 개발의 우선 순위를 정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-108">For example, if customers infrequently use a particular machine learning task, the product team investigates why and uses findings to prioritize feature development.</span></span> <span data-ttu-id="b2773-109">ML.NET CLI 원격 분석 분석은 충돌, 코드 예외 같은 문제의 디버깅에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-109">ML.NET CLI telemetry also helps with debugging of issues such as crashes and code anomalies.</span></span>

<span data-ttu-id="b2773-110">제품 팀은 이 인사이트가 중요하지만 모두가 이런 데이터를 보내고자 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-110">While the product team appreciates this insight, we also know that not everyone wants to send this data.</span></span> [<span data-ttu-id="b2773-111">원격 분석을 사용하지 않도록 설정하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-111">Find out how to disable telemetry.</span></span>](#opt-out-of-data-collection)

## <a name="scope"></a><span data-ttu-id="b2773-112">Scope</span><span class="sxs-lookup"><span data-stu-id="b2773-112">Scope</span></span>

<span data-ttu-id="b2773-113">`mlnet` 명령은 ML.NET CLI를 시작하지만 명령 자체는 원격 분석을 수집하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-113">The `mlnet` command launches the ML.NET CLI, but the command itself doesn't collect telemetry.</span></span>

<span data-ttu-id="b2773-114">연결된 명령 없이 `mlnet` 명령만 실행할 경우 원격 분석을 *사용할 수 없습니다*.</span><span class="sxs-lookup"><span data-stu-id="b2773-114">Telemetry *isn't enabled* when you run the `mlnet` command with no other command attached.</span></span> <span data-ttu-id="b2773-115">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="b2773-115">For example:</span></span>

- `mlnet`
- `mlnet --help`

<span data-ttu-id="b2773-116">`mlnet auto-train` 등, [ML.NET CLI 명령](../reference/ml-net-cli-reference.md)을 실행할 때는 원격 분석을 *사용합니다*.</span><span class="sxs-lookup"><span data-stu-id="b2773-116">Telemetry *is enabled* when you run an [ML.NET CLI command](../reference/ml-net-cli-reference.md), such as `mlnet auto-train`.</span></span>

## <a name="opt-out-of-data-collection"></a><span data-ttu-id="b2773-117">데이터 수집 옵트아웃</span><span class="sxs-lookup"><span data-stu-id="b2773-117">Opt out of data collection</span></span>

<span data-ttu-id="b2773-118">ML.NET CLI 원격 분석 기능은 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-118">The ML.NET CLI telemetry feature is enabled by default.</span></span>

<span data-ttu-id="b2773-119">`MLDOTNET_CLI_TELEMETRY_OPTOUT` 환경 변수를 `1` 또는 `true`로 설정하여 원격 분석 기능을 옵트아웃(opt out)합니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-119">Opt out of the telemetry feature by setting the `MLDOTNET_CLI_TELEMETRY_OPTOUT` environment variable to `1` or `true`.</span></span> <span data-ttu-id="b2773-120">이 환경 변수는 ML.NET CLI 도구에 전역적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-120">This environment variable applies globally to the ML.NET CLI tool.</span></span>

## <a name="data-points-collected"></a><span data-ttu-id="b2773-121">데이터 포인트 수집</span><span class="sxs-lookup"><span data-stu-id="b2773-121">Data points collected</span></span>

<span data-ttu-id="b2773-122">이 기능은 다음 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-122">The feature collects the following data:</span></span>

- <span data-ttu-id="b2773-123">`auto-train`과 같이 호출된 명령</span><span class="sxs-lookup"><span data-stu-id="b2773-123">What command was invoked, such as `auto-train`</span></span>
- <span data-ttu-id="b2773-124">사용된 명령줄 매개 변수 이름(예: "dataset-name, label-column-name, ml-task, output-path, max-exploration-time, verbosity")</span><span class="sxs-lookup"><span data-stu-id="b2773-124">Command-line parameter names used (that is, "dataset-name, label-column-name, ml-task, output-path, max-exploration-time, verbosity")</span></span>
- <span data-ttu-id="b2773-125">해시된 MAC 주소: 컴퓨터에 대한 암호화된(SHA256) 익명 및 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-125">Hashed MAC address: a cryptographically (SHA256) anonymous and unique ID for a machine</span></span>
- <span data-ttu-id="b2773-126">호출의 타임스탬프</span><span class="sxs-lookup"><span data-stu-id="b2773-126">Timestamp of an invocation</span></span>
- <span data-ttu-id="b2773-127">지리적 위치 확인에만 사용되는 8진수 IP 주소 3개(전체 IP 주소 아님)</span><span class="sxs-lookup"><span data-stu-id="b2773-127">Three octet IP address (not full IP address) used only to determine geographical location</span></span>
- <span data-ttu-id="b2773-128">모든 인수/사용된 매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="b2773-128">Name of all arguments/parameters used.</span></span> <span data-ttu-id="b2773-129">문자열 등, 고객의 값이 아님</span><span class="sxs-lookup"><span data-stu-id="b2773-129">Not the customer's values, such as strings</span></span>
- <span data-ttu-id="b2773-130">해시된 데이터 세트 파일 이름</span><span class="sxs-lookup"><span data-stu-id="b2773-130">Hashed dataset filename</span></span>
- <span data-ttu-id="b2773-131">데이터 세트 파일 크기 버킷</span><span class="sxs-lookup"><span data-stu-id="b2773-131">Dataset file-size bucket</span></span>
- <span data-ttu-id="b2773-132">운영 체제 및 버전</span><span class="sxs-lookup"><span data-stu-id="b2773-132">Operating system and version</span></span>
- <span data-ttu-id="b2773-133">작업 매개 변수의 값: 범주 값(예: `regression`, `binary-classification` 및 `multiclass-classification`)</span><span class="sxs-lookup"><span data-stu-id="b2773-133">Value of --task parameter: Categorical values, such as `regression`, `binary-classification`, and `multiclass-classification`</span></span>
- <span data-ttu-id="b2773-134">ML.NET CLI 버전(예: 0.3.27703.4)</span><span class="sxs-lookup"><span data-stu-id="b2773-134">ML.NET CLI version (that is, 0.3.27703.4)</span></span>

<span data-ttu-id="b2773-135">데이터는 [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) 기술을 사용하여 Microsoft 서버로 안전하게 전송되고, 제한된 액세스를 기준으로 보관되고, 안전한 [Azure Storage](https://azure.microsoft.com/services/storage/) 시스템에서 엄격한 보안 제어에 따라 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-135">The data is sent securely to Microsoft servers using [Azure Application Insights](https://azure.microsoft.com/services/application-insights/) technology, held under restricted access, and used under strict security controls from secure [Azure Storage](https://azure.microsoft.com/services/storage/) systems.</span></span>

### <a name="data-points-not-collected"></a><span data-ttu-id="b2773-136">데이터 포인트 수집 안 함</span><span class="sxs-lookup"><span data-stu-id="b2773-136">Data points not collected</span></span>

<span data-ttu-id="b2773-137">원격 분석 기능은 다음을 *수집하지 않습니다*.</span><span class="sxs-lookup"><span data-stu-id="b2773-137">The telemetry feature *doesn't* collect:</span></span>

- <span data-ttu-id="b2773-138">사용자 이름 등의 개인 데이터</span><span class="sxs-lookup"><span data-stu-id="b2773-138">personal data, such as usernames</span></span>
- <span data-ttu-id="b2773-139">데이터 세트 파일 이름</span><span class="sxs-lookup"><span data-stu-id="b2773-139">dataset filenames</span></span>
- <span data-ttu-id="b2773-140">데이터 세트 파일의 데이터</span><span class="sxs-lookup"><span data-stu-id="b2773-140">data from dataset files</span></span>

<span data-ttu-id="b2773-141">ML.NET CLI 원격 분석이 중요한 데이터를 수집하고 있는지 또는 데이터가 안전하지 않거나 부적절한 방식으로 처리되고 있는지 의심스러운 경우 조사를 위해 [ML.NET](https://github.com/dotnet/machinelearning) 리포지토리에서 문제를 보고하세요.</span><span class="sxs-lookup"><span data-stu-id="b2773-141">If you suspect that the ML.NET CLI telemetry is collecting sensitive data or that the data is being insecurely or inappropriately handled, file an issue in the [ML.NET](https://github.com/dotnet/machinelearning) repository for investigation.</span></span>

## <a name="license"></a><span data-ttu-id="b2773-142">라이선스</span><span class="sxs-lookup"><span data-stu-id="b2773-142">License</span></span>

<span data-ttu-id="b2773-143">ML.NET CLI의 Microsoft 배포는 [Microsoft 소프트웨어 사용 조건: Microsoft .NET 라이브러리](https://aka.ms/dotnet-core-eula)에 따라 라이선스가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-143">The Microsoft distribution of ML.NET CLI is licensed with the [Microsoft Software License Terms: Microsoft .NET Library](https://aka.ms/dotnet-core-eula).</span></span> <span data-ttu-id="b2773-144">데이터 수집 및 처리에 대한 자세한 내용은 "Data"라는 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2773-144">For details on data collection and processing, see the section entitled "Data."</span></span>

## <a name="disclosure"></a><span data-ttu-id="b2773-145">공개</span><span class="sxs-lookup"><span data-stu-id="b2773-145">Disclosure</span></span>

<span data-ttu-id="b2773-146">`mlnet auto-train` 같은 [ML.NET CLI 명령](../reference/ml-net-cli-reference.md)을 처음 실행하면 ML.NET CLI 도구가 원격 분석에서 옵트아웃하는 방법을 설명하는 공개 텍스트를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-146">When you first run a [ML.NET CLI command](../reference/ml-net-cli-reference.md) such as `mlnet auto-train`, the ML.NET CLI tool displays disclosure text that tells you how to opt out of telemetry.</span></span> <span data-ttu-id="b2773-147">실행 중인 CLI 버전에 따라 텍스트가 약간 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2773-147">Text may vary slightly depending on the version of the CLI you're running.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2773-148">참조</span><span class="sxs-lookup"><span data-stu-id="b2773-148">See also</span></span>

- [<span data-ttu-id="b2773-149">ML.NET CLI 참조</span><span class="sxs-lookup"><span data-stu-id="b2773-149">ML.NET CLI reference</span></span>](../reference/ml-net-cli-reference.md)
- [<span data-ttu-id="b2773-150">Microsoft 소프트웨어 사용 조건: Microsoft .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="b2773-150">Microsoft Software License Terms: Microsoft .NET Library</span></span>](https://aka.ms/dotnet-core-eula)
- [<span data-ttu-id="b2773-151">Microsoft 프라이버시</span><span class="sxs-lookup"><span data-stu-id="b2773-151">Privacy at Microsoft</span></span>](https://www.microsoft.com/trustcenter/privacy/)
- [<span data-ttu-id="b2773-152">Microsoft 개인정보처리방침</span><span class="sxs-lookup"><span data-stu-id="b2773-152">Microsoft Privacy Statement</span></span>](https://privacy.microsoft.com/privacystatement)
