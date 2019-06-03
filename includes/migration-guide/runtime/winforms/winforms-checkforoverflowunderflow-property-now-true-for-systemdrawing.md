---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "66379610"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="97117-101">WinForm의 CheckForOverflowUnderflow 속성은 이제 System.Drawing에 대해 true입니다.</span><span class="sxs-lookup"><span data-stu-id="97117-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="97117-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="97117-102">Details</span></span>|<span data-ttu-id="97117-103">System.Drawing.dll 어셈블리의 CheckForOverflowUnderflow 속성이 true로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="97117-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="97117-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="97117-104">Suggestion</span></span>|<span data-ttu-id="97117-105">이전에 오버플로가 발생했을 때는 결과가 자동으로 잘렸습니다.</span><span class="sxs-lookup"><span data-stu-id="97117-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="97117-106">이제 <xref:System.OverflowException?displayProperty=name> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="97117-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="97117-107">범위</span><span class="sxs-lookup"><span data-stu-id="97117-107">Scope</span></span>|<span data-ttu-id="97117-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="97117-108">Edge</span></span>|
|<span data-ttu-id="97117-109">버전</span><span class="sxs-lookup"><span data-stu-id="97117-109">Version</span></span>|<span data-ttu-id="97117-110">4.5</span><span class="sxs-lookup"><span data-stu-id="97117-110">4.5</span></span>|
|<span data-ttu-id="97117-111">형식</span><span class="sxs-lookup"><span data-stu-id="97117-111">Type</span></span>|<span data-ttu-id="97117-112">런타임</span><span class="sxs-lookup"><span data-stu-id="97117-112">Runtime</span></span>|
