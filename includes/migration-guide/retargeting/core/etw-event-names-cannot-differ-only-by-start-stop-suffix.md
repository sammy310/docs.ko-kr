---
ms.openlocfilehash: 0e25d5d9b545e5cb400cbf701fb13da572fadf10
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614674"
---
### <a name="etw-event-names-cannot-differ-only-by-a-start-or-stop-suffix"></a><span data-ttu-id="2361a-101">ETW 이벤트 이름은 "Start" 또는 "Stop" 접미사만 다를 수 없음</span><span class="sxs-lookup"><span data-stu-id="2361a-101">ETW event names cannot differ only by a "Start" or "Stop" suffix</span></span>

#### <a name="details"></a><span data-ttu-id="2361a-102">설명</span><span class="sxs-lookup"><span data-stu-id="2361a-102">Details</span></span>

<span data-ttu-id="2361a-103">.NET Framework 4.6 및 4.6.1의 경우 두 개의 ETW(Windows용 이벤트 추적) 이벤트 이름이 "Start" 또는 "Stop" 접미사만 다를 때(예: 한 이벤트는 `LogUser`, 다른 이벤트는 `LogUserStart`라고 이름을 지정하는 경우) 런타임에서 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="2361a-103">In the .NET Framework 4.6 and 4.6.1, the runtime throws an <xref:System.ArgumentException> when two Event Tracing for Windows (ETW) event names differ only by a "Start" or "Stop" suffix (as when one event is named `LogUser` and another is named `LogUserStart`).</span></span> <span data-ttu-id="2361a-104">이 경우 런타임에서 로깅을 발생할 수 없는 이벤트 소스를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2361a-104">In this case, the runtime cannot construct the event source, which cannot emit any logging.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="2361a-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="2361a-105">Suggestion</span></span>

<span data-ttu-id="2361a-106">예외를 방지하려면 두 이벤트 이름이 "Start" 또는 "Stop" 접미사만 다르지 않도록 하세요. 이 요구 사항은 .NET Framework 4.6.2부터 제거됩니다. 런타임은 "Start" 및 "Stop" 접미사만 다른 이벤트 이름을 명확하게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2361a-106">To prevent the exception, ensure that no two event names differ only by a "Start" or "Stop" suffix.This requirement is removed starting with the .NET Framework 4.6.2; the runtime can disambiguate event names that differ only by the "Start" and "Stop" suffix.</span></span>

| <span data-ttu-id="2361a-107">이름</span><span class="sxs-lookup"><span data-stu-id="2361a-107">Name</span></span>    | <span data-ttu-id="2361a-108">값</span><span class="sxs-lookup"><span data-stu-id="2361a-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="2361a-109">Scope</span><span class="sxs-lookup"><span data-stu-id="2361a-109">Scope</span></span>   | <span data-ttu-id="2361a-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="2361a-110">Edge</span></span>        |
| <span data-ttu-id="2361a-111">버전</span><span class="sxs-lookup"><span data-stu-id="2361a-111">Version</span></span> | <span data-ttu-id="2361a-112">4.6</span><span class="sxs-lookup"><span data-stu-id="2361a-112">4.6</span></span>         |
| <span data-ttu-id="2361a-113">형식</span><span class="sxs-lookup"><span data-stu-id="2361a-113">Type</span></span>    | <span data-ttu-id="2361a-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="2361a-114">Retargeting</span></span> |
