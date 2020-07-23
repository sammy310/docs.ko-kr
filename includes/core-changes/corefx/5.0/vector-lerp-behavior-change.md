---
ms.openlocfilehash: 4bc060f991501b81db0cb7c521e55996a2b5e91e
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281309"
---
### <a name="behavior-change-for-vector2lerp-and-vector4lerp"></a><span data-ttu-id="1fa7b-101">Vector2.Lerp 및 Vector4.Lerp의 동작 변경</span><span class="sxs-lookup"><span data-stu-id="1fa7b-101">Behavior change for Vector2.Lerp and Vector4.Lerp</span></span>

<span data-ttu-id="1fa7b-102"><xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> 및 <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> 구현이 부동 소수점 반올림 오차를 올바르게 고려하도록 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-102">The implementation of <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> changed to correctly account for a floating-point rounding error.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1fa7b-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="1fa7b-103">Change description</span></span>

<span data-ttu-id="1fa7b-104">이전에는 <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> 및 <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType>이 `value1 + (value2 - value1) * amount`로 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-104">Previously, <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=nameWithType> and <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=nameWithType> were implemented as `value1 + (value2 - value1) * amount`.</span></span> <span data-ttu-id="1fa7b-105">그러나 부동 소수점 반올림 오차로 인해 `amount`가 `1.0f`이면 알고리즘에서 `value2`를 반환하지 않는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-105">However, due to a floating-point rounding error, this algorithm doesn't always return `value2` when `amount` is `1.0f`.</span></span>

<span data-ttu-id="1fa7b-106">.NET 5.0 이상 구현에서는 <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>과 동일한 알고리즘(`(value1 * (1.0f - amount)) + (value2 * amount)`)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-106">In .NET 5.0 and later, the implementation uses the same algorithm as <xref:System.Numerics.Vector3.Lerp(System.Numerics.Vector3,System.Numerics.Vector3,System.Single)?displayProperty=nameWithType>, which is `(value1 * (1.0f - amount)) + (value2 * amount)`.</span></span> <span data-ttu-id="1fa7b-107">이 알고리즘은 반올림 오차를 올바르게 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-107">This algorithm correctly accounts for the rounding error.</span></span> <span data-ttu-id="1fa7b-108">이제 `amount`가 `1.0f`인 경우 결과는 정확하게 `value2`가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-108">Now, when `amount` is `1.0f`, the result is precisely `value2`.</span></span> <span data-ttu-id="1fa7b-109">업데이트된 알고리즘이 제공되면 <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType>을 사용하여 알고리즘을 자유롭게 최적화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-109">The updated algorithm also allows the algorithm to be freely optimized using <xref:System.MathF.FusedMultiplyAdd%2A?displayProperty=nameWithType> when it's available.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1fa7b-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="1fa7b-110">Version introduced</span></span>

<span data-ttu-id="1fa7b-111">5.0 미리 보기 7</span><span class="sxs-lookup"><span data-stu-id="1fa7b-111">5.0 Preview 7</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1fa7b-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="1fa7b-112">Recommended action</span></span>

<span data-ttu-id="1fa7b-113">별도의 동작이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-113">No action is necessary.</span></span> <span data-ttu-id="1fa7b-114">그러나 이전 동작을 유지하려는 경우 이전 알고리즘인 `value1 + (value2 - value1) * amount`를 사용하는 자체 `Lerp` 함수를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fa7b-114">However, if you want to maintain the old behavior, you can implement your own `Lerp` function that uses the previous algorithm of `value1 + (value2 - value1) * amount`.</span></span>

#### <a name="category"></a><span data-ttu-id="1fa7b-115">범주</span><span class="sxs-lookup"><span data-stu-id="1fa7b-115">Category</span></span>

<span data-ttu-id="1fa7b-116">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="1fa7b-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1fa7b-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="1fa7b-117">Affected APIs</span></span>

- <xref:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)?displayProperty=fullName>
- <xref:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Numerics.Vector2.Lerp(System.Numerics.Vector2,System.Numerics.Vector2,System.Single)`
- `M:System.Numerics.Vector4.Lerp(System.Numerics.Vector4,System.Numerics.Vector4,System.Single)`

-->
