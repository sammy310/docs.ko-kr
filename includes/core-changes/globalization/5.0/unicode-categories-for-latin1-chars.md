---
ms.openlocfilehash: 48d2f1b5fa2eced30d3c9fb65804268904f11ab8
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065068"
---
### <a name="unicode-category-changed-for-some-latin-1-characters"></a><span data-ttu-id="0e1b0-101">일부 라틴어-1 문자의 유니코드 범주가 변경됨</span><span class="sxs-lookup"><span data-stu-id="0e1b0-101">Unicode category changed for some Latin-1 characters</span></span>

<span data-ttu-id="0e1b0-102"><xref:System.Char> 메서드는 이제 라틴어-1 범위의 문자에 대해 올바른 유니코드 범주를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1b0-102"><xref:System.Char> methods now return the correct Unicode category for characters in the Latin-1 range.</span></span> <span data-ttu-id="0e1b0-103">범주는 유니코드 표준의 범주와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1b0-103">The category matches that of the Unicode standard.</span></span>

#### <a name="change-description"></a><span data-ttu-id="0e1b0-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="0e1b0-104">Change description</span></span>

<span data-ttu-id="0e1b0-105">이전 .NET 버전에서 <xref:System.Char> 메서드는 라틴어-1 범위의 문자에 대해 유니코드 범주의 고정 목록을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1b0-105">In previous .NET versions, <xref:System.Char> methods used a fixed list of Unicode categories for characters in the Latin-1 range.</span></span> <span data-ttu-id="0e1b0-106">그러나 유니코드 표준은 해당 API가 구현된 이후 이러한 문자 중 일부의 범주를 변경했으며 이에 따른 불일치가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1b0-106">However, the Unicode standard has changed the categories of some of these characters since those APIs were implemented, creating a discrepancy.</span></span> <span data-ttu-id="0e1b0-107">또한 <xref:System.Char> API와 <xref:System.Globalization.CharUnicodeInfo> API 간에 불일치가 있었으며, 이는 유니코드 표준을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="0e1b0-107">In addition, there was also a discrepancy between <xref:System.Char> and <xref:System.Globalization.CharUnicodeInfo> APIs, which follow the Unicode standard.</span></span> <span data-ttu-id="0e1b0-108">.NET 5.0 이상 버전에서 <xref:System.Char> 메서드는 모든 문자에 대한 유니코드 표준과 일치하는 유니코드 범주를 사용하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0e1b0-108">In .NET 5.0 and later versions, <xref:System.Char> methods use and return the Unicode category that matches the Unicode standard for all characters.</span></span>

<span data-ttu-id="0e1b0-109">다음 표에서는 .NET 5.0에서 유니코드 범주가 변경된 문자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0e1b0-109">The following table shows the characters whose Unicode categories have changed in .NET 5.0:</span></span>

| <span data-ttu-id="0e1b0-110">문자</span><span class="sxs-lookup"><span data-stu-id="0e1b0-110">Character</span></span>    | <span data-ttu-id="0e1b0-111">유니코드 범주</span><span class="sxs-lookup"><span data-stu-id="0e1b0-111">Unicode category</span></span><br><span data-ttu-id="0e1b0-112">이전 .NET 버전</span><span class="sxs-lookup"><span data-stu-id="0e1b0-112">in previous .NET versions</span></span> | <span data-ttu-id="0e1b0-113">유니코드 범주</span><span class="sxs-lookup"><span data-stu-id="0e1b0-113">Unicode category</span></span><br><span data-ttu-id="0e1b0-114">.NET 5.0 이상 버전</span><span class="sxs-lookup"><span data-stu-id="0e1b0-114">in .NET 5.0 and later versions</span></span> |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| <span data-ttu-id="0e1b0-115">§(\u00a7)</span><span class="sxs-lookup"><span data-stu-id="0e1b0-115">§ (\u00a7)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="0e1b0-116">ª(\u00aa)</span><span class="sxs-lookup"><span data-stu-id="0e1b0-116">ª (\u00aa)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |
| <span data-ttu-id="0e1b0-117">SHY(\u00ad)</span><span class="sxs-lookup"><span data-stu-id="0e1b0-117">SHY (\u00ad)</span></span> | `DashPunctuation`                             | `Format`                                           |
| <span data-ttu-id="0e1b0-118">¶(\u00b6)</span><span class="sxs-lookup"><span data-stu-id="0e1b0-118">¶ (\u00b6)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="0e1b0-119">º(\u00ba)</span><span class="sxs-lookup"><span data-stu-id="0e1b0-119">º (\u00ba)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |

#### <a name="version-introduced"></a><span data-ttu-id="0e1b0-120">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0e1b0-120">Version introduced</span></span>

<span data-ttu-id="0e1b0-121">.NET 5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="0e1b0-121">.NET 5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0e1b0-122">권장 조치</span><span class="sxs-lookup"><span data-stu-id="0e1b0-122">Recommended action</span></span>

<span data-ttu-id="0e1b0-123"><xref:System.Char> 클래스를 사용하여 유니코드 문자 범주를 가져오는 코드가 있으며 범주가 변경되지 않는다고 가정하는 경우 범주를 업데이트해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1b0-123">If you have any code that gets the Unicode character category by using the <xref:System.Char> class and assumes the category will never change, you may need to update it.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="0e1b0-124">변경 이유</span><span class="sxs-lookup"><span data-stu-id="0e1b0-124">Reason for change</span></span>

<span data-ttu-id="0e1b0-125"><xref:System.Char> 형식에서 반환된 범주가 유니코드 표준과 <xref:System.Globalization.CharUnicodeInfo> 형식 둘 다와 일치하도록 이렇게 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1b0-125">This change was made so that the categories returned by the <xref:System.Char> type are consistent with both the Unicode standard and the <xref:System.Globalization.CharUnicodeInfo> type.</span></span>

#### <a name="category"></a><span data-ttu-id="0e1b0-126">범주</span><span class="sxs-lookup"><span data-stu-id="0e1b0-126">Category</span></span>

- <span data-ttu-id="0e1b0-127">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="0e1b0-127">Core .NET libraries</span></span>
- <span data-ttu-id="0e1b0-128">전역화</span><span class="sxs-lookup"><span data-stu-id="0e1b0-128">Globalization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0e1b0-129">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0e1b0-129">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

<span data-ttu-id="0e1b0-130">또한 유니코드 문자 범주를 얻기 위해 <xref:System.Char>에 의존하는 클래스(예: <xref:System.Text.RegularExpressions.Regex>)는 이 변경의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0e1b0-130">Additionally, any class that depends on <xref:System.Char> to obtain the Unicode character category, for example, <xref:System.Text.RegularExpressions.Regex>, is affected by this change.</span></span>

<!--

#### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

-->
