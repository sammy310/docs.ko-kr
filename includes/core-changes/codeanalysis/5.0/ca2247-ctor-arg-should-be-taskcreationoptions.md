---
ms.openlocfilehash: 6bb3b11ef4e4cb6f6a039c97911b0acca862fe6f
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065191"
---
### <a name="ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value"></a><span data-ttu-id="c8d67-101">CA2247: TaskCompletionSource 생성자의 인수는 TaskCreationOptions 값이어야 함</span><span class="sxs-lookup"><span data-stu-id="c8d67-101">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>

<span data-ttu-id="c8d67-102">.NET 코드 분석기 규칙 [CA2247](/visualstudio/code-quality/ca2247)은 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-102">.NET code analyzer rule [CA2247](/visualstudio/code-quality/ca2247) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="c8d67-103"><xref:System.Threading.Tasks.TaskContinuationOptions> 형식의 인수를 전달하는 <xref:System.Threading.Tasks.TaskCompletionSource%601> 생성자 호출에 대한 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-103">It produces a build warning for calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c8d67-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="c8d67-104">Change description</span></span>

<span data-ttu-id="c8d67-105">.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../docs/fundamentals/productivity/code-analysis.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="c8d67-106">[CA2247](/visualstudio/code-quality/ca2247)을 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-106">Several of these rules are enabled, by default, including [CA2247](/visualstudio/code-quality/ca2247).</span></span> <span data-ttu-id="c8d67-107">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="c8d67-108">규칙 CA2247은 <xref:System.Threading.Tasks.TaskContinuationOptions> 형식의 인수를 전달하는 <xref:System.Threading.Tasks.TaskCompletionSource%601> 생성자 호출을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-108">Rule CA2247 finds calls to the <xref:System.Threading.Tasks.TaskCompletionSource%601> constructor that pass an argument of type <xref:System.Threading.Tasks.TaskContinuationOptions>.</span></span> <span data-ttu-id="c8d67-109"><xref:System.Threading.Tasks.TaskCompletionSource%601> 형식에는 <xref:System.Threading.Tasks.TaskCreationOptions> 값을 허용하는 생성자와 <xref:System.Object>를 허용하는 다른 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-109">The <xref:System.Threading.Tasks.TaskCompletionSource%601> type has a constructor that accepts a <xref:System.Threading.Tasks.TaskCreationOptions> value, and another constructor that accepts an <xref:System.Object>.</span></span> <span data-ttu-id="c8d67-110"><xref:System.Threading.Tasks.TaskCreationOptions> 값 대신 <xref:System.Threading.Tasks.TaskContinuationOptions> 값을 실수로 전달하는 경우 <xref:System.Object> 매개 변수를 사용하는 생성자가 런타임에 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-110">If you accidentally pass a <xref:System.Threading.Tasks.TaskContinuationOptions> value instead of a <xref:System.Threading.Tasks.TaskCreationOptions> value, the constructor with the <xref:System.Object> parameter is called at run time.</span></span> <span data-ttu-id="c8d67-111">코드가 컴파일되어 실행되지만 의도한 동작이 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-111">Your code will compile and run but won't have the intended behavior.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c8d67-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c8d67-112">Version introduced</span></span>

<span data-ttu-id="c8d67-113">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="c8d67-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c8d67-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="c8d67-114">Recommended action</span></span>

- <span data-ttu-id="c8d67-115"><xref:System.Threading.Tasks.TaskContinuationOptions> 인수를 해당하는 <xref:System.Threading.Tasks.TaskCreationOptions> 값으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-115">Replace the <xref:System.Threading.Tasks.TaskContinuationOptions> argument with the corresponding <xref:System.Threading.Tasks.TaskCreationOptions> value.</span></span> <span data-ttu-id="c8d67-116">코드의 버그를 대부분 강조 표시하므로 이 경고를 해제하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-116">Do not suppress this warning, since it almost always highlights a bug in your code.</span></span> <span data-ttu-id="c8d67-117">자세한 내용은 [CA2247](/visualstudio/code-quality/ca2247)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8d67-117">For more information, see [CA2247](/visualstudio/code-quality/ca2247).</span></span>

- <span data-ttu-id="c8d67-118">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c8d67-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="c8d67-119">자세한 내용은 [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c8d67-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="c8d67-120">범주</span><span class="sxs-lookup"><span data-stu-id="c8d67-120">Category</span></span>

<span data-ttu-id="c8d67-121">코드 분석</span><span class="sxs-lookup"><span data-stu-id="c8d67-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c8d67-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c8d67-122">Affected APIs</span></span>

- <xref:System.Threading.Tasks.TaskCompletionSource%601.%23ctor(System.Object)>

<!--

#### Affected APIs

- ``M:System.Threading.Tasks.TaskCompletionSource`1.#ctor(System.Object)``

-->
