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
ms.openlocfilehash: ee57b0409d7bb7574c965ff098e7f86c8332536d
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505508"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a><span data-ttu-id="f18aa-102">방법: 그리는 데 필요한 그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="f18aa-102">How to: Create Graphics Objects for Drawing</span></span>
<span data-ttu-id="f18aa-103">생성 해야 하는 선과 도형 그리기, 텍스트를 렌더링 하거나 표시 하 고 조작할 수 GDI +를 사용 하 여 이미지, 전에 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-103">Before you can draw lines and shapes, render text, or display and manipulate images with GDI+, you need to create a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="f18aa-104"><xref:System.Drawing.Graphics> 개체 GDI + 그리기 화면을 나타내며는 그래픽 이미지를 만드는 데 사용 되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-104">The <xref:System.Drawing.Graphics> object represents a GDI+ drawing surface, and is the object that is used to create graphical images.</span></span>  
  
 <span data-ttu-id="f18aa-105">그래픽 작업에 두 단계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-105">There are two steps in working with graphics:</span></span>  
  
1. <span data-ttu-id="f18aa-106">만들기는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-106">Creating a <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="f18aa-107">사용 하는 <xref:System.Drawing.Graphics> 선과 도형 그리기, 텍스트를 렌더링 하거나 이미지를 조작 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-107">Using the <xref:System.Drawing.Graphics> object to draw lines and shapes, render text, or display and manipulate images.</span></span>  
  
## <a name="creating-a-graphics-object"></a><span data-ttu-id="f18aa-108">그래픽 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="f18aa-108">Creating a Graphics Object</span></span>  
 <span data-ttu-id="f18aa-109">다양 한 방법에서에서 graphics 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-109">A graphics object can be created in a variety of ways.</span></span>  
  
#### <a name="to-create-a-graphics-object"></a><span data-ttu-id="f18aa-110">그래픽 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f18aa-110">To create a graphics object</span></span>  
  
- <span data-ttu-id="f18aa-111">그래픽 개체에 대 한 참조의 일부로 받은 합니다 <xref:System.Windows.Forms.PaintEventArgs> 에 <xref:System.Windows.Forms.Control.Paint> 양식이 나 컨트롤의 이벤트.</span><span class="sxs-lookup"><span data-stu-id="f18aa-111">Receive a reference to a graphics object as part of the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event of a form or control.</span></span> <span data-ttu-id="f18aa-112">컨트롤에 대 한 그리기 코드를 만들 때 그래픽 개체에 대 한 참조를 가져오는 방법을 일반적으로입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-112">This is usually how you obtain a reference to a graphics object when creating painting code for a control.</span></span> <span data-ttu-id="f18aa-113">마찬가지로 graphics 개체의 속성으로 가져올 수도 있습니다는 <xref:System.Drawing.Printing.PrintPageEventArgs> 처리할 때 합니다 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 에 대 한 이벤트를 <xref:System.Drawing.Printing.PrintDocument>합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-113">Similarly, you can also obtain a graphics object as a property of the <xref:System.Drawing.Printing.PrintPageEventArgs> when handling the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event for a <xref:System.Drawing.Printing.PrintDocument>.</span></span>  
  
     <span data-ttu-id="f18aa-114">또는</span><span class="sxs-lookup"><span data-stu-id="f18aa-114">-or-</span></span>  
  
- <span data-ttu-id="f18aa-115">호출을 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 에 대 한 참조를 가져오려면 폼 또는 컨트롤의 메서드는 <xref:System.Drawing.Graphics> 해당 폼 이나 컨트롤의 그리기 화면을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-115">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span> <span data-ttu-id="f18aa-116">양식이 나 이미 존재 하는 컨트롤을 그릴 하려는 경우이 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-116">Use this method if you want to draw on a form or control that already exists.</span></span>  
  
     <span data-ttu-id="f18aa-117">또는</span><span class="sxs-lookup"><span data-stu-id="f18aa-117">-or-</span></span>  
  
