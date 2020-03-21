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
# <a name="how-to-create-graphics-objects-for-drawing"></a>방법: 그리는 데 필요한 그래픽 개체 만들기
GDI+로 선과 모양을 그리거나 텍스트를 렌더링하거나 이미지를 표시및 조작하려면 오브젝트를 <xref:System.Drawing.Graphics> 만들어야 합니다. 오브젝트는 <xref:System.Drawing.Graphics> GDI+ 드로잉 표면을 나타내며 그래픽 이미지를 만드는 데 사용되는 오브젝트입니다.  
  
 그래픽 작업에는 두 단계가 있습니다.  
  
1. <xref:System.Drawing.Graphics> 개체 만들기  
  
2. 오브젝트를 <xref:System.Drawing.Graphics> 사용하여 선과 모양을 그리거나, 텍스트를 렌더링하거나, 이미지를 표시하고 조작합니다.  
  
## <a name="creating-a-graphics-object"></a>그래픽 개체 만들기  
 그래픽 개체는 다양한 방법으로 만들 수 있습니다.  
  
#### <a name="to-create-a-graphics-object"></a>그래픽 개체를 만들려면  
  
- 폼 또는 컨트롤의 경우 그래픽 <xref:System.Windows.Forms.PaintEventArgs> 개체에 <xref:System.Windows.Forms.Control.Paint> 대한 참조를 받습니다. 일반적으로 컨트롤에 대한 페인팅 코드를 만들 때 그래픽 개체에 대한 참조를 얻는 방법입니다. 마찬가지로 <xref:System.Drawing.Printing.PrintPageEventArgs> <xref:System.Drawing.Printing.PrintDocument>에 대한 이벤트를 처리할 때의 속성으로 그래픽 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 개체를 가져올 수도 있습니다.  
  
     또는  
  
- 컨트롤 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 또는 폼의 메서드를 호출하여 해당 <xref:System.Drawing.Graphics> 컨트롤 또는 폼의 드로잉 표면을 나타내는 개체에 대한 참조를 얻습니다. 이미 존재하는 폼이나 컨트롤을 그리려면 이 메서드를 사용합니다.  
  
     또는  
  
- 에서 <xref:System.Drawing.Graphics> 상속하는 모든 개체에서 <xref:System.Drawing.Image>개체를 만듭니다. 이 방법은 기존 이미지를 변경하려는 경우에 유용합니다.  
  
     다음 섹션에서는 이러한 각 프로세스에 대해 자세히 설명합니다.  
  
## <a name="painteventargs-in-the-paint-event-handler"></a>페인트 이벤트 처리기의 페인트EventArgs  
 <xref:System.Windows.Forms.PaintEventHandler> 에 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 대한 컨트롤 또는 <xref:System.Drawing.Printing.PrintDocument>에 대한 프로그래밍 할 때 그래픽 개체는 <xref:System.Windows.Forms.PaintEventArgs> 또는 의 <xref:System.Drawing.Printing.PrintPageEventArgs>속성 중 하나로 제공됩니다.  
  
#### <a name="to-obtain-a-reference-to-a-graphics-object-from-the-painteventargs-in-the-paint-event"></a>페인트 이벤트의 PaintEventArgs에서 그래픽 개체에 대한 참조를 얻으려면  
  
1. 개체를 <xref:System.Drawing.Graphics> 선언합니다.  
  
2. 의 일부로 전달된 <xref:System.Drawing.Graphics> 객체를 참조할 변수를 할당합니다. <xref:System.Windows.Forms.PaintEventArgs>  
  
3. 코드를 삽입하여 폼 또는 컨트롤을 페인칠합니다.  
  
     다음 예제에서는 <xref:System.Drawing.Graphics> <xref:System.Windows.Forms.PaintEventArgs> 이벤트에서 개체를 참조하는 <xref:System.Windows.Forms.Control.Paint> 방법을 보여 주며 있습니다.  
  
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
  
