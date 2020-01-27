---
title: 추가 보안 고려 사항
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, secure calls to Windows API
- security [Windows Forms]
- security [Windows Forms], calling APIs
- Clipboard [Windows Forms], securing access
ms.assetid: 15abda8b-0527-47c7-aedb-77ab595f2bf1
ms.openlocfilehash: c8d51a57194f1dc536bc4b5d0376987dbfd3b2cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739812"
---
# <a name="additional-security-considerations-in-windows-forms"></a>Windows Forms의 추가 보안 고려 사항
보안 설정을 .NET Framework 하면 로컬 컴퓨터의 부분 신뢰 환경에서 응용 프로그램이 다르게 실행 될 수 있습니다. .NET Framework는 파일 시스템, 네트워크 및 관리 되지 않는 Api와 같은 중요 한 로컬 리소스에 대 한 액세스를 제한 합니다. 보안 설정은 Microsoft Windows API 또는 보안 시스템에서 확인할 수 없는 기타 Api를 호출 하는 기능에 영향을 줍니다. 또한 파일, 데이터 액세스, 인쇄를 비롯한 애플리케이션의 다른 측면에도 영향을 줍니다. 부분 신뢰 환경에서의 파일 및 데이터 액세스에 대한 자세한 내용은 [Windows Forms의 파일 및 데이터 액세스 추가 보안](more-secure-file-and-data-access-in-windows-forms.md)을 참조하세요. 부분 신뢰 환경에서의 인쇄에 대한 자세한 내용은 [Windows Forms의 인쇄 추가 보안](more-secure-printing-in-windows-forms.md)을 참조하세요.  
  
 다음 섹션에서는 클립보드를 사용 하 여 작업 하 고, 창 조작을 수행 하 고, 부분 신뢰 환경에서 실행 되는 응용 프로그램에서 Windows API를 호출 하는 방법을 설명 합니다.  
  
## <a name="clipboard-access"></a>클립보드 액세스  
 합니다 <xref:System.Security.Permissions.UIPermission> 클래스를 클립보드에 연결 된 액세스 제어 <xref:System.Security.Permissions.UIPermissionClipboard> 열거형 값에 대 한 액세스 수준을 나타냅니다. 다음 표에서는 가능한 권한 수준을 보여 줍니다.  
  
|UIPermissionClipboard 값|설명|  
|---------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard>|클립보드 사용에 제한을 받지 않습니다.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard>|약간의 제한을 받으면서 클립보드를 사용할 수 있습니다. 복사 또는 잘라내기 명령 작업과 같이 클립보드에 데이터를 넣는 기능은 제한을 받지 않습니다. 텍스트 상자와 같이 붙여넣기를 허용하는 내장 컨트롤은 클립보드 데이터를 받아들일 수 있지만 사용자 정의 컨트롤은 프로그래밍 방식으로 클립보드에서 데이터를 읽을 수는 없습니다.|  
|<xref:System.Security.Permissions.UIPermissionClipboard.NoClipboard>|클립보드를 사용할 수 없습니다.|  
  
 기본적으로 로컬 인트라넷 영역에는 <xref:System.Security.Permissions.UIPermissionClipboard.AllClipboard> 액세스 권한이 부여 되 고 인터넷 영역에는 <xref:System.Security.Permissions.UIPermissionClipboard.OwnClipboard> 액세스 권한이 부여 됩니다. 이것은 애플리케이션에서 클립보드에 데이터를 복사할 수 있지만 프로그래밍 방식으로 클립보드에 데이터를 붙여넣거나 클립보드에서 데이터를 읽을 수는 없다는 것을 의미합니다. 이러한 제한으로 인해 신뢰 수준이 완전 신뢰가 아닌 프로그램은 다른 애플리케이션이 클립보드에 복사한 내용을 읽을 수 없습니다. 애플리케이션에 클립보드에 대한 모든 액세스가 필요하지만 해당 권한이 없을 경우에는 애플리케이션의 권한을 높여야 합니다. 권한 높이기에 대한 자세한 내용은 [일반 보안 정책 관리](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))를 참조하세요.  
  
