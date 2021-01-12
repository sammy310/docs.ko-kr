---
title: '호환성이 손상되는 변경: TextInfo.ListSeparator 값 변경'
description: 버전 5.0과 5.0.1 간에 TextInfo.ListSeparator의 기본값이 변경된 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 12/10/2020
ms.openlocfilehash: 720d46c1908bcd70812f575a90f580470dbc7f32
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596392"
---
# <a name="textinfolistseparator-values-changed"></a><span data-ttu-id="7cbe0-103">TextInfo.ListSeparator 값이 변경됨</span><span class="sxs-lookup"><span data-stu-id="7cbe0-103">TextInfo.ListSeparator values changed</span></span>

<span data-ttu-id="7cbe0-104">모든 운영 체제에서 여러 문화권의 기본 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-104">The default <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for different cultures have changed on all operating systems.</span></span>

## <a name="change-description"></a><span data-ttu-id="7cbe0-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="7cbe0-105">Change description</span></span>

<span data-ttu-id="7cbe0-106">.NET 5.0.0에서 [NLS에서 ICU 라이브러리로 전환](icu-globalization-api.md)의 일환으로 Windows에서 여러 문화권의 기본 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값이 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-106">In .NET 5.0.0, as part of the [switch from NLS to ICU libraries](icu-globalization-api.md), the default <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for different cultures changed on Windows.</span></span> <span data-ttu-id="7cbe0-107">ICU(International Components for Unicode)에서 가져온 소수 구분 기호 값이 <xref:System.Globalization.TextInfo.ListSeparator> 값으로 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-107">Decimal separator values, obtained from International Components for Unicode (ICU), were used as the <xref:System.Globalization.TextInfo.ListSeparator> values.</span></span> <span data-ttu-id="7cbe0-108">Linux 및 macOS에서는 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값이 변경되지 않았습니다. 즉, 소수 구분 기호 값을 계속 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-108">On Linux and macOS, there was no change in <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values; that is, they continued to use decimal separator values.</span></span>

<span data-ttu-id="7cbe0-109">.NET 5.0.1 이후 버전에서는 모든 운영 체제에서 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>의 값은 NLS에서 얻을 수 있는 값과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-109">For all operating systems in .NET 5.0.1 and later versions, the values for <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> are equivalent to the values that would be obtained from NLS.</span></span> <span data-ttu-id="7cbe0-110">Windows의 경우 이 값은 .NET Framework 및 .NET Core 1.0~3.1에서 사용된 값과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-110">For Windows, this means the values are equivalent to what they were in .NET Framework and .NET Core 1.0 - 3.1.</span></span> <span data-ttu-id="7cbe0-111">Linux 및 macOS의 경우 이제 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값이 Windows의 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-111">For Linux and macOS, the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values now match the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values for Windows.</span></span>

<span data-ttu-id="7cbe0-112">다음 표에 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값의 변경 내용이 요약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-112">The following table summarizes the changes for <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values.</span></span>

| | <span data-ttu-id="7cbe0-113">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="7cbe0-113">.NET Framework</span></span><br/><span data-ttu-id="7cbe0-114">.NET Core 1.0 - 3.1</span><span class="sxs-lookup"><span data-stu-id="7cbe0-114">.NET Core 1.0 - 3.1</span></span> | <span data-ttu-id="7cbe0-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="7cbe0-115">.NET 5.0</span></span> | <span data-ttu-id="7cbe0-116">.NET 5.0.1</span><span class="sxs-lookup"><span data-stu-id="7cbe0-116">.NET 5.0.1</span></span> |
-|-|-|-
| <span data-ttu-id="7cbe0-117">**Windows**</span><span class="sxs-lookup"><span data-stu-id="7cbe0-117">**Windows**</span></span> | <span data-ttu-id="7cbe0-118">NLS에서 가져옴</span><span class="sxs-lookup"><span data-stu-id="7cbe0-118">Obtain from NLS</span></span> | <span data-ttu-id="7cbe0-119">ICU의 소수 구분 기호.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-119">Decimal separator from ICU.</span></span><br/><span data-ttu-id="7cbe0-120">다시 NLS로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-120">Can switch back to NLS.</span></span> | <span data-ttu-id="7cbe0-121">NLS와 같음</span><span class="sxs-lookup"><span data-stu-id="7cbe0-121">Equivalent to NLS</span></span> |
| <span data-ttu-id="7cbe0-122">**Linux 및 macOS**</span><span class="sxs-lookup"><span data-stu-id="7cbe0-122">**Linux and macOS**</span></span> | <span data-ttu-id="7cbe0-123">ICU의 소수 구분 기호</span><span class="sxs-lookup"><span data-stu-id="7cbe0-123">Decimal separator from ICU</span></span> | <span data-ttu-id="7cbe0-124">ICU의 소수 구분 기호</span><span class="sxs-lookup"><span data-stu-id="7cbe0-124">Decimal separator from ICU</span></span> | <span data-ttu-id="7cbe0-125">NLS와 같음</span><span class="sxs-lookup"><span data-stu-id="7cbe0-125">Equivalent to NLS</span></span> |

## <a name="version-introduced"></a><span data-ttu-id="7cbe0-126">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="7cbe0-126">Version introduced</span></span>

<span data-ttu-id="7cbe0-127">5.0.1</span><span class="sxs-lookup"><span data-stu-id="7cbe0-127">5.0.1</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="7cbe0-128">변경 이유</span><span class="sxs-lookup"><span data-stu-id="7cbe0-128">Reason for change</span></span>

<span data-ttu-id="7cbe0-129">개발자가 CSV(쉼표로 구분된 값) 파일을 구문 분석할 때 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 속성을 사용하는 경우 새 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값에서 구문 분석이 중단된다고 보고했습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-129">Developers reported that they use the <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> property when parsing comma-separated value (CSV) files, and the new <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values broke that parsing.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="7cbe0-130">권장 조치</span><span class="sxs-lookup"><span data-stu-id="7cbe0-130">Recommended action</span></span>

<span data-ttu-id="7cbe0-131">코드에서 이전 소수 구분 기호 값을 사용하는 경우 원하는 <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> 값을 하드 코딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cbe0-131">If your code relies on the previous decimal separator values, you can hardcode the desired <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> values.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="7cbe0-132">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="7cbe0-132">Affected APIs</span></span>

- <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=fullName>

<!--

#### Category

- Globalization

### Affected APIs

- `P:System.Globalization.TextInfo.ListSeparator`

-->
