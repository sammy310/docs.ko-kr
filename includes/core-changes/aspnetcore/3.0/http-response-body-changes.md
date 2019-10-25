---
ms.openlocfilehash: 22ef5d0f91a4f61ca75203f677bcc14e91d77dc1
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394046"
---
### <a name="http-response-body-infrastructure-changes"></a><span data-ttu-id="7ad44-101">HTTP: 응답 본문 인프라 변경</span><span class="sxs-lookup"><span data-stu-id="7ad44-101">HTTP: Response body infrastructure changes</span></span>

<span data-ttu-id="7ad44-102">HTTP 응답 본문을 지원하는 인프라가 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad44-102">The infrastructure backing an HTTP response body has changed.</span></span> <span data-ttu-id="7ad44-103">`HttpResponse`를 직접 사용하는 경우 코드를 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad44-103">If you're using `HttpResponse` directly, you shouldn't need to make any code changes.</span></span> <span data-ttu-id="7ad44-104">`HttpResponse.Body`를 래핑 또는 대체하거나 `HttpContext.Features`에 액세스하는 경우 자세히 읽어보세요.</span><span class="sxs-lookup"><span data-stu-id="7ad44-104">Read further if you're wrapping or replacing `HttpResponse.Body` or accessing `HttpContext.Features`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="7ad44-105">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7ad44-105">Version introduced</span></span>

<span data-ttu-id="7ad44-106">3.0</span><span class="sxs-lookup"><span data-stu-id="7ad44-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="7ad44-107">이전 동작</span><span class="sxs-lookup"><span data-stu-id="7ad44-107">Old behavior</span></span>

<span data-ttu-id="7ad44-108">HTTP 응답 본문과 관련된 세 가지 API가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad44-108">There were three APIs associated with the HTTP response body:</span></span>

- `IHttpResponseFeature.Body`
- `IHttpSendFileFeature.SendFileAsync`
- `IHttpBufferingFeature.DisableResponseBuffering`

#### <a name="new-behavior"></a><span data-ttu-id="7ad44-109">새 동작</span><span class="sxs-lookup"><span data-stu-id="7ad44-109">New behavior</span></span>

<span data-ttu-id="7ad44-110">`HttpResponse.Body`를 바꾸면 `StreamResponseBodyFeature`를 사용하여 전체 `IHttpResponseBodyFeature`를 지정된 스트림 주변의 래퍼로 대체하여 모든 예상 API에 대한 기본 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad44-110">If you replace `HttpResponse.Body`, it replaces the entire `IHttpResponseBodyFeature` with a wrapper around your given stream using `StreamResponseBodyFeature` to provide default implementations for all of the expected APIs.</span></span> <span data-ttu-id="7ad44-111">원래 스트림으로 다시 설정하면 이 변경 내용이 되돌려집니다.</span><span class="sxs-lookup"><span data-stu-id="7ad44-111">Setting back the original stream reverts this change.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="7ad44-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7ad44-112">Reason for change</span></span>

<span data-ttu-id="7ad44-113">응답 본문 API를 새로운 단일 기능 인터페이스로 결합하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad44-113">The motivation is to combine the response body APIs into a single new feature interface.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7ad44-114">권장 작업</span><span class="sxs-lookup"><span data-stu-id="7ad44-114">Recommended action</span></span>

<span data-ttu-id="7ad44-115">이전에 `IHttpResponseFeature.Body`, `IHttpSendFileFeature` 또는 `IHttpBufferingFeature`를 사용했던 `IHttpResponseBodyFeature`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad44-115">Use `IHttpResponseBodyFeature` where you previously were using `IHttpResponseFeature.Body`, `IHttpSendFileFeature`, or `IHttpBufferingFeature`.</span></span>

#### <a name="category"></a><span data-ttu-id="7ad44-116">범주</span><span class="sxs-lookup"><span data-stu-id="7ad44-116">Category</span></span>

<span data-ttu-id="7ad44-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="7ad44-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7ad44-118">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7ad44-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature?displayProperty=nameWithType>
 
<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Http.Features.IHttpBufferingFeature`
- `P:Microsoft.AspNetCore.Http.Features.IHttpResponseFeature.Body`
- `T:Microsoft.AspNetCore.Http.Features.IHttpSendFileFeature`

-->
