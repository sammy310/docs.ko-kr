---
title: 상태 표시줄 컨트롤에서 클릭한 패널 확인
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- status bars [Windows Forms], determining panel clicked
- panels [Windows Forms], determining clicked
- StatusBar control [Windows Forms], coding panel click events
- StatusBar control [Windows Forms], determining panel clicked
- PanelClick event [Windows Forms], determining panel clicked
- Panel control [Windows Forms], determining click
ms.assetid: d14c6092-04b2-4a07-8ddf-0dd11277ff5f
ms.openlocfilehash: eb3b10d515ba5b62236594e063ca7f060b34b73e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182359"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인
> [!IMPORTANT]
> 및 <xref:System.Windows.Forms.StatusStrip> <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤을 대체하고 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤에 기능을 추가합니다. 그러나 <xref:System.Windows.Forms.StatusBar> 원하는 <xref:System.Windows.Forms.StatusBarPanel> 경우 이전 버전과의 호환성 및 향후 사용모두에 대해 및 컨트롤이 유지됩니다.  
  
 사용자 클릭에 응답하도록 [StatusBar 컨트롤](statusbar-control-windows-forms.md) 컨트롤을 프로그래밍하려면 <xref:System.Windows.Forms.StatusBar.PanelClick> 이벤트 내에서 사례 문을 사용합니다. 이벤트에는 클릭한 <xref:System.Windows.Forms.StatusBarPanel>에 대한 참조가 포함된 인수(패널 인수)가 포함되어 있습니다. 이 참조를 사용하여 클릭한 패널의 인덱스를 확인하고 그에 따라 프로그래밍할 수 있습니다.  
  
> [!NOTE]
> 컨트롤의 <xref:System.Windows.Forms.StatusBar> <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성이 `true`로 설정되어 있는지 확인합니다.  
  
### <a name="to-determine-which-panel-was-clicked"></a>클릭한 패널을 확인하려면  
  
1. <xref:System.Windows.Forms.StatusBar.PanelClick> 이벤트 처리기에서 `Select Case` (Visual Basic) 또는 `switch case` (Visual C# 또는 Visual C++) 문을 사용하여 이벤트 인수에서 클릭한 패널의 인덱스를 검사하여 클릭한 패널을 확인합니다.  
  
     다음 코드 예제에서는 <xref:System.Windows.Forms.StatusBar> 폼, 컨트롤 및 `StatusBar1`두 <xref:System.Windows.Forms.StatusBarPanel> 개체 `StatusBarPanel1` 및 `StatusBarPanel2`의 존재 가 필요합니다.  
  
    ```vb  
    Private Sub StatusBar1_PanelClick(ByVal sender As System.Object, ByVal e As System.Windows.Forms.StatusBarPanelClickEventArgs) Handles StatusBar1.PanelClick  
       Select Case StatusBar1.Panels.IndexOf(e.StatusBarPanel)  
         Case 0  
           MessageBox.Show("You have clicked Panel One.")  
         Case 1  
           MessageBox.Show("You have clicked Panel Two.")  
       End Select  
    End Sub  
    ```  
  
    ```csharp  
    private void statusBar1_PanelClick(object sender,
    System.Windows.Forms.StatusBarPanelClickEventArgs e)  
    {  
       switch (statusBar1.Panels.IndexOf(e.StatusBarPanel))  
       {  
          case 0 :  
             MessageBox.Show("You have clicked Panel One.");  
             break;  
          case 1 :  
             MessageBox.Show("You have clicked Panel Two.");  
             break;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void statusBar1_PanelClick(System::Object ^  sender,  
          System::Windows::Forms::StatusBarPanelClickEventArgs ^  e)  
       {  
          switch (statusBar1->Panels->IndexOf(e->StatusBarPanel))  
          {  
             case 0 :  
                MessageBox::Show("You have clicked Panel One.");  
                break;  
             case 1 :  
                MessageBox::Show("You have clicked Panel Two.");  
                break;  
          }  
       }  
    ```  
  
     (비주얼 C #, 비주얼 C++) 양식의 생성자에서 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```csharp  
    this.statusBar1.PanelClick += new
       System.Windows.Forms.StatusBarPanelClickEventHandler
       (this.statusBar1_PanelClick);  
    ```  
  
    ```cpp  
    this->statusBar1->PanelClick += gcnew  
       System::Windows::Forms::StatusBarPanelClickEventHandler  
       (this, &Form1::statusBar1_PanelClick);  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [방법: 상태 표시줄 패널의 크기 설정](how-to-set-the-size-of-status-bar-panels.md)
- [연습: 런타임에 상태 표시줄 정보 업데이트](walkthrough-updating-status-bar-information-at-run-time.md)
- [StatusBar 컨트롤 개요](statusbar-control-overview-windows-forms.md)