## <a name="window-manipulation"></a>창 조작  
 또한 <xref:System.Security.Permissions.UIPermission> 클래스는 창 조작 및 기타 UI 관련 작업을 수행할 수 있는 권한을 제어 하 고, 연결 된 <xref:System.Security.Permissions.UIPermissionWindow> 열거형 값은 액세스 수준을 나타냅니다. 다음 표에서는 가능한 권한 수준을 보여 줍니다.  
  
 기본적으로 로컬 인트라넷 영역에는 <xref:System.Security.Permissions.UIPermissionWindow.AllWindows> 액세스 권한이 부여 되 고 인터넷 영역에는 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> 액세스 권한이 부여 됩니다. 이것은 인터넷 영역에서는 애플리케이션이 대부분의 창 작업 및 UI 작업을 수행할 수 있지만 창의 모양은 수정된다는 것을 의미합니다. 처음 실행한 경우 수정된 창에는 풍선 알림과 수정된 제목 표시줄 텍스트가 표시되며, 제목 표시줄에 닫기 단추가 필요합니다. 풍선 알림과 제목 표시줄은 애플리케이션 사용자에게 애플리케이션이 부분 신뢰 환경에서 실행되고 있음을 알려 줍니다.  
  
|UIPermissionWindow 값|설명|  
|------------------------------|-----------------|  
|<xref:System.Security.Permissions.UIPermissionWindow.AllWindows>|사용자는 모든 창과 사용자 입력 이벤트를 제한 없이 사용할 수 있습니다.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows>|사용자가 안전한 최상위 창과 안전한 하위 창만 그리기 작업에 사용할 수 있고, 이러한 최상위 창 및 하위 창 내의 사용자 인터페이스에는 사용자 입력 이벤트만 사용할 수 있습니다. 이러한 안전한 창에는 명확하게 레이블이 지정되며 최소 및 최대 크기 제한이 있습니다. 이러한 제한 사항은 모방 시스템 로그온 화면 또는 시스템 데스크톱과 같은 잠재적으로 유해한 스푸핑 공격을 방지 하 고 부모 창, 포커스 관련 Api 및 <xref:System.Windows.Forms.ToolTip> 컨트롤 사용에 대 한 프로그래밍 방식의 액세스를 제한 합니다.|  
|<xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows>|사용자가 안전한 하위 창만 그리기 작업에 사용할 수 있고, 해당 하위 창 내의 사용자 인터페이스에는 사용자 입력 이벤트만 사용할 수 있습니다. 예를 들어, 브라우저 내에 표시되는 컨트롤은 안전한 하위 창입니다.|  
|<xref:System.Security.Permissions.UIPermissionWindow.NoWindows>|사용자가 창이나 사용자 인터페이스 이벤트를 사용할 수 없습니다. 사용자 인터페이스를 사용할 수 없습니다.|  
  
 <xref:System.Security.Permissions.UIPermissionWindow> 열거형으로 식별 되는 각 사용 권한 수준은 상위 수준 보다 더 작은 작업을 수행할 수 있습니다. 다음 표에서는 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> 및 <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> 값에 의해 제한 되는 작업을 표시 합니다. 각 멤버에 필요한 정확한 권한은 .NET Framework 클래스 라이브러리 설명서에서 해당 멤버의 항목을 참조하세요.  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> 권한은 다음 표에 나열 된 작업을 제한 합니다.  
  
