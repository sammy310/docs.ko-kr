---
title: '방법: 그리는 데 필요한 그래픽 개체 만들기'
description: 이제는 선 및 모양을 그리거나, 텍스트를 렌더링 하거나, GDI +를 사용 하 여 이미지를 표시 및 조작 하는 데 필요한 그래픽 개체를 만드는 방법을 알아봅니다.
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
ms.openlocfilehash: 1a0884c1e9956dc6f4608e32372deeea24ef4670
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903209"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="c2441-103">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="c2441-103">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="c2441-104">선 및 도형을 그리거나, 텍스트를 렌더링 하거나, GDI +를 사용 하 여 이미지를 표시 하 고 조작 하려면 먼저 <xref:System.Drawing.Graphics> 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-104">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="c2441-105"><xref:System.Drawing.Graphics>개체는 GDI + 그리기 화면을 나타내며 그래픽 이미지를 만드는 데 사용 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-105">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="c2441-106">그래픽 작업에는 두 가지 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-106">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="c2441-107">개체 만들기 <xref:System.Drawing.Graphics></span><span class="sxs-lookup"><span data-stu-id="c2441-107">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="c2441-108">개체를 사용 하 여 <xref:System.Drawing.Graphics> 선과 도형을 그리거나, 텍스트를 렌더링 하거나, 이미지를 표시 하 고 조작 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-108">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="c2441-109">그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="c2441-109">Creating a Graphics Object</span></span>  
 <span data-ttu-id="c2441-110">그래픽 개체는 다양 한 방법으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-110">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="c2441-111">그래픽 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c2441-111">To create a graphics object</span></span>  
  
- <span data-ttu-id="c2441-112"><xref:System.Windows.Forms.PaintEventArgs>폼 또는 컨트롤의 경우의 일부로 그래픽 개체에 대 한 참조를 받습니다 <xref:System.Windows.Forms.Control.Paint> .</span><span class="sxs-lookup"><span data-stu-id="c2441-112">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="c2441-113">일반적으로 컨트롤의 그리기 코드를 만들 때 그래픽 개체에 대 한 참조를 가져오는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-113">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="c2441-114">마찬가지로, <xref:System.Drawing.Printing.PrintPageEventArgs> <xref:System.Drawing.Printing.PrintDocument.PrintPage> 에 대 한 이벤트를 처리할 때 그래픽 개체를의 속성으로 가져올 수도 있습니다 <xref:System.Drawing.Printing.PrintDocument> .</span><span class="sxs-lookup"><span data-stu-id="c2441-114">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="c2441-115">또는</span><span class="sxs-lookup"><span data-stu-id="c2441-115">-or-</span></span>  
  
- <span data-ttu-id="c2441-116">컨트롤이 나 폼의 메서드를 호출 하 여 <xref:System.Windows.Forms.Control.CreateGraphics%2A> <xref:System.Drawing.Graphics> 해당 컨트롤이 나 폼의 그리기 화면을 나타내는 개체에 대 한 참조를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-116">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="c2441-117">이미 존재 하는 폼 이나 컨트롤에 그리려는 경우이 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-117">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="c2441-118">또는</span><span class="sxs-lookup"><span data-stu-id="c2441-118">-or-</span></span>  
  
- <span data-ttu-id="c2441-119"><xref:System.Drawing.Graphics>에서 상속 되는 개체에서 개체를 만듭니다 <xref:System.Drawing.Image> .</span><span class="sxs-lookup"><span data-stu-id="c2441-119">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="c2441-120">이 방법은 이미 존재 하는 이미지를 변경 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-120">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="c2441-121">다음 섹션에서는 이러한 각 프로세스에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-121">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="c2441-122">Paint 이벤트 처리기의 PaintEventArgs</span><span class="sxs-lookup"><span data-stu-id="c2441-122">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="c2441-123">컨트롤 또는의에 대 한를 프로그래밍할 때 <xref:System.Windows.Forms.PaintEventHandler> <xref:System.Drawing.Printing.PrintDocument.PrintPage> <xref:System.Drawing.Printing.PrintDocument> 그래픽 개체는 또는의 속성 중 하나로 제공 됩니다 <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Drawing.Printing.PrintPageEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="c2441-123">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="c2441-124">Paint 이벤트의 PaintEventArgs에서 그래픽 개체에 대 한 참조를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="c2441-124">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="c2441-125">개체를 선언 <xref:System.Drawing.Graphics> 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-125">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="c2441-126">의 일부로 전달 된 개체를 참조 하는 변수를 할당 합니다 <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> .</span><span class="sxs-lookup"><span data-stu-id="c2441-126">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="c2441-127">폼 이나 컨트롤을 그리는 코드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-127">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="c2441-128">다음 예제에서는 이벤트의에서 개체를 참조 하는 방법을 보여 줍니다 <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> <xref:System.Windows.Forms.Control.Paint> .</span><span class="sxs-lookup"><span data-stu-id="c2441-128">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="c2441-129">CreateGraphics 메서드</span><span class="sxs-lookup"><span data-stu-id="c2441-129">CreateGraphics Method</span></span>  
 <span data-ttu-id="c2441-130"><xref:System.Windows.Forms.Control.CreateGraphics%2A>컨트롤이 나 폼의 메서드를 사용 하 여 <xref:System.Drawing.Graphics> 해당 컨트롤이 나 폼의 그리기 화면을 나타내는 개체에 대 한 참조를 가져올 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-130">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="c2441-131">CreateGraphics 메서드를 사용 하 여 그래픽 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c2441-131">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="c2441-132"><xref:System.Windows.Forms.Control.CreateGraphics%2A>그래픽을 렌더링 하려는 폼 이나 컨트롤의 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-132">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="c2441-133">이미지 개체에서 만들기</span><span class="sxs-lookup"><span data-stu-id="c2441-133">Create from an Image Object</span></span>  
 <span data-ttu-id="c2441-134">또한 클래스에서 파생 되는 모든 개체에서 그래픽 개체를 만들 수 있습니다 <xref:System.Drawing.Image> .</span><span class="sxs-lookup"><span data-stu-id="c2441-134">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="c2441-135">이미지에서 그래픽 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="c2441-135">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="c2441-136">개체를 <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> 만들려는 이미지 변수의 이름을 제공 하 여 메서드를 호출 합니다 <xref:System.Drawing.Graphics> .</span><span class="sxs-lookup"><span data-stu-id="c2441-136">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="c2441-137">다음 예제에서는 개체를 사용 하는 방법을 보여 줍니다 <xref:System.Drawing.Bitmap> .</span><span class="sxs-lookup"><span data-stu-id="c2441-137">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
