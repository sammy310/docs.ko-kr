---
title: '방법: 컨트롤에 대한 도구 상자 비트맵 제공'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
ms.openlocfilehash: 7c26e00acd4278ced53ad29c748ac076e0215a23
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337710"
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a>방법: 컨트롤에 대한 도구 상자 비트맵 제공
컨트롤에 대 한 특수 아이콘에 표시 하려는 경우는 **도구 상자**를 사용 하 여 특정 이미지를 지정할 수 있습니다는 <xref:System.Drawing.ToolboxBitmapAttribute>합니다. 이 클래스는 *특성*이라는 다른 클래스에 연결할 수 있는 특수한 유형의 클래스입니다. 특성에 대 한 자세한 내용은 참조 하세요. [특성 개요 (Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md) Visual basic 또는 [특성 (C#)](../../../csharp/programming-guide/concepts/attributes/index.md) C#에 대 한 합니다.  
  
 사용 하는 <xref:System.Drawing.ToolboxBitmapAttribute>, 16x16 픽셀 비트맵에 대 한 경로 파일 이름을 나타내는 문자열을 지정할 수 있습니다. 그런 다음 이 비트맵은 **도구 상자**에 추가될 때 컨트롤 옆에 표시됩니다. 지정할 수도 있습니다는 <xref:System.Type>를 해당 형식과 연결 된 비트맵 로드 되는 경우. 둘 다 지정 하는 경우는 <xref:System.Type> 문자열 매개 변수에서 지정한 형식을 포함 하는 어셈블리에서 지정한 이름을 가진 이미지 리소스에 대 한 문자열을 컨트롤 검색을 <xref:System.Type> 매개 변수입니다.  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a>컨트롤의 도구 상자 비트맵을 지정하려면  
  
1. 추가 합니다 <xref:System.Drawing.ToolboxBitmapAttribute> 하기 전에 컨트롤의 클래스 선언에는 `Class` visual basic 및 Visual C#에 대 한 클래스 선언 위에 키워드입니다.  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2. 프로젝트를 다시 빌드합니다.  
  
    > [!NOTE]
    >  비트맵은 자동으로 생성된 컨트롤 및 구성 요소의 도구 상자에 나타나지 않습니다. 비트맵을 보려면 **도구 상자 항목 선택** 대화 상자를 사용하여 컨트롤을 다시 로드합니다. 자세한 내용은 [연습: 사용자 지정 구성 요소를 사용 하 여 도구 상자에 자동으로 채우기](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Drawing.ToolboxBitmapAttribute>
- [연습: 사용자 지정 구성 요소로 도구 상자 자동 채우기](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
- [디자인 타임에 Windows Forms 컨트롤 개발](developing-windows-forms-controls-at-design-time.md)
- [특성 개요(Visual Basic)](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [특성(C#)](../../../csharp/programming-guide/concepts/attributes/index.md)
