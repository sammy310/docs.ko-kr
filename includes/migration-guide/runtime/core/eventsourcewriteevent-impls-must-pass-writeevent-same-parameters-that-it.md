---
ms.openlocfilehash: 99a7fa0fcfce6d490a182f85709b5dd0e0e8c86f
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496138"
---
### <a name="eventsourcewriteevent-impls-must-pass-writeevent-the-same-parameters-that-it-received-plus-id"></a><span data-ttu-id="4f73d-101">EventSource.WriteEvent impls는 수신된 매개 변수와 동일한 WriteEvent를 전달해야 합니다(추가 ID).</span><span class="sxs-lookup"><span data-stu-id="4f73d-101">EventSource.WriteEvent impls must pass WriteEvent the same parameters that it received (plus ID)</span></span>

#### <a name="details"></a><span data-ttu-id="4f73d-102">설명</span><span class="sxs-lookup"><span data-stu-id="4f73d-102">Details</span></span>

<span data-ttu-id="4f73d-103">이제 런타임에서는 다음을 지정하는 계약이 적용됩니다. ETW 이벤트 메서드를 정의하는 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>에서 파생된 클래스는 이벤트 ID 다음에 ETW 이벤트 메서드가 전달된 동일한 인수를 사용하여 기본 클래스 <code>EventSource.WriteEvent</code> 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f73d-103">The runtime now enforces the contract that specifies the following: A class derived from <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> that defines an ETW event method must call the base class <code>EventSource.WriteEvent</code> method with the event ID followed by the same arguments that the ETW event method was passed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4f73d-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="4f73d-104">Suggestion</span></span>

<span data-ttu-id="4f73d-105"><xref:System.IndexOutOfRangeException?displayProperty=fullName>가 이 계약을 위반하는 이벤트 소스에 대해 프로세스의 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> 데이터를 읽는 경우 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f73d-105">An <xref:System.IndexOutOfRangeException?displayProperty=fullName> exception is thrown if an <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> reads <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process for an event source that violates this contract.</span></span>

| <span data-ttu-id="4f73d-106">이름</span><span class="sxs-lookup"><span data-stu-id="4f73d-106">Name</span></span>    | <span data-ttu-id="4f73d-107">값</span><span class="sxs-lookup"><span data-stu-id="4f73d-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4f73d-108">Scope</span><span class="sxs-lookup"><span data-stu-id="4f73d-108">Scope</span></span>   |<span data-ttu-id="4f73d-109">부</span><span class="sxs-lookup"><span data-stu-id="4f73d-109">Minor</span></span>|
|<span data-ttu-id="4f73d-110">버전</span><span class="sxs-lookup"><span data-stu-id="4f73d-110">Version</span></span>|<span data-ttu-id="4f73d-111">4.5.1</span><span class="sxs-lookup"><span data-stu-id="4f73d-111">4.5.1</span></span>|
|<span data-ttu-id="4f73d-112">형식</span><span class="sxs-lookup"><span data-stu-id="4f73d-112">Type</span></span>|<span data-ttu-id="4f73d-113">런타임</span><span class="sxs-lookup"><span data-stu-id="4f73d-113">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="4f73d-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="4f73d-114">Affected APIs</span></span>

<span data-ttu-id="4f73d-115">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f73d-115">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
