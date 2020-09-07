---
ms.openlocfilehash: e47a24239872e3fe86ff6902f66b38daaa106598
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496562"
---
### <a name="eventlistener-truncates-strings-with-embedded-nulls"></a><span data-ttu-id="8de78-101">EventListener는 포함된 null이 있는 문자열을 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="8de78-101">EventListener truncates strings with embedded nulls</span></span>

#### <a name="details"></a><span data-ttu-id="8de78-102">설명</span><span class="sxs-lookup"><span data-stu-id="8de78-102">Details</span></span>

<span data-ttu-id="8de78-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName>는 포함된 null이 있는 문자열을 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="8de78-103"><xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> truncates strings with embedded nulls.</span></span> <span data-ttu-id="8de78-104">Null 문자는 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 클래스에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8de78-104">Null characters are not supported by the <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> class.</span></span> <span data-ttu-id="8de78-105">이 변경 내용은 <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName>를 사용하여 프로세스의 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 데이터를 읽고 null 문자를 구분 기호로 사용하는 앱에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8de78-105">The change only affects apps that use <xref:System.Diagnostics.Tracing.EventListener?displayProperty=fullName> to read <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data in process and that use null characters as delimiters.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="8de78-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="8de78-106">Suggestion</span></span>

<span data-ttu-id="8de78-107">가능하면 포함된 null 문자를 사용하지 않도록 <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> 데이터를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8de78-107"><xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName> data should be updated, if possible, to not use embedded null characters.</span></span>

| <span data-ttu-id="8de78-108">이름</span><span class="sxs-lookup"><span data-stu-id="8de78-108">Name</span></span>    | <span data-ttu-id="8de78-109">값</span><span class="sxs-lookup"><span data-stu-id="8de78-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="8de78-110">Scope</span><span class="sxs-lookup"><span data-stu-id="8de78-110">Scope</span></span>   |<span data-ttu-id="8de78-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8de78-111">Edge</span></span>|
|<span data-ttu-id="8de78-112">버전</span><span class="sxs-lookup"><span data-stu-id="8de78-112">Version</span></span>|<span data-ttu-id="8de78-113">4.5.1</span><span class="sxs-lookup"><span data-stu-id="8de78-113">4.5.1</span></span>|
|<span data-ttu-id="8de78-114">형식</span><span class="sxs-lookup"><span data-stu-id="8de78-114">Type</span></span>|<span data-ttu-id="8de78-115">런타임</span><span class="sxs-lookup"><span data-stu-id="8de78-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="8de78-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="8de78-116">Affected APIs</span></span>

- <xref:System.Diagnostics.Tracing.EventListener.%23ctor>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)?displayProperty=nameWithType>
- <xref:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Diagnostics.Tracing.EventListener.#ctor`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords)`
- `M:System.Diagnostics.Tracing.EventListener.EnableEvents(System.Diagnostics.Tracing.EventSource,System.Diagnostics.Tracing.EventLevel,System.Diagnostics.Tracing.EventKeywords,System.Collections.Generic.IDictionary{System.String,System.String})`

-->