- <span data-ttu-id="f18aa-118">만들기는 <xref:System.Drawing.Graphics> 에서 상속 되는 모든 개체에서에서 만든 <xref:System.Drawing.Image>합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-118">Create a <xref:System.Drawing.Graphics> object from any object that inherits from <xref:System.Drawing.Image>.</span></span> <span data-ttu-id="f18aa-119">이 방법은 기존 이미지를 변경 하려는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-119">This approach is useful when you want to alter an already existing image.</span></span>  
  
     <span data-ttu-id="f18aa-120">다음 섹션에서는 이러한 각 프로세스에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-120">The following sections give details about each of these processes.</span></span>  
  
## <a name="painteventargs-in-the-paint-event-handler"></a><span data-ttu-id="f18aa-121">그리기 이벤트 처리기에서 PaintEventArgs</span><span class="sxs-lookup"><span data-stu-id="f18aa-121">PaintEventArgs in the Paint Event Handler</span></span>  
 <span data-ttu-id="f18aa-122">프로그래밍 하는 경우는 <xref:System.Windows.Forms.PaintEventHandler> 컨트롤에 대 한 또는 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 에 대 한를 <xref:System.Drawing.Printing.PrintDocument>, graphics 개체의 속성 중 하나로 제공 됩니다 <xref:System.Windows.Forms.PaintEventArgs> 또는 <xref:System.Drawing.Printing.PrintPageEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-122">When programming the <xref:System.Windows.Forms.PaintEventHandler> for controls or the <xref:System.Drawing.Printing.PrintDocument.PrintPage> for a <xref:System.Drawing.Printing.PrintDocument>, a graphics object is provided as one of the properties of <xref:System.Windows.Forms.PaintEventArgs> or <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a><span data-ttu-id="f18aa-123">Paint 이벤트에 PaintEventArgs에서 Graphics 개체에 대 한 참조를 가져오려면</span><span class="sxs-lookup"><span data-stu-id="f18aa-123">To obtain a reference to a Graphics object from the PaintEventArgs in the Paint event</span></span>  
  
1. <span data-ttu-id="f18aa-124">선언 된 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-124">Declare the <xref:System.Drawing.Graphics> object.</span></span>  
  
2. <span data-ttu-id="f18aa-125">변수 참조를 할당 합니다 <xref:System.Drawing.Graphics> 개체의 일부로 전달 되는 <xref:System.Windows.Forms.PaintEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-125">Assign the variable to refer to the <xref:System.Drawing.Graphics> object passed as part of the <xref:System.Windows.Forms.PaintEventArgs>.</span></span>  
  
3. <span data-ttu-id="f18aa-126">폼 이나 컨트롤을 그리는 코드를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-126">Insert code to paint the form or control.</span></span>  
  
     <span data-ttu-id="f18aa-127">다음 예제에서는 참조 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics> 에서 개체를 <xref:System.Windows.Forms.PaintEventArgs> 에 <xref:System.Windows.Forms.Control.Paint> 이벤트:</span><span class="sxs-lookup"><span data-stu-id="f18aa-127">The following example shows how to reference a <xref:System.Drawing.Graphics> object from the <xref:System.Windows.Forms.PaintEventArgs> in the <xref:System.Windows.Forms.Control.Paint> event:</span></span>  
  
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
  
## <a name="creategraphics-method"></a><span data-ttu-id="f18aa-128">CreateGraphics 메서드</span><span class="sxs-lookup"><span data-stu-id="f18aa-128">CreateGraphics Method</span></span>  
 <span data-ttu-id="f18aa-129">사용할 수도 있습니다는 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 에 대 한 참조를 가져오려면 폼 또는 컨트롤의 메서드는 <xref:System.Drawing.Graphics> 해당 폼 이나 컨트롤의 그리기 화면을 나타내는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-129">You can also use the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of a control or form to obtain a reference to a <xref:System.Drawing.Graphics> object that represents the drawing surface of that control or form.</span></span>  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a><span data-ttu-id="f18aa-130">CreateGraphics 메서드를 사용 하 여 그래픽 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f18aa-130">To create a Graphics object with the CreateGraphics method</span></span>  
  
