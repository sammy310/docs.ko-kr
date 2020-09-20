---
title: 코드 분석 호환성이 손상되는 변경
description: .NET 소스 코드 분석기의 호환성이 손상되는 변경을 나열합니다.
ms.date: 09/02/2020
ms.openlocfilehash: 20badd69b316e1d87700b3c5061a71d648b71c64
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065205"
---
# <a name="code-analysis-breaking-changes"></a><span data-ttu-id="1bd69-103">코드 분석 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="1bd69-103">Code analysis breaking changes</span></span>

<span data-ttu-id="1bd69-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1bd69-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="1bd69-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="1bd69-105">Breaking change</span></span> | <span data-ttu-id="1bd69-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="1bd69-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="1bd69-107">CA1416: 플랫폼 호환성</span><span class="sxs-lookup"><span data-stu-id="1bd69-107">CA1416: Platform compatibility</span></span>](#ca1416-platform-compatibility) | <span data-ttu-id="1bd69-108">5.0</span><span class="sxs-lookup"><span data-stu-id="1bd69-108">5.0</span></span> |
| [<span data-ttu-id="1bd69-109">CA1417: P/Invoke에 대한 문자열 매개 변수의 OutAttribute</span><span class="sxs-lookup"><span data-stu-id="1bd69-109">CA1417: OutAttribute on string parameter for P/Invoke</span></span>](#ca1417-outattribute-on-string-parameter-for-pinvoke) | <span data-ttu-id="1bd69-110">5.0</span><span class="sxs-lookup"><span data-stu-id="1bd69-110">5.0</span></span> |
| [<span data-ttu-id="1bd69-111">CA1831: 문자열에 대해 범위 기반 인덱서 대신 AsSpan 사용</span><span class="sxs-lookup"><span data-stu-id="1bd69-111">CA1831: Use AsSpan instead of Range-based indexers for string</span></span>](#ca1831-use-asspan-instead-of-range-based-indexers-for-string) | <span data-ttu-id="1bd69-112">5.0</span><span class="sxs-lookup"><span data-stu-id="1bd69-112">5.0</span></span> |
| [<span data-ttu-id="1bd69-113">CA2013: 값 형식과 함께 ReferenceEquals를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1bd69-113">CA2013: Do not use ReferenceEquals with value types</span></span>](#ca2013-do-not-use-referenceequals-with-value-types) | <span data-ttu-id="1bd69-114">5.0</span><span class="sxs-lookup"><span data-stu-id="1bd69-114">5.0</span></span> |
| [<span data-ttu-id="1bd69-115">CA2014: 루프에 stackalloc를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1bd69-115">CA2014: Do not use stackalloc in loops</span></span>](#ca2014-do-not-use-stackalloc-in-loops) | <span data-ttu-id="1bd69-116">5.0</span><span class="sxs-lookup"><span data-stu-id="1bd69-116">5.0</span></span> |
| [<span data-ttu-id="1bd69-117">CA2015: MemoryManager에서 파생된 형식에 대해 종료자 정의 안 함\<T></span><span class="sxs-lookup"><span data-stu-id="1bd69-117">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | <span data-ttu-id="1bd69-118">5.0</span><span class="sxs-lookup"><span data-stu-id="1bd69-118">5.0</span></span> |
| [<span data-ttu-id="1bd69-119">CA2247: TaskCompletionSource 생성자의 인수는 TaskCreationOptions 값이어야 함</span><span class="sxs-lookup"><span data-stu-id="1bd69-119">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | <span data-ttu-id="1bd69-120">5.0</span><span class="sxs-lookup"><span data-stu-id="1bd69-120">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="1bd69-121">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="1bd69-121">.NET 5.0</span></span>

[!INCLUDE [ca1416-platform-compatibility-analyzer](../../../includes/core-changes/codeanalysis/5.0/ca1416-platform-compatibility-analyzer.md)]

***

[!INCLUDE [outattributes-on-pinvoke-string-parameters](../../../includes/core-changes/codeanalysis/5.0/ca1417-outattributes-on-pinvoke-string-parameters.md)]

***

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/ca1831-range-based-indexer-on-string.md)]

***

[!INCLUDE [referenceequals-on-value-types](../../../includes/core-changes/codeanalysis/5.0/ca2013-referenceequals-on-value-types.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/ca2014-stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/ca2015-finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ca2247-ctor-arg-should-be-taskcreationoptions.md)]

***
