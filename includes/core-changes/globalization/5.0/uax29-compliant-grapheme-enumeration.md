---
ms.openlocfilehash: c0c1c9c9d8e3aeb6f689f754d09b50b208b54112
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702262"
---
### <a name="stringinfo-and-textelementenumerator-are-now-uax29-compliant"></a><span data-ttu-id="e86fb-101">StringInfo 및 TextElementEnumerator가 이제 UAX29 규격임</span><span class="sxs-lookup"><span data-stu-id="e86fb-101">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>

<span data-ttu-id="e86fb-102">이 변경 전에 <xref:System.Globalization.StringInfo?displayProperty=fullName> 및 <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>는 모든 문자소 클러스터를 제대로 처리하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-102">Prior to this change, <xref:System.Globalization.StringInfo?displayProperty=fullName> and <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName> didn't properly handle all grapheme clusters.</span></span> <span data-ttu-id="e86fb-103">일부 문자소는 함께 유지되지 않고 구성 요소로 분할되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-103">Some graphemes were split into their constituent components instead of being kept together.</span></span> <span data-ttu-id="e86fb-104">이제 <xref:System.Globalization.StringInfo> 및 <xref:System.Globalization.TextElementEnumerator>는 최신 버전의 유니코드 표준에 따라 문자소 클러스터를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-104">Now, <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> process grapheme clusters according to the latest version of the Unicode Standard.</span></span>

<span data-ttu-id="e86fb-105">또한 Visual Basic에서 문자열의 문자 순서를 반대로 만드는 <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> 메서드는 이제 문자소 클러스터에 대한 유니코드 표준을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-105">In addition, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

#### <a name="change-description"></a><span data-ttu-id="e86fb-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="e86fb-106">Change description</span></span>

