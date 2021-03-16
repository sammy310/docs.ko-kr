---
title: '호환성이 손상되는 변경: TextFormatFlags.ModifyString은 사용되지 않음'
description: TextFormatFlags.ModifyString 필드가 경고로 사용되지 않는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 11/05/2020
ms.openlocfilehash: 9fe1e04b1ad36070b08af2affdca1e058ec74bb8
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256168"
---
# <a name="textformatflagsmodifystring-is-obsolete"></a><span data-ttu-id="316cd-103">TextFormatFlags.ModifyString은 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="316cd-103">TextFormatFlags.ModifyString is obsolete</span></span>

<span data-ttu-id="316cd-104"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> 필드는 경고로 사용되지 않으며 이후 .NET 버전에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="316cd-104">The <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> field is obsolete, as a warning, and may be removed in a future .NET version.</span></span>

## <a name="change-description"></a><span data-ttu-id="316cd-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="316cd-105">Change description</span></span>

<span data-ttu-id="316cd-106">이전 .NET 버전에서 <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> 열거형 필드는 사용되지 않음으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="316cd-106">In previous .NET versions, the <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> enumeration field is not marked obsolete.</span></span> <span data-ttu-id="316cd-107">.NET 5 이상 버전에서는 경고로 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="316cd-107">In .NET 5 and later versions, it is marked obsolete as a warning.</span></span> <span data-ttu-id="316cd-108">이 필드는 이후 .NET 버전에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="316cd-108">This field may be removed in a future .NET version.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="316cd-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="316cd-109">Reason for change</span></span>

<span data-ttu-id="316cd-110"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>을 사용하여 <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType>에 문자열을 전달하면 일부 상황에서 문자열이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="316cd-110">Passing a string to <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> with <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> alters the string in some situations.</span></span> <span data-ttu-id="316cd-111">이 동작으로 인해 문자열 불변성 프라미스가 위반되고 .NET 런타임 상태가 심각하게 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="316cd-111">This behavior breaks the string immutability promise and may lead to a fatal .NET runtime state corruption.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="316cd-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="316cd-112">Version introduced</span></span>

<span data-ttu-id="316cd-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="316cd-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="316cd-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="316cd-114">Recommended action</span></span>

<span data-ttu-id="316cd-115"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>에 의존하는 모든 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="316cd-115">Update any code that relies on <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="316cd-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="316cd-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

### Category

Windows Forms

-->
