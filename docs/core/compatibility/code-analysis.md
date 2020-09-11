---
title: 코드 분석 호환성이 손상되는 변경
description: .NET 소스 코드 분석기의 호환성이 손상되는 변경을 나열합니다.
ms.date: 08/22/2020
ms.openlocfilehash: 8b2b50c5f03a3ca971aefd0f2cf53624dfa82274
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465585"
---
# <a name="code-analysis-breaking-changes"></a><span data-ttu-id="53073-103">코드 분석 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="53073-103">Code analysis breaking changes</span></span>

<span data-ttu-id="53073-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="53073-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="53073-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="53073-105">Breaking change</span></span> | <span data-ttu-id="53073-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="53073-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="53073-107">CA1831: 범위 기반 인덱서 대신 AsSpan 또는 AsMemory 사용</span><span class="sxs-lookup"><span data-stu-id="53073-107">CA1831: Use AsSpan or AsMemory instead of Range-based indexer</span></span>](#ca1831-use-asspan-or-asmemory-instead-of-range-based-indexer) | <span data-ttu-id="53073-108">5.0</span><span class="sxs-lookup"><span data-stu-id="53073-108">5.0</span></span> |
| [<span data-ttu-id="53073-109">CA2014: 루프에 stackalloc를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="53073-109">CA2014: Do not use stackalloc in loops</span></span>](#ca2014-do-not-use-stackalloc-in-loops) | <span data-ttu-id="53073-110">5.0</span><span class="sxs-lookup"><span data-stu-id="53073-110">5.0</span></span> |
| [<span data-ttu-id="53073-111">CA2015: MemoryManager에서 파생된 형식에 대해 종료자 정의 안 함\<T></span><span class="sxs-lookup"><span data-stu-id="53073-111">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | <span data-ttu-id="53073-112">5.0</span><span class="sxs-lookup"><span data-stu-id="53073-112">5.0</span></span> |
| [<span data-ttu-id="53073-113">CA2247: TaskCompletionSource 생성자의 인수는 TaskCreationOptions 값이어야 함</span><span class="sxs-lookup"><span data-stu-id="53073-113">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | <span data-ttu-id="53073-114">5.0</span><span class="sxs-lookup"><span data-stu-id="53073-114">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="53073-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="53073-115">.NET 5.0</span></span>

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/range-based-indexer-on-string.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ctor-arg-should-be-taskcreationoptions.md)]

***
