---
title: 바로 가기 메뉴를 NotifyIcon 구성 요소와 연결
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], for background processes
- NotifyIcon component [Windows Forms], associating shortcut menus
- shortcut menus [Windows Forms], for background processes
ms.assetid: d68f3926-08d3-4f7d-949f-1981b29cf188
ms.openlocfilehash: 15a4a06726de348745e5eef03217d693db496a42
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182261"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>방법: Windows Forms NotifyIcon 구성 요소에 바로 가기 메뉴 연결
> [!NOTE]
> 이전 <xref:System.Windows.Forms.MenuStrip> <xref:System.Windows.Forms.ContextMenuStrip> 버전의 컨트롤 및 <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 컨트롤에 기능을 교체 <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> 하고 추가하고 이전 버전의 호환성과 향후 사용모두에 대해 유지됩니다.  
  
 <xref:System.Windows.Forms.NotifyIcon> 구성 요소는 작업 표시줄의 상태 알림 영역에 아이콘을 표시합니다. 일반적으로 응용 프로그램을 사용하면 이 아이콘을 마우스 오른쪽 단추로 클릭하여 나타내는 응용 프로그램에 명령을 보낼 수 있습니다. <xref:System.Windows.Forms.ContextMenu> 구성 요소를 <xref:System.Windows.Forms.NotifyIcon> 구성 요소와 연결하여 응용 프로그램에 이 기능을 추가할 수 있습니다.  
  
> [!NOTE]
> 작업 <xref:System.Windows.Forms.NotifyIcon> 표시줄에 구성 요소의 인스턴스를 표시하는 동안 시작 시 응용 프로그램을 최소화하려면 주 <xref:System.Windows.Forms.Form.WindowState%2A> 폼의 속성을 <xref:System.Windows.Forms.FormWindowState.Minimized> <xref:System.Windows.Forms.NotifyIcon> 로 설정하고 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 구성 요소의 속성이 `true`로 설정되어 있는지 확인합니다.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>바로 가기 메뉴를 디자인 타임에 NotifyIcon 구성 요소와 연결하려면  
  
1. 양식에 <xref:System.Windows.Forms.NotifyIcon> 구성 요소를 추가하고 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성과 같은 중요한 속성을 설정합니다.  
  
     자세한 내용은 [Windows 양식 NotifyIcon 구성 요소와 함께 작업 표시줄에 응용 프로그램 아이콘을 추가하는 방법을](app-icons-to-the-taskbar-with-wf-notifyicon.md)참조하십시오.  
  
2. Windows <xref:System.Windows.Forms.ContextMenu> 양식에 구성 요소를 추가합니다.  
  
     런타임에 사용할 수 있도록 하려는 명령을 나타내는 바로 가기 메뉴에 메뉴 항목을 추가합니다. 또한 액세스 키와 같은 메뉴 항목에 메뉴 향상 을 추가하는 것이 좋습니다.  
  
3. <xref:System.Windows.Forms.NotifyIcon> 구성 요소의 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 속성을 추가한 바로 가기 메뉴로 설정합니다.  
  
     이 속성을 설정하면 작업 표시줄의 아이콘을 클릭하면 바로 가기 메뉴가 표시됩니다.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>바로 가기 메뉴를 NotifyIcon 구성 요소와 프로그래밍 방식으로 연결하려면  
  
1. 응용 프로그램에 필요한 <xref:System.Windows.Forms.NotifyIcon> 속성 <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 설정(및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> <xref:System.Windows.Forms.NotifyIcon> 구성 요소의 속성, 구성 요소의 메뉴 항목)을 <xref:System.Windows.Forms.ContextMenu> 사용하여 클래스 및 클래스의 인스턴스를 만듭니다.  
  
2. <xref:System.Windows.Forms.NotifyIcon> 구성 요소의 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 속성을 추가한 바로 가기 메뉴로 설정합니다.  
  
     이 속성을 설정하면 작업 표시줄의 아이콘을 클릭하면 바로 가기 메뉴가 표시됩니다.  
  
    > [!NOTE]
    > 다음 코드 예제는 기본 메뉴 구조를 만듭니다. 개발 중인 응용 프로그램에 맞는 메뉴 선택 항목으로 메뉴 선택을 사용자 지정해야 합니다. 또한 이러한 메뉴 항목에 대 한 <xref:System.Windows.Forms.MenuItem.Click> 이벤트를 처리 하는 코드를 작성 할 수 있습니다.  
  
    ```vb  
    Public ContextMenu1 As New ContextMenu  
    Public NotifyIcon1 As New NotifyIcon  
  
    Public Sub CreateIconMenuStructure()  
       ' Add menu items to shortcut menu.  
       ContextMenu1.MenuItems.Add("&Open Application")  
       ContextMenu1.MenuItems.Add("S&uspend Application")  
       ContextMenu1.MenuItems.Add("E&xit")  
  
       ' Set properties of NotifyIcon component.  
       NotifyIcon1.Icon = New System.Drawing.Icon _
          (System.Environment.GetFolderPath _
          (System.Environment.SpecialFolder.Personal)  _
          & "\Icon.ico")  
       NotifyIcon1.Text = "Right-click me!"  
       NotifyIcon1.Visible = True  
       NotifyIcon1.ContextMenu = ContextMenu1  
    End Sub  
    ```  
  
```csharp  
public NotifyIcon notifyIcon1 = new NotifyIcon();  
public ContextMenu contextMenu1 = new ContextMenu();  
  
public void createIconMenuStructure()  
{  
   // Add menu items to shortcut menu.  
   contextMenu1.MenuItems.Add("&Open Application");  
   contextMenu1.MenuItems.Add("S&uspend Application");  
   contextMenu1.MenuItems.Add("E&xit");  
  
   // Set properties of NotifyIcon component.  
   notifyIcon1.Icon = new System.Drawing.Icon  
      (System.Environment.GetFolderPath  
      (System.Environment.SpecialFolder.Personal)  
      + @"\Icon.ico");  
   notifyIcon1.Visible = true;  
   notifyIcon1.Text = "Right-click me!";  
   notifyIcon1.Visible = true;  
   notifyIcon1.ContextMenu = contextMenu1;  
}  
```  
  
```cpp  
public:  
   System::Windows::Forms::NotifyIcon ^ notifyIcon1;  
   System::Windows::Forms::ContextMenu ^ contextMenu1;  
  
   void createIconMenuStructure()  
   {  
      // Add menu items to shortcut menu.  
      contextMenu1->MenuItems->Add("&Open Application");  
      contextMenu1->MenuItems->Add("S&uspend Application");  
      contextMenu1->MenuItems->Add("E&xit");  
  
      // Set properties of NotifyIcon component.  
      notifyIcon1->Icon = gcnew System::Drawing::Icon  
          (String::Concat(System::Environment::GetFolderPath  
          (System::Environment::SpecialFolder::Personal),  
          "\\Icon.ico"));  
      notifyIcon1->Text = "Right-click me!";  
      notifyIcon1->Visible = true;  
      notifyIcon1->ContextMenu = contextMenu1;  
   }  
```  
  
> [!NOTE]
> 양식의 생성자에 다음 문을 포함하여 초기화해야 `notifyIcon1` 하며 `contextMenu1,` 수행할 수 있는 작업을 수행해야 합니다.  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [방법: Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 애플리케이션 아이콘 추가](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [NotifyIcon 구성 요소](notifyicon-component-windows-forms.md)
- [NotifyIcon 구성 요소 개요](notifyicon-component-overview-windows-forms.md)
