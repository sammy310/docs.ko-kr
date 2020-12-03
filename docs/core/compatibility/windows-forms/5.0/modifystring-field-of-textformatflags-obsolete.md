---
title: '호환성이 손상되는 변경: TextFormatFlags.ModifyString은 사용되지 않음'
description: TextFormatFlags.ModifyString 필드가 경고로 사용되지 않는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 11/05/2020
ms.openlocfilehash: 83dca65a770ccdcd5ce48bb669f5122dc2d5ad77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759680"
---
# <a name="textformatflagsmodifystring-is-obsolete"></a><span data-ttu-id="99db7-103">TextFormatFlags.ModifyString은 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="99db7-103">TextFormatFlags.ModifyString is obsolete</span></span>

<span data-ttu-id="99db7-104"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> 필드는 경고로 사용되지 않으며 이후 .NET 버전에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99db7-104">The <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> field is obsolete, as a warning, and may be removed in a future .NET version.</span></span>

## <a name="change-description"></a><span data-ttu-id="99db7-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="99db7-105">Change description</span></span>

<span data-ttu-id="99db7-106">이전 .NET 버전에서 <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> 열거형 필드는 사용되지 않음으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99db7-106">In previous .NET versions, the <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> enumeration field is not marked obsolete.</span></span> <span data-ttu-id="99db7-107">.NET 5.0 이상 버전에서는 경고로 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="99db7-107">In .NET 5.0 and later versions, it is marked obsolete as a warning.</span></span> <span data-ttu-id="99db7-108">이 필드는 이후 .NET 버전에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99db7-108">This field may be removed in a future .NET version.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="99db7-109">변경 이유</span><span class="sxs-lookup"><span data-stu-id="99db7-109">Reason for change</span></span>

<span data-ttu-id="99db7-110"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>을 사용하여 <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType>에 문자열을 전달하면 일부 상황에서 문자열이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="99db7-110">Passing a string to <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> with <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> alters the string in some situations.</span></span> <span data-ttu-id="99db7-111">이 동작으로 인해 문자열 불변성 프라미스가 위반되고 .NET 런타임 상태가 심각하게 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99db7-111">This behavior breaks the string immutability promise and may lead to a fatal .NET runtime state corruption.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="99db7-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="99db7-112">Version introduced</span></span>

<span data-ttu-id="99db7-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="99db7-113">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="99db7-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="99db7-114">Recommended action</span></span>

<span data-ttu-id="99db7-115"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>에 의존하는 모든 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="99db7-115">Update any code that relies on <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="99db7-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="99db7-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

### Category

Windows Forms

-->
