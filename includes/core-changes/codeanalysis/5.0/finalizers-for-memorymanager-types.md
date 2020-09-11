---
ms.openlocfilehash: 4fc31f75e8f8cdd50abebd399d9749688e6faa5a
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465588"
---
### <a name="ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a><span data-ttu-id="31bde-101">CA2015: MemoryManager에서 파생된 형식에 대해 종료자를 정의하지 마세요.\<T></span><span class="sxs-lookup"><span data-stu-id="31bde-101">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>

<span data-ttu-id="31bde-102">.NET 코드 분석기 규칙 [CA2015](/visualstudio/code-quality/ca2015)는 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-102">.NET code analyzer rule [CA2015](/visualstudio/code-quality/ca2015) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="31bde-103"><xref:System.Buffers.MemoryManager%601>에서 파생된, 종료자를 정의하는 모든 형식에 대해 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-103">It produces a build warning for any types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span>

#### <a name="change-description"></a><span data-ttu-id="31bde-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="31bde-104">Change description</span></span>

<span data-ttu-id="31bde-105">.Net 5.0부터 .Net SDK에는 [.NET 소스 코드 분석기](../../../../docs/fundamentals/productivity/code-analysis.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-105">Starting in .NET 5.0, the .NET SDK includes [.NET source code analyzers](../../../../docs/fundamentals/productivity/code-analysis.md).</span></span> <span data-ttu-id="31bde-106">[CA2015](/visualstudio/code-quality/ca2015)를 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-106">Several of these rules are enabled, by default, including [CA2015](/visualstudio/code-quality/ca2015).</span></span> <span data-ttu-id="31bde-107">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-107">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="31bde-108">규칙 CA2015는 <xref:System.Buffers.MemoryManager%601>에서 파생된, 종료자를 정의하는 형식에 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-108">Rule CA2015 flags types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span> <span data-ttu-id="31bde-109"><xref:System.Buffers.MemoryManager%601>에서 파생된 형식에 종료자를 추가하는 것은 버그를 나타낼 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-109">Adding a finalizer to a type that derives from <xref:System.Buffers.MemoryManager%601> is likely an indication of a bug.</span></span> <span data-ttu-id="31bde-110"><xref:System.Span%601>에서 확보했을 수 있는 네이티브 리소스가 <xref:System.Span%601>에서 아직 사용 중인데 정리되고 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-110">It suggests that a native resource that could have been obtained in a <xref:System.Span%601> is getting cleaned up, potentially while it's still in use by the <xref:System.Span%601>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="31bde-111">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="31bde-111">Version introduced</span></span>

<span data-ttu-id="31bde-112">5.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="31bde-112">5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="31bde-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="31bde-113">Recommended action</span></span>

- <span data-ttu-id="31bde-114">종료자 정의를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-114">Remove the finalizer definition.</span></span> <span data-ttu-id="31bde-115">자세한 내용은 [CA2015](/visualstudio/code-quality/ca2015)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31bde-115">For more information, see [CA2015](/visualstudio/code-quality/ca2015).</span></span>

- <span data-ttu-id="31bde-116">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-116">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="31bde-117">자세한 내용은 [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31bde-117">For more information, see [EnableNETAnalyzers](../../../../docs/core/project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

#### <a name="category"></a><span data-ttu-id="31bde-118">범주</span><span class="sxs-lookup"><span data-stu-id="31bde-118">Category</span></span>

<span data-ttu-id="31bde-119">코드 분석</span><span class="sxs-lookup"><span data-stu-id="31bde-119">Code analysis</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="31bde-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="31bde-120">Affected APIs</span></span>

<span data-ttu-id="31bde-121">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31bde-121">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
