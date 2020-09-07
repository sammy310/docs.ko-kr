---
ms.openlocfilehash: 26facb645de175d7ef0432394fc2b84f59e8437d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496650"
---
### <a name="error-codes-for-maxrequestlength-or-maxreceivedmessagesize-are-different"></a><span data-ttu-id="27e82-101">maxRequestLength 또는 maxReceivedMessageSize의 오류 코드가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="27e82-101">Error codes for maxRequestLength or maxReceivedMessageSize are different</span></span>

#### <a name="details"></a><span data-ttu-id="27e82-102">설명</span><span class="sxs-lookup"><span data-stu-id="27e82-102">Details</span></span>

<span data-ttu-id="27e82-103">IIS(인터넷 정보 서비스) 또는 ASP.NET 개발 서버에서 호스팅되는 WCF 웹 서비스의 메시지가 maxRequestLength(ASP.NET의 경우) 또는 maxReceivedMessageSize(WCF의 경우)를 초과할 경우 오류 코드가 변경됩니다. HTTP 상태 코드가 400(잘못된 요청)에서 413(요청 엔터티가 너무 큼)으로 변경되었으며, maxRequestLength 또는 maxReceivedMessageSize 설정을 초과하는 메시지가 <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="27e82-103">Messages in WCF web services hosted in Internet Information Services (IIS) or ASP.NET Development Server that exceed maxRequestLength (in ASP.NET) or maxReceivedMessageSize (in WCF) have different error codeThe HTTP status code has changed from 400 (Bad Request) to 413 (Request Entity Too Large), and messages that exceed either the maxRequestLength or the maxReceivedMessageSize setting throw a <xref:System.ServiceModel.ProtocolException?displayProperty=fullName> exception.</span></span> <span data-ttu-id="27e82-104">이는 전송 모드가 스트리밍 상태인 경우를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="27e82-104">This includes cases in which the transfer mode is Streamed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="27e82-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="27e82-105">Suggestion</span></span>

<span data-ttu-id="27e82-106">이러한 변경은 메시지 길이가 ASP.NET 또는 WCF에서 허용한 한계를 초과하는 경우에 디버깅을 용이하게 합니다. HTTP 400 상태 코드에 따라 처리를 수행하는 모든 코드를 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e82-106">This change facilitates debugging in cases where the message length exceeds the limits allowed by ASP.NET or WCF.You must modify any code that performs processing based on an HTTP 400 status code.</span></span>

| <span data-ttu-id="27e82-107">이름</span><span class="sxs-lookup"><span data-stu-id="27e82-107">Name</span></span>    | <span data-ttu-id="27e82-108">값</span><span class="sxs-lookup"><span data-stu-id="27e82-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="27e82-109">Scope</span><span class="sxs-lookup"><span data-stu-id="27e82-109">Scope</span></span>   |<span data-ttu-id="27e82-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="27e82-110">Edge</span></span>|
|<span data-ttu-id="27e82-111">버전</span><span class="sxs-lookup"><span data-stu-id="27e82-111">Version</span></span>|<span data-ttu-id="27e82-112">4.5</span><span class="sxs-lookup"><span data-stu-id="27e82-112">4.5</span></span>|
|<span data-ttu-id="27e82-113">형식</span><span class="sxs-lookup"><span data-stu-id="27e82-113">Type</span></span>|<span data-ttu-id="27e82-114">런타임</span><span class="sxs-lookup"><span data-stu-id="27e82-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="27e82-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="27e82-115">Affected APIs</span></span>

<span data-ttu-id="27e82-116">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="27e82-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
