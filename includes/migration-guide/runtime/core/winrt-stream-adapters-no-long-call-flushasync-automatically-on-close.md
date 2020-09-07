---
ms.openlocfilehash: 2b4f35fe15f806897e5e4d85ee774b2e4572d974
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496107"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="80b83-101">종료 시 WinRT 스트림 어댑터가 더 이상 FlushAsync를 자동으로 호출하지 않음</span><span class="sxs-lookup"><span data-stu-id="80b83-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

#### <a name="details"></a><span data-ttu-id="80b83-102">설명</span><span class="sxs-lookup"><span data-stu-id="80b83-102">Details</span></span>

<span data-ttu-id="80b83-103">Windows Store 앱에서 Windows 런타임 스트림 어댑터는 더 이상 Dispose 메서드에서 FlushAsync 메서드를 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80b83-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="80b83-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="80b83-104">Suggestion</span></span>

<span data-ttu-id="80b83-105">이 변경 내용은 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="80b83-105">This change should be transparent.</span></span> <span data-ttu-id="80b83-106">개발자는 다음과 같은 코드를 작성하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80b83-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>

| <span data-ttu-id="80b83-107">이름</span><span class="sxs-lookup"><span data-stu-id="80b83-107">Name</span></span>    | <span data-ttu-id="80b83-108">값</span><span class="sxs-lookup"><span data-stu-id="80b83-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="80b83-109">Scope</span><span class="sxs-lookup"><span data-stu-id="80b83-109">Scope</span></span>   |<span data-ttu-id="80b83-110">투명</span><span class="sxs-lookup"><span data-stu-id="80b83-110">Transparent</span></span>|
|<span data-ttu-id="80b83-111">버전</span><span class="sxs-lookup"><span data-stu-id="80b83-111">Version</span></span>|<span data-ttu-id="80b83-112">4.5.1</span><span class="sxs-lookup"><span data-stu-id="80b83-112">4.5.1</span></span>|
|<span data-ttu-id="80b83-113">형식</span><span class="sxs-lookup"><span data-stu-id="80b83-113">Type</span></span>|<span data-ttu-id="80b83-114">런타임</span><span class="sxs-lookup"><span data-stu-id="80b83-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="80b83-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="80b83-115">Affected APIs</span></span>

<span data-ttu-id="80b83-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80b83-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
