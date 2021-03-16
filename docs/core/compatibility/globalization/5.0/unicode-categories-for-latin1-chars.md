---
title: '호환성이 손상되는 변경: 일부 라틴어-1 문자의 유니코드 범주가 변경됨'
description: Char 메서드가 라틴어-1 범위의 문자에 대해 올바른 유니코드 범주를 반환하는 .NET 5의 세계화 관련 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 04/07/2020
ms.openlocfilehash: 03355c488d2bdae78f989e647c9b5b7913d73649
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256675"
---
# <a name="unicode-category-changed-for-some-latin-1-characters"></a><span data-ttu-id="481bd-103">일부 라틴어-1 문자의 유니코드 범주가 변경됨</span><span class="sxs-lookup"><span data-stu-id="481bd-103">Unicode category changed for some Latin-1 characters</span></span>

<span data-ttu-id="481bd-104"><xref:System.Char> 메서드는 이제 라틴어-1 범위의 문자에 대해 올바른 유니코드 범주를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="481bd-104"><xref:System.Char> methods now return the correct Unicode category for characters in the Latin-1 range.</span></span> <span data-ttu-id="481bd-105">범주는 유니코드 표준의 범주와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="481bd-105">The category matches that of the Unicode standard.</span></span>

## <a name="change-description"></a><span data-ttu-id="481bd-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="481bd-106">Change description</span></span>

<span data-ttu-id="481bd-107">이전 .NET 버전에서 <xref:System.Char> 메서드는 라틴어-1 범위의 문자에 대해 유니코드 범주의 고정 목록을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="481bd-107">In previous .NET versions, <xref:System.Char> methods used a fixed list of Unicode categories for characters in the Latin-1 range.</span></span> <span data-ttu-id="481bd-108">그러나 유니코드 표준은 해당 API가 구현된 이후 이러한 문자 중 일부의 범주를 변경했으며 이에 따른 불일치가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="481bd-108">However, the Unicode standard has changed the categories of some of these characters since those APIs were implemented, creating a discrepancy.</span></span> <span data-ttu-id="481bd-109">또한 <xref:System.Char> API와 <xref:System.Globalization.CharUnicodeInfo> API 간에 불일치가 있었으며, 이는 유니코드 표준을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="481bd-109">In addition, there was also a discrepancy between <xref:System.Char> and <xref:System.Globalization.CharUnicodeInfo> APIs, which follow the Unicode standard.</span></span> <span data-ttu-id="481bd-110">.NET 5 이상 버전에서 <xref:System.Char> 메서드는 모든 문자에 대한 유니코드 표준과 일치하는 유니코드 범주를 사용하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="481bd-110">In .NET 5 and later versions, <xref:System.Char> methods use and return the Unicode category that matches the Unicode standard for all characters.</span></span>

<span data-ttu-id="481bd-111">다음 표에서는 .NET 5.0에서 유니코드 범주가 변경된 문자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="481bd-111">The following table shows the characters whose Unicode categories have changed in .NET 5.0:</span></span>

| <span data-ttu-id="481bd-112">문자</span><span class="sxs-lookup"><span data-stu-id="481bd-112">Character</span></span>    | <span data-ttu-id="481bd-113">유니코드 범주</span><span class="sxs-lookup"><span data-stu-id="481bd-113">Unicode category</span></span><br><span data-ttu-id="481bd-114">이전 .NET 버전</span><span class="sxs-lookup"><span data-stu-id="481bd-114">in previous .NET versions</span></span> | <span data-ttu-id="481bd-115">유니코드 범주</span><span class="sxs-lookup"><span data-stu-id="481bd-115">Unicode category</span></span><br><span data-ttu-id="481bd-116">.NET 5 이상 버전</span><span class="sxs-lookup"><span data-stu-id="481bd-116">in .NET 5 and later versions</span></span> |
|:------------:|:---------------------------------------------:|:--------------------------------------------------:|
| <span data-ttu-id="481bd-117">§(\u00a7)</span><span class="sxs-lookup"><span data-stu-id="481bd-117">§ (\u00a7)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="481bd-118">ª(\u00aa)</span><span class="sxs-lookup"><span data-stu-id="481bd-118">ª (\u00aa)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |
| <span data-ttu-id="481bd-119">SHY(\u00ad)</span><span class="sxs-lookup"><span data-stu-id="481bd-119">SHY (\u00ad)</span></span> | `DashPunctuation`                             | `Format`                                           |
| <span data-ttu-id="481bd-120">¶(\u00b6)</span><span class="sxs-lookup"><span data-stu-id="481bd-120">¶ (\u00b6)</span></span>   | `OtherSymbol`                                 | `OtherPunctuation`                                 |
| <span data-ttu-id="481bd-121">º(\u00ba)</span><span class="sxs-lookup"><span data-stu-id="481bd-121">º (\u00ba)</span></span>   | `LowercaseLetter`                             | `OtherLetter`                                      |

## <a name="version-introduced"></a><span data-ttu-id="481bd-122">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="481bd-122">Version introduced</span></span>

<span data-ttu-id="481bd-123">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="481bd-123">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="481bd-124">권장 조치</span><span class="sxs-lookup"><span data-stu-id="481bd-124">Recommended action</span></span>

<span data-ttu-id="481bd-125"><xref:System.Char> 클래스를 사용하여 유니코드 문자 범주를 가져오는 코드가 있으며 범주가 변경되지 않는다고 가정하는 경우 범주를 업데이트해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="481bd-125">If you have any code that gets the Unicode character category by using the <xref:System.Char> class and assumes the category will never change, you may need to update it.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="481bd-126">변경 이유</span><span class="sxs-lookup"><span data-stu-id="481bd-126">Reason for change</span></span>

<span data-ttu-id="481bd-127"><xref:System.Char> 형식에서 반환된 범주가 유니코드 표준과 <xref:System.Globalization.CharUnicodeInfo> 형식 둘 다와 일치하도록 이렇게 변경했습니다.</span><span class="sxs-lookup"><span data-stu-id="481bd-127">This change was made so that the categories returned by the <xref:System.Char> type are consistent with both the Unicode standard and the <xref:System.Globalization.CharUnicodeInfo> type.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="481bd-128">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="481bd-128">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory%2A?displayProperty=fullName>
- <xref:System.Char.IsLetter%2A?displayProperty=fullName>
- <xref:System.Char.IsPunctuation%2A?displayProperty=fullName>
- <xref:System.Char.IsSymbol%2A?displayProperty=fullName>
- <xref:System.Char.IsLower%2A?displayProperty=fullName>

<span data-ttu-id="481bd-129">또한 유니코드 문자 범주를 얻기 위해 <xref:System.Char>에 의존하는 클래스(예: <xref:System.Text.RegularExpressions.Regex>)는 이 변경의 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="481bd-129">Additionally, any class that depends on <xref:System.Char> to obtain the Unicode character category, for example, <xref:System.Text.RegularExpressions.Regex>, is affected by this change.</span></span>

<!--

### Affected APIs

- `Overload:System.Char.GetUnicodeCategory`
- `Overload:System.Char.IsLetter`
- `Overload:System.Char.IsPunctuation`
- `Overload:System.Char.IsSymbol`
- `Overload:System.Char.IsLower`

### Category

- Core .NET libraries
- Globalization
-
-->
