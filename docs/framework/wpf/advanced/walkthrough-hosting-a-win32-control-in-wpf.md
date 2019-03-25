---
title: '연습: WPF에서 Win32 컨트롤 호스팅'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 13845eb662064e0ac1db913bedc0b21214292db5
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412320"
---
# <a name="walkthrough-hosting-a-win32-control-in-wpf"></a>연습: WPF에서 Win32 컨트롤 호스팅
Windows Presentation Foundation (WPF) 응용 프로그램을 만들기 위한 풍부한 환경을 제공 합니다. 그러나 Win32 코드에 상당한 투자를 해야 하는 경우는 것을 더욱 효율적으로 적어도 일부 다시 사용 하는의 WPF 응용 프로그램에서 코드 보다는 완전히 다시 작성 합니다. WPF는 Win32 창의 WPF 페이지를 호스트 하기 위한 간단한 메커니즘을 제공 합니다.  
  
 이 항목에서는 응용 프로그램을 통해 [WPF 샘플에서 Win32 ListBox 컨트롤 호스팅](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control), 호스트 Win32 목록 상자를 제어 합니다. 이 일반적인 절차는 모든 Win32 창 호스팅에 확장할 수 있습니다.  
  
  
<a name="requirements"></a>   
## <a name="requirements"></a>요구 사항  
 이 항목에서는 WPF와 Windows API 프로그래밍 기본에 익숙하다고를 가정합니다. WPF 프로그래밍에 대 한 기본적인 소개를 참조 하세요 [Getting Started](../getting-started/index.md)합니다. Windows API 프로그래밍 소개, 표시 서적 주제에 대 특히 *Windows 프로그래밍* Charles petzold가 저술한 합니다.  
  
 이 항목과 관련 된 샘플에서 구현 되기 때문에 C#, Windows API에 액세스 하려면 플랫폼 호출 서비스인 PInvoke 사용 합니다. PInvoke 지식이 있으면 도움이 되지만 필수 사항은 아닙니다.  
  
> [!NOTE]
>  이 항목에는 관련 샘플의 많은 코드 예제가 포함되어 있습니다. 그러나 가독성을 위해 전체 샘플 코드를 포함하지는 않습니다. 얻거나에서 전체 코드를 볼 수 있습니다 [WPF 샘플에서 Win32 ListBox 컨트롤 호스팅](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)합니다.  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>기본 절차  
 이 섹션에서는 WPF 페이지에서 Win32 창 호스팅에 대 한 기본 절차를 간략하게 설명 합니다. 나머지 섹션에서는 각 단계를 자세히 설명합니다.  
  
 기본 호스팅 절차는 다음과 같습니다.  
  
1.  창을 호스트 하는 WPF 페이지를 구현 합니다. 기술 중 하나를 만드는 것을 <xref:System.Windows.Controls.Border> 호스팅된 창의 페이지의 섹션을 예약 하는 요소입니다.  
  
2.  상속 되는 컨트롤을 호스트 하는 클래스를 구현 <xref:System.Windows.Interop.HwndHost>합니다.  
  
3.  해당 클래스에서 재정의 된 <xref:System.Windows.Interop.HwndHost> 클래스 멤버 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>합니다.  
  
4.  WPF 페이지를 포함 하는 창의 자식으로 호스트 된 창을 만듭니다. 기존 WPF 프로그래밍 명시적으로 확인 하지 않아도 되지만 호스팅 페이지는 창 핸들 (HWND)을 사용 하 여를 사용 합니다. 페이지 HWND를 받게 통해 합니다 `hwndParent` 의 매개 변수는 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> 메서드. 호스트된 창은 이 HWND의 자식으로 만들어야 합니다.  
  
5.  호스트 창을 만들었으면 호스트된 창의 HWND를 반환합니다. 하나 이상의 Win32 컨트롤을 호스트 하려는 경우 일반적으로 호스트 창을 HWND의 자식으로 만들 및 해당 호스트 창의 자식 컨트롤을 확인 합니다. 호스트 창에 컨트롤을 래핑하여 HWND 경계를 넘어 알림 사용 하 여 특정 Win32 문제를 처리 하는 컨트롤에서 알림을 받을 WPF 페이지는 간단한 방법을 제공 합니다.  
  