> <span data-ttu-id="c2441-138"><xref:System.Drawing.Graphics>16 비트, 24 비트 및 32 비트 .bmp 파일과 같은 인덱싱되지 않은 .bmp 파일의 개체만 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-138">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="c2441-139">비인덱스 .bmp 파일의 각 픽셀은 색 테이블에 대 한 인덱스를 포함 하는 인덱싱된 .bmp 파일의 픽셀과 달리 색을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-139">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="c2441-140">모양 및 이미지 그리기 및 조작</span><span class="sxs-lookup"><span data-stu-id="c2441-140">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="c2441-141">개체를 만든 후에 <xref:System.Drawing.Graphics> 는 개체를 사용 하 여 선과 셰이프를 그리거나, 텍스트를 렌더링 하거나, 이미지를 표시 하 고 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-141">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="c2441-142">개체와 함께 사용 되는 보안 주체 개체는 <xref:System.Drawing.Graphics> 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-142">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="c2441-143"><xref:System.Drawing.Pen>클래스-선 그리기, 모양 개요 또는 다른 기하학적 표현 렌더링에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-143">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="c2441-144"><xref:System.Drawing.Brush>클래스-채워진 도형, 이미지 또는 텍스트와 같은 그래픽 영역을 채우는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-144">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="c2441-145"><xref:System.Drawing.Font>클래스-텍스트를 렌더링할 때 사용할 도형에 대 한 설명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-145">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="c2441-146"><xref:System.Drawing.Color>구조는 표시할 여러 색을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-146">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="c2441-147">만든 그래픽 개체를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="c2441-147">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="c2441-148">위에 나열 된 적절 한 개체를 사용 하 여 필요한 항목을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="c2441-148">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="c2441-149">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2441-149">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="c2441-150">렌더링 하려면</span><span class="sxs-lookup"><span data-stu-id="c2441-150">To render</span></span>|<span data-ttu-id="c2441-151">참조 항목</span><span class="sxs-lookup"><span data-stu-id="c2441-151">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="c2441-152">선</span><span class="sxs-lookup"><span data-stu-id="c2441-152">Lines</span></span>|[<span data-ttu-id="c2441-153">방법: Windows Form에서 선 그리기</span><span class="sxs-lookup"><span data-stu-id="c2441-153">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="c2441-154">도형</span><span class="sxs-lookup"><span data-stu-id="c2441-154">Shapes</span></span>|[<span data-ttu-id="c2441-155">방법: 윤곽선이 있는 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="c2441-155">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="c2441-156">텍스트</span><span class="sxs-lookup"><span data-stu-id="c2441-156">Text</span></span>|[<span data-ttu-id="c2441-157">방법: Windows Form에서 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="c2441-157">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="c2441-158">이미지</span><span class="sxs-lookup"><span data-stu-id="c2441-158">Images</span></span>|[<span data-ttu-id="c2441-159">방법: GDI+를 사용하여 이미지 렌더링</span><span class="sxs-lookup"><span data-stu-id="c2441-159">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="c2441-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2441-160">See also</span></span>

- [<span data-ttu-id="c2441-161">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="c2441-161">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="c2441-162">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="c2441-162">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="c2441-163">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="c2441-163">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="c2441-164">방법: GDI+를 사용하여 이미지 렌더링</span><span class="sxs-lookup"><span data-stu-id="c2441-164">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
