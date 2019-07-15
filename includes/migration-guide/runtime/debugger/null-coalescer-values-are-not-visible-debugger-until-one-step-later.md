---
ms.openlocfilehash: c1a2d76b4e596acc395da6cefed008078e57a336
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67858603"
---
### <a name="null-coalescer-values-are-not-visible-in-debugger-until-one-step-later"></a><span data-ttu-id="47dad-101">디버거에서 한 단계가 지날 때까지 null 병합기 값을 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47dad-101">Null coalescer values are not visible in debugger until one step later</span></span>

|   |   |
|---|---|
|<span data-ttu-id="47dad-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="47dad-102">Details</span></span>|<span data-ttu-id="47dad-103">.NET Framework 4.5의 버그로 인해 64 비트 버전의 Framework에서 실행 중인 경우 할당 작업이 실행된 직후 null 병합 작업을 통해 설정된 값이 디버거에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="47dad-103">A bug in the .NET Framework 4.5 causes values set via a null coalescing operation to not be visible in the debugger immediately after the assignment operation is executed when running on the 64-bit version of the Framework.</span></span>|
|<span data-ttu-id="47dad-104">제안</span><span class="sxs-lookup"><span data-stu-id="47dad-104">Suggestion</span></span>|<span data-ttu-id="47dad-105">디버거에서 한 단계 더 실행하면 로컬/필드의 값이 올바르게 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="47dad-105">Stepping one additional time in the debugger will cause the local/field's value to be correctly updated.</span></span> <span data-ttu-id="47dad-106">또한 이 문제는 .NET Framework 4.6에서 해결되어 해당 버전의 Framework로 업그레이드하여 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47dad-106">Also, this issue has been fixed in the .NET Framework 4.6; upgrading to that version of the Framework should solve the issue.</span></span>|
|<span data-ttu-id="47dad-107">범위</span><span class="sxs-lookup"><span data-stu-id="47dad-107">Scope</span></span>|<span data-ttu-id="47dad-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="47dad-108">Edge</span></span>|
|<span data-ttu-id="47dad-109">버전</span><span class="sxs-lookup"><span data-stu-id="47dad-109">Version</span></span>|<span data-ttu-id="47dad-110">4.5</span><span class="sxs-lookup"><span data-stu-id="47dad-110">4.5</span></span>|
|<span data-ttu-id="47dad-111">형식</span><span class="sxs-lookup"><span data-stu-id="47dad-111">Type</span></span>|<span data-ttu-id="47dad-112">런타임</span><span class="sxs-lookup"><span data-stu-id="47dad-112">Runtime</span></span>|

