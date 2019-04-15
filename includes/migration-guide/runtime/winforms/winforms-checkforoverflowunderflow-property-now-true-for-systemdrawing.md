---
ms.openlocfilehash: 8b2a01eb6dfdd5bd2bcbef6014d4edeb3ec82ac1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235563"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="e8cce-101">WinForm의 CheckForOverflowUnderflow 속성은 이제 System.Drawing에 대해 true입니다.</span><span class="sxs-lookup"><span data-stu-id="e8cce-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

|   |   |
|---|---|
|<span data-ttu-id="e8cce-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e8cce-102">Details</span></span>|<span data-ttu-id="e8cce-103">System.Drawing.dll 어셈블리의 CheckForOverflowUnderflow 속성이 true로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cce-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>|
|<span data-ttu-id="e8cce-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e8cce-104">Suggestion</span></span>|<span data-ttu-id="e8cce-105">이전에 오버플로가 발생했을 때는 결과가 자동으로 잘렸습니다.</span><span class="sxs-lookup"><span data-stu-id="e8cce-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="e8cce-106">이제 <xref:System.OverflowException?displayProperty=name> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8cce-106">Now an <xref:System.OverflowException?displayProperty=name> exception is thrown.</span></span>|
|<span data-ttu-id="e8cce-107">범위</span><span class="sxs-lookup"><span data-stu-id="e8cce-107">Scope</span></span>|<span data-ttu-id="e8cce-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e8cce-108">Edge</span></span>|
|<span data-ttu-id="e8cce-109">버전</span><span class="sxs-lookup"><span data-stu-id="e8cce-109">Version</span></span>|<span data-ttu-id="e8cce-110">4.5</span><span class="sxs-lookup"><span data-stu-id="e8cce-110">4.5</span></span>|
|<span data-ttu-id="e8cce-111">형식</span><span class="sxs-lookup"><span data-stu-id="e8cce-111">Type</span></span>|<span data-ttu-id="e8cce-112">런타임</span><span class="sxs-lookup"><span data-stu-id="e8cce-112">Runtime</span></span>|