<span data-ttu-id="e86fb-107">[문자소](https://www.unicode.org/glossary/#grapheme) 또는 [확장 문자소 클러스터](https://www.unicode.org/glossary/#extended_grapheme_cluster)는 여러 유니코드 코드 포인트로 구성될 수 있는 단일 사용자 인식 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-107">A [grapheme](https://www.unicode.org/glossary/#grapheme) or [extended grapheme cluster](https://www.unicode.org/glossary/#extended_grapheme_cluster) is a single user-perceived character that may be made up of multiple Unicode code points.</span></span> <span data-ttu-id="e86fb-108">예를 들어 태국어 문자 "kam"(:::no-loc text="กำ":::)을 포함하는 문자열은 다음 두 개의 문자로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-108">For example, the string containing the Thai character "kam" (:::no-loc text="กำ":::) consists of the following two characters:</span></span>

- <span data-ttu-id="e86fb-109">:::no-loc text="ก":::(= '\u0e01') THAI CHARACTER KO KAI</span><span class="sxs-lookup"><span data-stu-id="e86fb-109">:::no-loc text="ก"::: (= '\u0e01') THAI CHARACTER KO KAI</span></span>
- <span data-ttu-id="e86fb-110">:::no-loc text=" ำ":::(= '\u0e33') THAI CHARACTER SARA AM</span><span class="sxs-lookup"><span data-stu-id="e86fb-110">:::no-loc text=" ำ"::: (= '\u0e33') THAI CHARACTER SARA AM</span></span>

<span data-ttu-id="e86fb-111">사용자에게 표시되는 경우 운영 체제는 두 문자를 결합하여 단일 표시 문자(또는 문자소)인 "kam"(또는 :::no-loc text="กำ":::)을 형성합니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-111">When displayed to the user, the operating system combines the two characters to form the single display character (or grapheme) "kam" or :::no-loc text="กำ":::.</span></span> <span data-ttu-id="e86fb-112">이모지도 비슷한 방식으로 표시하기 위해 결합된 여러 문자로 구성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-112">Emoji can also consist of multiple characters that are combined for display in a similar way.</span></span>

> [!TIP]
> <span data-ttu-id="e86fb-113">.NET 문서에서는 문자소를 참조하는 경우 “텍스트 요소”라는 용어를 사용하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-113">The .NET documentation sometimes uses the term "text element" when referring to a grapheme.</span></span>

<span data-ttu-id="e86fb-114"><xref:System.Globalization.StringInfo> 및 <xref:System.Globalization.TextElementEnumerator> 클래스는 문자열을 검사하고 포함된 문자소에 관한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-114">The <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes inspect strings and return information about the graphemes they contain.</span></span> <span data-ttu-id="e86fb-115">.NET Framework(모든 버전) 및 .NET Core 3.x 이하에서 이 두 개의 클래스는 일부 결합 클래스를 처리하지만 [유니코드 표준](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries)을 완전하게 준수하지는 않는 사용자 지정 논리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-115">In .NET Framework (all versions) and .NET Core 3.x and earlier, these two classes use custom logic that handles some combining classes but doesn't fully comply with the [Unicode Standard](https://www.unicode.org/reports/tr29/tr29-35.html#Grapheme_Cluster_Boundaries).</span></span> <span data-ttu-id="e86fb-116">예를 들어 <xref:System.Globalization.StringInfo> 및 <xref:System.Globalization.TextElementEnumerator> 클래스는 해당 구성 요소를 함께 유지하는 대신 단일 태국어 문자 “kam”을 다시 구성 요소로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-116">For example, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes incorrectly split the single Thai character "kam" back into its constituent components instead of keeping them together.</span></span> <span data-ttu-id="e86fb-117">또한 해당 클래스는 단일 문자소 클러스터로 함께 유지하는 대신 이모지 문자 "🤷🏽‍♀️"를 4개의 클러스터(어깨를 으쓱하는 사람, 피부색 한정자, 성별 한정자 및 표시되지 않는 결합자)로 잘못 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-117">These classes also incorrectly split the emoji character "🤷🏽‍♀️" into four clusters (person shrugging, skin tone modifier, gender modifier, and an invisible combiner) instead of keeping them together as a single grapheme cluster.</span></span>

<span data-ttu-id="e86fb-118">.NET 5부터 <xref:System.Globalization.StringInfo> 및 <xref:System.Globalization.TextElementEnumerator> 클래스는 [유니코드 표준 부록\# 29 수정 35, 섹션 3](https://www.unicode.org/reports/tr29/tr29-35.html)에서 정의한 대로 유니코드 표준을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-118">Starting with .NET 5, the <xref:System.Globalization.StringInfo> and <xref:System.Globalization.TextElementEnumerator> classes implement the Unicode standard as defined by [Unicode Standard Annex \#29, rev. 35, sec. 3](https://www.unicode.org/reports/tr29/tr29-35.html).</span></span> <span data-ttu-id="e86fb-119">특히 이제는 모든 결합 클래스에 대해 [확장 문자소 클러스터](https://www.unicode.org/glossary/#extended_grapheme_cluster)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-119">In particular, they now return [extended grapheme clusters](https://www.unicode.org/glossary/#extended_grapheme_cluster) for all combining classes.</span></span>

<span data-ttu-id="e86fb-120">다음 C# 코드를 생각해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-120">Consider the following C# code:</span></span>

```cs
using System.Globalization;

static void Main(string[] args)
{
    PrintGraphemes("กำ");
    PrintGraphemes("🤷🏽‍♀️");
}

static void PrintGraphemes(string str)
{
    Console.WriteLine($"Printing graphemes of \"{str}\"...");
    int i = 0;

    TextElementEnumerator enumerator = StringInfo.GetTextElementEnumerator(str);
    while (enumerator.MoveNext())
    {
        Console.WriteLine($"Grapheme {++i}: \"{enumerator.Current}\"");
    }

    Console.WriteLine($"({i} grapheme(s) total.)");
    Console.WriteLine();
}
```

<span data-ttu-id="e86fb-121">.NET Framework 및 .NET Core 3.x 이하 버전에서는 문자소가 분할되고 콘솔 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-121">In .NET Framework and .NET Core 3.x and earlier versions, the graphemes are split up, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "ก"
Grapheme 2: "ำ"
(2 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷"
Grapheme 2: "🏽"
Grapheme 3: "‍"
Grapheme 4: "♀️"
(4 grapheme(s) total.)
```

<span data-ttu-id="e86fb-122">.NET 5 이상 버전에서 문자소는 함께 유지되며 콘솔 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-122">In .NET 5 and later versions, the graphemes are kept together, and the console output is as follows:</span></span>

```txt
Printing graphemes of "กำ"...
Grapheme 1: "กำ"
(1 grapheme(s) total.)

Printing graphemes of "🤷🏽‍♀️"...
Grapheme 1: "🤷🏽‍♀️"
(1 grapheme(s) total.)
```

<span data-ttu-id="e86fb-123">또한 .NET 5부터 Visual Basic에서 문자열의 문자 순서를 반대로 만드는 <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> 메서드는 이제 문자소 클러스터에 대한 유니코드 표준을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-123">In addition, starting in .NET 5, the <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName> method, which reverses the characters in a string in Visual Basic, now also follows the Unicode standard for grapheme clusters.</span></span>

<span data-ttu-id="e86fb-124">해당 변경 내용은 .Net Core 3.0에서 <xref:System.Text.Rune?displayProperty=fullName> 형식으로 도입된 유니코드 스칼라 값 열거형 API를 보완하기 위해 확장 문자소 클러스터 열거형 API를 비롯하여 .NET의 광범위한 유니코드 및 UTF-8 개선 사항 세트에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-124">These changes are part of a wider set of Unicode and UTF-8 improvements in .NET, including an extended grapheme cluster enumeration API to complement the Unicode scalar-value enumeration APIs that were introduced with the <xref:System.Text.Rune?displayProperty=fullName> type in .NET Core 3.0.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="e86fb-125">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="e86fb-125">Version introduced</span></span>

<span data-ttu-id="e86fb-126">.NET 5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="e86fb-126">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="e86fb-127">권장 조치</span><span class="sxs-lookup"><span data-stu-id="e86fb-127">Recommended action</span></span>

<span data-ttu-id="e86fb-128">아무 작업도 수행할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-128">You don't need to take any action.</span></span> <span data-ttu-id="e86fb-129">앱은 자동으로 다양한 세계화 관련 시나리오에서 더 많은 표준 규격 방식으로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="e86fb-129">Your apps will automatically behave in a more standards-compliant manner in a variety of globalization-related scenarios.</span></span>

#### <a name="category"></a><span data-ttu-id="e86fb-130">범주</span><span class="sxs-lookup"><span data-stu-id="e86fb-130">Category</span></span>

<span data-ttu-id="e86fb-131">전역화</span><span class="sxs-lookup"><span data-stu-id="e86fb-131">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="e86fb-132">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="e86fb-132">Affected APIs</span></span>

- <xref:System.Globalization.StringInfo?displayProperty=fullName>
- <xref:System.Globalization.TextElementEnumerator?displayProperty=fullName>
- <xref:Microsoft.VisualBasic.Strings.StrReverse%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Globalization.StringInfo`
- `T:System.Globalization.TextElementEnumerator`
- `Overload:Microsoft.VisualBasic.Strings.StrReverse`

-->
