---
ms.openlocfilehash: f1fc70075ef09a4f036c69788342c07ee51d72ce
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702507"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="c02e1-101">WinForms 메서드는 이제 ArgumentException을 throw함</span><span class="sxs-lookup"><span data-stu-id="c02e1-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="c02e1-102">이제 일부 Windows Forms 메서드에서는 이전에는 없었던 잘못된 인수에 대한 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c02e1-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c02e1-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="c02e1-103">Change description</span></span>

<span data-ttu-id="c02e1-104">이전에는 예기치 않거나 잘못된 형식의 인수를 특정 Windows Forms 메서드에 전달하면 불분명한 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c02e1-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="c02e1-105">.NET 5.0부터 이러한 메서드는 잘못된 인수를 전달하면 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="c02e1-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="c02e1-106"><xref:System.ArgumentException> throw는 .NET 런타임의 동작을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c02e1-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="c02e1-107">또한 잘못된 인수를 명확하게 전달하여 디버깅 환경을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="c02e1-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="c02e1-108">다음 표에서는 영향을 받는 메서드 및 매개 변수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c02e1-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="c02e1-109">메서드</span><span class="sxs-lookup"><span data-stu-id="c02e1-109">Method</span></span> | <span data-ttu-id="c02e1-110">매개 변수 이름</span><span class="sxs-lookup"><span data-stu-id="c02e1-110">Parameter name</span></span> | <span data-ttu-id="c02e1-111">조건</span><span class="sxs-lookup"><span data-stu-id="c02e1-111">Condition</span></span> | <span data-ttu-id="c02e1-112">추가된 버전</span><span class="sxs-lookup"><span data-stu-id="c02e1-112">Version added</span></span> |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="c02e1-113">인수가 <xref:System.Windows.Forms.TabPage> 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c02e1-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="c02e1-114">5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="c02e1-114">5.0 Preview 1</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="c02e1-115">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c02e1-115">Version introduced</span></span>

<span data-ttu-id="c02e1-116">.NET 5.0 미리 보기 1</span><span class="sxs-lookup"><span data-stu-id="c02e1-116">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c02e1-117">권장 조치</span><span class="sxs-lookup"><span data-stu-id="c02e1-117">Recommended action</span></span>

- <span data-ttu-id="c02e1-118">잘못된 인수가 전달되지 않도록 코드를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="c02e1-118">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="c02e1-119">필요한 경우 메서드를 호출할 때 <xref:System.ArgumentException>을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c02e1-119">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="c02e1-120">범주</span><span class="sxs-lookup"><span data-stu-id="c02e1-120">Category</span></span>

<span data-ttu-id="c02e1-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c02e1-121">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c02e1-122">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="c02e1-122">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

#### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