|구성 요소|제한된 작업|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.Application>|-   <xref:System.Windows.Forms.Application.SafeTopLevelCaptionFormat%2A> 속성을 설정합니다.|  
|<xref:System.Windows.Forms.Control>|-<xref:System.Windows.Forms.Control.Parent%2A> 속성을 가져옵니다.<br />-   `Region` 속성을 설정합니다.<br />-<xref:System.Windows.Forms.Control.FindForm%2A>, <xref:System.Windows.Forms.Control.Focus%2A>, <xref:System.Windows.Forms.Control.FromChildHandle%2A> 및 <xref:System.Windows.Forms.Control.FromHandle%2A>, <xref:System.Windows.Forms.Control.PreProcessMessage%2A>, <xref:System.Windows.Forms.Control.ReflectMessage%2A>또는 <xref:System.Windows.Forms.Control.SetTopLevel%2A> 메서드를 호출 합니다.<br />-반환 된 컨트롤이 호출 하는 컨트롤의 자식이 아닌 경우 <xref:System.Windows.Forms.Control.GetChildAtPoint%2A> 메서드를 호출 합니다.<br />-   컨테이너 컨트롤 내에서 컨트롤 포커스를 수정합니다.|  
|<xref:System.Windows.Forms.Cursor>|-   <xref:System.Windows.Forms.Cursor.Clip%2A> 속성을 설정합니다.<br />-<xref:System.Windows.Forms.Control.Hide%2A> 메서드를 호출 합니다.|  
|<xref:System.Windows.Forms.DataGrid>|-<xref:System.Windows.Forms.ContainerControl.ProcessTabKey%2A> 메서드를 호출 합니다.|  
|<xref:System.Windows.Forms.Form>|-<xref:System.Windows.Forms.Form.ActiveForm%2A> 또는 <xref:System.Windows.Forms.Form.MdiParent%2A> 속성을 가져옵니다.<br />-<xref:System.Windows.Forms.Form.ControlBox%2A>, <xref:System.Windows.Forms.Form.ShowInTaskbar%2A>또는 <xref:System.Windows.Forms.Form.TopMost%2A> 속성을 설정 합니다.<br />-<xref:System.Windows.Forms.Form.Opacity%2A> 속성을 50% 미만으로 설정 합니다.<br />-<xref:System.Windows.Forms.Form.WindowState%2A> 속성을 프로그래밍 방식으로 <xref:System.Windows.Forms.FormWindowState.Minimized>로 설정 합니다.<br />-<xref:System.Windows.Forms.Form.Activate%2A> 메서드를 호출 합니다.<br />-<xref:System.Windows.Forms.FormBorderStyle.None>, <xref:System.Windows.Forms.FormBorderStyle.FixedToolWindow>및 <xref:System.Windows.Forms.FormBorderStyle.SizableToolWindow><xref:System.Windows.Forms.FormBorderStyle> 열거형 값을 사용 합니다.|  
|<xref:System.Windows.Forms.NotifyIcon>|-<xref:System.Windows.Forms.NotifyIcon> 구성 요소를 사용 하는 것은 완전히 제한 됩니다.|  
  
 <xref:System.Security.Permissions.UIPermissionWindow.SafeSubWindows> 값은 <xref:System.Security.Permissions.UIPermissionWindow.SafeTopLevelWindows> 값에 의해 배치 되는 제한 사항 외에도 다음 표에 나열 된 작업을 제한 합니다.  
  
|구성 요소|제한된 작업|  
|---------------|------------------------|  
|<xref:System.Windows.Forms.CommonDialog>|-<xref:System.Windows.Forms.CommonDialog> 클래스에서 파생 된 대화 상자를 표시 합니다.|  
|<xref:System.Windows.Forms.Control>|-<xref:System.Windows.Forms.Control.CreateGraphics%2A> 메서드를 호출 합니다.<br />-   <xref:System.Windows.Forms.Control.Cursor%2A> 속성을 설정합니다.|  
|<xref:System.Windows.Forms.Control.Cursor%2A>|-   <xref:System.Windows.Forms.Cursor.Current%2A> 속성을 설정합니다.|  
|<xref:System.Windows.Forms.MessageBox>|-<xref:System.Windows.Forms.Form.Show%2A> 메서드를 호출 합니다.|  
  
### <a name="hosting-third-party-controls"></a>타사 컨트롤 호스팅  
 다른 종류의 창 조작은 양식에서 타사 컨트롤을 호스팅하는 경우에 발생할 수 있습니다. 타사 컨트롤은 사용자가 직접 개발 하 고 컴파일하지 않은 사용자 지정 <xref:System.Windows.Forms.UserControl>입니다. 호스팅 시나리오를 악용하기는 어렵지만 타사 컨트롤이 렌더링 화면을 확장하여 사용자 양식의 전체 영역을 가리는 것이 논리적으로 가능합니다. 이 컨트롤은 중요한 대화 상자를 모방하여 사용자 이름/암호 조합이나 은행 계좌 번호 등의 정보를 사용자에게 요청할 수 있습니다.  
  
 이러한 잠재적인 위험을 방지하려면 신뢰할 수 있는 공급업체의 타사 컨트롤만 사용해야 합니다. 확인할 수 없는 소스에서 다운로드한 타사 컨트롤을 사용할 경우에는 소스 코드를 검토하여 악용 가능성이 있는지 확인하는 것이 좋습니다. 소스에 악의적인 내용이 없는지 확인한 후 어셈블리를 직접 컴파일하여 소스와 어셈블리가 일치하는지 확인해야 합니다.  
  
