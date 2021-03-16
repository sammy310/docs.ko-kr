---
title: '호환성이 손상되는 변경: CA2015: MemoryManager에서 파생된 형식에 대해 종료자를 정의하지 마세요.<T>'
description: 코드 분석 규칙 CA2015 사용으로 인해 발생하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 09/03/2020
ms.openlocfilehash: 4333cec7657657f7e9ba864bcb9979609ad379e0
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257741"
---
# <a name="warning-ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert"></a><span data-ttu-id="8a2fc-103">경고 CA2015: MemoryManager에서 파생된 형식에 대해 종료자를 정의하지 마세요.\<T></span><span class="sxs-lookup"><span data-stu-id="8a2fc-103">Warning CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>

<span data-ttu-id="8a2fc-104">.NET 코드 분석기 규칙 [CA2015](/visualstudio/code-quality/ca2015)는 .NET 5.0부터 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-104">.NET code analyzer rule [CA2015](/visualstudio/code-quality/ca2015) is enabled, by default, starting in .NET 5.0.</span></span> <span data-ttu-id="8a2fc-105"><xref:System.Buffers.MemoryManager%601>에서 파생된, 종료자를 정의하는 모든 형식에 대해 빌드 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-105">It produces a build warning for any types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span>

## <a name="change-description"></a><span data-ttu-id="8a2fc-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="8a2fc-106">Change description</span></span>

<span data-ttu-id="8a2fc-107">.NET 5부터 .NET SDK에는 [.NET 소스 코드 분석기](../../../../fundamentals/code-analysis/overview.md)가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-107">Starting in .NET 5, the .NET SDK includes [.NET source code analyzers](../../../../fundamentals/code-analysis/overview.md).</span></span> <span data-ttu-id="8a2fc-108">[CA2015](/visualstudio/code-quality/ca2015)를 포함하여 해당 규칙 중 여러 개가 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-108">Several of these rules are enabled, by default, including [CA2015](/visualstudio/code-quality/ca2015).</span></span> <span data-ttu-id="8a2fc-109">해당 규칙을 위반하는 코드가 프로젝트에 포함되고 프로젝트가 경고를 오류로 처리하도록 구성된 경우 해당 변경으로 인해 빌드의 호환성이 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-109">If your project contains code that violates this rule and is configured to treat warnings as errors, this change could break your build.</span></span>

<span data-ttu-id="8a2fc-110">규칙 CA2015는 <xref:System.Buffers.MemoryManager%601>에서 파생된, 종료자를 정의하는 형식에 플래그를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-110">Rule CA2015 flags types that derive from <xref:System.Buffers.MemoryManager%601> that define a finalizer.</span></span> <span data-ttu-id="8a2fc-111"><xref:System.Buffers.MemoryManager%601>에서 파생된 형식에 종료자를 추가하는 것은 버그를 나타낼 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-111">Adding a finalizer to a type that derives from <xref:System.Buffers.MemoryManager%601> is likely an indication of a bug.</span></span> <span data-ttu-id="8a2fc-112"><xref:System.Span%601>에서 확보했을 수 있는 네이티브 리소스가 <xref:System.Span%601>에서 아직 사용 중인데 정리되고 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-112">It suggests that a native resource that could have been obtained in a <xref:System.Span%601> is getting cleaned up, potentially while it's still in use by the <xref:System.Span%601>.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="8a2fc-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="8a2fc-113">Version introduced</span></span>

<span data-ttu-id="8a2fc-114">5.0</span><span class="sxs-lookup"><span data-stu-id="8a2fc-114">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="8a2fc-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="8a2fc-115">Recommended action</span></span>

- <span data-ttu-id="8a2fc-116">종료자 정의를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-116">Remove the finalizer definition.</span></span> <span data-ttu-id="8a2fc-117">자세한 내용은 [CA2015](/visualstudio/code-quality/ca2015)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-117">For more information, see [CA2015](/visualstudio/code-quality/ca2015).</span></span>

- <span data-ttu-id="8a2fc-118">코드 분석을 완전히 사용하지 않으려면 프로젝트 파일에서 `EnableNETAnalyzers`를 `false`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-118">To disable code analysis completely, set `EnableNETAnalyzers` to `false` in your project file.</span></span> <span data-ttu-id="8a2fc-119">자세한 내용은 [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-119">For more information, see [EnableNETAnalyzers](../../../project-sdk/msbuild-props.md#enablenetanalyzers).</span></span>

## <a name="affected-apis"></a><span data-ttu-id="8a2fc-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="8a2fc-120">Affected APIs</span></span>

<span data-ttu-id="8a2fc-121">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a2fc-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

Code analysis

-->
