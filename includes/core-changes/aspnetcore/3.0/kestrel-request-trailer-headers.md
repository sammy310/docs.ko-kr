---
ms.openlocfilehash: b0e1d6d720a1c9b827fb4585606e64b545d395d7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394372"
---
### <a name="kestrel-request-trailer-headers-moved-to-new-collection"></a><span data-ttu-id="31085-101">Kestrel: 요청 트레일러 헤더가 새 컬렉션으로 이동됨</span><span class="sxs-lookup"><span data-stu-id="31085-101">Kestrel: Request trailer headers moved to new collection</span></span>

<span data-ttu-id="31085-102">이전 버전에서 Kestrel은 요청 본문을 끝까지 읽을 때 HTTP/1.1 청크 처리된 트레일러 헤더를 요청 헤더 컬렉션에 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="31085-102">In prior versions, Kestrel added HTTP/1.1 chunked trailer headers into the request headers collection when the request body was read to the end.</span></span> <span data-ttu-id="31085-103">이 동작은 헤더와 트레일러 사이의 모호성에 대한 문제를 발생시켰습니다.</span><span class="sxs-lookup"><span data-stu-id="31085-103">This behavior caused concerns about ambiguity between headers and trailers.</span></span> <span data-ttu-id="31085-104">트레일러를 새 컬렉션으로 이동하기로 결정했습니다.</span><span class="sxs-lookup"><span data-stu-id="31085-104">The decision was made to move the trailers to a new collection.</span></span>

<span data-ttu-id="31085-105">HTTP/2 요청 트레일러는 ASP.NET Core 2.2에서 사용할 수 없었지만 이제 ASP.NET Core 3.0의 이 새 컬렉션에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31085-105">HTTP/2 request trailers were unavailable in ASP.NET Core 2.2 but are now also available in this new collection in ASP.NET Core 3.0.</span></span>

<span data-ttu-id="31085-106">이러한 트레일러에 액세스하기 위해 새 요청 확장 메서드가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="31085-106">New request extension methods have been added to access these trailers.</span></span>

<span data-ttu-id="31085-107">HTTP/1.1 트레일러는 전체 요청 본문을 읽은 후에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31085-107">HTTP/1.1 trailers are available once the entire request body has been read.</span></span>

<span data-ttu-id="31085-108">HTTP/2 트레일러는 클라이언트에서 수신한 후 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31085-108">HTTP/2 trailers are available once they're received from the client.</span></span> <span data-ttu-id="31085-109">클라이언트는 전체 요청 본문이 최소한 서버에 의해 버퍼링될 때까지 트레일러를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31085-109">The client won't send the trailers until the entire request body has been at least buffered by the server.</span></span> <span data-ttu-id="31085-110">버퍼 공간을 확보하기 위해 요청 본문을 읽어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31085-110">You may need to read the request body to free up buffer space.</span></span> <span data-ttu-id="31085-111">트레일러는 요청 본문을 끝까지 읽으면 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="31085-111">Trailers are always available if you read the request body to the end.</span></span> <span data-ttu-id="31085-112">트레일러는 본문의 끝을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="31085-112">The trailers mark the end of the body.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="31085-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="31085-113">Version introduced</span></span>

<span data-ttu-id="31085-114">3.0</span><span class="sxs-lookup"><span data-stu-id="31085-114">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="31085-115">이전 동작</span><span class="sxs-lookup"><span data-stu-id="31085-115">Old behavior</span></span>

<span data-ttu-id="31085-116">요청 트레일러 헤더가 `HttpRequest.Headers` 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="31085-116">Request trailer headers would be added to the `HttpRequest.Headers` collection.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="31085-117">새 동작</span><span class="sxs-lookup"><span data-stu-id="31085-117">New behavior</span></span>

<span data-ttu-id="31085-118">요청 트레일러 헤더가 `HttpRequest.Headers` 컬렉션에 **존재하지 않습니다**.</span><span class="sxs-lookup"><span data-stu-id="31085-118">Request trailer headers **aren't present** in the `HttpRequest.Headers` collection.</span></span> <span data-ttu-id="31085-119">`HttpRequest`에서 다음 확장 메서드를 사용하여 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="31085-119">Use the following extension methods on `HttpRequest` to access them:</span></span>

- <span data-ttu-id="31085-120">`GetDeclaredTrailers()` - 본문 다음에 사용할 트레일러를 나열하는 요청 "트레일러" 헤더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31085-120">`GetDeclaredTrailers()` - Gets the request "Trailer" header that lists which trailers to expect after the body.</span></span>
- <span data-ttu-id="31085-121">`SupportsTrailers()` - 요청에서 트레일러 헤더 수신을 지원하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31085-121">`SupportsTrailers()` - Indicates if the request supports receiving trailer headers.</span></span>
- <span data-ttu-id="31085-122">`CheckTrailersAvailable()` - 요청에서 트레일러를 지원하는지 여부와 읽을 수 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="31085-122">`CheckTrailersAvailable()` - Determines if the request supports trailers and if they're available for reading.</span></span>
- <span data-ttu-id="31085-123">`GetTrailer(string trailerName)` - 응답에서 요청된 후행 헤더를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="31085-123">`GetTrailer(string trailerName)` - Gets the requested trailing header from the response.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="31085-124">변경 이유</span><span class="sxs-lookup"><span data-stu-id="31085-124">Reason for change</span></span>

<span data-ttu-id="31085-125">트레일러는 gRPC와 같은 시나리오의 주요 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="31085-125">Trailers are a key feature in scenarios like gRPC.</span></span> <span data-ttu-id="31085-126">트레일러를 병합하여 헤더를 요청하는 것은 사용자에게 혼동을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31085-126">Merging the trailers in to request headers was confusing to users.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="31085-127">권장 조치</span><span class="sxs-lookup"><span data-stu-id="31085-127">Recommended action</span></span>

<span data-ttu-id="31085-128">`HttpRequest`에서 트레일러 관련 확장 메서드를 사용하여 트레일러에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="31085-128">Use the trailer-related extension methods on `HttpRequest` to access trailers.</span></span>

#### <a name="category"></a><span data-ttu-id="31085-129">범주</span><span class="sxs-lookup"><span data-stu-id="31085-129">Category</span></span>

<span data-ttu-id="31085-130">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="31085-130">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="31085-131">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="31085-131">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Http.HttpRequest.Headers?displayProperty=nameWithType>

<!--

#### Affected APIs

`P:Microsoft.AspNetCore.Http.HttpRequest.Headers`

-->
