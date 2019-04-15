---
ms.openlocfilehash: dbe96abebdc61fae469f7727673e6fcb93cbc739
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236668"
---
### <a name="no-longer-able-to-set-enableviewstatemac-to-false"></a><span data-ttu-id="c20a5-101">더 이상 EnableViewStateMac를 false로 설정할 수 없음</span><span class="sxs-lookup"><span data-stu-id="c20a5-101">No longer able to set EnableViewStateMac to false</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c20a5-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c20a5-102">Details</span></span>|<span data-ttu-id="c20a5-103">ASP.NET에서 개발자는 더 이상 <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> 또는 <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c20a5-103">ASP.NET no longer allows developers to specify <code>&lt;pages enableViewStateMac=&quot;false&quot;/&gt;</code> or <code>&lt;@Page EnableViewStateMac=&quot;false&quot; %&gt;</code>.</span></span> <span data-ttu-id="c20a5-104">포함된 뷰 상태가 사용된 모든 요청에 뷰 상태 MAC(메시지 인증 코드)가 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c20a5-104">The view state message authentication code (MAC) is now enforced for all requests with embedded view state.</span></span> <span data-ttu-id="c20a5-105">EnableViewStateMac 속성이 <code>false</code>로 명시적으로 설정된 앱에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c20a5-105">Only apps that explicitly set the EnableViewStateMac property to <code>false</code> are affected.</span></span>|
|<span data-ttu-id="c20a5-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="c20a5-106">Suggestion</span></span>|<span data-ttu-id="c20a5-107">EnableViewStateMac은 true로 간주되어야 하고 모든 결과 MAC 오류는(MAC 오류 원인의 세부 정보에 따른 여러 해결 방법을 포함하는 [이 지침](https://support.microsoft.com/kb/2915218)에 설명된 대로) 해결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c20a5-107">EnableViewStateMac must be assumed to be true, and any resulting MAC errors must be resolved (as explained in [this guidance](https://support.microsoft.com/kb/2915218), which contains multiple resolutions depending on the specifics of what is causing MAC errors).</span></span>|
|<span data-ttu-id="c20a5-108">범위</span><span class="sxs-lookup"><span data-stu-id="c20a5-108">Scope</span></span>|<span data-ttu-id="c20a5-109">주요함</span><span class="sxs-lookup"><span data-stu-id="c20a5-109">Major</span></span>|
|<span data-ttu-id="c20a5-110">버전</span><span class="sxs-lookup"><span data-stu-id="c20a5-110">Version</span></span>|<span data-ttu-id="c20a5-111">4.5.2</span><span class="sxs-lookup"><span data-stu-id="c20a5-111">4.5.2</span></span>|
|<span data-ttu-id="c20a5-112">형식</span><span class="sxs-lookup"><span data-stu-id="c20a5-112">Type</span></span>|<span data-ttu-id="c20a5-113">런타임</span><span class="sxs-lookup"><span data-stu-id="c20a5-113">Runtime</span></span>|
