---
title: 진행률을 표시 하는 컨트롤 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], progress tracking
- controls [Windows Forms], creating
- progress [Windows Forms], reporting [Windows Forms]
- FlashTrackBar custom control
ms.assetid: 24c5a2e3-058c-4b8d-a217-c06e6a130c2f
ms.openlocfilehash: 9d2cf353ba2309380221bb51733baaca1b81a5d5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731182"
---
# <a name="how-to-create-a-windows-forms-control-that-shows-progress"></a><span data-ttu-id="94784-102">방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="94784-102">How to: Create a Windows Forms Control That Shows Progress</span></span>
<span data-ttu-id="94784-103">다음 코드 예제에서는 사용자에게 수준 또는 애플리케이션의 진행률을 표시하는 데 사용할 수 있는 `FlashTrackBar`이라는 사용자 지정 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94784-103">The following code example shows a custom control called `FlashTrackBar` that can be used to show the user the level or the progress of an application.</span></span> <span data-ttu-id="94784-104">그라데이션을 사용하여 진행률을 시각적으로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94784-104">It uses a gradient to visually represent progress.</span></span>  
  
 <span data-ttu-id="94784-105">`FlashTrackBar` 컨트롤에서는 다음과 같은 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94784-105">The `FlashTrackBar` control illustrates the following concepts:</span></span>  
  
- <span data-ttu-id="94784-106">사용자 지정 속성 정의</span><span class="sxs-lookup"><span data-stu-id="94784-106">Defining custom properties.</span></span>  
  
- <span data-ttu-id="94784-107">사용자 지정 이벤트 정의</span><span class="sxs-lookup"><span data-stu-id="94784-107">Defining custom events.</span></span> <span data-ttu-id="94784-108">`FlashTrackBar`은 `ValueChanged` 이벤트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-108">(`FlashTrackBar` defines the `ValueChanged` event.)</span></span>  
  
- <span data-ttu-id="94784-109"><xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의 하 여 컨트롤을 그리는 논리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-109">Overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method to provide logic to draw the control.</span></span>  
  
- <span data-ttu-id="94784-110"><xref:System.Windows.Forms.Control.ClientRectangle%2A> 속성을 사용 하 여 컨트롤을 그리는 데 사용할 수 있는 영역을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-110">Computing the area available for drawing the control by using its <xref:System.Windows.Forms.Control.ClientRectangle%2A> property.</span></span> <span data-ttu-id="94784-111">`FlashTrackBar`은 해당 `OptimizedInvalidate` 메서드에서 이를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-111">`FlashTrackBar` does this in its `OptimizedInvalidate` method.</span></span>  
  
- <span data-ttu-id="94784-112">Windows Forms 디자이너에서 변경되는 경우 속성의 serialization 또는 지속성을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-112">Implementing serialization or persistence for a property when it is changed in the Windows Forms Designer.</span></span> <span data-ttu-id="94784-113">`FlashTrackBar`은 `StartColor` 및 `EndColor` 속성을 직렬화하는 `ShouldSerializeStartColor` 및 `ShouldSerializeEndColor` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-113">`FlashTrackBar` defines the `ShouldSerializeStartColor` and `ShouldSerializeEndColor` methods for serializing its `StartColor` and `EndColor` properties.</span></span>  
  
 <span data-ttu-id="94784-114">다음 테이블에서는 `FlashTrackBar`에서 정의된 사용자 지정 속성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94784-114">The following table shows the custom properties defined by `FlashTrackBar`.</span></span>  
  
|<span data-ttu-id="94784-115">속성</span><span class="sxs-lookup"><span data-stu-id="94784-115">Property</span></span>|<span data-ttu-id="94784-116">설명</span><span class="sxs-lookup"><span data-stu-id="94784-116">Description</span></span>|  
|--------------|-----------------|  
|`AllowUserEdit`|<span data-ttu-id="94784-117">사용자가 플래시 트랙 표시줄의 값을 클릭하고 끌어와서 변경할 수 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94784-117">Indicates whether the user can change the value of the flash track bar by clicking and dragging it.</span></span>|  
|`EndColor`|<span data-ttu-id="94784-118">트랙 표시줄의 끝 색을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-118">Specifies the ending color of the track bar.</span></span>|  
|`DarkenBy`|<span data-ttu-id="94784-119">전경 그라데이션과 관련하여 배경 밝기의 정도를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-119">Specifies how much to darken the background with respect to the foreground gradient.</span></span>|  
|`Max`|<span data-ttu-id="94784-120">트랙 표시줄의 최대값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-120">Specifies the maximum value of the track bar.</span></span>|  
|`Min`|<span data-ttu-id="94784-121">트랙 표시줄의 최소값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-121">Specifies the minimum value of the track bar.</span></span>|  
|`StartColor`|<span data-ttu-id="94784-122">그라데이션의 시작 색을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-122">Specifies the starting color of the gradient.</span></span>|  
|`ShowPercentage`|<span data-ttu-id="94784-123">그라데이션의 백분율을 표시할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94784-123">Indicates whether to display a percentage over the gradient.</span></span>|  
|`ShowValue`|<span data-ttu-id="94784-124">그라데이션의 현재 값을 표시할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94784-124">Indicates whether to display the current value over the gradient.</span></span>|  
|`ShowGradient`|<span data-ttu-id="94784-125">트랙 표시줄에서 현재 값을 나타내는 색 그라데이션을 표시해야 할지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94784-125">Indicates whether the track bar should display a color gradient showing the current value.</span></span>|  
|-   `Value`|<span data-ttu-id="94784-126">트랙 표시줄의 현재 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-126">Specifies the current value of the track bar.</span></span>|  
  
 <span data-ttu-id="94784-127">다음 테이블에서는 `FlashTrackBar:` 속성 변경 이벤트 및 이벤트를 발생시키는 메서드에 의해 정의된 추가 구성원을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94784-127">The following table shows additional members defined by `FlashTrackBar:` the property-changed event and the method that raises the event.</span></span>  
  
