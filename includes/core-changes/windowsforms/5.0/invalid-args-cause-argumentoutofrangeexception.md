---
ms.openlocfilehash: f42da00487735acdcc60f876c75e1dfd17103008
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2020
ms.locfileid: "84702448"
---
### <a name="winforms-properties-now-throw-argumentoutofrangeexception"></a><span data-ttu-id="9de12-101">WinForms 속성은 이제 ArgumentOutOfRangeException을 throw함</span><span class="sxs-lookup"><span data-stu-id="9de12-101">WinForms properties now throw ArgumentOutOfRangeException</span></span>

<span data-ttu-id="9de12-102">이제 일부 Windows Forms 속성에서는 이전에는 없었던 잘못된 인수에 대한 <xref:System.ArgumentOutOfRangeException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="9de12-102">Some Windows Forms properties now throw an <xref:System.ArgumentOutOfRangeException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="9de12-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="9de12-103">Change description</span></span>

<span data-ttu-id="9de12-104">이전에 범위를 벗어난 인수를 전달하면 이 속성은 <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>,<xref:System.ArgumentException>과 같은 다양한 예외를 throw했습니다.</span><span class="sxs-lookup"><span data-stu-id="9de12-104">Previously, these properties threw various exceptions, such as <xref:System.NullReferenceException>, <xref:System.IndexOutOfRangeException>, or <xref:System.ArgumentException>, when passed out-of-range arguments.</span></span> <span data-ttu-id="9de12-105">.NET 5.0부터 범위를 벗어난 인수를 전달하면 이 속성은 이제 <xref:System.ArgumentOutOfRangeException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="9de12-105">Starting in .NET 5.0, these properties now throw an <xref:System.ArgumentOutOfRangeException> when passed arguments that are out of range.</span></span>

<span data-ttu-id="9de12-106"><xref:System.ArgumentOutOfRangeException> throw는 .NET 런타임의 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="9de12-106">Throwing an <xref:System.ArgumentOutOfRangeException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="9de12-107">또한 잘못된 인수를 명확하게 전달하여 디버깅 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="9de12-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="9de12-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="9de12-108">Version introduced</span></span>

<span data-ttu-id="9de12-109">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="9de12-109">.NET 5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="9de12-110">권장 조치</span><span class="sxs-lookup"><span data-stu-id="9de12-110">Recommended action</span></span>

- <span data-ttu-id="9de12-111">잘못된 인수가 전달되지 않도록 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="9de12-111">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="9de12-112">필요한 경우 속성을 설정할 때 <xref:System.ArgumentOutOfRangeException>을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9de12-112">If necessary, handle an <xref:System.ArgumentOutOfRangeException> when setting the property.</span></span>

#### <a name="category"></a><span data-ttu-id="9de12-113">범주</span><span class="sxs-lookup"><span data-stu-id="9de12-113">Category</span></span>

<span data-ttu-id="9de12-114">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9de12-114">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="9de12-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="9de12-115">Affected APIs</span></span>

<span data-ttu-id="9de12-116">다음 표에서는 영향을 받는 속성 및 매개 변수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="9de12-116">The following table lists the affected properties and parameters:</span></span>

> [!div class="mx-tdBreakAll"]
> | <span data-ttu-id="9de12-117">속성</span><span class="sxs-lookup"><span data-stu-id="9de12-117">Property</span></span> | <span data-ttu-id="9de12-118">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="9de12-118">Parameter name</span></span> | <span data-ttu-id="9de12-119">추가된 버전</span><span class="sxs-lookup"><span data-stu-id="9de12-119">Version added</span></span> |
> |-|-|-|
> | <xref:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)?displayProperty=nameWithType> | `index` | <span data-ttu-id="9de12-120">5.0 미리 보기 5</span><span class="sxs-lookup"><span data-stu-id="9de12-120">5.0 Preview 5</span></span> |
> | <xref:System.Windows.Forms.TreeNode.ImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="9de12-121">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="9de12-121">5.0 Preview 6</span></span> |
> | <xref:System.Windows.Forms.TreeNode.SelectedImageIndex?displayProperty=nameWithType> | `value` | <span data-ttu-id="9de12-122">5.0 미리 보기 6</span><span class="sxs-lookup"><span data-stu-id="9de12-122">5.0 Preview 6</span></span> |

<!-- 

#### Affected APIs

- `P:System.Windows.Forms.ListBox.IntegerCollection.Item(System.Int32)`
- `P:System.Windows.Forms.TreeNode.ImageIndex`
- `P:System.Windows.Forms.TreeNode.SelectedImageIndex`

-->
