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
ms.openlocfilehash: 79eae4d37c056fc95ac73c78e00dd1a2b68bcd24
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937685"
---
# <a name="how-to-create-graphics-objects-for-drawing"></a>방법: 그리는 데 필요한 그래픽 개체 만들기
선과 셰이프를 그릴 수 있습니다, 전에 텍스트를 렌더링 되거나 표시 및 사용 하 여 이미지 조작 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]을 만들어야을 <xref:System.Drawing.Graphics> 개체입니다. 합니다 <xref:System.Drawing.Graphics> 개체가 나타내는 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 그리기 화면, 및는 그래픽 이미지를 만드는 데 사용 되는 개체입니다.  
  
 그래픽 작업에 두 단계가 있습니다.  
  
1. 만들기는 <xref:System.Drawing.Graphics> 개체입니다.  
  
2. 사용 하는 <xref:System.Drawing.Graphics> 선과 도형 그리기, 텍스트를 렌더링 하거나 이미지를 조작 하는 개체입니다.  
  
## <a name="creating-a-graphics-object"></a>그래픽 개체 만들기  
 다양 한 방법에서에서 graphics 개체를 만들 수 있습니다.  
  
#### <a name="to-create-a-graphics-object"></a>그래픽 개체를 만들려면  
  
- 그래픽 개체에 대 한 참조의 일부로 받은 합니다 <xref:System.Windows.Forms.PaintEventArgs> 에 <xref:System.Windows.Forms.Control.Paint> 양식이 나 컨트롤의 이벤트. 컨트롤에 대 한 그리기 코드를 만들 때 그래픽 개체에 대 한 참조를 가져오는 방법을 일반적으로입니다. 마찬가지로 graphics 개체의 속성으로 가져올 수도 있습니다는 <xref:System.Drawing.Printing.PrintPageEventArgs> 처리할 때 합니다 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 에 대 한 이벤트를 <xref:System.Drawing.Printing.PrintDocument>합니다.  
  
     또는  
  
- 호출을 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 에 대 한 참조를 가져오려면 폼 또는 컨트롤의 메서드는 <xref:System.Drawing.Graphics> 해당 폼 이나 컨트롤의 그리기 화면을 나타내는 개체입니다. 양식이 나 이미 존재 하는 컨트롤을 그릴 하려는 경우이 메서드를 사용 합니다.  
  
     또는  
  
- 만들기는 <xref:System.Drawing.Graphics> 에서 상속 되는 모든 개체에서에서 만든 <xref:System.Drawing.Image>합니다. 이 방법은 기존 이미지를 변경 하려는 경우에 유용 합니다.  
  
     다음 섹션에서는 이러한 각 프로세스에 대 한 세부 정보를 제공 합니다.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>그리기 이벤트 처리기에서 PaintEventArgs  
 프로그래밍 하는 경우는 <xref:System.Windows.Forms.PaintEventHandler> 컨트롤에 대 한 또는 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 에 대 한를 <xref:System.Drawing.Printing.PrintDocument>, graphics 개체의 속성 중 하나로 제공 됩니다 <xref:System.Windows.Forms.PaintEventArgs> 또는 <xref:System.Drawing.Printing.PrintPageEventArgs>합니다.  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>Paint 이벤트에 PaintEventArgs에서 Graphics 개체에 대 한 참조를 가져오려면  
  
1. 선언 된 <xref:System.Drawing.Graphics> 개체입니다.  
  
2. 변수 참조를 할당 합니다 <xref:System.Drawing.Graphics> 개체의 일부로 전달 되는 <xref:System.Windows.Forms.PaintEventArgs>합니다.  
  
3. 폼 이나 컨트롤을 그리는 코드를 삽입 합니다.  
  
     다음 예제에서는 참조 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics> 에서 개체를 <xref:System.Windows.Forms.PaintEventArgs> 에 <xref:System.Windows.Forms.Control.Paint> 이벤트:  
  
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
  
## <a name="creategraphics-method"></a>CreateGraphics 메서드  
 사용할 수도 있습니다는 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 에 대 한 참조를 가져오려면 폼 또는 컨트롤의 메서드는 <xref:System.Drawing.Graphics> 해당 폼 이나 컨트롤의 그리기 화면을 나타내는 개체입니다.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>CreateGraphics 메서드를 사용 하 여 그래픽 개체를 만들려면  
  
- 호출 된 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 기반이 그래픽을 렌더링 하려는 폼 이나 컨트롤의 메서드.  
  
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
  
## <a name="create-from-an-image-object"></a>이미지 개체에서 만들기  
 또한에서 파생 된 모든 개체에서 graphics 개체를 만들 수 있습니다는 <xref:System.Drawing.Image> 클래스입니다.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>이미지에서 Graphics 개체를 만들려면  
  
- 호출 된 <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> 를 만들려는 이미지 변수의 이름을 제공 하는 메서드는 <xref:System.Drawing.Graphics> 개체입니다.  
  
     다음 예제에서는 사용 하는 방법을 보여 줍니다는 <xref:System.Drawing.Bitmap> 개체:  
  
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
>  만들 수 있습니다 <xref:System.Drawing.Graphics> 인덱싱되지 않은.bmp 파일을 16 비트, 24 비트 및 32 비트.bmp 파일 등의 개체입니다. 인덱싱되지 않은.bmp 파일의 각 픽셀 색 테이블에 인덱스를 저장 하는 인덱싱된.bmp 파일의 픽셀 달리 색을 보유 합니다.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>그리기 및 도형 및 이미지 조작  
 를 만든 후를 <xref:System.Drawing.Graphics> 개체를 사용 하 여 선과 도형 그리기, 텍스트를 렌더링 하거나 표시 하 고 이미지를 조작할 수 있습니다. 사용 되는 보안 주체 개체는 <xref:System.Drawing.Graphics> 개체:  
  
- <xref:System.Drawing.Pen> 클래스-선 그리기, 도형의 윤곽을 또는 기타 기하학적 표현을 렌더링에 사용 합니다.  
  
- <xref:System.Drawing.Brush> 클래스-을 그래픽 채워진된 도형, 이미지, 텍스트 등의 영역을 채우는 데 사용 합니다.  
  
- <xref:System.Drawing.Font> 클래스-텍스트를 렌더링할 때 사용할 도형에 대 한 설명을 제공 합니다.  
  
- <xref:System.Drawing.Color> 구조-표시할 다른 색을 나타냅니다.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>사용자가 만든 그래픽 개체를 사용 하려면  
  
- 필요한 것 그리기 위에 나열 된 적절 한 개체를 사용 하 여 작동 합니다.  
  
     자세한 내용은 다음 항목을 참조하세요.  
  
    |렌더링|참조|  
    |---------------|---------|  
    |선|[방법: Windows Form에 선 그리기](how-to-draw-a-line-on-a-windows-form.md)|  
    |도형|[방법: 윤곽선이 있는 도형 그리기](how-to-draw-an-outlined-shape.md)|  
    |텍스트|[방법: Windows Form에 텍스트 그리기](how-to-draw-text-on-a-windows-form.md)|  
    |이미지|[방법: GDI +를 사용 하 여 이미지를 렌더링 합니다.](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>참고자료

- [그래픽 프로그래밍 시작](getting-started-with-graphics-programming.md)
- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
- [선, 곡선 및 도형](lines-curves-and-shapes.md)
- [방법: GDI +를 사용 하 여 이미지를 렌더링 합니다.](how-to-render-images-with-gdi.md)
