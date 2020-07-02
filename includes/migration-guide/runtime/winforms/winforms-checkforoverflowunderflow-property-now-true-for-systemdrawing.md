---
ms.openlocfilehash: 4cd06fd02fadbaa9f74e40f850e688ee883454ed
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620444"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="f5f01-101">WinForm의 CheckForOverflowUnderflow 속성은 이제 System.Drawing에 대해 true입니다.</span><span class="sxs-lookup"><span data-stu-id="f5f01-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="f5f01-102">설명</span><span class="sxs-lookup"><span data-stu-id="f5f01-102">Details</span></span>

<span data-ttu-id="f5f01-103">System.Drawing.dll 어셈블리의 CheckForOverflowUnderflow 속성이 true로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5f01-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="f5f01-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f5f01-104">Suggestion</span></span>

<span data-ttu-id="f5f01-105">이전에 오버플로가 발생했을 때는 결과가 자동으로 잘렸습니다.</span><span class="sxs-lookup"><span data-stu-id="f5f01-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="f5f01-106">이제 <xref:System.OverflowException?displayProperty=fullName> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5f01-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="f5f01-107">이름</span><span class="sxs-lookup"><span data-stu-id="f5f01-107">Name</span></span>    | <span data-ttu-id="f5f01-108">값</span><span class="sxs-lookup"><span data-stu-id="f5f01-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="f5f01-109">Scope</span><span class="sxs-lookup"><span data-stu-id="f5f01-109">Scope</span></span>   |<span data-ttu-id="f5f01-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="f5f01-110">Edge</span></span>|
|<span data-ttu-id="f5f01-111">버전</span><span class="sxs-lookup"><span data-stu-id="f5f01-111">Version</span></span>|<span data-ttu-id="f5f01-112">4.5</span><span class="sxs-lookup"><span data-stu-id="f5f01-112">4.5</span></span>|
|<span data-ttu-id="f5f01-113">형식</span><span class="sxs-lookup"><span data-stu-id="f5f01-113">Type</span></span>|<span data-ttu-id="f5f01-114">런타임</span><span class="sxs-lookup"><span data-stu-id="f5f01-114">Runtime</span></span>|
