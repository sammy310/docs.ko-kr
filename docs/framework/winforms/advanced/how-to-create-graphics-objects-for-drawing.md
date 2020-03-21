---
title: '방법: 그리는 데 필요한 그래픽 개체 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], creating
- images [Windows Forms], creating
- GDI+, creating images
ms.assetid: 162861f9-f050-445e-8abb-b2c43a918b8b
ms.openlocfilehash: d591d65904484e33285e5db7aa99760f3e1909d3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142435"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="22593-102">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="22593-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="22593-103">GDI+로 선과 모양을 그리거나 텍스트를 렌더링하거나 이미지를 표시및 조작하려면 오브젝트를 <xref:System.Drawing.Graphics> 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22593-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="22593-104">오브젝트는 <xref:System.Drawing.Graphics> GDI+ 드로잉 표면을 나타내며 그래픽 이미지를 만드는 데 사용되는 오브젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="22593-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="22593-105">그래픽 작업에는 두 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="22593-106"><xref:System.Drawing.Graphics> 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="22593-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="22593-107">오브젝트를 <xref:System.Drawing.Graphics> 사용하여 선과 모양을 그리거나, 텍스트를 렌더링하거나, 이미지를 표시하고 조작합니다.</span><span class="sxs-lookup"><span data-stu-id="22593-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="22593-108">그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="22593-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="22593-109">그래픽 개체는 다양한 방법으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="22593-110">그래픽 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="22593-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="22593-111">폼 또는 컨트롤의 경우 그래픽 <xref:System.Windows.Forms.PaintEventArgs> 개체에 <xref:System.Windows.Forms.Control.Paint> 대한 참조를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="22593-112">일반적으로 컨트롤에 대한 페인팅 코드를 만들 때 그래픽 개체에 대한 참조를 얻는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="22593-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="22593-113">마찬가지로 <xref:System.Drawing.Printing.PrintPageEventArgs> <xref:System.Drawing.Printing.PrintDocument>에 대한 이벤트를 처리할 때의 속성으로 그래픽 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 개체를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="22593-114">또는</span><span class="sxs-lookup"><span data-stu-id="22593-114">-or-</span></span>  
  
- <span data-ttu-id="22593-115">컨트롤 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 또는 폼의 메서드를 호출하여 해당 <xref:System.Drawing.Graphics> 컨트롤 또는 폼의 드로잉 표면을 나타내는 개체에 대한 참조를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="22593-116">이미 존재하는 폼이나 컨트롤을 그리려면 이 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="22593-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="22593-117">또는</span><span class="sxs-lookup"><span data-stu-id="22593-117">-or-</span></span>  
  
- <span data-ttu-id="22593-118">에서 <xref:System.Drawing.Graphics> 상속하는 모든 개체에서 <xref:System.Drawing.Image>개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="22593-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="22593-119">이 방법은 기존 이미지를 변경하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="22593-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="22593-120">다음 섹션에서는 이러한 각 프로세스에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="22593-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="22593-121">페인트 이벤트 처리기의 페인트EventArgs</span><span class="sxs-lookup"><span data-stu-id="22593-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="22593-122"><xref:System.Windows.Forms.PaintEventHandler> 에 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 대한 컨트롤 또는 <xref:System.Drawing.Printing.PrintDocument>에 대한 프로그래밍 할 때 그래픽 개체는 <xref:System.Windows.Forms.PaintEventArgs> 또는 의 <xref:System.Drawing.Printing.PrintPageEventArgs>속성 중 하나로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="22593-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="22593-123">페인트 이벤트의 PaintEventArgs에서 그래픽 개체에 대한 참조를 얻으려면</span><span class="sxs-lookup"><span data-stu-id="22593-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="22593-124">개체를 <xref:System.Drawing.Graphics> 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="22593-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="22593-125">의 일부로 전달된 <xref:System.Drawing.Graphics> 객체를 참조할 변수를 할당합니다. <xref:System.Windows.Forms.PaintEventArgs></span><span class="sxs-lookup"><span data-stu-id="22593-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="22593-126">코드를 삽입하여 폼 또는 컨트롤을 페인칠합니다.</span><span class="sxs-lookup"><span data-stu-id="22593-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="22593-127">다음 예제에서는 <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> 이벤트에서 개체를 참조하는 <xref:System.Windows.Forms.Control.Paint> 방법을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
    ```vb  
    Private Sub Form1_Paint(sender As Object, pe As PaintEventArgs) Handles _  
       MyBase.Paint  
       ' Declares the Graphics object and sets it to the Graphics object  
       ' supplied in the PaintEventArgs.  
       Dim g As Graphics = pe.Graphics  
       ' Insert code to paint the form here.  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Paint(object sender,
       System.Windows.Forms.PaintEventArgs pe)
    {  
       // Declares the Graphics object and sets it to the Graphics object  
       // supplied in the PaintEventArgs.  
       Graphics g = pe.Graphics;  
       // Insert code to paint the form here.  
    }  
    ```  
  
    ```cpp  
    private:  
       void Form1_Paint(System::Object ^ sender,  
          System::Windows::Forms::PaintEventArgs ^ pe)  
       {  
          // Declares the Graphics object and sets it to the Graphics object  
          // supplied in the PaintEventArgs.  
          Graphics ^ g = pe->Graphics;  
          // Insert code to paint the form here.  
       }  
    ```  
  
