---
ms.openlocfilehash: 56127309c5f5993ffc2e2faedd1f481e8131e094
ms.sourcegitcommit: 48466b8fb7332ececff5dc388f19f6b3ff503dd4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2020
ms.locfileid: "93400637"
---
### <a name="textformatflagsmodifystring-is-obsolete"></a><span data-ttu-id="295e7-101">TextFormatFlags.ModifyString은 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="295e7-101">TextFormatFlags.ModifyString is obsolete</span></span>

<span data-ttu-id="295e7-102"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> 필드는 경고로 사용되지 않으며 이후 .NET 버전에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295e7-102">The <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> field is obsolete, as a warning, and may be removed in a future .NET version.</span></span>

#### <a name="change-description"></a><span data-ttu-id="295e7-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="295e7-103">Change description</span></span>

<span data-ttu-id="295e7-104">이전 .NET 버전에서 <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> 열거형 필드는 사용되지 않음으로 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="295e7-104">In previous .NET versions, the <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> enumeration field is not marked obsolete.</span></span> <span data-ttu-id="295e7-105">.NET 5.0 이상 버전에서는 경고로 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="295e7-105">In .NET 5.0 and later versions, it is marked obsolete as a warning.</span></span> <span data-ttu-id="295e7-106">이 필드는 이후 .NET 버전에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295e7-106">This field may be removed in a future .NET version.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="295e7-107">변경 이유</span><span class="sxs-lookup"><span data-stu-id="295e7-107">Reason for change</span></span>

<span data-ttu-id="295e7-108"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>을 사용하여 <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType>에 문자열을 전달하면 일부 상황에서 문자열이 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="295e7-108">Passing a string to <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> with <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> alters the string in some situations.</span></span> <span data-ttu-id="295e7-109">이 동작으로 인해 문자열 불변성 프라미스가 위반되고 .NET 런타임 상태가 심각하게 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="295e7-109">This behavior breaks the string immutability promise and may lead to a fatal .NET runtime state corruption.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="295e7-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="295e7-110">Version introduced</span></span>

<span data-ttu-id="295e7-111">.NET 5.0 RC1</span><span class="sxs-lookup"><span data-stu-id="295e7-111">.NET 5.0 RC1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="295e7-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="295e7-112">Recommended action</span></span>

<span data-ttu-id="295e7-113"><xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>에 의존하는 모든 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="295e7-113">Update any code that relies on <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType>.</span></span>

#### <a name="category"></a><span data-ttu-id="295e7-114">범주</span><span class="sxs-lookup"><span data-stu-id="295e7-114">Category</span></span>

<span data-ttu-id="295e7-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="295e7-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="295e7-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="295e7-116">Affected APIs</span></span>

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

#### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

-->