## <a name="windows-api-calls"></a>Windows API 호출  
 응용 프로그램을 디자인할 때 Windows API에서 함수를 호출 해야 하는 경우 비관리 코드에 액세스 하 게 됩니다. 이 경우 Windows API 호출 또는 값으로 작업할 때 창 또는 운영 체제에 대 한 코드 작업을 확인할 수 없습니다. <xref:System.Security.Permissions.SecurityPermission> 클래스 및 <xref:System.Security.Permissions.SecurityPermissionFlag> 열거형의 <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> 값은 비관리 코드에 대 한 액세스를 제어 합니다. 응용 프로그램은 <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> 권한이 부여 된 경우에만 비관리 코드에 액세스할 수 있습니다. 기본적으로 로컬에서 실행되고 있는 애플리케이션만 비관리 코드에 액세스할 수 있습니다.  
  
 일부 Windows Forms 멤버는 <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> 권한이 필요한 관리 되지 않는 액세스를 제공 합니다. 다음 표에서는 권한이 필요한 <xref:System.Windows.Forms> 네임 스페이스의 멤버를 나열 합니다. 멤버에 필요한 권한에 대한 자세한 내용은 .NET Framework 클래스 라이브러리 설명서를 참조하세요.  
  
|구성 요소|Member|  
|---------------|------------|  
|<xref:System.Windows.Forms.Application>|-   <xref:System.Windows.Forms.Application.AddMessageFilter%2A> 메서드<br />-   <xref:System.Windows.Forms.Application.CurrentInputLanguage%2A> 속성<br />-   `Exit` 메서드<br />-   <xref:System.Windows.Forms.Application.ExitThread%2A> 메서드<br />-   <xref:System.Windows.Forms.Application.ThreadException> 이벤트|  
|<xref:System.Windows.Forms.CommonDialog>|-   <xref:System.Windows.Forms.CommonDialog.HookProc%2A> 메서드<br />-   <xref:System.Windows.Forms.CommonDialog.OwnerWndProc%2A>\ method<br />-   <xref:System.Windows.Forms.CommonDialog.Reset%2A> 메서드<br />-   <xref:System.Windows.Forms.CommonDialog.RunDialog%2A> 메서드|  
|<xref:System.Windows.Forms.Control>|-   <xref:System.Windows.Forms.Control.CreateParams%2A> 메서드<br />-   <xref:System.Windows.Forms.Control.DefWndProc%2A> 메서드<br />-   <xref:System.Windows.Forms.Control.DestroyHandle%2A> 메서드<br />-   <xref:System.Windows.Forms.Control.WndProc%2A> 메서드|  
|<xref:System.Windows.Forms.Help>|-   <xref:System.Windows.Forms.Help.ShowHelp%2A> 메서드<br />-   <xref:System.Windows.Forms.Help.ShowHelpIndex%2A> 메서드|  
|<xref:System.Windows.Forms.NativeWindow>|-   <xref:System.Windows.Forms.NativeWindow> 클래스|  
|<xref:System.Windows.Forms.Screen>|-   <xref:System.Windows.Forms.Screen.FromHandle%2A> 메서드|  
|<xref:System.Windows.Forms.SendKeys>|-   <xref:System.Windows.Forms.SendKeys.Send%2A> 메서드<br />-   <xref:System.Windows.Forms.SendKeys.SendWait%2A> 메서드|  
  
 응용 프로그램에 비관리 코드를 호출할 수 있는 권한이 없는 경우 응용 프로그램에서 <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> 권한을 요청 하거나 기능을 구현 하는 다른 방법을 고려해 야 합니다. 대부분의 경우 Windows Forms Windows API 함수에 대 한 관리 되는 대안을 제공 합니다. 이러한 대안이 없는 상황에서 비관리 코드에 액세스해야 할 경우에는 애플리케이션의 권한을 높여야 합니다.  
  
 비관리 코드를 호출할 수 있는 권한을 부여하면 애플리케이션이 거의 모든 작업을 수행할 수 있습니다. 따라서 비관리 코드를 호출할 수 있는 권한은 신뢰할 수 있는 소스의 애플리케이션에만 부여해야 합니다. 또는 애플리케이션에 따라 비관리 코드를 호출하는 기능을 옵션으로 지정하거나 완전 신뢰 환경에서만 이 기능을 사용하도록 할 수 있습니다. 위험한 권한에 대한 자세한 내용은 [위험한 권한 및 정책 관리](../misc/dangerous-permissions-and-policy-administration.md)를 참조하세요. 권한 높이기에 대한 자세한 내용은 [일반 보안 정책 관리](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))를 참조하세요.  
  
## <a name="see-also"></a>참조

- [Windows Forms의 파일 및 데이터 액세스 추가 보안](more-secure-file-and-data-access-in-windows-forms.md)
- [Windows Forms의 인쇄 추가 보안](more-secure-printing-in-windows-forms.md)
- [Windows Forms의 보안 개요](security-in-windows-forms-overview.md)
- [Windows Forms 보안](windows-forms-security.md)
- [ClickOnce 애플리케이션 보안](/visualstudio/deployment/securing-clickonce-applications)
