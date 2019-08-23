---
title: Windows Forms 컨트롤 렌더링
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
ms.openlocfilehash: b24fbefac0dcfb666e25ad1d1726ef2cf8a5d84e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968271"
---
# <a name="rendering-a-windows-forms-control"></a><span data-ttu-id="dd2b1-102">Windows Forms 컨트롤 렌더링</span><span class="sxs-lookup"><span data-stu-id="dd2b1-102">Rendering a Windows Forms Control</span></span>
<span data-ttu-id="dd2b1-103">렌더링은 사용자 화면에서 시각적 표시를 만드는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-103">Rendering refers to the process of creating a visual representation on a user's screen.</span></span> <span data-ttu-id="dd2b1-104">Windows Forms는 GDI (새 Windows graphics library)를 사용 하 여 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-104">Windows Forms uses GDI (the new Windows graphics library) for rendering.</span></span> <span data-ttu-id="dd2b1-105">GDI에 대 한 액세스를 제공 하는 관리 되 <xref:System.Drawing?displayProperty=nameWithType> 는 클래스는 네임 스페이스 및 네임 스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-105">The managed classes that provide access to GDI are in the <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces.</span></span>  
  
 <span data-ttu-id="dd2b1-106">컨트롤 렌더링에는 다음 요소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-106">The following elements are involved in control rendering:</span></span>  
  
- <span data-ttu-id="dd2b1-107">기본 클래스 <xref:System.Windows.Forms.Control?displayProperty=nameWithType>에서 제공 하는 그리기 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-107">The drawing functionality provided by the base class <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="dd2b1-108">GDI 그래픽 라이브러리의 필수 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-108">The essential elements of the GDI graphics library.</span></span>  
  
- <span data-ttu-id="dd2b1-109">그리기 영역의 기 하 도형입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-109">The geometry of the drawing region.</span></span>  
  
- <span data-ttu-id="dd2b1-110">그래픽 리소스를 해제 하기 위한 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-110">The procedure for freeing graphics resources.</span></span>  
  
