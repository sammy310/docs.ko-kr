---
title: '방법: 상태 표시줄 패널의 크기 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- StatusBar control [Windows Forms], panel size
- status bars [Windows Forms], setting panel size
- panels [Windows Forms], setting size in status bars
ms.assetid: a01bee43-d9eb-4954-84e6-45a93532d08d
ms.openlocfilehash: efd3074aaf018e7226c484061cbacb2eac0be820
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311905"
---
# <a name="how-to-set-the-size-of-status-bar-panels"></a>방법: 상태 표시줄 패널의 크기 설정
> [!NOTE]
>  <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤은 <xref:System.Windows.Forms.StatusBar> 컨트롤을 대체하고 여기에 다른 기능을 추가하여 새로 도입된 컨트롤이지만 이전 버전과의 호환성 및 이후 사용 가능성을 고려하여 <xref:System.Windows.Forms.StatusBar> 컨트롤을 계속 유지하도록 선택할 수 있습니다.  
  
 각 인스턴스는 <xref:System.Windows.Forms.StatusBarPanel> 내에서 클래스를 [StatusBar 컨트롤](statusbar-control-windows-forms.md) 컨트롤에 다양 한 너비를 결정 하 고 런타임에 동작을 조정 하는 동적 속성입니다.  
  
### <a name="to-set-the-size-of-a-panel"></a>패널의 크기를 설정 하려면  
  
1. 프로시저를 설정 합니다 <xref:System.Windows.Forms.StatusBarPanel.AutoSize%2A>, <xref:System.Windows.Forms.StatusBarPanel.MinWidth%2A>, 및 <xref:System.Windows.Forms.StatusBarPanel.Width%2A> 속성 (또는 하위 집합 여기) 상태 표시줄에 대 한 인덱스를 사용 하 여 패널을 통해 전달를 <xref:System.Windows.Forms.StatusBar.Panels%2A> 속성은 <xref:System.Windows.Forms.StatusBarPanel> 컬렉션.  
  
    ```vb  
    Public Sub SetStatusBarPanelSize()  
    ' Create panel and set text property.  
       StatusBar1.Panels.Add("One")  
    ' Set properties of panels.  
       StatusBar1.Panels(0).AutoSize = StatusBarPanelAutoSize.Spring  
       StatusBar1.Panels(0).Width = 200  
    ' Enable the StatusBar control to display panels.  
       StatusBar1.ShowPanels = True  
        End Sub  
    ```  
  
    ```csharp  
    public void SetStatusBarPanelSize()  
    {  
       // Create panel and set text property.  
       statusBar1.Panels.Add("One");  
       // Set properties of panels.  
       statusBar1.Panels[0].AutoSize = StatusBarPanelAutoSize.Spring;  
       statusBar1.Panels[0].Width = 200;  
       statusBar1.ShowPanels = true;  
    }  
    ```  
  
    ```cpp  
    public:  
       void SetStatusBarPanelSize()  
       {  
          // Create panel and set text property.  
          statusBar1->Panels->Add("One");  
          // Set properties of panels.  
          statusBar1->Panels[0]->AutoSize =  
             StatusBarPanelAutoSize::Spring;  
          statusBar1->Panels[0]->Width = 200;  
          statusBar1->ShowPanels = true;  
       }  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [연습: 런타임에 상태 표시줄 정보 업데이트](walkthrough-updating-status-bar-information-at-run-time.md)
- [방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인](determine-which-panel-wf-statusbar-control-was-clicked.md)
- [StatusBar 컨트롤 개요](statusbar-control-overview-windows-forms.md)