- <span data-ttu-id="f18aa-131">호출 된 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 기반이 그래픽을 렌더링 하려는 폼 이나 컨트롤의 메서드.</span><span class="sxs-lookup"><span data-stu-id="f18aa-131">Call the <xref:System.Windows.Forms.Control.CreateGraphics%2A> method of the form or control upon which you want to render graphics.</span></span>  
  
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
  
## <a name="create-from-an-image-object"></a><span data-ttu-id="f18aa-132">이미지 개체에서 만들기</span><span class="sxs-lookup"><span data-stu-id="f18aa-132">Create from an Image Object</span></span>  
 <span data-ttu-id="f18aa-133">또한에서 파생 된 모든 개체에서 graphics 개체를 만들 수 있습니다는 <xref:System.Drawing.Image> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-133">Additionally, you can create a graphics object from any object that derives from the <xref:System.Drawing.Image> class.</span></span>  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a><span data-ttu-id="f18aa-134">이미지에서 Graphics 개체를 만들려면</span><span class="sxs-lookup"><span data-stu-id="f18aa-134">To create a Graphics object from an Image</span></span>  
  
- <span data-ttu-id="f18aa-135">호출 된 <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> 를 만들려는 이미지 변수의 이름을 제공 하는 메서드는 <xref:System.Drawing.Graphics> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-135">Call the <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> method, supplying the name of the Image variable from which you want to create a <xref:System.Drawing.Graphics> object.</span></span>  
  
     <span data-ttu-id="f18aa-136">다음 예제에서는 사용 하는 방법을 보여 줍니다는 <xref:System.Drawing.Bitmap> 개체:</span><span class="sxs-lookup"><span data-stu-id="f18aa-136">The following example shows how to use a <xref:System.Drawing.Bitmap> object:</span></span>  
  
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
>  <span data-ttu-id="f18aa-137">만들 수 있습니다 <xref:System.Drawing.Graphics> 인덱싱되지 않은.bmp 파일을 16 비트, 24 비트 및 32 비트.bmp 파일 등의 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-137">You can only create <xref:System.Drawing.Graphics> objects from nonindexed .bmp files, such as 16-bit, 24-bit, and 32-bit .bmp files.</span></span> <span data-ttu-id="f18aa-138">인덱싱되지 않은.bmp 파일의 각 픽셀 색 테이블에 인덱스를 저장 하는 인덱싱된.bmp 파일의 픽셀 달리 색을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-138">Each pixel of nonindexed .bmp files holds a color, in contrast to pixels of indexed .bmp files, which hold an index to a color table.</span></span>  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a><span data-ttu-id="f18aa-139">그리기 및 도형 및 이미지 조작</span><span class="sxs-lookup"><span data-stu-id="f18aa-139">Drawing and Manipulating Shapes and Images</span></span>  
 <span data-ttu-id="f18aa-140">를 만든 후를 <xref:System.Drawing.Graphics> 개체를 사용 하 여 선과 도형 그리기, 텍스트를 렌더링 하거나 표시 하 고 이미지를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-140">After it is created, a <xref:System.Drawing.Graphics> object may be used to draw lines and shapes, render text, or display and manipulate images.</span></span> <span data-ttu-id="f18aa-141">사용 되는 보안 주체 개체는 <xref:System.Drawing.Graphics> 개체:</span><span class="sxs-lookup"><span data-stu-id="f18aa-141">The principal objects that are used with the <xref:System.Drawing.Graphics> object are:</span></span>  
  
- <span data-ttu-id="f18aa-142"><xref:System.Drawing.Pen> 클래스-선 그리기, 도형의 윤곽을 또는 기타 기하학적 표현을 렌더링에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-142">The <xref:System.Drawing.Pen> class—Used for drawing lines, outlining shapes, or rendering other geometric representations.</span></span>  
  
