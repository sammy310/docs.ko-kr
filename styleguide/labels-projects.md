---
ms.openlocfilehash: 99153bb9cf3287951a1e52e716c799ee64eb82ad
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78950987"
---
# <a name="labels-and-projects-roadmap"></a><span data-ttu-id="aad30-101">레이블 및 프로젝트 로드맵</span><span class="sxs-lookup"><span data-stu-id="aad30-101">Labels and projects roadmap</span></span>

<span data-ttu-id="aad30-102">.NET docs 팀은 [GitHub 레이블](https://github.com/dotnet/docs/labels)을 광범위하게 사용하여 작업을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-102">The .NET docs team makes extensive use of [GitHub labels](https://github.com/dotnet/docs/labels) to organize our work.</span></span> <span data-ttu-id="aad30-103">레이블 조합을 필터링하여 [.NET docs 웹 사이트](https://docs.microsoft.com/dotnet)의 관심 섹션에 빠르게 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-103">By filtering on combinations of labels, we can quickly focus on sections of interest on the [.NET docs website](https://docs.microsoft.com/dotnet).</span></span>

<span data-ttu-id="aad30-104">또한 [GitHub 프로젝트](https://github.com/dotnet/docs/projects)를 사용하여 스프린트 및 기타 목표 지향 에픽을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-104">We also use [GitHub projects](https://github.com/dotnet/docs/projects) to organize sprints and other goal-oriented epics.</span></span>

<span data-ttu-id="aad30-105">이 로드맵에서는 이러한 조직 도구를 사용하는 방법을 설명하고 관심 영역을 찾는 데 사용하는 편리한 필터 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-105">This roadmap explains how we use these organizational tools and has links to handy filters we use to find areas of interest.</span></span>

## <a name="labels"></a><span data-ttu-id="aad30-106">레이블</span><span class="sxs-lookup"><span data-stu-id="aad30-106">Labels</span></span>

<span data-ttu-id="aad30-107">[dotnet/docs](https://github.com/dotnet/docs)를 처음 사용하는 경우에는 [일반](https://github.com/dotnet/docs/labels/up-for-grabs) 문제부터 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="aad30-107">If this is your first experience contributing to [dotnet/docs](https://github.com/dotnet/docs), start with the [up-for-grabs](https://github.com/dotnet/docs/labels/up-for-grabs) issues.</span></span> <span data-ttu-id="aad30-108">이러한 문제는 더 집중적인 범위가 있는 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-108">These are issues that have a more focused scope.</span></span> <span data-ttu-id="aad30-109">첫 번째 기여를 만드는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-109">They are a great way to make your first contribution.</span></span> <span data-ttu-id="aad30-110">일반 보기에서 영역 및 우선 순위를 기준으로 문제를 추가로 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-110">From the up-for-grabs view, you can further filter issues based on areas and priority.</span></span> <span data-ttu-id="aad30-111">작은 규모의 첫 번째 기여를 시도하려는 경우 [처음 사용하기 좋은 문제](https://github.com/dotnet/docs/labels/good-first-issue)로 초보자에게 좋은 문제를 식별했습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-111">We've identified good issues for beginners with the [good-first-issue](https://github.com/dotnet/docs/labels/good-first-issue) if you want to try a smaller first contribution.</span></span>

<span data-ttu-id="aad30-112">레이블을 사용하여 다양한 방법으로 문제를 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-112">We use labels to classify issues in many different ways:</span></span>

- <span data-ttu-id="aad30-113">[.NET 가이드](#find-a-single-net-guide) 및 [가이드 섹션](#search-one-section-of-a-guide)</span><span class="sxs-lookup"><span data-stu-id="aad30-113">[.NET Guides](#find-a-single-net-guide) and [sections of a guide](#search-one-section-of-a-guide).</span></span>
- [<span data-ttu-id="aad30-114">대상 릴리스</span><span class="sxs-lookup"><span data-stu-id="aad30-114">Target release</span></span>](#releases)
- [<span data-ttu-id="aad30-115">우선 순위</span><span class="sxs-lookup"><span data-stu-id="aad30-115">Priority</span></span>](#priority)

<span data-ttu-id="aad30-116">각 집합(가이드, 릴리스, 우선 순위)의 레이블을 결합하여 좁은 범위로 만들고 작업하려는 문제를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-116">You can combine a label from each set (guide, release, priority) to create a narrow focus to find issues you want to work on.</span></span>

### <a name="find-a-single-net-guide"></a><span data-ttu-id="aad30-117">단일 .NET 가이드 찾기</span><span class="sxs-lookup"><span data-stu-id="aad30-117">Find a single .NET guide</span></span>

<span data-ttu-id="aad30-118">각 아키텍처 전자책 및 각 .NET 가이드에 대해 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-118">We use labels for each of the architecture e-books and for each .NET Guide.</span></span>

<span data-ttu-id="aad30-119">![:book: 연한 녹색 배경의 가이드](./images/guide.png "아키텍처 가이드 레이블의 접두사")</span><span class="sxs-lookup"><span data-stu-id="aad30-119">![:book: guide on light green background](./images/guide.png "Prefix for architecture guide labels")</span></span>

<span data-ttu-id="aad30-120">아키텍처 전자책은 `:book: guide` 접두사로 표시되며 연한 녹색 배경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-120">Architecture e-books are noted with the `:book: guide` prefix and have a light green background.</span></span> <span data-ttu-id="aad30-121">다음은 권장 아키텍처를 다루는 긴 형식의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-121">These are the long-form areas that cover recommended architecture.</span></span> <span data-ttu-id="aad30-122">각 .NET 아키텍처 가이드에 대해 필터링된 현재 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-122">Here are current issues filtered for each of the .NET architecture guides.</span></span>

- [<span data-ttu-id="aad30-123">ASP.NET Core 웹앱</span><span class="sxs-lookup"><span data-stu-id="aad30-123">ASP.NET Core web apps</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20ASP.NET%20Core%20web%20apps)
- [<span data-ttu-id="aad30-124">Blazor</span><span class="sxs-lookup"><span data-stu-id="aad30-124">Blazor</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Blazor)
- [<span data-ttu-id="aad30-125">클라우드 네이티브</span><span class="sxs-lookup"><span data-stu-id="aad30-125">Cloud Native</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Cloud%20Native)
- [<span data-ttu-id="aad30-126">Docker 수명 주기</span><span class="sxs-lookup"><span data-stu-id="aad30-126">Docker lifecycle</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Docker%20lifecycle)
- [<span data-ttu-id="aad30-127">gRPC</span><span class="sxs-lookup"><span data-stu-id="aad30-127">gRPC</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20gRPC)
- [<span data-ttu-id="aad30-128">w/ Windows 컨테이너 현대화</span><span class="sxs-lookup"><span data-stu-id="aad30-128">Modernizing w/ Windows containers</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Modernizing%20w%2F%20Windows%20containers)
- [<span data-ttu-id="aad30-129">.NET 마이크로 서비스</span><span class="sxs-lookup"><span data-stu-id="aad30-129">.NET Microservices</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20.NET%20Microservices)
- [<span data-ttu-id="aad30-130">서버를 사용하지 않는 앱</span><span class="sxs-lookup"><span data-stu-id="aad30-130">Serverless apps</span></span>](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Serverless%20apps)

<span data-ttu-id="aad30-131">이 레이블 스타일은 [프레임워크 디자인 지침](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines)에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-131">This label style is also applied to the [Framework design guidelines](https://github.com/dotnet/docs/labels/%3Abook%3A%20guide%20-%20Framework%20Design%20Guidelines).</span></span> <span data-ttu-id="aad30-132">이 영역의 레이블 디자인은 동일하지만 커뮤니티 PR은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-132">This area has the same label design, but community PRs are discouraged.</span></span> <span data-ttu-id="aad30-133">이는 허가를 받아 재인쇄된 자료이므로 편집해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-133">This is material reprinted with permission and should not be edited.</span></span>

<span data-ttu-id="aad30-134">![:books: 진한 파란색 배경의 영역](./images/area.png ".NET 가이드 영역 레이블의 접두사")</span><span class="sxs-lookup"><span data-stu-id="aad30-134">![:books: Area on dark blue background](./images/area.png "Prefix for .NET Guide area labels")</span></span>

<span data-ttu-id="aad30-135">각 .NET 가이드는 `:books: Area` 접두사로 표시되며 진한 파란색 배경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-135">Each .NET Guide is noted with the `:books: Area` prefix and has a dark blue background.</span></span> <span data-ttu-id="aad30-136">각 .NET 가이드에 대해 필터링된 현재 문제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-136">Here are current issues filtered for each of the .NET guides.</span></span>

- [<span data-ttu-id="aad30-137">API 참조</span><span class="sxs-lookup"><span data-stu-id="aad30-137">API Reference</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20API%20Reference)
- [<span data-ttu-id="aad30-138">Azure .NET SDK</span><span class="sxs-lookup"><span data-stu-id="aad30-138">Azure .NET SDK</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Azure%20.NET%20SDk)
- [<span data-ttu-id="aad30-139">C# 가이드</span><span class="sxs-lookup"><span data-stu-id="aad30-139">C# Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20C%23%20Guide)
- [<span data-ttu-id="aad30-140">데스크톱 가이드</span><span class="sxs-lookup"><span data-stu-id="aad30-140">Desktop Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Desktop%20Guide)
- [<span data-ttu-id="aad30-141">F# 가이드</span><span class="sxs-lookup"><span data-stu-id="aad30-141">F# Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20F%23%20Guide)
- [<span data-ttu-id="aad30-142">ML.NET 가이드</span><span class="sxs-lookup"><span data-stu-id="aad30-142">ML.NET Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20ML.NET%20Guide)
- <span data-ttu-id="aad30-143">[.NET 아키텍처 가이드](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) - 제거 가능</span><span class="sxs-lookup"><span data-stu-id="aad30-143">[.NET Architecture Guide](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Architecture%20Guide) - Could be removed</span></span>
- [<span data-ttu-id="aad30-144">.NET Core 가이드</span><span class="sxs-lookup"><span data-stu-id="aad30-144">.NET Core Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Core%20Guide)
- [<span data-ttu-id="aad30-145">Apache Spark 가이드용 .NET</span><span class="sxs-lookup"><span data-stu-id="aad30-145">.NET for Apache Spark Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20for%20Apache%20Spark%20Guide)
- [<span data-ttu-id="aad30-146">.NET Framework 가이드</span><span class="sxs-lookup"><span data-stu-id="aad30-146">.NET Framework Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Framework%20Guide)
- [<span data-ttu-id="aad30-147">.NET 가이드</span><span class="sxs-lookup"><span data-stu-id="aad30-147">.NET Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20.NET%20Guide)
- <span data-ttu-id="aad30-148">[Roslyn API 참조](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) - 제거 가능</span><span class="sxs-lookup"><span data-stu-id="aad30-148">[Roslyn API Reference](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Roslyn%20API%20Reference) - could be removed.</span></span>
- [<span data-ttu-id="aad30-149">Visual Basic 가이드</span><span class="sxs-lookup"><span data-stu-id="aad30-149">Visual Basic Guide</span></span>](https://github.com/dotnet/docs/labels/%3Abooks%3A%20Area%20-%20Visual%20Basic%20Guide)

#### <a name="search-one-section-of-a-guide"></a><span data-ttu-id="aad30-150">가이드의 한 섹션 검색</span><span class="sxs-lookup"><span data-stu-id="aad30-150">Search one section of a guide</span></span>

<span data-ttu-id="aad30-151">![:card_file_box: 감색 배경의 영역](./images/technology.png ".NET 가이드 하위 영역 레이블의 접두사")</span><span class="sxs-lookup"><span data-stu-id="aad30-151">![:card_file_box: Area on medium blue background](./images/technology.png "Prefix for .NET Guide sub-area labels")</span></span>

<span data-ttu-id="aad30-152">.NET 가이드는 대용량이므로 이 레이블은 가이드 섹션별로 범위를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-152">The .NET guides are large, so these labels further limit the scope by a section of a guide.</span></span> <span data-ttu-id="aad30-153">각 .NET 가이드 하위 영역은 `:card_file_box: Technology` 접두사로 표시되며 감색 배경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-153">Each .NET Guide subarea is noted with the `:card_file_box: Technology` prefix and has a medium blue background.</span></span> <span data-ttu-id="aad30-154">이러한 레이블의 대부분은 여러 가이드에 적용되고, 일부는 하나의 가이드에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-154">Many of these labels apply to multiple guides, while others are in only one guide.</span></span> <span data-ttu-id="aad30-155">영역을 필터링한 후 이러한 레이블 중 하나를 추가하여 문제 범위를 추가로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-155">After filtering on an area, add one of these labels to further limit the scope of issues.</span></span>

- <span data-ttu-id="aad30-156">AppCompat</span><span class="sxs-lookup"><span data-stu-id="aad30-156">AppCompat</span></span>
- <span data-ttu-id="aad30-157">비동기 작업</span><span class="sxs-lookup"><span data-stu-id="aad30-157">Async Task</span></span>
- <span data-ttu-id="aad30-158">C# 고급 개념</span><span class="sxs-lookup"><span data-stu-id="aad30-158">C# Advanced concepts</span></span>
- <span data-ttu-id="aad30-159">C# 컴파일러</span><span class="sxs-lookup"><span data-stu-id="aad30-159">C# compiler</span></span>
- <span data-ttu-id="aad30-160">C# 기초</span><span class="sxs-lookup"><span data-stu-id="aad30-160">C# Fundamentals</span></span>
- <span data-ttu-id="aad30-161">C# 시작하기</span><span class="sxs-lookup"><span data-stu-id="aad30-161">C# Get Started</span></span>
- <span data-ttu-id="aad30-162">C# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="aad30-162">C# Language Reference</span></span>
- <span data-ttu-id="aad30-163">C# Null 보안</span><span class="sxs-lookup"><span data-stu-id="aad30-163">C# Null safety</span></span>
- <span data-ttu-id="aad30-164">C# 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="aad30-164">C# What's new</span></span>
- <span data-ttu-id="aad30-165">CLI</span><span class="sxs-lookup"><span data-stu-id="aad30-165">CLI</span></span>
- <span data-ttu-id="aad30-166">데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="aad30-166">Data Access</span></span>
- <span data-ttu-id="aad30-167">Docker</span><span class="sxs-lookup"><span data-stu-id="aad30-167">Docker</span></span>
- <span data-ttu-id="aad30-168">설치 관리자</span><span class="sxs-lookup"><span data-stu-id="aad30-168">Installers</span></span>
- <span data-ttu-id="aad30-169">LINQ</span><span class="sxs-lookup"><span data-stu-id="aad30-169">LINQ</span></span>
- <span data-ttu-id="aad30-170">NCL</span><span class="sxs-lookup"><span data-stu-id="aad30-170">NCL</span></span>
- <span data-ttu-id="aad30-171">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="aad30-171">.NET Standard</span></span>
- <span data-ttu-id="aad30-172">Roslyn API</span><span class="sxs-lookup"><span data-stu-id="aad30-172">Roslyn APIs</span></span>
- <span data-ttu-id="aad30-173">보안</span><span class="sxs-lookup"><span data-stu-id="aad30-173">Security</span></span>
- <span data-ttu-id="aad30-174">WCF</span><span class="sxs-lookup"><span data-stu-id="aad30-174">WCF</span></span>
- <span data-ttu-id="aad30-175">WF</span><span class="sxs-lookup"><span data-stu-id="aad30-175">WF</span></span>
- <span data-ttu-id="aad30-176">WIF</span><span class="sxs-lookup"><span data-stu-id="aad30-176">WIF</span></span>
- <span data-ttu-id="aad30-177">WinForms</span><span class="sxs-lookup"><span data-stu-id="aad30-177">WinForms</span></span>
- <span data-ttu-id="aad30-178">WPF</span><span class="sxs-lookup"><span data-stu-id="aad30-178">WPF</span></span>

### <a name="releases"></a><span data-ttu-id="aad30-179">릴리스</span><span class="sxs-lookup"><span data-stu-id="aad30-179">Releases</span></span>

<span data-ttu-id="aad30-180">![:checkered_flag: 릴리스: 진한 노랑](./images/release.png "릴리스 레이블의 접두사")</span><span class="sxs-lookup"><span data-stu-id="aad30-180">![:checkered_flag: Release: on dark yellow](./images/release.png "Prefix for release labels")</span></span>

<span data-ttu-id="aad30-181">특정 릴리스에 대해 태그가 지정된 문제는 `:checkered_flag: Release:` 접두사로 표시되고 진한 노란색 배경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-181">Issues tagged for a specific release are noted with the `:checkered_flag: Release:` prefix and have a dark yellow background.</span></span>

- <span data-ttu-id="aad30-182">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="aad30-182">.NET Core 2.2</span></span>
- <span data-ttu-id="aad30-183">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="aad30-183">.NET Core 3.0</span></span>

### <a name="priority"></a><span data-ttu-id="aad30-184">우선 순위</span><span class="sxs-lookup"><span data-stu-id="aad30-184">Priority</span></span>

<span data-ttu-id="aad30-185">우선 순위 레이블은 모두 `P` 뒤에 단일 숫자가 옵니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-185">Priority labels are all `P` followed by a single digit.</span></span> <span data-ttu-id="aad30-186">숫자가 낮을수록 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-186">Lower numbers are higher priority:</span></span>

- <span data-ttu-id="aad30-187">P0</span><span class="sxs-lookup"><span data-stu-id="aad30-187">P0</span></span>
- <span data-ttu-id="aad30-188">P1</span><span class="sxs-lookup"><span data-stu-id="aad30-188">P1</span></span>
- <span data-ttu-id="aad30-189">P2</span><span class="sxs-lookup"><span data-stu-id="aad30-189">P2</span></span>

### <a name="what-about-the-other-labels"></a><span data-ttu-id="aad30-190">나머지 레이블은 무엇일까요?</span><span class="sxs-lookup"><span data-stu-id="aad30-190">What about the other labels?</span></span>

<span data-ttu-id="aad30-191">콘텐츠 팀에서 다양한 문제 분류를 관리하기 위해 사용하는 다른 레이블이 많이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-191">There are many other labels used by the content teams to manage different classifications of issues.</span></span> <span data-ttu-id="aad30-192">콘텐츠 팀에 있지 않은 경우에는 이러한 다른 레이블을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-192">If you're not on the content team, you can ignore these other labels.</span></span>

## <a name="projects"></a><span data-ttu-id="aad30-193">프로젝트</span><span class="sxs-lookup"><span data-stu-id="aad30-193">Projects</span></span>

<span data-ttu-id="aad30-194">참가자는 [.NET 커뮤니티 협력자에 대한 프로젝트](https://github.com/dotnet/docs/projects/35)를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-194">Contributors should check the [Projects for .NET community collaborators](https://github.com/dotnet/docs/projects/35).</span></span> <span data-ttu-id="aad30-195">유지 관리, 문서 업데이트 및 새 콘텐츠 작업을 위해 다른 열을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-195">We've created different columns for maintenance, document updates, and new content tasks.</span></span> <span data-ttu-id="aad30-196">이를 통해 관심 작업을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-196">This can be a way to find tasks of interest.</span></span> <span data-ttu-id="aad30-197">(위에 설명 된 레이블을 사용하여 프로젝트 보기를 필터링할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="aad30-197">(Note that the project view can be filtered using the labels described above.)</span></span>

<span data-ttu-id="aad30-198">또한 다음과 같은 두 가지 방법으로 프로젝트를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-198">We also use projects in two other ways:</span></span>

- <span data-ttu-id="aad30-199">월 YYYY 프로젝트 형식: 각 월의 작업 계획에 대한 스크럼 보드입니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-199">Month YYYY project types: These are scrum boards for each month's working plan.</span></span>
- <span data-ttu-id="aad30-200">장기 실행 에픽: 이러한 작업은 여러 달 동안 작업을 수행하는 경우 목표를 달성하기 위해 작업을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aad30-200">Long-running epics: These are used to organize tasks toward a goal when the work will occur over several months.</span></span>
