---
ms.openlocfilehash: 3d29848e12d496d2d53c204e00ef8604831495e1
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024703"
---
### <a name="intptr-and-uintptr-implement-iformattable"></a><span data-ttu-id="c824f-101">IntPtr 및 UIntPtr에서 IFormattable 구현</span><span class="sxs-lookup"><span data-stu-id="c824f-101">IntPtr and UIntPtr implement IFormattable</span></span>

<span data-ttu-id="c824f-102"><xref:System.IntPtr> 및 <xref:System.UIntPtr>에서는 이제 <xref:System.IFormattable>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-102"><xref:System.IntPtr> and <xref:System.UIntPtr> now implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="c824f-103"><xref:System.IFormattable> 지원을 확인하는 함수는 형식 지정자와 문화권을 전달할 수 있으므로 이러한 형식에 대해 다른 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-103">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c824f-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="c824f-104">Change description</span></span>

<span data-ttu-id="c824f-105">이전 버전의 .NET에서는 <xref:System.IntPtr> 및 <xref:System.UIntPtr>이 <xref:System.IFormattable>을 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-105">In previous versions of .NET, <xref:System.IntPtr> and <xref:System.UIntPtr> do not implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="c824f-106"><xref:System.IFormattable>을 확인하는 함수는 <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> 또는 <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>를 호출하는 것으로 대체될 수 있습니다. 이 경우 형식 지정자와 문화권이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-106">Functions that check for <xref:System.IFormattable> may fall back to just calling <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> or <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, which means that format specifiers and cultures are not respected.</span></span>

<span data-ttu-id="c824f-107">.NET 5.0 이상 버전에서는 <xref:System.IntPtr> 및 <xref:System.UIntPtr>이 <xref:System.IFormattable>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-107">In .NET 5.0 and later versions, <xref:System.IntPtr> and <xref:System.UIntPtr> implement <xref:System.IFormattable>.</span></span> <span data-ttu-id="c824f-108"><xref:System.IFormattable> 지원을 확인하는 함수는 형식 지정자와 문화권을 전달할 수 있으므로 이러한 형식에 대해 다른 결과를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-108">Functions that check for <xref:System.IFormattable> support may now return different results for these types, because they may pass in a format specifier and a culture.</span></span>

<span data-ttu-id="c824f-109">이러한 변경은 보간된 문자열 및 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>과 같은 시나리오에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-109">This change impacts scenarios like interpolated strings and <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, among others.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="c824f-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="c824f-110">Reason for change</span></span>

<span data-ttu-id="c824f-111"><xref:System.IntPtr> 및 <xref:System.UIntPtr>은 이제 `nint` 및 `nuint` 키워드를 통해 C# 언어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-111"><xref:System.IntPtr> and <xref:System.UIntPtr> now have language support in C# through the `nint` and `nuint` keywords.</span></span> <span data-ttu-id="c824f-112">지원 형식이 <xref:System.Int32?displayProperty=nameWithType> 등의 다른 기본 형식에 의해 노출되는 기능을 근거리 패리티(가능한 경우)에 제공하도록 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-112">The backing types were updated to provide near parity (where possible) with functionality exposed by other primitive types, such as <xref:System.Int32?displayProperty=nameWithType>.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c824f-113">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c824f-113">Version introduced</span></span>

<span data-ttu-id="c824f-114">5.0 미리 보기 4</span><span class="sxs-lookup"><span data-stu-id="c824f-114">5.0 Preview 4</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c824f-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="c824f-115">Recommended action</span></span>

<span data-ttu-id="c824f-116">이러한 형식의 값을 표시할 때 형식 지정자 또는 사용자 지정 문화권을 사용하지 않으려는 경우 `ToString()`의 <xref:System.IntPtr.ToString?displayProperty=nameWithType> 및 <xref:System.UIntPtr.ToString?displayProperty=nameWithType> 오버로드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-116">If you don't want a format specifier or custom culture to be used when displaying values of these types, you can call the <xref:System.IntPtr.ToString?displayProperty=nameWithType> and <xref:System.UIntPtr.ToString?displayProperty=nameWithType> overloads of `ToString()`.</span></span>

#### <a name="category"></a><span data-ttu-id="c824f-117">범주</span><span class="sxs-lookup"><span data-stu-id="c824f-117">Category</span></span>

<span data-ttu-id="c824f-118">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="c824f-118">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c824f-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c824f-119">Affected APIs</span></span>

<span data-ttu-id="c824f-120">API 분석을 통해 검색할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c824f-120">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
