---
title: '방법: Windows Forms에서 컨트롤 배치'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: 22225c97ec082022cb609e47d3cafcdcc052143d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59132797"
---
# <a name="how-to-position-controls-on-windows-forms"></a>방법: Windows Forms에서 컨트롤 배치
컨트롤의 위치, Windows Forms 디자이너를 사용 하거나 지정 된 <xref:System.Windows.Forms.Control.Location%2A> 속성입니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>Windows Forms 디자이너의 디자인 화면에서 컨트롤 위치  
  
-   컨트롤이 마우스를 사용 하 여 적절 한 위치로 끕니다.  
  
    > [!NOTE]
    >  컨트롤을 선택 하 고 화살표를 사용 하 여 키를 보다 정확 하 게 위치를 이동 합니다. 또한 *맞춤선* 정확 하 게 양식의 컨트롤을 배치 하는 데 도움이 됩니다. 자세한 내용은 [연습: Snaplines를 사용 하 여 Forms Windows에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.  
  
### <a name="to-position-a-control-using-the-properties-window"></a>속성 창을 사용 하 여 컨트롤 위치  
  
1.  배치 하려는 컨트롤을 클릭 합니다.  
  
2.  에 **속성** 창에 대 한 형식 값을 <xref:System.Windows.Forms.Control.Location%2A> 속성을 해당 컨테이너 내의 컨트롤을 배치 하는 쉼표로 구분 된 합니다.  
  
     첫 번째 숫자 (X)가; 컨테이너의 왼쪽된 테두리의 거리 두 번째 숫자 (Y)는 픽셀 컨테이너 영역의 위쪽 테두리의 거리입니다.  
  
    > [!NOTE]
    >  확장할 수 있습니다 합니다 <xref:System.Windows.Forms.Control.Location%2A> 속성을 입력 합니다 **X** 및 **Y** 값을 개별적으로 합니다.  
  
### <a name="to-position-a-control-programmatically"></a>컨트롤을 프로그래밍 방식으로 배치 하려면  
  
1.  설정 된 <xref:System.Windows.Forms.Control.Location%2A> 컨트롤의 속성을 <xref:System.Drawing.Point>입니다.  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  컨트롤 위치의 X 좌표를 변경를 사용 하는 <xref:System.Windows.Forms.Control.Left%2A> 하위 속성입니다.  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a>컨트롤의 위치를 프로그래밍 방식으로 증가  
  
1.  설정 된 <xref:System.Windows.Forms.Control.Left%2A> 하위 컨트롤의 X 좌표를 늘립니다.  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  사용 하 여는 <xref:System.Windows.Forms.Control.Location%2A> 설정할 컨트롤의 X 및 Y 속성을 동시에 배치 합니다. 사용 하 여 컨트롤의 위치를 개별적으로 설정 하려면 <xref:System.Windows.Forms.Control.Left%2A> (**X**) 또는 <xref:System.Windows.Forms.Control.Top%2A> (**Y**) 하위 속성입니다. X 및 Y 좌표를 암시적으로 설정 하지 마십시오는 <xref:System.Drawing.Point> 이 구조는 단추의 좌표 복사본을 포함 하기 때문에 단추 위치를 나타내는 구조체입니다.  
  
## <a name="see-also"></a>참고자료

- [Windows Forms 컨트롤](index.md)
- [연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)
- [연습: TableLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)
- [연습: FlowLayoutPanel을 사용하여 Windows Forms에서 컨트롤 정렬](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)
- [Windows Forms에서 컨트롤 정렬](arranging-controls-on-windows-forms.md)
- [개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
- [기능별 Windows Forms 컨트롤](windows-forms-controls-by-function.md)
- [방법: Windows Forms의 화면 위치 설정](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/52aha046(v=vs.100))
