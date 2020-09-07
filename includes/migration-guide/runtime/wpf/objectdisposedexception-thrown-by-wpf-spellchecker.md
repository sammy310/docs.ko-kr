---
ms.openlocfilehash: 3244913e06a744dafc4440f824ebe6bed25b8dd1
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496629"
---
### <a name="objectdisposedexception-thrown-by-wpf-spellchecker"></a><span data-ttu-id="e2ca0-101">WPF 맞춤법 검사기에 의해 throw된 ObjectDisposedException</span><span class="sxs-lookup"><span data-stu-id="e2ca0-101">ObjectDisposedException thrown by WPF spellchecker</span></span>

#### <a name="details"></a><span data-ttu-id="e2ca0-102">설명</span><span class="sxs-lookup"><span data-stu-id="e2ca0-102">Details</span></span>

<span data-ttu-id="e2ca0-103">WPF 애플리케이션은 애플리케이션 종료 중에 맞춤법 검사기에서 throw된 <xref:System.ObjectDisposedException?displayProperty=fullName>으로 인해 때때로 크래시됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2ca0-103">WPF applications occasionally crash during application shutdown with an <xref:System.ObjectDisposedException?displayProperty=fullName> thrown by the spellchecker.</span></span> <span data-ttu-id="e2ca0-104">이는 .NET Framework 4.7 WPF에서 예외를 제대로 처리하여 애플리케이션이 더 이상 부정적인 영향을 받지 않도록 함으로써 해결되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ca0-104">This is fixed in .NET Framework 4.7 WPF by handling the exception gracefully, and thus ensuring that applications are no longer adversely affected.</span></span> <span data-ttu-id="e2ca0-105">디버거에서 실행 중인 애플리케이션에서는 경우에 따라 첫째 예외만 계속 확인될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ca0-105">It should be noted that occasional first-chance exceptions would continue to be observed in applications running under a debugger.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e2ca0-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e2ca0-106">Suggestion</span></span>

<span data-ttu-id="e2ca0-107">NET Framework 4.7로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="e2ca0-107">Upgrade to .NET Framework 4.7</span></span>

| <span data-ttu-id="e2ca0-108">이름</span><span class="sxs-lookup"><span data-stu-id="e2ca0-108">Name</span></span>    | <span data-ttu-id="e2ca0-109">값</span><span class="sxs-lookup"><span data-stu-id="e2ca0-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e2ca0-110">Scope</span><span class="sxs-lookup"><span data-stu-id="e2ca0-110">Scope</span></span>   |<span data-ttu-id="e2ca0-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="e2ca0-111">Edge</span></span>|
|<span data-ttu-id="e2ca0-112">버전</span><span class="sxs-lookup"><span data-stu-id="e2ca0-112">Version</span></span>|<span data-ttu-id="e2ca0-113">4.6.1</span><span class="sxs-lookup"><span data-stu-id="e2ca0-113">4.6.1</span></span>|
|<span data-ttu-id="e2ca0-114">형식</span><span class="sxs-lookup"><span data-stu-id="e2ca0-114">Type</span></span>|<span data-ttu-id="e2ca0-115">런타임</span><span class="sxs-lookup"><span data-stu-id="e2ca0-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="e2ca0-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e2ca0-116">Affected APIs</span></span>

<span data-ttu-id="e2ca0-117">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2ca0-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
