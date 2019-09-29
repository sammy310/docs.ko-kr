---
ms.openlocfilehash: 843007ac6467584fbe6350b6ea19ef67609d73e2
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216914"
---
### <a name="controldefaultfont-changed-to-segoe-ui-9pt"></a><span data-ttu-id="46666-101">`Control.DefaultFont`를 `Segoe UI 9pt`로 변경</span><span class="sxs-lookup"><span data-stu-id="46666-101">`Control.DefaultFont` changed to `Segoe UI 9pt`</span></span>

#### <a name="change-description"></a><span data-ttu-id="46666-102">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="46666-102">Change description</span></span>

<span data-ttu-id="46666-103">.NET Framework에서는 <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> 속성이 `Microsoft Sans Serif 8pt`로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="46666-103">In the .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="46666-104">다음 그림에서는 기본 글꼴을 사용하는 창을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="46666-104">The following figure shows a window that uses the default font.</span></span>

![.NET Framework의 기본 컨트롤 글꼴](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="46666-106">.NET Core에서는 .Net core 3.0부터 이 글꼴이 `Segoe UI 9pt`로 설정됩니다(<xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>와 동일한 글꼴).</span><span class="sxs-lookup"><span data-stu-id="46666-106">In .NET Core starting with .NET Core 3.0, it is set to `Segoe UI 9pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="46666-107">이 변경으로 인해 양식 및 컨트롤의 크기가 새 기본 글꼴의 더 큰 크기를 고려하여 약 27% 커집니다.</span><span class="sxs-lookup"><span data-stu-id="46666-107">As a result of this change, forms and controls will be sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="46666-108">예:</span><span class="sxs-lookup"><span data-stu-id="46666-108">For example:</span></span>

![.NET Core의 기본 컨트롤 글꼴](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="46666-110">이 변경은 [Windows UX 지침](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors)에 따라 실시된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="46666-110">This change was made to align with [Windows UX guidelines](https://docs.microsoft.com/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="46666-111">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="46666-111">Version introduced</span></span>

<span data-ttu-id="46666-112">3.0</span><span class="sxs-lookup"><span data-stu-id="46666-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="46666-113">권장 작업</span><span class="sxs-lookup"><span data-stu-id="46666-113">Recommended action</span></span>

<span data-ttu-id="46666-114">양식 및 컨트롤의 크기가 변경되므로 애플리케이션이 올바르게 렌더링되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="46666-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="46666-115">원래 글꼴을 유지하려면 양식의 기본 글꼴을 `Microsoft Sans Serif 8pt`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="46666-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8pt`.</span></span> <span data-ttu-id="46666-116">예:</span><span class="sxs-lookup"><span data-stu-id="46666-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="46666-117">범주</span><span class="sxs-lookup"><span data-stu-id="46666-117">Category</span></span>

- <span data-ttu-id="46666-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46666-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="46666-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="46666-119">Affected APIs</span></span>

<span data-ttu-id="46666-120">없음</span><span class="sxs-lookup"><span data-stu-id="46666-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