6.  자식 컨트롤의 알림과 같이 호스트 창으로 전송되는 선택한 메시지를 처리합니다. 그런 경우 두 가지 방법이 있습니다.  
  
    -   호스팅 클래스에서 메시지를 처리 하려는 경우 재정의 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 메서드는 <xref:System.Windows.Interop.HwndHost> 클래스입니다.  
  
    -   WPF의 메시지 처리를 처리 하려는 경우는 <xref:System.Windows.Interop.HwndHost> 클래스 <xref:System.Windows.Interop.HwndHost.MessageHook> 코드 숨김에서 이벤트입니다. 이 이벤트는 호스트된 창에서 받은 모든 메시지에 대해 발생합니다. 이 옵션을 선택 하는 경우는 여전히 재정의 해야 <xref:System.Windows.Interop.HwndHost.WndProc%2A>, 하지만 최소 구현만 필요 합니다.  
  
7.  재정의 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 하 고 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 메서드의 <xref:System.Windows.Interop.HwndHost>합니다. 충족 하기 위해 이러한 메서드를 재정의 해야 합니다는 <xref:System.Windows.Interop.HwndHost> 계약 있지만 최소 구현을 제공 해야 할 수 있습니다.  
  
8.  코드 숨김 파일에서 컨트롤 호스팅 클래스의 인스턴스를 만듭니다 및의 자식으로 설정 된 <xref:System.Windows.Controls.Border> 창을 호스트 하기 위한 요소입니다.  
  
9. 전송 하 여 호스팅된 창과 통신 [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] 메시지 및 해당 자식 창 컨트롤에서 보낸 알림과 같은 메시지를 처리 합니다.  
  
<a name="page_layout"></a>   
## <a name="implement-the-page-layout"></a>페이지 레이아웃 구현  
 ListBox 컨트롤을 호스팅하는 WPF 페이지에 대 한 레이아웃 두 지역으로 구성 됩니다. 제공 하는 몇 가지 WPF 컨트롤을 호스트 하는 페이지의 왼쪽을 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] Win32 컨트롤을 조작할 수 있도록 합니다. 페이지의 오른쪽 위에는 호스트된 ListBox 컨트롤에 대한 사각형 영역이 있습니다.  
  
 이 레이아웃을 구현 하는 코드는 매우 간단 합니다. 루트 요소는 <xref:System.Windows.Controls.DockPanel> 두 자식 요소가 들어 있는입니다. 첫 번째는 <xref:System.Windows.Controls.Border> ListBox 컨트롤을 호스팅하는 요소입니다. 이 요소는 페이지의 오른쪽 위에 있는 200x200 정사각형을 사용합니다. 두 번째는 <xref:System.Windows.Controls.StackPanel> 요소 정보를 표시 하 고 설정 하 여 ListBox 컨트롤을 조작할 수 있는 WPF 컨트롤의 집합을 포함 하는 상호 운용 속성을 노출 합니다. 각 자식 요소에 대 한는 <xref:System.Windows.Controls.StackPanel>이러한 요소 또는 용도에 대 한 세부 정보에 사용 되는 다양 한 요소에 대 한 참조 자료를 참조 하세요, 이러한 아래 예제 코드에 나와 있지만 됩니다 (기본 여기에서 설명한 상호 운용성 모델이 필요 하지 않으면 그 중 하나에 제공 되기 샘플에 몇 가지 대화형 작업 추가).  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>   
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Microsoft Win32 컨트롤을 호스트하는 클래스 구현  
 이 샘플의 핵심은 ControlHost.cs 컨트롤을 실제로 호스트하는 클래스입니다. 상속 <xref:System.Windows.Interop.HwndHost>합니다. 두 개의 매개 변수, 높이 너비, 높이 및 너비에 해당 하는 생성자를 <xref:System.Windows.Controls.Border> ListBox 컨트롤을 호스팅하는 요소입니다. 일치 하는 컨트롤 항목의 크기 하도록 이러한 값은 나중에 사용 하는 <xref:System.Windows.Controls.Border> 요소입니다.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 또한 상수 집합도 있습니다. 이러한 상수는 주로 Winuser.h에서 이동 및 Win32 함수를 호출할 때 기존 이름을 사용할 수 있습니다.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>   
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>BuildWindowCore를 재정의하여 Microsoft Win32 창 만들기  
 페이지에서 호스팅될 창과 페이지 간에 연결을 설정 하는 Win32 창을 만들기 위해이 메서드를 재정의 합니다. 이 샘플에서는 ListBox 컨트롤을 호스트하므로 두 개의 창을 만듭니다. 첫 번째는 실제로 WPF 페이지에서 호스트 되는 창입니다. ListBox 컨트롤은 해당 창의 자식으로 만듭니다.  
  
 이 방법은 컨트롤에서 알림을 받는 프로세스를 간소화하기 위해서 사용합니다. <xref:System.Windows.Interop.HwndHost> 클래스를 사용 하면 호스트 하는 창으로 전송 된 메시지를 처리할 수 있습니다. Win32 호스트를 직접 제어 하는 경우 컨트롤의 내부 메시지 루프로 전송 메시지를 받게 됩니다. 컨트롤을 표시하고 메시지를 전송할 수 있지만 컨트롤이 해당 부모 창으로 전송된다는 알림은 받지 않습니다. 즉, 사용자가 컨트롤과 상호 작용하는 경우를 검색할 방법이 없습니다. 대신 호스트 창을 만들고 컨트롤을 해당 창의 자식으로 설정합니다. 이렇게 하면 컨트롤에서 전송한 알림을 포함하여 호스트 창에 대한 메시지를 처리할 수 있습니다. 호스트 창은 컨트롤에 대한 간단한 래퍼에 불과하므로 편의상 패키지를 ListBox 컨트롤이라고 합니다.  
  