- <span data-ttu-id="f18aa-143"><xref:System.Drawing.Brush> 클래스-을 그래픽 채워진된 도형, 이미지, 텍스트 등의 영역을 채우는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-143">The <xref:System.Drawing.Brush> class—Used for filling areas of graphics, such as filled shapes, images, or text.</span></span>  
  
- <span data-ttu-id="f18aa-144"><xref:System.Drawing.Font> 클래스-텍스트를 렌더링할 때 사용할 도형에 대 한 설명을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-144">The <xref:System.Drawing.Font> class—Provides a description of what shapes to use when rendering text.</span></span>  
  
- <span data-ttu-id="f18aa-145"><xref:System.Drawing.Color> 구조-표시할 다른 색을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-145">The <xref:System.Drawing.Color> structure—Represents the different colors to display.</span></span>  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a><span data-ttu-id="f18aa-146">사용자가 만든 그래픽 개체를 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="f18aa-146">To use the Graphics object you have created</span></span>  
  
- <span data-ttu-id="f18aa-147">필요한 것 그리기 위에 나열 된 적절 한 개체를 사용 하 여 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-147">Work with the appropriate object listed above to draw what you need.</span></span>  
  
     <span data-ttu-id="f18aa-148">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f18aa-148">For more information, see the following topics:</span></span>  
  
    |<span data-ttu-id="f18aa-149">렌더링</span><span class="sxs-lookup"><span data-stu-id="f18aa-149">To render</span></span>|<span data-ttu-id="f18aa-150">참조</span><span class="sxs-lookup"><span data-stu-id="f18aa-150">See</span></span>|  
    |---------------|---------|  
    |<span data-ttu-id="f18aa-151">선</span><span class="sxs-lookup"><span data-stu-id="f18aa-151">Lines</span></span>|[<span data-ttu-id="f18aa-152">방법: Windows Form에 선 그리기</span><span class="sxs-lookup"><span data-stu-id="f18aa-152">How to: Draw a Line on a Windows Form</span></span>](how-to-draw-a-line-on-a-windows-form.md)|  
    |<span data-ttu-id="f18aa-153">도형</span><span class="sxs-lookup"><span data-stu-id="f18aa-153">Shapes</span></span>|[<span data-ttu-id="f18aa-154">방법: 윤곽선이 있는 도형 그리기</span><span class="sxs-lookup"><span data-stu-id="f18aa-154">How to: Draw an Outlined Shape</span></span>](how-to-draw-an-outlined-shape.md)|  
    |<span data-ttu-id="f18aa-155">텍스트</span><span class="sxs-lookup"><span data-stu-id="f18aa-155">Text</span></span>|[<span data-ttu-id="f18aa-156">방법: Windows Form에 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="f18aa-156">How to: Draw Text on a Windows Form</span></span>](how-to-draw-text-on-a-windows-form.md)|  
    |<span data-ttu-id="f18aa-157">이미지</span><span class="sxs-lookup"><span data-stu-id="f18aa-157">Images</span></span>|[<span data-ttu-id="f18aa-158">방법: GDI +를 사용 하 여 이미지를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-158">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a><span data-ttu-id="f18aa-159">참고자료</span><span class="sxs-lookup"><span data-stu-id="f18aa-159">See also</span></span>

- [<span data-ttu-id="f18aa-160">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="f18aa-160">Getting Started with Graphics Programming</span></span>](getting-started-with-graphics-programming.md)
- [<span data-ttu-id="f18aa-161">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="f18aa-161">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="f18aa-162">선, 곡선 및 도형</span><span class="sxs-lookup"><span data-stu-id="f18aa-162">Lines, Curves, and Shapes</span></span>](lines-curves-and-shapes.md)
- [<span data-ttu-id="f18aa-163">방법: GDI +를 사용 하 여 이미지를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="f18aa-163">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
