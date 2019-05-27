---
title: '방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인'
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
ms.openlocfilehash: a659de62965d17e965eee2f750337a08ae1801e0
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053715"
---
# <a name="how-to-determine-which-panel-in-the-windows-forms-statusbar-control-was-clicked"></a>방법: Windows Forms StatusBar 컨트롤에서 클릭한 패널 확인
> [!IMPORTANT]
>  <xref:System.Windows.Forms.StatusStrip> 및 <xref:System.Windows.Forms.ToolStripStatusLabel> 대체 컨트롤과 기능을 추가 합니다 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 제어; 그러나를 <xref:System.Windows.Forms.StatusBar> 및 <xref:System.Windows.Forms.StatusBarPanel> 컨트롤 하는 경우 이전 버전과 호환성 및 향후 사용을 위해 유지 됩니다 있습니다 이 옵션을 선택 합니다.  
  
 프로그램에는 [StatusBar 컨트롤](statusbar-control-windows-forms.md) 사용자 클릭에 응답, 내에서 case 문을 사용 하 여 컨트롤을 <xref:System.Windows.Forms.StatusBar.PanelClick> 이벤트입니다. 이벤트에는 클릭에 대 한 참조를 포함 하는 인수 (패널 인수) <xref:System.Windows.Forms.StatusBarPanel>합니다. 이 참조를 사용 하 여 클릭 한 패널의 인덱스를 확인할 수 있으며 그에 따라 프로그램 수도 있습니다.  
  
> [!NOTE]
>  있는지 확인 합니다 <xref:System.Windows.Forms.StatusBar> 컨트롤의 <xref:System.Windows.Forms.StatusBar.ShowPanels%2A> 속성이 `true`합니다.  
  
### <a name="to-determine-which-panel-was-clicked"></a>클릭 한 패널을 확인 하려면  
  
1. 에 <xref:System.Windows.Forms.StatusBar.PanelClick> 이벤트 처리기를 사용 하 여는 `Select Case` (Visual Basic)에서는 또는 `switch case` (Visual C# 또는 시각적 개체 C++) 문에를 이벤트 인수에서 클릭 한 패널의 인덱스를 검사 하 여 클릭 한 패널을 확인 합니다.  
  
     다음 코드 예제에서는의 현재 상태, 폼에 필요는 <xref:System.Windows.Forms.StatusBar> 제어 `StatusBar1`, 두 개의 <xref:System.Windows.Forms.StatusBarPanel> 개체 `StatusBarPanel1` 및 `StatusBarPanel2`합니다.  
  
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
  
     (Visual C#, Visual C++) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.  
  
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
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.StatusBar>
- <xref:System.Windows.Forms.ToolStripStatusLabel>
- [방법: 상태 표시줄 패널의 크기를 설정 합니다.](how-to-set-the-size-of-status-bar-panels.md)
- [연습: 런타임에 상태 표시줄 정보 업데이트](walkthrough-updating-status-bar-information-at-run-time.md)
- [StatusBar 컨트롤 개요](statusbar-control-overview-windows-forms.md)
