---
ms.openlocfilehash: a51160a8ab5a4b437e51db31def577f8d8f50182
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065181"
---
### <a name="ca2014-do-not-use-stackalloc-in-loops"></a><span data-ttu-id="96275-101">CA2014: 루프에 stackalloc를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="96275-101">CA2014: Do not use stackalloc in loops</span></span>

<span data-ttu-id="96275-102">.NET 코드 분석기 규칙 [CA2014](/visualstudio/code-quality/ca2014)는 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96275-102">.NET code analyzer rule [CA2014](/visualstudio/code-quality/ca2014) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="96275-103">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) 식이 루프 내에서 사용되는 모든 C# 코드에 대해 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="96275-103">It produces a build warning for any C# code where a [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) expression is used inside a loop.</span></span>

#### <a name="change-description"></a><span data-ttu-id="96275-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="96275-104">Change description</span></span>

<span data-ttu-id="96275-105">.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../docs/fundamentals/productivity/code-analysis.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96275-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="96275-106">[CA2014](/visualstudio/code-quality/ca2014)를 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96275-106">Several of these rules are enabled, by default, including [CA2014](/visualstudio/code-quality/ca2014).</span></span> <span data-ttu-id="96275-107">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96275-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="96275-108">규칙 CA2014는 [stackalloc 식](../../../../docs/csharp/language-reference/operators/stackalloc.md)이 루프 내에서 사용되는 C# 코드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="96275-108">Rule CA2014 looks for C# code where a [stackalloc expression](../../../../docs/csharp/language-reference/operators/stackalloc.md) is used inside a loop.</span></span> <span data-ttu-id="96275-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md)는 현재 스택 프레임에서 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="96275-109">[stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) allocates memory from the current stack frame.</span></span> <span data-ttu-id="96275-110">현재 메서드 호출이 반환될 때까지 메모리가 해제되지 않아 스택 오버플로가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96275-110">The memory isn't released until the current method call returns, which can lead to stack overflows.</span></span> <span data-ttu-id="96275-111">스택 오버플로 예외를 catch할 수 없기 때문에 스택 오버플로가 발생할 경우 앱이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="96275-111">Because you can't catch stack overflow exceptions, the app will terminate in case of stack overflow.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="96275-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="96275-112">Version introduced</span></span>

<span data-ttu-id="96275-113">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="96275-113">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="96275-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="96275-114">Recommended action</span></span>

- <span data-ttu-id="96275-115">루프 내에서 [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md)를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96275-115">Avoid using [stackalloc](../../../../docs/csharp/language-reference/operators/stackalloc.md) inside loops.</span></span> <span data-ttu-id="96275-116">루프 외부에서 메모리 블록을 할당하고 루프 내부에서 재사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96275-116">Allocate the memory block outside the loop and reuse it inside the loop.</span></span> <span data-ttu-id="96275-117">자세한 내용은 [CA2014](/visualstudio/code-quality/ca2014)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96275-117">For more information, see [CA2014](/visualstudio/code-quality/ca2014).</span></span>

- <span data-ttu-id="96275-118">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="96275-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="96275-119">자세한 내용은 [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96275-119">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="96275-120">범주</span><span class="sxs-lookup"><span data-stu-id="96275-120">Category</span></span>

<span data-ttu-id="96275-121">코드 분석</span><span class="sxs-lookup"><span data-stu-id="96275-121">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="96275-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="96275-122">Affected APIs</span></span>

<span data-ttu-id="96275-123">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96275-123">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
