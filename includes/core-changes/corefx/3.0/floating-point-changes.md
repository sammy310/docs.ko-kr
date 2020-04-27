---
ms.openlocfilehash: 22dbb1e982f83687a9e0eb288ed72c78c676db77
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021630"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a><span data-ttu-id="3f238-101">부동 소수점 서식 및 구문 분석 동작 변경됨</span><span class="sxs-lookup"><span data-stu-id="3f238-101">Floating-point formatting and parsing behavior changed</span></span>

<span data-ttu-id="3f238-102">이제 부동 소수점 구문 분석 및 서식 동작(<xref:System.Double> 및 <xref:System.Single> 형식 사용)이 IEEE 규격으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3f238-102">Floating point parsing and formatting behavior (by the <xref:System.Double> and <xref:System.Single> types) are now IEEE-compliant.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3f238-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="3f238-103">Change description</span></span>

<span data-ttu-id="3f238-104">.NET Core 2.2 및 이전 버전에서는 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 및 <xref:System.Single.ToString%2A?displayProperty=nameWithType>을 사용한 서식과 <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, <xref:System.Single.TryParse%2A?displayProperty=nameWithType>을 사용한 구문 분석이 IEEE 규격이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3f238-104">In .NET Core 2.2 and earlier versions, formatting with <xref:System.Double.ToString%2A?displayProperty=nameWithType> and <xref:System.Single.ToString%2A?displayProperty=nameWithType>, and parsing with <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType>, and <xref:System.Single.TryParse%2A?displayProperty=nameWithType> are not IEEE-compliant.</span></span> <span data-ttu-id="3f238-105">따라서 지원되는 표준 또는 사용자 지정 형식 문자열로 값이 왕복한다고 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f238-105">As a result, it is impossible to guarantee that a value will roundtrip with any supported standard or custom format string.</span></span> <span data-ttu-id="3f238-106">입력에 따라 서식이 지정된 값을 구문 분석하려는 시도가 실패하는 경우도 있고, 구문 분석된 값이 원래 값과 달라지는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f238-106">For some inputs, the attempt to parse a formatted value can fail, and for others, the parsed value doesn't equal the original value.</span></span>

<span data-ttu-id="3f238-107">.NET Core 3.0부터는 구문 분석 및 서식 작업이 IEEE 754 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="3f238-107">Starting with .NET Core 3.0, parsing and formatting operations are IEEE 754-compliant.</span></span> <span data-ttu-id="3f238-108">따라서 .NET의 부동 소수점 형식 동작이 C#과 같은 IEEE 규격 언어의 동작과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="3f238-108">This ensures that the behavior of floating-point types in .NET matches that of IEEE-compliant languages such as C#.</span></span> <span data-ttu-id="3f238-109">자세한 내용은 [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)(.NET Core 3.0의 부동 소수점 구문 분석 및 서식 개선 사항)에 대한 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3f238-109">For more information, see the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3f238-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="3f238-110">Version introduced</span></span>

<span data-ttu-id="3f238-111">3.0</span><span class="sxs-lookup"><span data-stu-id="3f238-111">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3f238-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="3f238-112">Recommended action</span></span>

<span data-ttu-id="3f238-113">[Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)(.NET Core 3.0의 부동 소수점 구문 분석 및 서식 개선 사항) 블로그 게시물의 “기존 코드에 대한 잠재적 영향” 섹션에서는 .NET Core 2.2 애플리케이션과 비교해서 동작이 변경된 경우 코드를 변경하도록 제안합니다. 이 제안을 따르려면 일반적으로 다른 표준 또는 사용자 지정 형식 문자열을 사용하여 필요한 동작을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f238-113">The "Potential impact to existing code" section of the [Floating-point parsing and formatting improvements in .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/) blog post suggests changes to your code if you observe a change of behavior when compared to .NET Core 2.2 applications Generally, this involves using a different standard or custom format string to enforce the desired behavior.</span></span> <span data-ttu-id="3f238-114">이전에 잘못된 일부 결과는 해결 방법이 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f238-114">Some results may not have a workaround if they were previously incorrect.</span></span>

#### <a name="category"></a><span data-ttu-id="3f238-115">범주</span><span class="sxs-lookup"><span data-stu-id="3f238-115">Category</span></span>

<span data-ttu-id="3f238-116">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="3f238-116">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3f238-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="3f238-117">Affected APIs</span></span>

- <xref:System.Double.ToString%2A?displayProperty=nameWithType>
- <xref:System.Single.ToString%2A?displayProperty=nameWithType>
- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `Overload:System.Double.ToString`
- `Overload:System.Single.ToString`
- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