<a name="create_the_window_and_listbox"></a>   
#### <a name="create-the-host-window-and-listbox-control"></a>호스트 창 및 ListBox 컨트롤 만들기  
 컨트롤에 대 한 호스트 창을 만들고 창 클래스를 등록 하 여 만들려면 PInvoke를 사용 하 고 등 수 있습니다. 그러나 미리 정의된 "정적" 창 클래스를 사용하여 창을 만드는 방법이 훨씬 더 간단합니다. 이 방법은 컨트롤에서 알림을 받기 위해 필요한 창 프로시저를 제공하며 최소한의 코딩이 필요합니다.  
  
 컨트롤의 HWND는 읽기 전용 속성을 통해 노출되므로 호스트 페이지에서 컨트롤로 메시지를 전송하는 데 사용할 수 있습니다.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 ListBox 컨트롤은 호스트 창의 자식으로 만듭니다. 두 창의 너비와 높이는 위에서 설명한 대로 생성자에 전달된 값으로 설정됩니다. 이렇게 하면 호스트 창과 컨트롤의 크기가 페이지에서 예약된 영역과 동일해집니다.  Windows를 만든 후 샘플 반환을 <xref:System.Runtime.InteropServices.HandleRef> 호스트 창의 HWND를 포함 하는 개체입니다.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>   
### <a name="implement-destroywindow-and-wndproc"></a>DestroyWindow 및 WndProc 구현  
 외에 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>를 재정의 해야 합니다 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 및 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 의 메서드는 <xref:System.Windows.Interop.HwndHost>합니다. 이 예제에서는 컨트롤에 대 한 메시지에서 처리 합니다 <xref:System.Windows.Interop.HwndHost.MessageHook> 처리기의 구현이 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 및 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 최소화 됩니다. 경우 <xref:System.Windows.Interop.HwndHost.WndProc%2A>로 설정 `handled` 에 `false` 하는 메시지가 처리 되지 않았음을 나타내는 0을 반환 합니다. 에 대 한 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>, 창을 제거 하면 됩니다.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>   
## <a name="host-the-control-on-the-page"></a>페이지에서 컨트롤 호스트  
 페이지의 컨트롤을 호스트 하려면 먼저 만들어야의 새 인스턴스를 `ControlHost` 클래스입니다. 컨트롤이 있는 border 요소의 너비와 높이가 전달 (`ControlHostElement`)에 `ControlHost` 생성자입니다. 이렇게 하면 ListBox 크기가 정확하게 조정됩니다. 할당 하 여 다음 페이지의 컨트롤을 호스트 합니다 `ControlHost` 개체를 <xref:System.Windows.Controls.Decorator.Child%2A> 호스트의 속성 <xref:System.Windows.Controls.Border>합니다.  
  
 샘플에는 처리기를 연결 합니다 <xref:System.Windows.Interop.HwndHost.MessageHook> 의 이벤트를 `ControlHost` 컨트롤에서 메시지를 수신 하 합니다. 이 이벤트는 호스트된 창으로 전송된 모든 메시지에 대해 발생됩니다. 이 경우 컨트롤의 알림을 포함하여 실제 ListBox 컨트롤을 래핑하는 창에 전송된 메시지입니다. 샘플에서는 SendMessage를 호출하여 컨트롤에서 정보를 가져오고 해당 내용을 수정합니다. 페이지가 컨트롤과 통신하는 방법에 대한 자세한 내용은 다음 섹션에서 설명합니다.  
  
