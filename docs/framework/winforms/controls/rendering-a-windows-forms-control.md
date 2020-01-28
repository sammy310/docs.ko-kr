---
title: 컨트롤 렌더링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- OnPaintBackground method [Windows Forms], invoking in Windows Forms custom controls
- custom controls [Windows Forms], graphics resources
- custom controls [Windows Forms], invalidation and painting
ms.assetid: aae8e1e6-4786-432b-a15e-f4c44760d302
ms.openlocfilehash: 0e1a7ca5dc0414d518c081b1db2dca5477d4f743
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742390"
---
# <a name="rendering-a-windows-forms-control"></a><span data-ttu-id="4a99a-102">Windows Forms 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="4a99a-102">Rendering a Windows Forms Control</span></span>
<span data-ttu-id="4a99a-103">렌더링은 사용자 화면에서 시각적 표시를 만드는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-103">Rendering refers to the process of creating a visual representation on a user's screen.</span></span> <span data-ttu-id="4a99a-104">Windows Forms는 GDI (새 Windows graphics library)를 사용 하 여 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-104">Windows Forms uses GDI (the new Windows graphics library) for rendering.</span></span> <span data-ttu-id="4a99a-105">GDI에 대 한 액세스를 제공 하는 관리 되는 클래스는 <xref:System.Drawing?displayProperty=nameWithType> 네임 스페이스와 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-105">The managed classes that provide access to GDI are in the <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces.</span></span>  
  
 <span data-ttu-id="4a99a-106">컨트롤 렌더링에는 다음 요소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-106">The following elements are involved in control rendering:</span></span>  
  
- <span data-ttu-id="4a99a-107">기본 클래스에서 제공 하는 그리기 기능을 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-107">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="4a99a-108">GDI 그래픽 라이브러리의 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-108">The essential elements of the GDI graphics library.</span></span>  
  
- <span data-ttu-id="4a99a-109">그리기 영역의 기 하 도형입니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-109">The geometry of the drawing region.</span></span>  
  
- <span data-ttu-id="4a99a-110">그래픽 리소스를 해제 하기 위한 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-110">The procedure for freeing graphics resources.</span></span>  
  
