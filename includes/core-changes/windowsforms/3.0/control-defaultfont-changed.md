---
ms.openlocfilehash: b0c4e9617677cf95e3a059b57f3d50ddfb072f4a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937114"
---
### <a name="default-control-font-changed-to-segoe-ui-9-pt"></a><span data-ttu-id="f5ddb-101">기본 컨트롤 글꼴이 맑은 고딕 9pt로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-101">Default control font changed to Segoe UI 9 pt</span></span>

#### <a name="change-description"></a><span data-ttu-id="f5ddb-102">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="f5ddb-102">Change description</span></span>

<span data-ttu-id="f5ddb-103">.NET Framework에서는 <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> 속성이 `Microsoft Sans Serif 8 pt`로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-103">In .NET Framework, the <xref:System.Windows.Forms.Control.DefaultFont?displayProperty=nameWithType> property was set to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="f5ddb-104">다음 이미지에서는 기본 글꼴을 사용하는 창을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-104">The following image shows a window that uses the default font.</span></span>

![.NET Framework의 기본 컨트롤 글꼴](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-framework.png)

<span data-ttu-id="f5ddb-106">.NET Core 3.0부터 기본 글꼴은 `Segoe UI 9 pt`(<xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>과 동일한 글꼴)으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-106">Starting in .NET Core 3.0, the default font is set to `Segoe UI 9 pt` (the same font as <xref:System.Drawing.SystemFonts.MessageBoxFont?displayProperty=nameWithType>).</span></span> <span data-ttu-id="f5ddb-107">이 변경으로 인해 양식 및 컨트롤의 크기가 새 기본 글꼴의 더 큰 크기를 고려하여 약 27% 커졌습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-107">As a result of this change, forms and controls are sized about 27% larger to account for the larger size of the new default font.</span></span> <span data-ttu-id="f5ddb-108">예들 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-108">For example:</span></span>

![.NET Core의 기본 컨트롤 글꼴](~/docs/images/core-changes/windowsforms/control-defaultfont-changed/defaultfont-core.png)

<span data-ttu-id="f5ddb-110">이 변경은 [Windows 사용자 환경(UX) 지침](/windows/win32/uxguide/vis-fonts#fonts-and-colors)에 맞게 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-110">This change was made to align with [Windows user experience (UX) guidelines](/windows/win32/uxguide/vis-fonts#fonts-and-colors).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="f5ddb-111">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="f5ddb-111">Version introduced</span></span>

<span data-ttu-id="f5ddb-112">3.0</span><span class="sxs-lookup"><span data-stu-id="f5ddb-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="f5ddb-113">권장 조치</span><span class="sxs-lookup"><span data-stu-id="f5ddb-113">Recommended action</span></span>

<span data-ttu-id="f5ddb-114">양식 및 컨트롤의 크기가 변경되므로 애플리케이션이 올바르게 렌더링되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-114">Because of the change in the size of forms and controls, ensure that your application renders correctly.</span></span>

<span data-ttu-id="f5ddb-115">원래 글꼴을 유지하려면 양식의 기본 글꼴을 `Microsoft Sans Serif 8 pt`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-115">To retain the original font, set your form's default font to `Microsoft Sans Serif 8 pt`.</span></span> <span data-ttu-id="f5ddb-116">예들 들어 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f5ddb-116">For example:</span></span>

```csharp
public MyForm()
{
    InitializeComponent();
    Font = new Font(new FontFamily("Microsoft Sans Serif"), 8f);
}
```

#### <a name="category"></a><span data-ttu-id="f5ddb-117">범주</span><span class="sxs-lookup"><span data-stu-id="f5ddb-117">Category</span></span>

- <span data-ttu-id="f5ddb-118">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5ddb-118">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="f5ddb-119">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="f5ddb-119">Affected APIs</span></span>

<span data-ttu-id="f5ddb-120">없음</span><span class="sxs-lookup"><span data-stu-id="f5ddb-120">None.</span></span>

<!--

### Affected APIs

- Not detectable via API analysis

-->
