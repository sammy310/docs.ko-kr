---
title: '방법: GDI+를 사용하여 이미지 렌더링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- images [Windows Forms], creating
- GDI+, rendering existing images
ms.assetid: c128b79a-3e31-47d8-9e66-3470f570a056
ms.openlocfilehash: fffe1f1052d7323d234985b7e752866f2e89657d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182511"
---
# <a name="how-to-render-images-with-gdi"></a>방법: GDI+를 사용하여 이미지 렌더링
GDI+를 사용하여 응용 프로그램에 있는 파일로 존재하는 이미지를 렌더링할 수 있습니다. 이 작업을 수행하려면 <xref:System.Drawing.Image> 클래스의 새 개체(예:)를 <xref:System.Drawing.Bitmap>만들고, 사용할 드로잉 서피스를 참조하는 <xref:System.Drawing.Graphics> 객체를 만들고, <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics> 객체의 메서드를 호출합니다. 이미지는 그래픽 클래스에서 표시하는 그리기 화면에 그려집니다. 이미지 편집기를 사용하여 디자인 타임에 이미지 파일을 만들고 편집하고 런타임에 GDI+로 렌더링할 수 있습니다. 자세한 내용은 [아이콘에 대한 이미지 편집기](/cpp/windows/image-editor-for-icons)를 참조하세요.  
  
### <a name="to-render-an-image-with-gdi"></a>GDI+를 사용하여 이미지를 렌더링하려면  
  
1. 표시하려는 이미지를 나타내는 개체를 만듭니다. 이 개체는 <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> 또는 <xref:System.Drawing.Imaging.Metafile>와 같은 에서 상속되는 클래스의 멤버여야 합니다. 예제를 다음과 같이 보여 줍니다.  
  
    ```vb  
    ' Uses the System.Environment.GetFolderPath to get the path to the
    ' current user's MyPictures folder.  
    Dim myBitmap as New Bitmap _  
       (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.MyPictures))  
    ```  
  
    ```csharp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap myBitmap = new Bitmap  
       (System.Environment.GetFolderPath  
          (System.Environment.SpecialFolder.MyPictures));  
    ```  
  
    ```cpp  
    // Uses the System.Environment.GetFolderPath to get the path to the
    // current user's MyPictures folder.  
    Bitmap^ myBitmap = gcnew Bitmap  
       (System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::MyPictures));  
    ```  
  
2. 사용할 <xref:System.Drawing.Graphics> 드로잉 서피스를 나타내는 객체를 작성합니다. 자세한 내용은 [방법: 그리는 데 필요한 그래픽 개체 만들기](how-to-create-graphics-objects-for-drawing.md)를 참조하세요.  
  
    ```vb  
    ' Creates a Graphics object that represents the drawing surface of
    ' Button1.  
    Dim g as Graphics = Button1.CreateGraphics  
    ```  
  
    ```csharp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics g = Button1.CreateGraphics();  
    ```  
  
    ```cpp  
    // Creates a Graphics object that represents the drawing surface of
    // Button1.  
    Graphics^ g = button1->CreateGraphics();  
    ```  
  
3. 그래픽 <xref:System.Drawing.Graphics.DrawImage%2A> 개체를 호출하여 이미지를 렌더링합니다. 가져올 이미지 및 이미지를 가져올 좌표를 지정해야 합니다.  
  
    ```vb  
    g.DrawImage(myBitmap, 1, 1)  
    ```  
  
    ```csharp  
    g.DrawImage(myBitmap, 1, 1);  
    ```  
  
    ```cpp  
    g->DrawImage(myBitmap, 1, 1);  
    ```  
  
## <a name="see-also"></a>참고 항목

- [그래픽 프로그래밍 시작](getting-started-with-graphics-programming.md)
- [방법: 그리는 데 필요한 그래픽 개체 만들기](how-to-create-graphics-objects-for-drawing.md)
- [GDI+의 펜, 선 및 사각형](pens-lines-and-rectangles-in-gdi.md)
- [방법: Windows Form에 텍스트 그리기](how-to-draw-text-on-a-windows-form.md)
- [Windows Forms의 그래픽 및 그리기](graphics-and-drawing-in-windows-forms.md)
- [선 또는 닫힌 그림 그리기](/cpp/windows/drawing-lines-or-closed-figures-image-editor-for-icons)
- [아이콘에 대한 이미지 편집기](/cpp/windows/image-editor-for-icons)