## <a name="drawing-functionality-provided-by-control"></a><span data-ttu-id="4a99a-111">컨트롤에서 제공 하는 그리기 기능</span><span class="sxs-lookup"><span data-stu-id="4a99a-111">Drawing Functionality Provided by Control</span></span>  
 <span data-ttu-id="4a99a-112">기본 클래스 <xref:System.Windows.Forms.Control> <xref:System.Windows.Forms.Control.Paint> 이벤트를 통해 그리기 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-112">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="4a99a-113">컨트롤은 표시를 업데이트 해야 할 때마다 <xref:System.Windows.Forms.Control.Paint> 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-113">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="4a99a-114">.NET Framework 이벤트에 대 한 자세한 내용은 [이벤트 처리 및 발생](../../../standard/events/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a99a-114">For more information about events in the .NET Framework, see [Handling and Raising Events](../../../standard/events/index.md).</span></span>  
  
 <span data-ttu-id="4a99a-115"><xref:System.Windows.Forms.PaintEventArgs><xref:System.Windows.Forms.Control.Paint> 이벤트에 대 한 이벤트 데이터 클래스는 컨트롤을 그리는 데 필요한 데이터, 즉 그래픽 개체에 대 한 핸들과 그릴 영역을 나타내는 사각형 개체를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-115">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control — a handle to a graphics object and a rectangle object that represents the region to draw in.</span></span> <span data-ttu-id="4a99a-116">이러한 개체는 다음 코드 조각에서 굵게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-116">These objects are shown in bold in the following code fragment.</span></span>  
  
```vb  
Public Class PaintEventArgs  
   Inherits EventArgs  
   Implements IDisposable  
  
   Public ReadOnly Property ClipRectangle() As System.Drawing.Rectangle  
      ...  
   End Property  
  
   Public ReadOnly Property Graphics() As System.Drawing.Graphics  
      ...  
   End Property  
   ' Other properties and methods.  
   ...  
End Class  
```  
  
```csharp  
public class PaintEventArgs : EventArgs, IDisposable {  
public System.Drawing.Rectangle ClipRectangle {get;}  
public System.Drawing.Graphics Graphics {get;}  
// Other properties and methods.  
...  
}  
```  
  
 <span data-ttu-id="4a99a-117"><xref:System.Drawing.Graphics>은이 항목의 뒷부분에 나오는 GDI의 설명에 설명 된 대로 그리기 기능을 캡슐화 하는 관리 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-117"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of GDI later in this topic.</span></span> <span data-ttu-id="4a99a-118"><xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>은 <xref:System.Drawing.Rectangle> 구조의 인스턴스이고 컨트롤에서 그릴 수 있는 사용 가능한 영역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-118">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="4a99a-119">컨트롤 개발자는이 항목의 뒷부분에 나오는 geometry의 설명에 설명 된 대로 컨트롤의 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성을 사용 하 여 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A>를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-119">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this topic.</span></span>  
  
 <span data-ttu-id="4a99a-120">컨트롤은 <xref:System.Windows.Forms.Control>에서 상속 하는 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 재정의 하 여 렌더링 논리를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-120">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="4a99a-121"><xref:System.Windows.Forms.Control.OnPaint%2A>는 그래픽 개체 및 <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A>를 통해 그릴 사각형 및 해당 개체에 전달 된 <xref:System.Windows.Forms.PaintEventArgs> 인스턴스의 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성에 대 한 액세스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-121"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <span data-ttu-id="4a99a-122">기본 <xref:System.Windows.Forms.Control> 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드는 그리기 기능을 구현 하지 않고 단순히 <xref:System.Windows.Forms.Control.Paint> 이벤트에 등록 된 이벤트 대리자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-122">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class does not implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="4a99a-123"><xref:System.Windows.Forms.Control.OnPaint%2A>를 재정의 하는 경우 등록 된 대리자가 <xref:System.Windows.Forms.Control.Paint> 이벤트를 받도록 일반적으로 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-123">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="4a99a-124">그러나이로 인해 깜박임이 도입 됨에 따라 전체 화면을 그리는 컨트롤은 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaint%2A>호출 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-124">However, controls that paint their entire surface should not invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span> <span data-ttu-id="4a99a-125"><xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트를 재정의 하는 예제는 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a99a-125">For an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> event, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4a99a-126">컨트롤에서 직접 <xref:System.Windows.Forms.Control.OnPaint%2A>를 호출 하지 마십시오. 대신 <xref:System.Windows.Forms.Control>에서 상속 된 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드 또는 <xref:System.Windows.Forms.Control.Invalidate%2A>를 호출 하는 다른 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-126">Do not invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="4a99a-127">그러면 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드가 <xref:System.Windows.Forms.Control.OnPaint%2A>를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-127">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="4a99a-128"><xref:System.Windows.Forms.Control.Invalidate%2A> 메서드가 오버 로드 되 고 <xref:System.Windows.Forms.Control.Invalidate%2A> `e`에 제공 된 인수에 따라 컨트롤이 화면 영역의 일부 또는 전체를 다시 그립니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-128">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, a control redraws either some or all of its screen area.</span></span>  
  
 <span data-ttu-id="4a99a-129">기본 <xref:System.Windows.Forms.Control> 클래스는 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드인 그리기에 유용한 다른 메서드를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-129">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing — the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <span data-ttu-id="4a99a-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A>는 창의 배경 (이 하)을 칠하고, <xref:System.Windows.Forms.Control.OnPaint%2A>는 속도가 빠르며, 개별 페인트 요청은 다시 그려야 하는 모든 영역을 포함 하는 하나의 <xref:System.Windows.Forms.Control.Paint> 이벤트로 결합 되기 때문에 속도가 느릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and thereby the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="4a99a-131">예를 들어 컨트롤에 대 한 그라데이션 색 배경을 그리려는 경우 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>를 호출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-131">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>  
  
 <span data-ttu-id="4a99a-132"><xref:System.Windows.Forms.Control.OnPaintBackground%2A>는 이벤트와 유사한 명명법이 있고 `OnPaint` 메서드와 동일한 인수를 사용 하지만 <xref:System.Windows.Forms.Control.OnPaintBackground%2A>는 진정한 이벤트 메서드가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-132">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> is not a true event method.</span></span> <span data-ttu-id="4a99a-133">`PaintBackground` 이벤트는 없으며 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 이벤트 대리자를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-133">There is no `PaintBackground` event and <xref:System.Windows.Forms.Control.OnPaintBackground%2A> does not invoke event delegates.</span></span> <span data-ttu-id="4a99a-134"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드를 재정의 하는 경우 파생 클래스는 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드를 호출 하는 데 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-134">When overriding the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method, a derived class is not required to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method of its base class.</span></span>  
  
## <a name="gdi-basics"></a><span data-ttu-id="4a99a-135">GDI + 기본 사항</span><span class="sxs-lookup"><span data-stu-id="4a99a-135">GDI+ Basics</span></span>  
 <span data-ttu-id="4a99a-136"><xref:System.Drawing.Graphics> 클래스는 텍스트를 표시 하는 메서드 뿐만 아니라 원, 삼각형, 원호 및 타원과 같은 다양 한 모양을 그리기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-136">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, as well as methods for displaying text.</span></span> <span data-ttu-id="4a99a-137"><xref:System.Drawing?displayProperty=nameWithType> 네임 스페이스 및 해당 하위 네임 스페이스는 도형 (원, 사각형, 원호 등), 색, 글꼴, 브러시 등의 그래픽 요소를 캡슐화 하는 클래스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-137">The <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces contain classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span> <span data-ttu-id="4a99a-138">GDI에 대 한 자세한 내용은 [관리 되는 그래픽 클래스 사용](../advanced/using-managed-graphics-classes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a99a-138">For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).</span></span> <span data-ttu-id="4a99a-139">GDI의 essentials는 [방법: 진행률을 표시 하는 Windows Forms 컨트롤 만들기](how-to-create-a-windows-forms-control-that-shows-progress.md)에도 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-139">The essentials of GDI are also described in the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="4a99a-140">그리기 영역의 기 하 도형</span><span class="sxs-lookup"><span data-stu-id="4a99a-140">Geometry of the Drawing Region</span></span>  
 <span data-ttu-id="4a99a-141">컨트롤의 <xref:System.Windows.Forms.Control.ClientRectangle%2A> 속성은 사용자 화면에서 컨트롤에 사용할 수 있는 사각형 영역을 지정 하는 반면 <xref:System.Windows.Forms.PaintEventArgs>의 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성은 실제로 그려지는 영역을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-141">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is actually painted.</span></span> <span data-ttu-id="4a99a-142"><xref:System.Windows.Forms.Control.Paint> 이벤트 메서드에서는 <xref:System.Windows.Forms.PaintEventArgs> 인스턴스를 인수로 사용 하는 그리기를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-142">(Remember that painting is done in the <xref:System.Windows.Forms.Control.Paint> event method that takes a <xref:System.Windows.Forms.PaintEventArgs> instance as its argument).</span></span> <span data-ttu-id="4a99a-143">컨트롤 표시의 작은 섹션이 변경 되는 경우 처럼 컨트롤은 사용 가능한 영역의 일부만 그려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-143">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="4a99a-144">이러한 상황에서 컨트롤 개발자는 그릴 실제 사각형을 계산 하 고이를 <xref:System.Windows.Forms.Control.Invalidate%2A>에 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-144">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="4a99a-145"><xref:System.Drawing.Rectangle> 또는 <xref:System.Drawing.Region> 인수로 사용 되는 <xref:System.Windows.Forms.Control.Invalidate%2A>의 오버 로드 된 버전은 해당 인수를 사용 하 여 <xref:System.Windows.Forms.PaintEventArgs>의 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-145">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
 <span data-ttu-id="4a99a-146">다음 코드 조각에서는 `FlashTrackBar` 사용자 지정 컨트롤이 그릴 사각형 영역을 계산 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-146">The following code fragment shows how the `FlashTrackBar` custom control computes the rectangular area to draw in.</span></span> <span data-ttu-id="4a99a-147">`client` 변수는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 속성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-147">The `client` variable denotes the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property.</span></span> <span data-ttu-id="4a99a-148">전체 샘플은 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a99a-148">For a complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a><span data-ttu-id="4a99a-149">그래픽 리소스 해제</span><span class="sxs-lookup"><span data-stu-id="4a99a-149">Freeing Graphics Resources</span></span>  
 <span data-ttu-id="4a99a-150">그래픽 개체는 시스템 리소스를 사용 하기 때문에 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-150">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="4a99a-151">이러한 개체에는 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 클래스 인스턴스와 <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>및 기타 그래픽 클래스 인스턴스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-151">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class as well as instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="4a99a-152">필요한 경우에만 그래픽 리소스를 만들고 사용을 마친 후에 바로 릴리스 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-152">It is important that you create a graphics resource only when you need it and release it soon as you are finished using it.</span></span> <span data-ttu-id="4a99a-153"><xref:System.IDisposable> 인터페이스를 구현 하는 형식을 만드는 경우 리소스를 해제 하기 위해 작업이 완료 되 면 해당 <xref:System.IDisposable.Dispose%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-153">If you create a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you are finished with it in order to free resources.</span></span>  
  
 <span data-ttu-id="4a99a-154">다음 코드 조각에서는 `FlashTrackBar` 사용자 지정 컨트롤이 <xref:System.Drawing.Brush> 리소스를 만들고 해제 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a99a-154">The following code fragment shows how the `FlashTrackBar` custom control creates and releases a <xref:System.Drawing.Brush> resource.</span></span> <span data-ttu-id="4a99a-155">전체 소스 코드는 [방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기](how-to-create-a-windows-forms-control-that-shows-progress.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a99a-155">For the complete source code, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="4a99a-156">참조</span><span class="sxs-lookup"><span data-stu-id="4a99a-156">See also</span></span>

- [<span data-ttu-id="4a99a-157">방법: 진행률을 보여 주는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="4a99a-157">How to: Create a Windows Forms Control That Shows Progress</span></span>](how-to-create-a-windows-forms-control-that-shows-progress.md)
