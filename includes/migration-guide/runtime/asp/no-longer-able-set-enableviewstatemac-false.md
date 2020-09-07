---
ms.openlocfilehash: c1793bb51f7da9169e912078fde202d0d62a4183
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496676"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="a7f11-101">더 이상 EnableViewStateMac를 false로 설정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="a7f11-101">No longer able to set EnableViewStateMac to false</span></span>

#### <a name="details"></a><span data-ttu-id="a7f11-102">설명</span><span class="sxs-lookup"><span data-stu-id="a7f11-102">Details</span></span>

<span data-ttu-id="a7f11-103">ASP.NET에서 개발자는 더 이상 <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> 또는 <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7f11-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="a7f11-104">포함된 뷰 상태가 사용된 모든 요청에 뷰 상태 MAC(메시지 인증 코드)가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a7f11-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="a7f11-105">EnableViewStateMac 속성이 <code>false</code>로 명시적으로 설정된 앱에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a7f11-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a7f11-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="a7f11-106">Suggestion</span></span>

<span data-ttu-id="a7f11-107">EnableViewStateMac은 true로 간주되어야 하고 모든 결과 MAC 오류는(MAC 오류 원인의 세부 정보에 따른 여러 해결 방법을 포함하는 [이 지침](https://support.microsoft.com/kb/2915218)에 설명된 대로) 해결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7f11-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>

| <span data-ttu-id="a7f11-108">이름</span><span class="sxs-lookup"><span data-stu-id="a7f11-108">Name</span></span>    | <span data-ttu-id="a7f11-109">값</span><span class="sxs-lookup"><span data-stu-id="a7f11-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a7f11-110">Scope</span><span class="sxs-lookup"><span data-stu-id="a7f11-110">Scope</span></span>   |<span data-ttu-id="a7f11-111">주요함</span><span class="sxs-lookup"><span data-stu-id="a7f11-111">Major</span></span>|
|<span data-ttu-id="a7f11-112">버전</span><span class="sxs-lookup"><span data-stu-id="a7f11-112">Version</span></span>|<span data-ttu-id="a7f11-113">4.5.2</span><span class="sxs-lookup"><span data-stu-id="a7f11-113">4.5.2</span></span>|
|<span data-ttu-id="a7f11-114">형식</span><span class="sxs-lookup"><span data-stu-id="a7f11-114">Type</span></span>|<span data-ttu-id="a7f11-115">런타임</span><span class="sxs-lookup"><span data-stu-id="a7f11-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="a7f11-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="a7f11-116">Affected APIs</span></span>

<span data-ttu-id="a7f11-117">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a7f11-117">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
