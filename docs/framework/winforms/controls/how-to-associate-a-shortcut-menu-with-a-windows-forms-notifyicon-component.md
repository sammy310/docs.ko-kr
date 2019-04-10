---
title: '방법: Windows Forms NotifyIcon 구성 요소에 바로 가기 메뉴 연결'
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
ms.openlocfilehash: f2a086cc25eb6996b2643742a887bccf481916d6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59337060"
---
# <a name="how-to-associate-a-shortcut-menu-with-a-windows-forms-notifyicon-component"></a>방법: Windows Forms NotifyIcon 구성 요소에 바로 가기 메뉴 연결
> [!NOTE]
>  있지만 <xref:System.Windows.Forms.MenuStrip> 하 고 <xref:System.Windows.Forms.ContextMenuStrip> 바꾸고 기능을 추가 합니다 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 이전 버전의 컨트롤 <xref:System.Windows.Forms.MainMenu> 및 <xref:System.Windows.Forms.ContextMenu> 선택 하면 이전 버전과 호환성 및 향후 사용을 위해 유지 됩니다.  
  
 <xref:System.Windows.Forms.NotifyIcon> 구성 요소 작업 표시줄의 상태 알림 영역에 아이콘을 표시 합니다. 일반적으로 응용 프로그램을 사용 하면 명령을 나타내는 응용 프로그램에 보내는 데이 아이콘을 마우스 오른쪽 단추로 클릭 수 있습니다. 연결 하 여는 <xref:System.Windows.Forms.ContextMenu> 구성 요소는 <xref:System.Windows.Forms.NotifyIcon> 구성 요소를 응용 프로그램에이 기능을 추가할 수 있습니다.  
  
> [!NOTE]
>  응용 프로그램의 인스턴스를 표시 하는 동안 시작 시 최소화 하려는 경우는 <xref:System.Windows.Forms.NotifyIcon> 작업 표시줄에서 구성 요소에는 기본 폼의 설정 <xref:System.Windows.Forms.Form.WindowState%2A> 속성을 <xref:System.Windows.Forms.FormWindowState.Minimized> 해야 합니다 <xref:System.Windows.Forms.NotifyIcon> 구성 요소의 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성 로 설정 된 `true`합니다.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-at-design-time"></a>NotifyIcon 구성 요소를 사용 하 여 디자인 타임에 바로 가기 메뉴를 연결 하려면  
  
1. 추가 <xref:System.Windows.Forms.NotifyIcon> 구성 요소를 폼에 같은 중요 한 속성을 설정 하 고는 <xref:System.Windows.Forms.NotifyIcon.Icon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 속성입니다.  
  
     자세한 내용은 [방법: Forms NotifyIcon 구성 요소는 Windows 사용 하 여 작업 표시줄에 응용 프로그램 아이콘 추가](app-icons-to-the-taskbar-with-wf-notifyicon.md)합니다.  
  
2. 추가 된 <xref:System.Windows.Forms.ContextMenu> Windows 폼에 구성 요소입니다.  
  
     런타임에 사용할 수 있도록 하려는 명령을 나타내는 바로 가기 메뉴에 메뉴 항목을 추가 합니다. 액세스 키와 같은 이러한 새 메뉴 항목 메뉴 향상 된 기능을 추가할 수 있는 좋은 기회 이기도 합니다.  
  
3. 설정 합니다 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 의 속성을 <xref:System.Windows.Forms.NotifyIcon> 구성 요소를 추가 하는 바로 가기 메뉴.  
  
     이 속성이 설정 된 작업 표시줄에서 아이콘을 클릭 하면 바로 가기 메뉴를 표시 됩니다.  
  
### <a name="to-associate-a-shortcut-menu-with-the-notifyicon-component-programmatically"></a>NotifyIcon 구성 요소를 사용 하 여 바로 가기 메뉴를 프로그래밍 방식으로 연결 하려면  
  
1. 인스턴스를 만듭니다는 <xref:System.Windows.Forms.NotifyIcon> 클래스 및 <xref:System.Windows.Forms.ContextMenu> 속성 설정은 응용 프로그램에 필요한 모든 클래스 (<xref:System.Windows.Forms.NotifyIcon.Icon%2A> 및 <xref:System.Windows.Forms.NotifyIcon.Visible%2A> 에 대 한 속성을 <xref:System.Windows.Forms.NotifyIcon> 구성 요소, 메뉴 항목에 대 한는 <xref:System.Windows.Forms.ContextMenu> 구성 요소)입니다.  
  
2. 설정 합니다 <xref:System.Windows.Forms.NotifyIcon.ContextMenu%2A> 의 속성을 <xref:System.Windows.Forms.NotifyIcon> 구성 요소를 추가 하는 바로 가기 메뉴.  
  
     이 속성이 설정 된 작업 표시줄에서 아이콘을 클릭 하면 바로 가기 메뉴를 표시 됩니다.  
  
    > [!NOTE]
    >  다음 코드 예제에서는 기본 메뉴 구조를 만듭니다. 메뉴 선택 항목으로 개발 하는 응용 프로그램에 맞게 사용자 지정 해야 합니다. 처리할 코드를 작성 하려고 또한는 <xref:System.Windows.Forms.MenuItem.Click> 이러한 메뉴 항목에 대 한 이벤트입니다.  
  
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
>  초기화 해야 합니다 `notifyIcon1` 고 `contextMenu1,` 폼의 생성자에서 다음 문을 포함 하 여 수행할 수 있습니다.  
  
```cpp  
notifyIcon1 = gcnew System::Windows::Forms::NotifyIcon();  
contextMenu1 = gcnew System::Windows::Forms::ContextMenu();  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.NotifyIcon>
- <xref:System.Windows.Forms.NotifyIcon.Icon%2A>
- [방법: Windows Forms NotifyIcon 구성 요소를 사용하여 작업 표시줄에 애플리케이션 아이콘 추가](app-icons-to-the-taskbar-with-wf-notifyicon.md)
- [NotifyIcon 구성 요소](notifyicon-component-windows-forms.md)
- [NotifyIcon 구성 요소 개요](notifyicon-component-overview-windows-forms.md)
