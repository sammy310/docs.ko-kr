---
title: StatusBar 컨트롤에서 클릭 한 패널 확인
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
ms.openlocfilehash: 94619f8bd426a42e5dafa0db99880e20d24f9963
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746018"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인
> [!IMPORTANT]
> <xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 컨트롤은 기능을 대체 하 고 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤에 추가 합니다. 그러나 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤은 이전 버전과의 호환성 및 향후 사용을 위해 유지 됩니다 (선택 하는 경우).  
  
 사용자 클릭에 응답 하도록 [StatusBar 컨트롤](statusbar-control-windows-forms.md) 컨트롤을 프로그래밍 하려면 <xref:System.Windows.Forms.StatusBar.PanelClick> 이벤트 내에서 case 문을 사용 합니다. 이벤트는 클릭 한 <xref:System.Windows.Forms.StatusBarPanel>에 대 한 참조를 포함 하는 인수 (panel 인수)를 포함 합니다. 이 참조를 사용 하 여 클릭 한 패널의 인덱스를 확인 하 고 적절 하 게 프로그래밍할 수 있습니다.  
  
> [!NOTE]
> <xref:System.Windows.Forms.StatusBar> 컨트롤의 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성이 `true`으로 설정 되어 있는지 확인 합니다.  
  
### <a name="to-determine-which-panel-was-clicked"></a>클릭 한 패널을 확인 하려면  
  
1. <xref:System.Windows.Forms.StatusBar.PanelClick> 이벤트 처리기에서 `Select Case` (Visual Basic) 또는 `switch case` (시각적 개체 C# 또는 시각적 개체 C++) 문을 사용 하 여 이벤트 인수에서 클릭 된 패널의 인덱스를 검사 하 여 클릭 한 패널을 확인 합니다.  
  
     다음 코드 예제에서는 폼의 <xref:System.Windows.Forms.StatusBar> 컨트롤, `StatusBar1`및 두 개의 <xref:System.Windows.Forms.StatusBarPanel> 개체 `StatusBarPanel1` 및 `StatusBarPanel2`가 있어야 합니다.  
  
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
  
     (시각적 C#개체, C++시각적 개체) 폼의 생성자에 다음 코드를 추가 하 여 이벤트 처리기를 등록 합니다.  
  
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
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [방법: 상태 표시줄 패널의 크기 설정](how-to-set-the-size-of-status-bar-panels.md)
- [연습: 런타임에 상태 표시줄 정보 업데이트](walkthrough-updating-status-bar-information-at-run-time.md)
- [StatusBar 컨트롤 개요](statusbar-control-overview-windows-forms.md)
