---
ms.openlocfilehash: 1047f4028697a73741470d1aac8b3aeed37be217
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497496"
---
### <a name="allow-unicode-in-uris-that-resemble-unc-shares"></a><span data-ttu-id="18487-101">UNC 공유와 비슷한 URI에서 유니코드 허용</span><span class="sxs-lookup"><span data-stu-id="18487-101">Allow Unicode in URIs that resemble UNC shares</span></span>

#### <a name="details"></a><span data-ttu-id="18487-102">설명</span><span class="sxs-lookup"><span data-stu-id="18487-102">Details</span></span>

<span data-ttu-id="18487-103"><xref:System.Uri?displayProperty=fullName>에서 UNC 공유 이름 및 유니코드 문자 모두를 포함하는 파일 URI를 생성하면 더 이상 잘못된 내부 상태의 URI를 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18487-103">In <xref:System.Uri?displayProperty=fullName>, constructing a file URI containing both a UNC share name and Unicode characters will no longer result in a URI with invalid internal state.</span></span> <span data-ttu-id="18487-104">이 동작은 다음의 모든 것이 True인 경우에만 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="18487-104">The behavior will change only when all of the following are true:</span></span><ul><li><span data-ttu-id="18487-105">URI는 구성표 <code>file:</code>을 보유하며 4개 이상의 슬래시가 뒤따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18487-105">The URI has the scheme <code>file:</code> and is followed by four or more slashes.</span></span></li><li><span data-ttu-id="18487-106">호스트 이름은 밑줄 또는 기타 예약되지 않은 기호로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="18487-106">The host name begins with an underscore or other non-reserved symbol.</span></span></li><li><span data-ttu-id="18487-107">URI에 유니코드 문자가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18487-107">The URI contains Unicode characters.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="18487-108">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="18487-108">Suggestion</span></span>

<span data-ttu-id="18487-109">지속적으로 유니코드를 포함하는 URI를 사용하여 작동하는 애플리케이션은 UNC 공유에 대한 참조를 허용하지 않기 위해 이 동작을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="18487-109">Applications working with URIs consistently containing Unicode could have conceivably used this behavior to disallow references to UNC shares.</span></span> <span data-ttu-id="18487-110">이러한 애플리케이션은 대신 <xref:System.Uri.IsUnc>을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18487-110">Those applications should use <xref:System.Uri.IsUnc> instead.</span></span>

| <span data-ttu-id="18487-111">이름</span><span class="sxs-lookup"><span data-stu-id="18487-111">Name</span></span>    | <span data-ttu-id="18487-112">값</span><span class="sxs-lookup"><span data-stu-id="18487-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="18487-113">Scope</span><span class="sxs-lookup"><span data-stu-id="18487-113">Scope</span></span>   |<span data-ttu-id="18487-114">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="18487-114">Edge</span></span>|
|<span data-ttu-id="18487-115">버전</span><span class="sxs-lookup"><span data-stu-id="18487-115">Version</span></span>|<span data-ttu-id="18487-116">4.7.2</span><span class="sxs-lookup"><span data-stu-id="18487-116">4.7.2</span></span>|
|<span data-ttu-id="18487-117">형식</span><span class="sxs-lookup"><span data-stu-id="18487-117">Type</span></span>|<span data-ttu-id="18487-118">런타임</span><span class="sxs-lookup"><span data-stu-id="18487-118">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="18487-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="18487-119">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Uri`

-->
