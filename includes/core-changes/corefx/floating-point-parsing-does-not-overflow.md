---
ms.openlocfilehash: 30580b3fde5b8a99862896bb7d31c6c4024f97e8
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198501"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a><span data-ttu-id="094eb-101">부동 소수점 구문 분석 작업은 더 이상 실패하거나 OverflowException을 throw하지 않음</span><span class="sxs-lookup"><span data-stu-id="094eb-101">Floating-point parsing operations no longer fail or throw an OverflowException</span></span>

<span data-ttu-id="094eb-102">부동 소수점 구문 분석 메서드는 더 이상 <xref:System.OverflowException>을 throw하지 않거나, 숫자 값이 <xref:System.Single> 또는 <xref:System.Double> 부동 소수점 형식의 범위를 벗어난 문자열을 구문 분석할 때 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-102">The floating-point parsing methods no longer throw an <xref:System.OverflowException> or return `false` when they parse a string whose numeric value is outside the range of the <xref:System.Single> or <xref:System.Double> floating-point type.</span></span>

#### <a name="change-description"></a><span data-ttu-id="094eb-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="094eb-103">Change description</span></span>

<span data-ttu-id="094eb-104">.NET Core 2.2 및 이전 버전에서 <xref:System.Double.Parse%2A?displayProperty=nameWithType> 및 <xref:System.Single.Parse%2A?displayProperty=nameWithType> 메서드는 해당 형식의 범위를 벗어난 값에 대해 <xref:System.OverflowException>를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-104">In .NET Core 2.2 and earlier versions, the <xref:System.Double.Parse%2A?displayProperty=nameWithType> and <xref:System.Single.Parse%2A?displayProperty=nameWithType> methods throw an <xref:System.OverflowException> for values that outside the range of their respective type.</span></span> <span data-ttu-id="094eb-105"><xref:System.Double.TryParse%2A?displayProperty=nameWithType> 및 <xref:System.Single.TryParse%2A?displayProperty=nameWithType> 메서드는 범위를 벗어난 숫자 값의 문자열 표현에 대해 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-105">The <xref:System.Double.TryParse%2A?displayProperty=nameWithType> and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods return `false` for the string representations of out-of-range numeric values.</span></span>

<span data-ttu-id="094eb-106">.NET Core 3.0부터 범위를 벗어난 숫자 문자열을 구문 분석할 때 <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> 및 <xref:System.Single.TryParse%2A?displayProperty=nameWithType> 메서드가 더 이상 실패하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-106">Starting with .NET Core 3.0, the <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> methods no longer fail when parsing out-of-range numeric strings.</span></span> <span data-ttu-id="094eb-107">대신 <xref:System.Double> 구문 분석 메서드는 <xref:System.Double.MaxValue?displayProperty=nameWithType>를 초과하는 값에 대해 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>를 반환하고 <xref:System.Double.MinValue?displayProperty=nameWithType>보다 작은 값에 대해 <xref:System.Double.NegativeInfinity?displayProperty=nameWithType>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-107">Instead, the <xref:System.Double> parsing methods return <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Double.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Double.MinValue?displayProperty=nameWithType>.</span></span> <span data-ttu-id="094eb-108">마찬가지로 <xref:System.Single> 구문 분석 메서드는 <xref:System.Single.MaxValue?displayProperty=nameWithType>를 초과하는 값에 대해 <xref:System.Single.PositiveInfinity?displayProperty=nameWithType>를 반환하고 <xref:System.Single.MinValue?displayProperty=nameWithType>보다 작은 값에 대해 <xref:System.Single.NegativeInfinity?displayProperty=nameWithType>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-108">Similarly, the <xref:System.Single> parsing methods return <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> for values that exceed <xref:System.Single.MaxValue?displayProperty=nameWithType>, and they return <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> for values that are less than <xref:System.Single.MinValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="094eb-109">이러한 변경은 개정된 IEEE 754:2008 규정 준수를 위해 이루어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-109">This change was made for improved IEEE 754:2008 compliance.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="094eb-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="094eb-110">Version introduced</span></span>

<span data-ttu-id="094eb-111">3.0</span><span class="sxs-lookup"><span data-stu-id="094eb-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="094eb-112">권장 작업</span><span class="sxs-lookup"><span data-stu-id="094eb-112">Recommended action</span></span>

<span data-ttu-id="094eb-113">이러한 변경 내용은 다음 두 가지 방법 중 하나로 코드에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-113">This change can affect your code in either of two ways:</span></span>

- <span data-ttu-id="094eb-114">코드는 오버플로가 발생할 때 실행되는 <xref:System.OverflowException>에 대한 처리기에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-114">Your code depends on the handler for the <xref:System.OverflowException> to execute when an overflow occurs.</span></span> <span data-ttu-id="094eb-115">이 경우 `catch` 문을 제거하고 <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> 또는 <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType>가 `true`인지 여부를 테스트하는 `If` 문에 필요한 코드를 넣어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-115">In this case, you should remove the `catch` statement and place any necessary code in an `If` statement that tests whether <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> or <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> is `true`.</span></span>

- <span data-ttu-id="094eb-116">코드에서 부동 소수점 값이 `Infinity`가 아니라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-116">Your code assumes that floating-point values are not `Infinity`.</span></span> <span data-ttu-id="094eb-117">이 경우 `PositiveInfinity` 및 `NegativeInfinity`의 부동 소수점 값을 확인하는 데 필요한 코드를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="094eb-117">In this case, you should add the necessary code to check for floating-point values of `PositiveInfinity` and `NegativeInfinity`.</span></span>

#### <a name="category"></a><span data-ttu-id="094eb-118">범주</span><span class="sxs-lookup"><span data-stu-id="094eb-118">Category</span></span>

<span data-ttu-id="094eb-119">CoreFx</span><span class="sxs-lookup"><span data-stu-id="094eb-119">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="094eb-120">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="094eb-120">Affected APIs</span></span>

- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
