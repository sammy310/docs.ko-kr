---
ms.openlocfilehash: 60759e3d03137bb5983703cbf04719ba4946cb6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804604"
---
### <a name="winrt-stream-adapters-no-long-call-flushasync-automatically-on-close"></a><span data-ttu-id="cc7bc-101">종료 시 WinRT 스트림 어댑터가 더 이상 FlushAsync를 자동으로 호출하지 않음</span><span class="sxs-lookup"><span data-stu-id="cc7bc-101">WinRT stream adapters no long call FlushAsync automatically on close</span></span>

|   |   |
|---|---|
|<span data-ttu-id="cc7bc-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="cc7bc-102">Details</span></span>|<span data-ttu-id="cc7bc-103">Windows Store 앱에서 Windows 런타임 스트림 어댑터는 더 이상 Dispose 메서드에서 FlushAsync 메서드를 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7bc-103">In Windows Store apps, Windows Runtime stream adapters no longer call the FlushAsync method from the Dispose method.</span></span>|
|<span data-ttu-id="cc7bc-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="cc7bc-104">Suggestion</span></span>|<span data-ttu-id="cc7bc-105">이 변경 내용은 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7bc-105">This change should be transparent.</span></span> <span data-ttu-id="cc7bc-106">개발자는 다음과 같은 코드를 작성하여 이전 동작을 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc7bc-106">Developers can restore the previous behavior by writing code like this:</span></span><pre><code class="lang-csharp">using (var stream = GetWindowsRuntimeStream() as Stream)&#13;&#10;{&#13;&#10;// do something&#13;&#10;await stream.FlushAsync();&#13;&#10;}&#13;&#10;</code></pre>|
|<span data-ttu-id="cc7bc-107">범위</span><span class="sxs-lookup"><span data-stu-id="cc7bc-107">Scope</span></span>|<span data-ttu-id="cc7bc-108">투명</span><span class="sxs-lookup"><span data-stu-id="cc7bc-108">Transparent</span></span>|
|<span data-ttu-id="cc7bc-109">버전</span><span class="sxs-lookup"><span data-stu-id="cc7bc-109">Version</span></span>|<span data-ttu-id="cc7bc-110">4.5.1</span><span class="sxs-lookup"><span data-stu-id="cc7bc-110">4.5.1</span></span>|
|<span data-ttu-id="cc7bc-111">형식</span><span class="sxs-lookup"><span data-stu-id="cc7bc-111">Type</span></span>|<span data-ttu-id="cc7bc-112">런타임</span><span class="sxs-lookup"><span data-stu-id="cc7bc-112">Runtime</span></span>|
