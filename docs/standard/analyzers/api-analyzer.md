---
title: .NET API 분석기
description: .NET API 분석기가 사용되지 않는 API 및 플랫폼 호환성 문제를 발견하는 데 어떻게 도움이 되는지 알아봅니다.
author: oliag
ms.date: 02/20/2020
ms.technology: dotnet-standard
ms.openlocfilehash: e214c91f2beebc7f3b3324f4879deba9a5623f86
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "78156136"
---
# <a name="net-api-analyzer"></a><span data-ttu-id="7876f-103">.NET API 분석기</span><span class="sxs-lookup"><span data-stu-id="7876f-103">.NET API analyzer</span></span>

<span data-ttu-id="7876f-104">.NET API 분석기는 여러 플랫폼에서 C# API에 대한 잠재적 호환성 위험을 검색하고 사용되지 않는 API에 대한 호출을 감지하는 Roslyn 분석기입니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-104">The .NET API Analyzer is a Roslyn analyzer that discovers potential compatibility risks for C# APIs on different platforms and detects calls to deprecated APIs.</span></span> <span data-ttu-id="7876f-105">모든 개발 단계의 모든 C# 개발자에게 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-105">It can be useful for all C# developers at any stage of development.</span></span>

<span data-ttu-id="7876f-106">API 분석기는 NuGet 패키지 [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/)로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-106">API Analyzer comes as a NuGet package [Microsoft.DotNet.Analyzers.Compatibility](https://www.nuget.org/packages/Microsoft.DotNet.Analyzers.Compatibility/).</span></span> <span data-ttu-id="7876f-107">이 패키지를 프로젝트에서 참조한 후에는 패키지가 코드를 자동으로 모니터링하고 문제가 있는 API 사용을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-107">After you reference it in a project, it automatically monitors the code and indicates problematic API usage.</span></span> <span data-ttu-id="7876f-108">전구를 클릭하여 가능한 수정 사항에 대한 제안을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-108">You can also get suggestions on possible fixes by clicking on the light bulb.</span></span> <span data-ttu-id="7876f-109">드롭다운 메뉴에는 경고를 표시하지 않은 옵션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-109">The drop-down menu includes an option to suppress the warnings.</span></span>

> [!NOTE]
> <span data-ttu-id="7876f-110">.NET API 분석기는 여전히 시험판 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-110">The .NET API analyzer is still a pre-release version.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7876f-111">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7876f-111">Prerequisites</span></span>

- <span data-ttu-id="7876f-112">Visual Studio 2017 이상 버전 또는 Mac용 Visual Studio(모든 버전).</span><span class="sxs-lookup"><span data-stu-id="7876f-112">Visual Studio 2017 and later versions, or Visual Studio for Mac (all versions).</span></span>

## <a name="discover-deprecated-apis"></a><span data-ttu-id="7876f-113">사용되지 않는 API 검색</span><span class="sxs-lookup"><span data-stu-id="7876f-113">Discover deprecated APIs</span></span>

### <a name="what-are-deprecated-apis"></a><span data-ttu-id="7876f-114">사용되지 않는 API란 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="7876f-114">What are deprecated APIs?</span></span>