|<span data-ttu-id="94784-128">Member</span><span class="sxs-lookup"><span data-stu-id="94784-128">Member</span></span>|<span data-ttu-id="94784-129">설명</span><span class="sxs-lookup"><span data-stu-id="94784-129">Description</span></span>|  
|------------|-----------------|  
|`ValueChanged`|<span data-ttu-id="94784-130">트랙 표시줄의 `Value` 속성이 변경되면 발생하는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="94784-130">The event that is raised when the `Value` property of the track bar changes.</span></span>|  
|`OnValueChanged`|<span data-ttu-id="94784-131">메서드는 `ValueChanged` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="94784-131">The method that raises the `ValueChanged` event.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="94784-132">`FlashTrackBar`는 이벤트 데이터에 대해 <xref:System.EventArgs> 클래스를 사용 하 고 이벤트 대리자에 <xref:System.EventHandler> 합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-132">`FlashTrackBar` uses the <xref:System.EventArgs> class for event data and <xref:System.EventHandler> for the event delegate.</span></span>  
  
 <span data-ttu-id="94784-133">해당 *EventName* 이벤트를 처리 하기 위해 `FlashTrackBar`는 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>에서 상속 하는 다음 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-133">To handle the corresponding *EventName* events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnPaint%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseDown%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseMove%2A>  
  
- <xref:System.Windows.Forms.Control.OnMouseUp%2A>  
  
- <xref:System.Windows.Forms.Control.OnResize%2A>  
  
 <span data-ttu-id="94784-134">해당 속성 변경 이벤트를 처리 하기 위해 `FlashTrackBar`는 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>에서 상속 하는 다음 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-134">To handle the corresponding property-changed events, `FlashTrackBar` overrides the following methods that it inherits from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>:</span></span>  
  
- <xref:System.Windows.Forms.Control.OnBackColorChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnBackgroundImageChanged%2A>  
  
- <xref:System.Windows.Forms.Control.OnTextChanged%2A>  
  
## <a name="example"></a><span data-ttu-id="94784-135">예</span><span class="sxs-lookup"><span data-stu-id="94784-135">Example</span></span>  
 <span data-ttu-id="94784-136">`FlashTrackBar` 컨트롤은 `FlashTrackBarValueEditor` 및 `FlashTrackBarDarkenByEditor`이라는 두 개의 UI 형식 편집기를 정의하며 이는 다음 코드 목록에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="94784-136">The `FlashTrackBar` control defines two UI type editors, `FlashTrackBarValueEditor` and `FlashTrackBarDarkenByEditor`, which are shown in the following code listings.</span></span> <span data-ttu-id="94784-137">`HostApp` 클래스는 Windows Form에소 `FlashTrackBar` 컨트롤을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="94784-137">The `HostApp` class uses the `FlashTrackBar` control on a Windows Form.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#1)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#1)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarDarkenByEditor.cs#10)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarDarkenByEditor.vb#10)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBarValueEditor.cs#20)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBarValueEditor.vb#20)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/HostApp.cs#30)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#30](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/HostApp.vb#30)]  
  
## <a name="see-also"></a><span data-ttu-id="94784-138">참조</span><span class="sxs-lookup"><span data-stu-id="94784-138">See also</span></span>

- <span data-ttu-id="94784-139">[디자인 타임 지원 확장](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="94784-139">[Extending Design-Time Support](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/37899azc(v=vs.120))</span></span>
- [<span data-ttu-id="94784-140">Windows Forms 컨트롤 개발 기본 사항</span><span class="sxs-lookup"><span data-stu-id="94784-140">Windows Forms Control Development Basics</span></span>](windows-forms-control-development-basics.md)