> [!NOTE]
>  SendMessage에 대 한 두 PInvoke 선언 인지 확인 합니다. 하나를 사용 하므로이 작업이 필요 합니다 `wParam` 문자열 및 다른 전달할 매개 변수는 정수를 전달 하는 데 사용 합니다. 데이터가 올바르게 마샬링되도록 하려면 각 시그니처에 대해 별도의 선언이 필요합니다.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>   
## <a name="implement-communication-between-the-control-and-the-page"></a>컨트롤과 페이지 간의 통신 구현  
 Windows 메시지를 전송 하 여 해당 컨트롤을 조작 합니다. 컨트롤은 사용자가 호스트 창에 알림을 보내 상호 작용할 때 알려 줍니다. 합니다 [WPF에서 Win32 ListBox 컨트롤 호스팅](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) 샘플에는 몇 가지 예가이 과정을 제공 하는 UI를 포함 합니다.  
  
-   목록에 항목을 추가합니다.  
  
-   선택한 항목을 목록에서 삭제합니다.  
  
-   현재 선택한 항목의 텍스트를 표시합니다.  
  
-   목록의 항목 수를 표시합니다.  
  
 사용자 수 또한 항목을 선택 목록 상자에서를 클릭 하 여 기존 Win32 응용 프로그램에 대 한 것 처럼 합니다. 표시된 데이터는 사용자가 항목을 선택 또는 추가하여 목록 상자의 상태를 변경할 때마다 업데이트됩니다.  
  
 항목을 추가 하려면로 송신 되는 목록 상자는 [ `LB_ADDSTRING` 메시지](/windows/desktop/Controls/lb-addstring)합니다. 항목을 삭제 하려면 송신 [ `LB_GETCURSEL` ](/windows/desktop/Controls/lb-getcursel) 현재 선택 영역의 인덱스를 가져올 차례로 [ `LB_DELETESTRING` ](/windows/desktop/Controls/lb-deletestring) 항목을 삭제 합니다. 샘플도 보냅니다 [ `LB_GETCOUNT` ](/windows/desktop/Controls/lb-getcount), 반환된 된 값을 사용 하 여 항목의 수를 보여 주는 디스플레이를 업데이트 합니다. 이러한 두 인스턴스 [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) 이전 섹션에서 설명한 PInvoke 선언 중 하나를 사용 합니다.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 컨트롤을 전송 하 여 호스트 창에 알립니다 사용자가 항목을 선택 또는 선택 변경 하는 경우는 [ `WM_COMMAND` 메시지](/windows/desktop/menurc/wm-command), 시키는 <xref:System.Windows.Interop.HwndHost.MessageHook> 페이지에 대 한 이벤트입니다. 처리기는 호스트 창의 주 창 프로시저와 같은 정보를 수신합니다. 또한 부울 값에 대 한 참조가 전달 `handled`합니다. 설정한 `handled` 에 `true` 를 나타내고는 메시지를 처리 했으며 추가 처리가 필요 합니다.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command) 처리 하려는 이벤트 인지 여부를 확인 하려면 알림 ID를 확인 해야 하므로 다양 한 이유로에 전송 됩니다. 상위 단언에 포함 된 ID는 `wParam` 매개 변수입니다. 샘플 비트 연산자를 사용 하 여 ID를 추출 사용자에 대 한 선택을 수행 하거나, ID 됩니다 [ `LBN_SELCHANGE` ](/windows/desktop/Controls/lbn-selchange)합니다.  
  
 때 [ `LBN_SELCHANGE` ](/windows/desktop/Controls/lbn-selchange) 가 수신 샘플 인덱스를 가져옵니다 선택한 항목의 컨트롤을 전송 하 여를 [ `LB_GETCURSEL` 메시지](/windows/desktop/Controls/lb-getcursel)합니다. 텍스트를 가져오려면 먼저 만듭니다는 <xref:System.Text.StringBuilder>합니다. 보내십시오 컨트롤을 [ `LB_GETTEXT` 메시지](/windows/desktop/Controls/lb-gettext)합니다. 빈 전달 <xref:System.Text.StringBuilder> 개체는 `wParam` 매개 변수입니다. 때 [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) 반환 된 <xref:System.Text.StringBuilder> 선택한 항목의 텍스트가 포함 됩니다. 이 이용 [ `SendMessage` ](/windows/desktop/api/winuser/nf-winuser-sendmessage) 또 PInvoke 선언 해야 합니다.  
  
 마지막으로 설정 합니다 `handled` 에 `true` 메시지가 처리 된 것을 나타냅니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.Windows.Interop.HwndHost>
- [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)
- [연습: 내 첫 WPF 데스크톱 애플리케이션](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