## <a name="creategraphics-method"></a><span data-ttu-id="22593-128">그래픽 만들기 방법</span><span class="sxs-lookup"><span data-stu-id="22593-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="22593-129">컨트롤 또는 양식의 메서드를 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 사용하여 해당 컨트롤 또는 <xref:System.Drawing.Graphics> 양식의 드로잉 서피스를 나타내는 객체에 대한 참조를 얻을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="22593-130">CreateGraphics 메서드를 사용하여 그래픽 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="22593-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="22593-131">그래픽을 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 렌더링할 폼 또는 컨트롤의 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="22593-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
    ```vb  
    Dim g as Graphics  
    ' Sets g to a Graphics object representing the drawing surface of the  
    ' control or form g is a member of.  
    g = Me.CreateGraphics  
    ```  
  
    ```csharp  
    Graphics g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this.CreateGraphics();  
    ```  
  
    ```cpp  
    Graphics ^ g;  
    // Sets g to a graphics object representing the drawing surface of the  
    // control or form g is a member of.  
    g = this->CreateGraphics();  
    ```  
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="22593-132">이미지 개체에서 만들기</span><span class="sxs-lookup"><span data-stu-id="22593-132">Create from an Image Object</span></span>  
 <span data-ttu-id="22593-133">또한 클래스에서 파생 된 모든 개체에서 그래픽 <xref:System.Drawing.Image> 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="22593-134">이미지에서 그래픽 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="22593-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="22593-135"><xref:System.Drawing.Graphics> 메서드를 <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> 호출하여 개체를 만들 려는 Image 변수의 이름을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22593-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="22593-136">다음 예제에서는 개체를 <xref:System.Drawing.Bitmap> 사용하는 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주실 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
    ```vb  
    Dim myBitmap as New Bitmap("C:\Documents and Settings\Joe\Pics\myPic.bmp")  
    Dim g as Graphics = Graphics.FromImage(myBitmap)  
    ```  
  
    ```csharp  
    Bitmap myBitmap = new Bitmap(@"C:\Documents and
       Settings\Joe\Pics\myPic.bmp");  
    Graphics g = Graphics.FromImage(myBitmap);  
    ```  
  
    ```cpp  
    Bitmap ^ myBitmap = gcnew  
       Bitmap("D:\\Documents and Settings\\Joe\\Pics\\myPic.bmp");  
    Graphics ^ g = Graphics::FromImage(myBitmap);  
    ```  
  
> [!NOTE]
> <span data-ttu-id="22593-137">16비트, <xref:System.Drawing.Graphics> 24비트 및 32비트 .bmp 파일과 같이 인덱싱되지 않은 .bmp 파일에서만 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="22593-138">인덱싱되지 않은 .bmp 파일의 각 픽셀에는 색이 있는 .bmp 파일의 픽셀과 달리 색테이블에 인덱스가 있는 .bmp 파일이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="22593-139">셰이프 및 이미지 그리기 및 조작</span><span class="sxs-lookup"><span data-stu-id="22593-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="22593-140">생성된 후에는 오브젝트를 <xref:System.Drawing.Graphics> 사용하여 선과 모양을 그리거나 텍스트를 렌더링하거나 이미지를 표시하고 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="22593-141"><xref:System.Drawing.Graphics> 개체와 함께 사용되는 주 개체는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="22593-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="22593-142"><xref:System.Drawing.Pen> 클래스-선을 그리거나, 셰이프를 윤곽을 그리거나, 다른 기하학적 표현을 렌더링하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="22593-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="22593-143"><xref:System.Drawing.Brush> 클래스- 채워진 셰이프, 이미지 또는 텍스트와 같은 그래픽 영역을 채우는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="22593-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="22593-144"><xref:System.Drawing.Font> 클래스-텍스트를 렌더링할 때 사용할 셰이프에 대한 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="22593-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="22593-145"><xref:System.Drawing.Color> 구조-표시할 다른 색상을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="22593-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="22593-146">만든 그래픽 개체를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="22593-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="22593-147">위에 나열된 적절한 개체로 작업하여 필요한 것을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="22593-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="22593-148">자세한 내용은 아래 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="22593-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="22593-149">렌더링하려면</span><span class="sxs-lookup"><span data-stu-id="22593-149">To render</span></span>|<span data-ttu-id="22593-150">참조 항목</span><span class="sxs-lookup"><span data-stu-id="22593-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="22593-151">선</span><span class="sxs-lookup"><span data-stu-id="22593-151">Lines</span></span>|[<span data-ttu-id="22593-152">방법: Windows Form에 선 그리기</span><span class="sxs-lookup"><span data-stu-id="22593-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="22593-153">셰이프</span><span class="sxs-lookup"><span data-stu-id="22593-153">Shapes</span></span>|[<span data-ttu-id="22593-154">방법: 윤곽선이 있는 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="22593-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="22593-155">텍스트</span><span class="sxs-lookup"><span data-stu-id="22593-155">Text</span></span>|[<span data-ttu-id="22593-156">방법: Windows Form에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="22593-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="22593-157">이미지</span><span class="sxs-lookup"><span data-stu-id="22593-157">Images</span></span>|[<span data-ttu-id="22593-158">방법: GDI+를 사용하여 이미지 렌더링</span><span class="sxs-lookup"><span data-stu-id="22593-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="22593-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22593-159">See also</span></span>

- [<span data-ttu-id="22593-160">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="22593-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="22593-161">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="22593-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="22593-162">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="22593-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="22593-163">방법: GDI+를 사용하여 이미지 렌더링</span><span class="sxs-lookup"><span data-stu-id="22593-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
