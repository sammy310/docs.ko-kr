---
ms.openlocfilehash: aab7d8538c875e35c832acc2a6c64beb84d4fb47
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702447"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="26bba-101">WinForms 메서드는 이제 ArgumentException을 throw함</span><span class="sxs-lookup"><span data-stu-id="26bba-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="26bba-102">이제 일부 Windows Forms 메서드에서는 이전에는 없었던 잘못된 인수에 대한 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="26bba-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="26bba-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="26bba-103">Change description</span></span>

<span data-ttu-id="26bba-104">이전에는 예기치 않거나 잘못된 형식의 인수를 특정 Windows Forms 메서드에 전달하면 불분명한 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26bba-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="26bba-105">.NET 5.0부터 이러한 메서드는 잘못된 인수를 전달하면 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="26bba-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="26bba-106"><xref:System.ArgumentException> throw는 .NET 런타임의 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="26bba-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="26bba-107">또한 잘못된 인수를 명확하게 전달하여 디버깅 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="26bba-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="26bba-108">다음 표에서는 영향을 받는 메서드 및 매개 변수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="26bba-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="26bba-109">메서드</span><span class="sxs-lookup"><span data-stu-id="26bba-109">Method</span></span> | <span data-ttu-id="26bba-110">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="26bba-110">Parameter name</span></span> | <span data-ttu-id="26bba-111">조건</span><span class="sxs-lookup"><span data-stu-id="26bba-111">Condition</span></span> | <span data-ttu-id="26bba-112">추가된 버전</span><span class="sxs-lookup"><span data-stu-id="26bba-112">Version added</span></span> |
|-|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="26bba-113">인수가 <xref:System.Windows.Forms.TabPage> 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="26bba-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="26bba-114">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="26bba-114">5.0 Preview 1</span></span> |
| <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName> | `format` | <span data-ttu-id="26bba-115">인수는 `null`, <xref:System.String.Empty?displayProperty=nameWithType> 또는 공백입니다.</span><span class="sxs-lookup"><span data-stu-id="26bba-115">Argument is `null`, <xref:System.String.Empty?displayProperty=nameWithType>, or white space.</span></span> | <span data-ttu-id="26bba-116">5.0 미리 보기 5</span><span class="sxs-lookup"><span data-stu-id="26bba-116">5.0 Preview 5</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="26bba-117">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="26bba-117">Version introduced</span></span>

<span data-ttu-id="26bba-118">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="26bba-118">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="26bba-119">권장 조치</span><span class="sxs-lookup"><span data-stu-id="26bba-119">Recommended action</span></span>

- <span data-ttu-id="26bba-120">잘못된 인수가 전달되지 않도록 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="26bba-120">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="26bba-121">필요한 경우 메서드를 호출할 때 <xref:System.ArgumentException>을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="26bba-121">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="26bba-122">범주</span><span class="sxs-lookup"><span data-stu-id="26bba-122">Category</span></span>

<span data-ttu-id="26bba-123">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="26bba-123">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="26bba-124">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="26bba-124">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>
- <xref:System.Windows.Forms.DataFormats.GetFormat(System.String)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`
- `M:System.Windows.Forms.DataFormats.GetFormat(System.String)`

-->
