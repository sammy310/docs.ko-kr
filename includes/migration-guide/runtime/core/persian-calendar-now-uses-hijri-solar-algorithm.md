---
ms.openlocfilehash: 14581b193fc000c7f805a0602e191cad688c014a
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497571"
---
### <a name="persian-calendar-now-uses-the-hijri-solar-algorithm"></a><span data-ttu-id="0ac6d-101">이제 페르시아력이 회교식 양력 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac6d-101">Persian calendar now uses the Hijri solar algorithm</span></span>

#### <a name="details"></a><span data-ttu-id="0ac6d-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0ac6d-102">Details</span></span>

<span data-ttu-id="0ac6d-103">.NET Framework 4.6부터는 <xref:System.Globalization.PersianCalendar?displayProperty=fullName> 클래스에서 회교식 양력 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0ac6d-103">Starting with the .NET Framework 4.6, the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> class uses the Hijri solar algorithm.</span></span> <span data-ttu-id="0ac6d-104">.NET Framework 4.6부터 <xref:System.Globalization.PersianCalendar?displayProperty=fullName>와 다른 달력 간의 날짜 변환은 1800년 전 또는 2023년 후에 대한 날짜에 대해(그레고리오력) 약간 다른 결과를 생성할 수 있습니다. 또한 <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType>은 이제 <code>March 21, 0622</code> 대신 <code>March 22, 0622</code>입니다.</span><span class="sxs-lookup"><span data-stu-id="0ac6d-104">Converting dates between the <xref:System.Globalization.PersianCalendar?displayProperty=fullName> and other calendars may produce a slightly different result beginning with the .NET Framework 4.6 for dates earlier than 1800 or later than 2023 (Gregorian).Also, <xref:System.Globalization.PersianCalendar.MinSupportedDateTime?displayProperty=nameWithType> is now <code>March 22, 0622</code> instead of <code>March 21, 0622</code>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0ac6d-105">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="0ac6d-105">Suggestion</span></span>

<span data-ttu-id="0ac6d-106">.NET Framework 4.6에서 PersianCalendar를 사용할 때 일부 이전 또는 늦은 날짜는 약간 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ac6d-106">Be aware that some early or late dates may be slightly different when using the PersianCalendar in .NET Framework 4.6.</span></span> <span data-ttu-id="0ac6d-107">또한 다른 .NET Framework 버전에서 실행될 수 있는 프로세스 사이의 날짜를 직렬화할 때 PersianCalendar 날짜 문자열로 저장하지 마십시오(해당 값이 다를 수 있음).</span><span class="sxs-lookup"><span data-stu-id="0ac6d-107">Also, when serializing dates between processes which may run on different .NET Framework versions, do not store them as PersianCalendar date strings (since those values may be different).</span></span>

| <span data-ttu-id="0ac6d-108">Name</span><span class="sxs-lookup"><span data-stu-id="0ac6d-108">Name</span></span>    | <span data-ttu-id="0ac6d-109">값</span><span class="sxs-lookup"><span data-stu-id="0ac6d-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0ac6d-110">Scope</span><span class="sxs-lookup"><span data-stu-id="0ac6d-110">Scope</span></span>   |<span data-ttu-id="0ac6d-111">부</span><span class="sxs-lookup"><span data-stu-id="0ac6d-111">Minor</span></span>|
|<span data-ttu-id="0ac6d-112">버전</span><span class="sxs-lookup"><span data-stu-id="0ac6d-112">Version</span></span>|<span data-ttu-id="0ac6d-113">4.6</span><span class="sxs-lookup"><span data-stu-id="0ac6d-113">4.6</span></span>|
|<span data-ttu-id="0ac6d-114">형식</span><span class="sxs-lookup"><span data-stu-id="0ac6d-114">Type</span></span>|<span data-ttu-id="0ac6d-115">런타임</span><span class="sxs-lookup"><span data-stu-id="0ac6d-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0ac6d-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0ac6d-116">Affected APIs</span></span>

- <xref:System.Globalization.PersianCalendar?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Globalization.PersianCalendar`

-->
