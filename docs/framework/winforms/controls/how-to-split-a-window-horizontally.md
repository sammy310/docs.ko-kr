---
title: '방법: 가로로 창 분합니다'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], horizontal splitter
- splitter windows [Windows Forms], changing splitter orientation
- splitter windows [Windows Forms], horizontal
- windows [Windows Forms], splitting horizontally
ms.assetid: a1f74f29-048c-4723-85fa-b9d375ab8f4b
ms.openlocfilehash: e11e1d6730c6c8c9c0a1ac170aeb5393bf3153b7
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708043"
---
# <a name="how-to-split-a-window-horizontally"></a>방법: 가로로 창 분합니다
다음 코드 예제에서는 분할 하는 분할자는 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 가로로 합니다.  
  
> [!NOTE]
>  합니다 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 의 속성을 <xref:System.Windows.Forms.SplitContainer> 컨트롤 컨트롤 자체가 아닌 분할자의 방향을 결정 합니다.  
  
### <a name="to-split-a-window-horizontally"></a>가로로 창 분할 하려면  
  
1.  프로시저 내에서 설정 합니다 <xref:System.Windows.Forms.SplitContainer.Orientation%2A> 의 속성을 <xref:System.Windows.Forms.SplitContainer> 컨트롤을 <xref:System.Windows.Forms.Orientation.Horizontal>.  
  
    ```vb  
    Sub ShowSplitContainer()  
        Dim splitContainer1 as new SplitContainer()  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D  
        splitContainer1.Location = New System.Drawing.Point(74, 20)  
        splitContainer1.Name = "DemoSplitContainer"  
        splitContainer1.Size = New System.Drawing.Size(212, 435)  
        splitContainer1.TabIndex = 0  
        splitContainer1.Orientation = Orientation.Horizontal  
        Controls.Add(splitContainer1)  
    End Sub  
    ```  
  
    ```csharp  
    public void showSplitContainer()  
    {  
        SplitContainer splitContainer1 = new SplitContainer ();  
        splitContainer1.BorderStyle = BorderStyle.Fixed3D;  
        splitContainer1.Location = new System.Drawing.Point (74, 20);  
        splitContainer1.Name = "DemoSplitContainer";  
        splitContainer1.Size = new System.Drawing.Size (212, 435);  
        splitContainer1.TabIndex = 0;  
        splitContainer1.Orientation = Orientation.Horizontal;  
        this.Controls.Add (splitContainer1);  
  
    }  
    ```  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Forms.SplitContainer>
- [SplitContainer 컨트롤](splitcontainer-control-windows-forms.md)