## <a name="creategraphics-method"></a>그래픽 만들기 방법  
 컨트롤 또는 양식의 메서드를 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 사용하여 해당 컨트롤 또는 <xref:System.Drawing.Graphics> 양식의 드로잉 서피스를 나타내는 객체에 대한 참조를 얻을 수도 있습니다.  
  
#### <a name="to-create-a-graphics-object-with-the-creategraphics-method"></a>CreateGraphics 메서드를 사용하여 그래픽 개체를 만들려면  
  
- 그래픽을 <xref:System.Windows.Forms.Control.CreateGraphics%2A> 렌더링할 폼 또는 컨트롤의 메서드를 호출합니다.  
  
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
 또한 클래스에서 파생 된 모든 개체에서 그래픽 <xref:System.Drawing.Image> 개체를 만들 수 있습니다.  
  
#### <a name="to-create-a-graphics-object-from-an-image"></a>이미지에서 그래픽 개체를 만들려면  
  
- <xref:System.Drawing.Graphics> 메서드를 <xref:System.Drawing.Graphics.FromImage%2A?displayProperty=nameWithType> 호출하여 개체를 만들 려는 Image 변수의 이름을 제공 합니다.  
  
     다음 예제에서는 개체를 <xref:System.Drawing.Bitmap> 사용하는 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주며 다음과 같은 방법을 보여 주실 수 있습니다.  
  
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
> 16비트, <xref:System.Drawing.Graphics> 24비트 및 32비트 .bmp 파일과 같이 인덱싱되지 않은 .bmp 파일에서만 개체를 만들 수 있습니다. 인덱싱되지 않은 .bmp 파일의 각 픽셀에는 색이 있는 .bmp 파일의 픽셀과 달리 색테이블에 인덱스가 있는 .bmp 파일이 있습니다.  
  
## <a name="drawing-and-manipulating-shapes-and-images"></a>셰이프 및 이미지 그리기 및 조작  
 생성된 후에는 오브젝트를 <xref:System.Drawing.Graphics> 사용하여 선과 모양을 그리거나 텍스트를 렌더링하거나 이미지를 표시하고 조작할 수 있습니다. <xref:System.Drawing.Graphics> 개체와 함께 사용되는 주 개체는 다음과 같습니다.  
  
- <xref:System.Drawing.Pen> 클래스-선을 그리거나, 셰이프를 윤곽을 그리거나, 다른 기하학적 표현을 렌더링하는 데 사용됩니다.  
  
- <xref:System.Drawing.Brush> 클래스- 채워진 셰이프, 이미지 또는 텍스트와 같은 그래픽 영역을 채우는 데 사용됩니다.  
  
- <xref:System.Drawing.Font> 클래스-텍스트를 렌더링할 때 사용할 셰이프에 대한 설명을 제공합니다.  
  
- <xref:System.Drawing.Color> 구조-표시할 다른 색상을 나타냅니다.  
  
#### <a name="to-use-the-graphics-object-you-have-created"></a>만든 그래픽 개체를 사용하려면  
  
- 위에 나열된 적절한 개체로 작업하여 필요한 것을 그립니다.  
  
     자세한 내용은 아래 항목을 참조하세요.  
  
    |렌더링하려면|참조 항목|  
    |---------------|---------|  
    |선|[방법: Windows Form에 선 그리기](how-to-draw-a-line-on-a-windows-form.md)|  
    |셰이프|[방법: 윤곽선이 있는 도형 그리기](how-to-draw-an-outlined-shape.md)|  
    |텍스트|[방법: Windows Form에 텍스트 그리기](how-to-draw-text-on-a-windows-form.md)|  
    |이미지|[방법: GDI+를 사용하여 이미지 렌더링](how-to-render-images-with-gdi.md)|  
  
## <a name="see-also"></a>참고 항목

- [그래픽 프로그래밍 시작](getting-started-with-graphics-programming.md)
- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
- [선, 곡선 및 도형](lines-curves-and-shapes.md)
- [방법: GDI+를 사용하여 이미지 렌더링](how-to-render-images-with-gdi.md)
