---
ms.openlocfilehash: 3cd5052dffcb059c240a310e0b89384f28409264
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234465"
---
### <a name="calls-to-systemwindowsinputpencontextdisable-on-touch-enabled-systems-may-throw-an-argumentexception"></a><span data-ttu-id="b1111-101">터치 지원 시스템에서 System.Windows.Input.PenContext.Disable 호출하면 ArgumentException이 throw될 수 있음</span><span class="sxs-lookup"><span data-stu-id="b1111-101">Calls to System.Windows.Input.PenContext.Disable on touch-enabled systems may throw an ArgumentException</span></span>

|   |   |
|---|---|
|<span data-ttu-id="b1111-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="b1111-102">Details</span></span>|<span data-ttu-id="b1111-103">상황에 따라 터치 지원 시스템에서 내부 <strong>System.Windows.Input.PenContext.Disable</strong> 메서드를 호출하면 재진입 때문에 처리되지 않은 <code>T:System.ArgumentException</code>가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1111-103">Under some circumstances, calls to the internal <strong>System.Windows.Intput.PenContext.Disable</strong> method on touch-enabled systems may throw an unhandled <code>T:System.ArgumentException</code> because of reentrancy.</span></span>|
|<span data-ttu-id="b1111-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="b1111-104">Suggestion</span></span>|<span data-ttu-id="b1111-105">이 문제는 .NET Framework 4.7에서 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1111-105">This issue has been addressed in the .NET Framework 4.7.</span></span> <span data-ttu-id="b1111-106">예외를 방지하려면 .NET Framework 4.7 이상의 .NET Framework 버전으로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="b1111-106">To prevent the exception, upgrade to a version of the .NET Framework starting with the .NET Framework 4.7.</span></span>|
|<span data-ttu-id="b1111-107">범위</span><span class="sxs-lookup"><span data-stu-id="b1111-107">Scope</span></span>|<span data-ttu-id="b1111-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b1111-108">Edge</span></span>|
|<span data-ttu-id="b1111-109">버전</span><span class="sxs-lookup"><span data-stu-id="b1111-109">Version</span></span>|<span data-ttu-id="b1111-110">4.6.1</span><span class="sxs-lookup"><span data-stu-id="b1111-110">4.6.1</span></span>|
|<span data-ttu-id="b1111-111">형식</span><span class="sxs-lookup"><span data-stu-id="b1111-111">Type</span></span>|<span data-ttu-id="b1111-112">대상 변경</span><span class="sxs-lookup"><span data-stu-id="b1111-112">Retargeting</span></span>|