## <a name="drawing-functionality-provided-by-control"></a><span data-ttu-id="dd2b1-111">컨트롤에서 제공 하는 그리기 기능</span><span class="sxs-lookup"><span data-stu-id="dd2b1-111">Drawing Functionality Provided by Control</span></span>  
 <span data-ttu-id="dd2b1-112">기본 클래스 <xref:System.Windows.Forms.Control> 는 <xref:System.Windows.Forms.Control.Paint> 이벤트를 통해 그리기 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-112">The base class <xref:System.Windows.Forms.Control> provides drawing functionality through its <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="dd2b1-113">컨트롤은 표시를 <xref:System.Windows.Forms.Control.Paint> 업데이트 해야 할 때마다 이벤트를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-113">A control raises the <xref:System.Windows.Forms.Control.Paint> event whenever it needs to update its display.</span></span> <span data-ttu-id="dd2b1-114">.NET Framework 이벤트에 대 한 자세한 내용은 [이벤트 처리 및 발생](../../../standard/events/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-114">For more information about events in the .NET Framework, see [Handling and Raising Events](../../../standard/events/index.md).</span></span>  
  
 <span data-ttu-id="dd2b1-115"><xref:System.Windows.Forms.Control.Paint> 이벤트에 대 한 이벤트 데이터 클래스는 컨트롤을 그리는 데 필요한 데이터, 즉 그래픽 개체에 대 한 핸들과 그릴 영역을 나타내는 사각형 개체를 보유 합니다. <xref:System.Windows.Forms.PaintEventArgs></span><span class="sxs-lookup"><span data-stu-id="dd2b1-115">The event data class for the <xref:System.Windows.Forms.Control.Paint> event, <xref:System.Windows.Forms.PaintEventArgs>, holds the data needed for drawing a control — a handle to a graphics object and a rectangle object that represents the region to draw in.</span></span> <span data-ttu-id="dd2b1-116">이러한 개체는 다음 코드 조각에서 굵게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-116">These objects are shown in bold in the following code fragment.</span></span>  
  
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
  
 <span data-ttu-id="dd2b1-117"><xref:System.Drawing.Graphics>는이 항목의 뒷부분에 나오는 GDI의 설명에 설명 된 대로 그리기 기능을 캡슐화 하는 관리 되는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-117"><xref:System.Drawing.Graphics> is a managed class that encapsulates drawing functionality, as described in the discussion of GDI later in this topic.</span></span> <span data-ttu-id="dd2b1-118">는 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 구조체<xref:System.Drawing.Rectangle> 의 인스턴스이고 컨트롤에서 그릴 수 있는 사용 가능한 영역을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-118">The <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> is an instance of the <xref:System.Drawing.Rectangle> structure and defines the available area in which a control can draw.</span></span> <span data-ttu-id="dd2b1-119">컨트롤 개발자는이 항목의 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 뒷부분에 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 있는 geometry의 설명에 설명 된 대로 컨트롤의 속성을 사용 하 여를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-119">A control developer can compute the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> using the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of a control, as described in the discussion of geometry later in this topic.</span></span>  
  
 <span data-ttu-id="dd2b1-120"><xref:System.Windows.Forms.Control.OnPaint%2A> 컨트롤이<xref:System.Windows.Forms.Control>상속 하는 메서드를 재정의 하 여 렌더링 논리를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-120">A control must provide rendering logic by overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> method that it inherits from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="dd2b1-121"><xref:System.Windows.Forms.Control.OnPaint%2A>및에 전달 된 <xref:System.Windows.Forms.PaintEventArgs> 인스턴스의 속성을통해그릴사각형및그래픽개체에대한액세스를가져옵니다.<xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A></span><span class="sxs-lookup"><span data-stu-id="dd2b1-121"><xref:System.Windows.Forms.Control.OnPaint%2A> gets access to a graphics object and a rectangle to draw in through the <xref:System.Drawing.Design.PaintValueEventArgs.Graphics%2A> and the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> properties of the <xref:System.Windows.Forms.PaintEventArgs> instance passed to it.</span></span>  
  
```vb  
Protected Overridable Sub OnPaint(pe As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaint(PaintEventArgs pe);  
```  
  
 <span data-ttu-id="dd2b1-122">기본 <xref:System.Windows.Forms.Control.OnPaint%2A> <xref:System.Windows.Forms.Control.Paint> 클래스의 메서드는 그리기 기능을 구현 하지 않지만 단순히 이벤트에 등록 된 이벤트 대리자를 호출 합니다. <xref:System.Windows.Forms.Control></span><span class="sxs-lookup"><span data-stu-id="dd2b1-122">The <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base <xref:System.Windows.Forms.Control> class does not implement any drawing functionality but merely invokes the event delegates that are registered with the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="dd2b1-123">을 재정의 <xref:System.Windows.Forms.Control.OnPaint%2A>하는 경우 일반적으로 등록 된 <xref:System.Windows.Forms.Control.OnPaint%2A> 대리자가 이벤트를 <xref:System.Windows.Forms.Control.Paint> 받도록 기본 클래스의 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-123">When you override <xref:System.Windows.Forms.Control.OnPaint%2A>, you should typically invoke the <xref:System.Windows.Forms.Control.OnPaint%2A> method of the base class so that registered delegates receive the <xref:System.Windows.Forms.Control.Paint> event.</span></span> <span data-ttu-id="dd2b1-124">그러나이로 인해 깜박임이 도입 되므로 전체 화면을 그리는 컨트롤은 기본 클래스 <xref:System.Windows.Forms.Control.OnPaint%2A>의를 호출 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-124">However, controls that paint their entire surface should not invoke the base class's <xref:System.Windows.Forms.Control.OnPaint%2A>, as this introduces flicker.</span></span> <span data-ttu-id="dd2b1-125"><xref:System.Windows.Forms.Control.OnPaint%2A> 이벤트를 재정의 하는 예제를 [보려면 방법: 진행률](how-to-create-a-windows-forms-control-that-shows-progress.md)을 표시 하는 Windows Forms 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-125">For an example of overriding the <xref:System.Windows.Forms.Control.OnPaint%2A> event, see the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="dd2b1-126">컨트롤에서 직접 <xref:System.Windows.Forms.Control.OnPaint%2A> 호출 하지 말고 대신 <xref:System.Windows.Forms.Control.Invalidate%2A> 메서드 (에서 <xref:System.Windows.Forms.Control>상속) 또는를 호출 <xref:System.Windows.Forms.Control.Invalidate%2A>하는 다른 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-126">Do not invoke <xref:System.Windows.Forms.Control.OnPaint%2A> directly from your control; instead, invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method (inherited from <xref:System.Windows.Forms.Control>) or some other method that invokes <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="dd2b1-127">그런 <xref:System.Windows.Forms.Control.Invalidate%2A> 다음 메서드는를 <xref:System.Windows.Forms.Control.OnPaint%2A>호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-127">The <xref:System.Windows.Forms.Control.Invalidate%2A> method in turn invokes <xref:System.Windows.Forms.Control.OnPaint%2A>.</span></span> <span data-ttu-id="dd2b1-128">메서드가 오버 로드 되 고에 <xref:System.Windows.Forms.Control.Invalidate%2A> `e`제공 된 인수에 따라 컨트롤이 화면 영역의 일부 또는 전체를 다시 그립니다. <xref:System.Windows.Forms.Control.Invalidate%2A></span><span class="sxs-lookup"><span data-stu-id="dd2b1-128">The <xref:System.Windows.Forms.Control.Invalidate%2A> method is overloaded, and, depending on the arguments supplied to <xref:System.Windows.Forms.Control.Invalidate%2A> `e`, a control redraws either some or all of its screen area.</span></span>  
  
 <span data-ttu-id="dd2b1-129">기본 <xref:System.Windows.Forms.Control> 클래스는 메서드를 그리는 데 유용한 다른 메서드를 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-129">The base <xref:System.Windows.Forms.Control> class defines another method that is useful for drawing — the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method.</span></span>  
  
```vb  
Protected Overridable Sub OnPaintBackground(pevent As PaintEventArgs)  
```  
  
```csharp  
protected virtual void OnPaintBackground(PaintEventArgs pevent);  
```  
  
 <span data-ttu-id="dd2b1-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A>는 창의 배경 (그리고 그에 따라 셰이프)을 칠하고,는 <xref:System.Windows.Forms.Control.OnPaint%2A> 빠른 것으로 확인 되 고, 개별 페인트 요청은 모든 영역을 포함 하는 하나의 <xref:System.Windows.Forms.Control.Paint> 이벤트로 결합 되기 때문에 속도가 느릴 수 있습니다. 그려야.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-130"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> paints the background (and thereby the shape) of the window and is guaranteed to be fast, while <xref:System.Windows.Forms.Control.OnPaint%2A> paints the details and might be slower because individual paint requests are combined into one <xref:System.Windows.Forms.Control.Paint> event that covers all areas that have to be redrawn.</span></span> <span data-ttu-id="dd2b1-131">예를 들어 컨트롤의 그라데이션 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 색 배경을 그리려면를 호출 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-131">You might want to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> if, for instance, you want to draw a gradient-colored background for your control.</span></span>  
  
 <span data-ttu-id="dd2b1-132">에는 이벤트와 유사한 명명법이 있고 `OnPaint` 메서드와 동일한 인수를 사용 하지만 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 는 진정한 이벤트 메서드가 아닙니다. <xref:System.Windows.Forms.Control.OnPaintBackground%2A></span><span class="sxs-lookup"><span data-stu-id="dd2b1-132">While <xref:System.Windows.Forms.Control.OnPaintBackground%2A> has an event-like nomenclature and takes the same argument as the `OnPaint` method, <xref:System.Windows.Forms.Control.OnPaintBackground%2A> is not a true event method.</span></span> <span data-ttu-id="dd2b1-133">이벤트는 없으며 `PaintBackground`이벤트대리자 를호출하지않습니다.<xref:System.Windows.Forms.Control.OnPaintBackground%2A></span><span class="sxs-lookup"><span data-stu-id="dd2b1-133">There is no `PaintBackground` event and <xref:System.Windows.Forms.Control.OnPaintBackground%2A> does not invoke event delegates.</span></span> <span data-ttu-id="dd2b1-134"><xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드를 재정의 하는 경우 파생 클래스는 기본 클래스의 <xref:System.Windows.Forms.Control.OnPaintBackground%2A> 메서드를 호출 하는 데 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-134">When overriding the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method, a derived class is not required to invoke the <xref:System.Windows.Forms.Control.OnPaintBackground%2A> method of its base class.</span></span>  
  
## <a name="gdi-basics"></a><span data-ttu-id="dd2b1-135">GDI + 기본 사항</span><span class="sxs-lookup"><span data-stu-id="dd2b1-135">GDI+ Basics</span></span>  
 <span data-ttu-id="dd2b1-136">이 <xref:System.Drawing.Graphics> 클래스는 텍스트를 표시 하는 메서드 뿐만 아니라 원, 삼각형, 원호 및 타원과 같은 다양 한 모양을 그리기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-136">The <xref:System.Drawing.Graphics> class provides methods for drawing various shapes such as circles, triangles, arcs, and ellipses, as well as methods for displaying text.</span></span> <span data-ttu-id="dd2b1-137">네임 <xref:System.Drawing?displayProperty=nameWithType> 스페이스 및 네임 스페이스에는 도형 (원, 사각형, 원호 등), 색, 글꼴, 브러시 등의 그래픽 요소를 캡슐화 하는 클래스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-137">The <xref:System.Drawing?displayProperty=nameWithType> namespace and its subnamespaces contain classes that encapsulate graphics elements such as shapes (circles, rectangles, arcs, and others), colors, fonts, brushes, and so on.</span></span> <span data-ttu-id="dd2b1-138">GDI에 대 한 자세한 내용은 [관리 되는 그래픽 클래스 사용](../advanced/using-managed-graphics-classes.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-138">For more information about GDI, see [Using Managed Graphics Classes](../advanced/using-managed-graphics-classes.md).</span></span> <span data-ttu-id="dd2b1-139">또한 GDI의 essentials는 [방법: 진행률](how-to-create-a-windows-forms-control-that-shows-progress.md)을 표시 하는 Windows Forms 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-139">The essentials of GDI are also described in the [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
## <a name="geometry-of-the-drawing-region"></a><span data-ttu-id="dd2b1-140">그리기 영역의 기 하 도형</span><span class="sxs-lookup"><span data-stu-id="dd2b1-140">Geometry of the Drawing Region</span></span>  
 <span data-ttu-id="dd2b1-141">컨트롤 <xref:System.Windows.Forms.Control.ClientRectangle%2A> 의 속성은 사용자 화면에서 컨트롤에 사용할 수 있는 사각형 영역을 지정 하는 반면의 <xref:System.Windows.Forms.PaintEventArgs> 속성 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 은 실제로 그려지는 영역을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-141">The <xref:System.Windows.Forms.Control.ClientRectangle%2A> property of a control specifies the rectangular region available to the control on the user's screen, while the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs> specifies the area that is actually painted.</span></span> <span data-ttu-id="dd2b1-142">인스턴스를 <xref:System.Windows.Forms.Control.Paint> <xref:System.Windows.Forms.PaintEventArgs> 인수로 사용 하는 이벤트 메서드에서 그리기가 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-142">(Remember that painting is done in the <xref:System.Windows.Forms.Control.Paint> event method that takes a <xref:System.Windows.Forms.PaintEventArgs> instance as its argument).</span></span> <span data-ttu-id="dd2b1-143">컨트롤 표시의 작은 섹션이 변경 되는 경우 처럼 컨트롤은 사용 가능한 영역의 일부만 그려야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-143">A control might need to paint only a portion of its available area, as is the case when a small section of the control's display changes.</span></span> <span data-ttu-id="dd2b1-144">이러한 상황에서 컨트롤 개발자는에 그릴 실제 사각형을 계산 하 고이를에 <xref:System.Windows.Forms.Control.Invalidate%2A>전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-144">In those situations, a control developer must compute the actual rectangle to draw in and pass that to <xref:System.Windows.Forms.Control.Invalidate%2A>.</span></span> <span data-ttu-id="dd2b1-145"><xref:System.Windows.Forms.Control.Invalidate%2A> 또는 <xref:System.Drawing.Rectangle> <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 를 인수로 사용 하는의 오버 로드 된 버전은 해당 인수를 사용 하 여의 속성을 생성 합니다. <xref:System.Drawing.Region></span><span class="sxs-lookup"><span data-stu-id="dd2b1-145">The overloaded versions of <xref:System.Windows.Forms.Control.Invalidate%2A> that take a <xref:System.Drawing.Rectangle> or <xref:System.Drawing.Region> as an argument use that argument to generate the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property of <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
 <span data-ttu-id="dd2b1-146">다음 코드 조각에서는 `FlashTrackBar` 사용자 지정 컨트롤이 그릴 사각형 영역을 계산 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-146">The following code fragment shows how the `FlashTrackBar` custom control computes the rectangular area to draw in.</span></span> <span data-ttu-id="dd2b1-147">변수 `client` 는 속성을 <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-147">The `client` variable denotes the <xref:System.Windows.Forms.PaintEventArgs.ClipRectangle%2A> property.</span></span> <span data-ttu-id="dd2b1-148">전체 샘플을 보려면 [방법: 진행률](how-to-create-a-windows-forms-control-that-shows-progress.md)을 표시 하는 Windows Forms 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-148">For a complete sample, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#6)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#6)]  
  
## <a name="freeing-graphics-resources"></a><span data-ttu-id="dd2b1-149">그래픽 리소스 해제</span><span class="sxs-lookup"><span data-stu-id="dd2b1-149">Freeing Graphics Resources</span></span>  
 <span data-ttu-id="dd2b1-150">그래픽 개체는 시스템 리소스를 사용 하기 때문에 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-150">Graphics objects are expensive because they use system resources.</span></span> <span data-ttu-id="dd2b1-151">이러한 개체에는 <xref:System.Drawing.Graphics?displayProperty=nameWithType> 클래스 <xref:System.Drawing.Brush?displayProperty=nameWithType>인스턴스 뿐 아니라, <xref:System.Drawing.Pen?displayProperty=nameWithType>및 기타 그래픽 클래스 인스턴스도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-151">Such objects include instances of the <xref:System.Drawing.Graphics?displayProperty=nameWithType> class as well as instances of <xref:System.Drawing.Brush?displayProperty=nameWithType>, <xref:System.Drawing.Pen?displayProperty=nameWithType>, and other graphics classes.</span></span> <span data-ttu-id="dd2b1-152">필요한 경우에만 그래픽 리소스를 만들고 사용을 마친 후에 바로 릴리스 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-152">It is important that you create a graphics resource only when you need it and release it soon as you are finished using it.</span></span> <span data-ttu-id="dd2b1-153">인터페이스를 <xref:System.IDisposable> 구현 하는 형식을 만드는 경우 리소스를 해제 하기 <xref:System.IDisposable.Dispose%2A> 위해 작업이 완료 되 면 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-153">If you create a type that implements the <xref:System.IDisposable> interface, call its <xref:System.IDisposable.Dispose%2A> method when you are finished with it in order to free resources.</span></span>  
  
 <span data-ttu-id="dd2b1-154">다음 코드 조각에서는 사용자 지정 컨트롤 `FlashTrackBar` 에서 리소스를 <xref:System.Drawing.Brush> 만들고 해제 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-154">The following code fragment shows how the `FlashTrackBar` custom control creates and releases a <xref:System.Drawing.Brush> resource.</span></span> <span data-ttu-id="dd2b1-155">전체 소스 코드를 보려면 [방법: 진행률](how-to-create-a-windows-forms-control-that-shows-progress.md)을 표시 하는 Windows Forms 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dd2b1-155">For the complete source code, see [How to: Create a Windows Forms Control That Shows Progress](how-to-create-a-windows-forms-control-that-shows-progress.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#5)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#5)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#4)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#4)]  
  
 [!code-csharp[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/CS/FlashTrackBar.cs#3)]
 [!code-vb[System.Windows.Forms.FlashTrackBar#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FlashTrackBar/VB/FlashTrackBar.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="dd2b1-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="dd2b1-156">See also</span></span>

- [<span data-ttu-id="dd2b1-157">방법: 진행률을 표시 하는 Windows Forms 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="dd2b1-157">How to: Create a Windows Forms Control That Shows Progress</span></span>](how-to-create-a-windows-forms-control-that-shows-progress.md)