<span data-ttu-id="7876f-115">.NET 제품군은 고객의 요구 사항을 더 잘 해결하기 위해 지속적으로 업그레이드되는 대규모 제품 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-115">The .NET family is a set of large products that are constantly upgraded to better serve customer needs.</span></span> <span data-ttu-id="7876f-116">일부 API를 더 이상 사용하지 않고 새 API를 교체하는 것은 자연스러운 일입니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-116">It's natural to deprecate some APIs and replace them with new ones.</span></span> <span data-ttu-id="7876f-117">더 나은 대체가 있는 경우 API는 사용되지 않는 것으로 간주합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-117">An API is considered deprecated when a better alternative exists.</span></span> <span data-ttu-id="7876f-118">API가 사용되지 않으며 사용되면 안 된다는 것을 알리는 한 가지 방법은 <xref:System.ObsoleteAttribute> 특성을 사용하여 표시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-118">One way to inform that an API is deprecated and shouldn't be used is to mark it with the <xref:System.ObsoleteAttribute> attribute.</span></span> <span data-ttu-id="7876f-119">이 방법의 단점은 모든 사용되지 않는 API에 대한 진단 ID가 하나만 있다는 것입니다(C#의 경우 [CS0612](../../csharp/misc/cs0612.md)).</span><span class="sxs-lookup"><span data-stu-id="7876f-119">The disadvantage of this approach is that there is only one diagnostic ID for all obsolete APIs (for C#, [CS0612](../../csharp/misc/cs0612.md)).</span></span> <span data-ttu-id="7876f-120">이는 다음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-120">This means that:</span></span>

- <span data-ttu-id="7876f-121">각 사례에 대한 전용 문서를 포함할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-121">It's impossible to have dedicated documents for each case.</span></span>
- <span data-ttu-id="7876f-122">특정 경고 범주를 표시하지 않을 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-122">It's impossible to suppress certain category of warnings.</span></span> <span data-ttu-id="7876f-123">모든 경고를 표시하거나 아무것도 표시하지 않을 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-123">You can suppress either all or none of them.</span></span>
- <span data-ttu-id="7876f-124">사용자에게 새로운 사용 중단을 알리려면 참조된 어셈블리 또는 대상 패키지를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-124">To inform users of a new deprecation, a referenced assembly or targeting package has to be updated.</span></span>

<span data-ttu-id="7876f-125">API 분석기는 개별 경고 표시를 제어할 수 있는 DE(사용 중단 오류)로 시작하는 API 관련 오류 코드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-125">The API Analyzer uses API-specific error codes that begin with DE (which stands for Deprecation Error), which allows control over the display of individual warnings.</span></span> <span data-ttu-id="7876f-126">분석기가 식별하는 사용되지 않는 API는 [dotnet/platform-compat](https://github.com/dotnet/platform-compat) 리포지토리에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-126">The deprecated APIs identified by the analyzer are defined in the [dotnet/platform-compat](https://github.com/dotnet/platform-compat) repo.</span></span>

### <a name="add-the-api-analyzer-to-your-project"></a><span data-ttu-id="7876f-127">프로젝트에 API 분석기 추가</span><span class="sxs-lookup"><span data-stu-id="7876f-127">Add the API Analyzer to your project</span></span>

1. <span data-ttu-id="7876f-128">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-128">Open Visual Studio.</span></span>
2. <span data-ttu-id="7876f-129">분석기를 실행하려는 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-129">Open the project you want to run the analyzer on.</span></span>
3. <span data-ttu-id="7876f-130">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-130">In **Solution Explorer**, right-click on your project and choose **Manage NuGet Packages**.</span></span> <span data-ttu-id="7876f-131">(이 옵션은 **프로젝트** 메뉴에서도 사용 가능합니다.)</span><span class="sxs-lookup"><span data-stu-id="7876f-131">(This option is also available from the **Project** menu.)</span></span>
4. <span data-ttu-id="7876f-132">NuGet 패키지 관리자 탭에서</span><span class="sxs-lookup"><span data-stu-id="7876f-132">On the NuGet Package Manager tab:</span></span>
   1. <span data-ttu-id="7876f-133">패키지 원본으로 "nuget.org"를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-133">Select "nuget.org" as the Package source.</span></span>
   2. <span data-ttu-id="7876f-134">**찾아보기** 탭으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-134">Go to the **Browse** tab.</span></span>
   3. <span data-ttu-id="7876f-135">**시험판 포함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-135">Select **Include prerelease**.</span></span>
   4. <span data-ttu-id="7876f-136">**Microsoft.DotNet.Analyzers.Compatibility**를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-136">Search for **Microsoft.DotNet.Analyzers.Compatibility**.</span></span>
   5. <span data-ttu-id="7876f-137">목록에서 해당 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-137">Select that package in the list.</span></span>
   6. <span data-ttu-id="7876f-138">**설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-138">Select the **Install** button.</span></span>
   7. <span data-ttu-id="7876f-139">**변경 내용 미리 보기** 대화 상자에서 **확인** 단추를 선택한 다음, 나열된 패키지의 사용 조건에 동의하는 경우 **라이선스 승인** 대화 상자에서 **동의함** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-139">Select the **OK** button on the **Preview Changes** dialog and then select the **I Accept** button on the **License Acceptance** dialog if you agree with the license terms for the packages listed.</span></span>

### <a name="use-the-api-analyzer"></a><span data-ttu-id="7876f-140">API 분석기 사용</span><span class="sxs-lookup"><span data-stu-id="7876f-140">Use the API Analyzer</span></span>

<span data-ttu-id="7876f-141"><xref:System.Net.WebClient>와 같은 사용되지 않는 API가 코드에서 사용되는 경우 API 분석기는 녹색 물결선으로 API를 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-141">When a deprecated API, such as <xref:System.Net.WebClient>, is used in a code, API Analyzer highlights it with a green squiggly line.</span></span> <span data-ttu-id="7876f-142">API 호출을 마우스로 가리키면 다음 예제와 같이 API 사용 중단에 대한 정보가 포함된 전구가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-142">When you hover over the API call, a light bulb is displayed with information about the API deprecation, as in the following example:</span></span>

![“왼쪽에 있는 녹색 물결선과 전구가 있는 WebClient API의 스크린샷”](media/api-analyzer/green-squiggle.jpg)

<span data-ttu-id="7876f-144">다음 예제(`DE004`)와 같이 **오류 목록** 창에는 사용되지 않는 API별 고유 ID가 포함된 경고가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-144">The **Error List** window contains warnings with a unique ID per deprecated API, as shown in the following example (`DE004`):</span></span>

<span data-ttu-id="7876f-145">![“경고 ID 및 설명을 표시하는 오류 목록 창의 스크린샷”](media/api-analyzer/warnings-id-and-descriptions.jpg "경고가 포함된 오류 목록 창입니다.")</span><span class="sxs-lookup"><span data-stu-id="7876f-145">!["Screenshot of the Error List window showing warning's ID and description"](media/api-analyzer/warnings-id-and-descriptions.jpg "Error List window that includes warnings.")</span></span>

<span data-ttu-id="7876f-146">ID를 클릭하면 API가 사용되지 않는 이유에 대한 자세한 정보와 사용할 수 있는 대체 API에 대한 제안이 있는 웹 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-146">By clicking on the ID, you go to a webpage with detailed information about why the API was deprecated and suggestions regarding alternative APIs that can be used.</span></span>

<span data-ttu-id="7876f-147">강조 표시된 멤버를 마우스 오른쪽 단추로 클릭하고 **\<진단 ID>을(를) 표시하지 않음**을 선택하여 모든 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-147">Any warnings can be suppressed by right-clicking on the highlighted member and selecting **Suppress \<diagnostic ID>**.</span></span> <span data-ttu-id="7876f-148">경고를 표시하지 않는 두 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-148">There are two ways to suppress warnings:</span></span>

- [<span data-ttu-id="7876f-149">로컬로(소스)</span><span class="sxs-lookup"><span data-stu-id="7876f-149">locally (in source)</span></span>](#suppress-warnings-locally)
- <span data-ttu-id="7876f-150">[전역으로(비표시 오류(Suppression) 파일)](#suppress-warnings-globally) - 권장됨</span><span class="sxs-lookup"><span data-stu-id="7876f-150">[globally (in a suppression file)](#suppress-warnings-globally) - recommended</span></span>

### <a name="suppress-warnings-locally"></a><span data-ttu-id="7876f-151">로컬로 경고 표시 안 함</span><span class="sxs-lookup"><span data-stu-id="7876f-151">Suppress warnings locally</span></span>

<span data-ttu-id="7876f-152">로컬로 경고를 표시하지 않으려면 경고를 표시하지 않을 멤버를 마우스 오른쪽 단추로 클릭한 다음, **빠른 작업 및 리팩터링** >  **‘진단 ID’ 표시 안 함\<진단 ID>**  > **소스**를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="7876f-152">To suppress warnings locally, right-click on the member you want to suppress warnings for and then select **Quick Actions and Refactorings** > **Suppress *diagnostic ID*\<diagnostic ID>** > **in Source**.</span></span> <span data-ttu-id="7876f-153">[#pragma](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) 경고 전처리기 지시문이 정의된 범위의 소스 코드에 추가됩니다. !["#pragma warning disable로 묶인 코드의 스크린샷"](media/api-analyzer/suppress-in-source.jpg)</span><span class="sxs-lookup"><span data-stu-id="7876f-153">The [#pragma](../../csharp/language-reference/preprocessor-directives/preprocessor-pragma-warning.md) warning preprocessor directive is added to your source code in the scope defined: !["Screenshot of code framed with #pragma warning disable"](media/api-analyzer/suppress-in-source.jpg)</span></span>

### <a name="suppress-warnings-globally"></a><span data-ttu-id="7876f-154">전역으로 경고 표시 안 함</span><span class="sxs-lookup"><span data-stu-id="7876f-154">Suppress warnings globally</span></span>

<span data-ttu-id="7876f-155">전역으로 경고를 표시하지 않으려면 경고를 표시하지 않을 멤버를 마우스 오른쪽 단추로 클릭한 다음, **빠른 작업 및 리팩터링** >  **‘진단 ID’ 표시 안 함\<진단 ID>**  > **비표시 오류(Suppression) 파일**을 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="7876f-155">To suppress warnings globally, right-click on the member you want to suppress warnings for and then select **Quick Actions and Refactorings** > **Suppress *diagnostic ID*\<diagnostic ID>** > **in Suppression File**.</span></span>

![“왼쪽에 있는 녹색 물결선과 전구가 있는 WebClient API의 스크린샷”](media/api-analyzer/suppress-in-sup-file.jpg)

<span data-ttu-id="7876f-157">*GlobalSuppressions.cs* 파일이 첫 번째 비표시 오류(Supression) 후에 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-157">A *GlobalSuppressions.cs* file is added to your project after the first suppression.</span></span> <span data-ttu-id="7876f-158">새 전역 비표시 오류(Supression)가 이 파일에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-158">New global suppressions are appended to this file.</span></span>

![“왼쪽에 있는 녹색 물결선과 전구가 있는 WebClient API의 스크린샷”](media/api-analyzer/suppression-file.jpg)

<span data-ttu-id="7876f-160">전역 비표시 오류(Supression)는 여러 프로젝트에서 API 사용의 일관성을 보장하는 권장 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-160">Global suppression is the recommended way to ensure consistency of API usage across projects.</span></span>

## <a name="discover-cross-platform-issues"></a><span data-ttu-id="7876f-161">플랫폼 간 문제 검색</span><span class="sxs-lookup"><span data-stu-id="7876f-161">Discover cross-platform issues</span></span>

<span data-ttu-id="7876f-162">사용되지 않는 API와 비슷하게 분석기는 플랫폼 간이 아닌 모든 API를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-162">Similar to deprecated APIs, the analyzer identifies all APIs that are not cross-platform.</span></span> <span data-ttu-id="7876f-163">예를 들어 <xref:System.Console.WindowWidth?displayProperty=nameWithType>는 Windows에서 작동하지만 Linux 및 macOS에서는 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-163">For example, <xref:System.Console.WindowWidth?displayProperty=nameWithType> works on Windows but not on Linux and macOS.</span></span> <span data-ttu-id="7876f-164">진단 ID는 **오류 목록** 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-164">The diagnostic ID is shown in the **Error List** window.</span></span> <span data-ttu-id="7876f-165">마우스 오른쪽 단추를 클릭하고 **빠른 작업 및 리팩터링**을 선택하여 해당 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-165">You can suppress that warning by right-clicking and selecting **Quick Actions and Refactorings**.</span></span> <span data-ttu-id="7876f-166">예를 들어 두 개의 옵션(사용되지 않는 멤버를 계속 사용하고 경고를 표시하지 않음 또는 전혀 사용하지 않음)이 있는 사용 중단 사례와 달리, 여기서는 특정 플랫폼에 대한 코드만 개발하는 경우 코드를 실행할 계획이 없는 모든 다른 플랫폼에 대한 모든 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-166">Unlike deprecation cases where you have two options (either keep using the deprecated member and suppress warnings or not use it at all), here if you're developing your code only for certain platforms, you can suppress all warnings for all other platforms you don't plan to run your code on.</span></span> <span data-ttu-id="7876f-167">이렇게 하려면 프로젝트 파일을 편집하고 무시할 모든 플랫폼을 나열하는 `PlatformCompatIgnore` 속성을 추가하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-167">To do so, you just need to edit your project file and add the `PlatformCompatIgnore` property that lists all platforms to be ignored.</span></span> <span data-ttu-id="7876f-168">허용되는 값은 `Linux`, `macOS` 및 `Windows`입니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-168">The accepted values are: `Linux`, `macOS`, and `Windows`.</span></span>

```xml
<PropertyGroup>
    <PlatformCompatIgnore>Linux;macOS</PlatformCompatIgnore>
</PropertyGroup>
```

<span data-ttu-id="7876f-169">코드가 여러 플랫폼을 대상으로 하고 이들 중 일부에서 지원되지 않는 API를 활용하려는 경우 코드의 해당 파트를 `if` 문으로 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-169">If your code targets multiple platforms and you want to take advantage of an API not supported on some of them, you can guard that part of the code with an `if` statement:</span></span>

```csharp
if (RuntimeInformation.IsOSPlatform(OSPlatform.Windows))
{
     var w = Console.WindowWidth;
     // More code
}
```

<span data-ttu-id="7876f-170">대상 프레임워크/운영 체제별로 조건부로 컴파일할 수도 있지만 현재는 해당 작업을 [수동으로](../frameworks.md#how-to-specify-target-frameworks) 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-170">You can also conditionally compile per target framework/operating system, but you currently need to do that [manually](../frameworks.md#how-to-specify-target-frameworks).</span></span>

## <a name="supported-diagnostics"></a><span data-ttu-id="7876f-171">지원되는 진단</span><span class="sxs-lookup"><span data-stu-id="7876f-171">Supported diagnostics</span></span>

<span data-ttu-id="7876f-172">현재 분석기는 다음과 같은 경우를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-172">Currently, the analyzer handles the following cases:</span></span>

- <span data-ttu-id="7876f-173"><xref:System.PlatformNotSupportedException>(PC001)을 throw하는 .NET Standard API 사용.</span><span class="sxs-lookup"><span data-stu-id="7876f-173">Usage of a .NET Standard API that throws <xref:System.PlatformNotSupportedException> (PC001).</span></span>
- <span data-ttu-id="7876f-174">.NET Framework 4.6.1(PC002)에서 사용할 수 없는 .NET Standard API 사용.</span><span class="sxs-lookup"><span data-stu-id="7876f-174">Usage of a .NET Standard API that isn't available on the .NET Framework 4.6.1 (PC002).</span></span>
- <span data-ttu-id="7876f-175">UWP(PC003)에 존재하지 않는 네이티브 API 사용.</span><span class="sxs-lookup"><span data-stu-id="7876f-175">Usage of a native API that doesn’t exist in UWP (PC003).</span></span>
- <span data-ttu-id="7876f-176">Delegate.BeginInvoke 및 EndInvoke API(PC004) 사용.</span><span class="sxs-lookup"><span data-stu-id="7876f-176">Usage of Delegate.BeginInvoke and EndInvoke APIs (PC004).</span></span>
- <span data-ttu-id="7876f-177">사용되지 않음(DEXXXX)으로 표시된 API 사용.</span><span class="sxs-lookup"><span data-stu-id="7876f-177">Usage of an API that is marked as deprecated (DEXXXX).</span></span>

## <a name="ci-machine"></a><span data-ttu-id="7876f-178">CI 컴퓨터</span><span class="sxs-lookup"><span data-stu-id="7876f-178">CI machine</span></span>

<span data-ttu-id="7876f-179">이러한 모든 진단은 IDE뿐 아니라 명령줄에서도 CI 서버가 포함된 프로젝트 빌드의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-179">All these diagnostics are available not only in the IDE, but also on the command line as part of building your project, which includes the CI server.</span></span>

## <a name="configuration"></a><span data-ttu-id="7876f-180">Configuration</span><span class="sxs-lookup"><span data-stu-id="7876f-180">Configuration</span></span>

<span data-ttu-id="7876f-181">사용자는 진단을 처리하는 방법을 경고, 오류, 제안 또는 해제로 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-181">The user decides how the diagnostics should be treated: as warnings, errors, suggestions, or to be turned off.</span></span> <span data-ttu-id="7876f-182">예를 들어 설계자가 호환성 문제를 오류로 처리하도록 결정하면 일부 사용되지 않는 API에 대한 호출은 경고를 생성하지만 다른 API에 대한 호출은 제안만 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-182">For example, as an architect, you can decide that compatibility issues should be treated as errors, calls to some deprecated APIs generate warnings, while others only generate suggestions.</span></span> <span data-ttu-id="7876f-183">이 방법은 진단 ID 및 프로젝트별로 별도로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-183">You can configure this separately by diagnostic ID and by project.</span></span> <span data-ttu-id="7876f-184">**솔루션 탐색기**에서 이를 수행하려면 프로젝트 아래의 **종속성** 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-184">To do so in **Solution Explorer**, navigate to the **Dependencies** node under your project.</span></span> <span data-ttu-id="7876f-185">노드 **종속성** > **분석** > **Microsoft.DotNet.Analyzers.Compatibility**를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-185">Expand the nodes **Dependencies** > **Analyzers** > **Microsoft.DotNet.Analyzers.Compatibility**.</span></span> <span data-ttu-id="7876f-186">진단 ID를 마우스 오른쪽 단추로 클릭하고 **규칙 집합 심각도 설정**을 선택하고 원하는 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7876f-186">Right click on the diagnostic ID, select **Set Rule Set Severity** and pick the desired option.</span></span>

![“진단 및 규칙 집합 심각도가 있는 팝업 대화 상자를 표시하는 솔루션 탐색기의 스크린샷”](media/api-analyzer/disable-notifications.jpg)

## <a name="see-also"></a><span data-ttu-id="7876f-188">참조</span><span class="sxs-lookup"><span data-stu-id="7876f-188">See also</span></span>

- <span data-ttu-id="7876f-189">[API 분석기 소개](https://devblogs.microsoft.com/dotnet/introducing-api-analyzer/) 블로그 게시물.</span><span class="sxs-lookup"><span data-stu-id="7876f-189">[Introducing API Analyzer](https://devblogs.microsoft.com/dotnet/introducing-api-analyzer/) blog post.</span></span>
- <span data-ttu-id="7876f-190">YouTube의 [API 분석기](https://youtu.be/eeBEahYXGd0) 데모 동영상.</span><span class="sxs-lookup"><span data-stu-id="7876f-190">[API Analyzer](https://youtu.be/eeBEahYXGd0) demo video on YouTube.</span></span>
