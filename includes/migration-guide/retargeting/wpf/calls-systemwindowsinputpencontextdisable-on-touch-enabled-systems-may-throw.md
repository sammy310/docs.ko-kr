---
ms.openlocfilehash: a44458484ea09c566defeabc9b604bd55d994e93
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617542"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="5d4cd-101">터치 지원 시스템에서 System.Windows.Input.PenContext.Disable 호출하면 ArgumentException이 throw될 수 있음</span><span class="sxs-lookup"><span data-stu-id="5d4cd-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

#### <a name="details"></a><span data-ttu-id="5d4cd-102">설명</span><span class="sxs-lookup"><span data-stu-id="5d4cd-102">Details</span></span>

<span data-ttu-id="5d4cd-103">상황에 따라 터치 지원 시스템에서 내부 **System.Windows.Input.PenContext.Disable** 메서드를 호출하면 재진입 때문에 처리되지 않은 `T:System.ArgumentException`가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-103">Under some circumstances, calls to the internal **System.Windows.Intput.PenContext.Disable** method on touch-enabled systems may throw an unhandled `T:System.ArgumentException` because of reentrancy.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="5d4cd-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="5d4cd-104">Suggestion</span></span>

<span data-ttu-id="5d4cd-105">이 문제는 .NET Framework 4.7에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="5d4cd-106">예외를 방지하려면 .NET Framework 4.7 이상의 .NET Framework 버전으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="5d4cd-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>

| <span data-ttu-id="5d4cd-107">이름</span><span class="sxs-lookup"><span data-stu-id="5d4cd-107">Name</span></span>    | <span data-ttu-id="5d4cd-108">값</span><span class="sxs-lookup"><span data-stu-id="5d4cd-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="5d4cd-109">Scope</span><span class="sxs-lookup"><span data-stu-id="5d4cd-109">Scope</span></span>   | <span data-ttu-id="5d4cd-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5d4cd-110">Edge</span></span>        |
| <span data-ttu-id="5d4cd-111">버전</span><span class="sxs-lookup"><span data-stu-id="5d4cd-111">Version</span></span> | <span data-ttu-id="5d4cd-112">4.6.1</span><span class="sxs-lookup"><span data-stu-id="5d4cd-112">4.6.1</span></span>       |
| <span data-ttu-id="5d4cd-113">형식</span><span class="sxs-lookup"><span data-stu-id="5d4cd-113">Type</span></span>    | <span data-ttu-id="5d4cd-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="5d4cd-114">Retargeting</span></span> |
