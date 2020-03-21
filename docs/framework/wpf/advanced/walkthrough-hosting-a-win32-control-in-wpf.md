---
title: WPF에서 Win32 컨트롤 호스트
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting Win32 control in WPF [WPF]
- Win32 code [WPF], WPF interoperation
ms.assetid: a676b1eb-fc55-4355-93ab-df840c41cea0
ms.openlocfilehash: 5185e60640c652b79bd105db54830ac3acc57129
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186749"
---
# <a name="walkthrough-host-a-win32-control-in-wpf"></a>연습: WPF에서 Win32 컨트롤 호스트
WPF(Windows 프레젠테이션 파운데이션)는 응용 프로그램을 만들기 위한 풍부한 환경을 제공합니다. 그러나 Win32 코드에 상당한 투자가 있는 경우 완전히 다시 작성하는 대신 WPF 응용 프로그램에서 해당 코드 중 적어도 일부를 재사용하는 것이 더 효과적일 수 있습니다. WPF는 WPF 페이지에서 Win32 창을 호스팅하기 위한 간단한 메커니즘을 제공합니다.  
  
 이 항목에서는 Win32 목록 상자 컨트롤을 호스트하는 [WPF 샘플에서 Win32 ListBox 컨트롤을 호스팅하는](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)응용 프로그램을 안내합니다. 이 일반 절차는 Win32 창을 호스팅하도록 확장할 수 있습니다.  

<a name="requirements"></a>
## <a name="requirements"></a>요구 사항  
 이 항목에서는 WPF 및 Windows API 프로그래밍에 대한 기본적인 친숙함을 가정합니다. WPF 프로그래밍에 대한 기본 소개는 [시작 하기](../getting-started/index.md)를 참조하십시오. Windows API 프로그래밍에 대한 소개는 특히 찰스 페츨의 *프로그래밍 윈도우와* 같은 주제에 관한 수많은 책을 참조하십시오.  
  
 이 항목과 함께 제공되는 샘플은 C#에서 구현되므로 PInvoke(플랫폼 호출 서비스)를 사용하여 Windows API에 액세스합니다. PInvoke에 대한 몇 가지 친숙함은 도움이되지만 필수적지는 않습니다.  
  
> [!NOTE]
> 이 항목에는 관련 샘플의 많은 코드 예제가 포함되어 있습니다. 그러나 가독성을 위해 전체 샘플 코드를 포함하지는 않습니다. [WPF 샘플에서 Win32 ListBox 컨트롤 호스팅에서](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control)전체 코드를 얻거나 볼 수 있습니다.  
  
<a name="basic_procedure"></a>
## <a name="the-basic-procedure"></a>기본 절차  
 이 섹션에서는 WPF 페이지에서 Win32 창을 호스팅하기 위한 기본 절차에 대해 간략하게 설명합니다. 나머지 섹션에서는 각 단계를 자세히 설명합니다.  
  
 기본 호스팅 절차는 다음과 같습니다.  
  
1. 창을 호스트하는 WPF 페이지를 구현합니다. 한 가지 방법은 <xref:System.Windows.Controls.Border> 호스트된 창에 대한 페이지의 섹션을 예약하는 요소를 만드는 것입니다.  
  
2. <xref:System.Windows.Interop.HwndHost>에서 상속하는 컨트롤을 호스트하는 클래스를 구현합니다.  
  
3. 해당 클래스에서 클래스 <xref:System.Windows.Interop.HwndHost> 멤버를 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>재정의합니다.  
  
4. WPF 페이지를 포함 하는 창의 자식으로 호스팅된 창을 만듭니다. 기존의 WPF 프로그래밍을 명시적으로 사용할 필요는 없지만 호스팅 페이지는 핸들(HWND)이 있는 창입니다. 메서드의 매개 변수를 `hwndParent` 통해 HWND 페이지를 받습니다. <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A> 호스트된 창은 이 HWND의 자식으로 만들어야 합니다.  
  
5. 호스트 창을 만들었으면 호스트된 창의 HWND를 반환합니다. 하나 이상의 Win32 컨트롤을 호스트하려는 경우 일반적으로 HWND의 자식으로 호스트 창을 만들고 해당 호스트 창의 컨트롤 자식을 만듭니다. 호스트 창에서 컨트롤을 래핑하면 WPF 페이지가 HWND 경계에서 알림과 함께 특정 Win32 문제를 처리하는 컨트롤에서 알림을 받을 수 있는 간단한 방법을 제공합니다.  
  
6. 자식 컨트롤의 알림과 같이 호스트 창으로 전송되는 선택한 메시지를 처리합니다. 두 가지 방법으로 이 작업을 수행할 수 있습니다.  
  
    - 호스팅 클래스에서 메시지를 처리하려면 클래스의 메서드를 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 재정의합니다. <xref:System.Windows.Interop.HwndHost>  
  
    - WPF가 메시지를 처리하도록 하려면 코드 숨결에서 <xref:System.Windows.Interop.HwndHost> 클래스 <xref:System.Windows.Interop.HwndHost.MessageHook> 이벤트를 처리합니다. 이 이벤트는 호스트된 창에서 받은 모든 메시지에 대해 발생합니다. 이 옵션을 선택하면 계속 재정의해야 <xref:System.Windows.Interop.HwndHost.WndProc%2A>하지만 최소한의 구현만 있으면 됩니다.  
  
7. 의 메서드 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 및 메서드를 재정의합니다. <xref:System.Windows.Interop.HwndHost> <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 계약을 충족하기 위해 이러한 메서드를 <xref:System.Windows.Interop.HwndHost> 재정의해야 하지만 최소한의 구현만 제공해야 할 수 있습니다.  
  
8. 코드 숨김 파일에서 컨트롤 호스팅 클래스의 인스턴스를 만들고 창을 <xref:System.Windows.Controls.Border> 호스트하기 위한 요소의 자식으로 만듭니다.  
  
9. Microsoft Windows 메시지를 보내고 컨트롤에서 보낸 알림과 같은 자식 창에서 메시지를 처리하여 호스팅된 창과 통신합니다.  
  
<a name="page_layout"></a>
## <a name="implement-the-page-layout"></a>페이지 레이아웃 구현  
 ListBox 컨트롤을 호스트 하는 WPF 페이지의 레이아웃은 두 리전으로 구성 됩니다. 페이지 왼쪽에는 Win32 컨트롤을 조작할 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 수 있는 여러 WPF 컨트롤이 있습니다. 페이지의 오른쪽 위에는 호스트된 ListBox 컨트롤에 대한 사각형 영역이 있습니다.  
  
 이 레이아웃을 구현하는 코드는 매우 간단합니다. 루트 요소는 두 <xref:System.Windows.Controls.DockPanel> 개의 자식 요소가 있는 a입니다. 첫 번째는 <xref:System.Windows.Controls.Border> ListBox 컨트롤을 호스트하는 요소입니다. 이 요소는 페이지의 오른쪽 위에 있는 200x200 정사각형을 사용합니다. 두 번째는 <xref:System.Windows.Controls.StackPanel> 정보를 표시하고 노출된 상호 운용 속성을 설정하여 ListBox 컨트롤을 조작할 수 있는 WPF 컨트롤 집합을 포함하는 요소입니다. <xref:System.Windows.Controls.StackPanel>의 자식 요소 각각에 대해 , 이러한 요소가 무엇인지 또는 수행하는 작업에 대한 세부 사항에 사용되는 다양한 요소에 대한 참조 자료를 참조하십시오.  
  
 [!code-xaml[WPFHostingWin32Control#WPFUI](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml#wpfui)]  
  
<a name="host_class"></a>
## <a name="implement-a-class-to-host-the-microsoft-win32-control"></a>Microsoft Win32 컨트롤을 호스트하는 클래스 구현  
 이 샘플의 핵심은 ControlHost.cs 컨트롤을 실제로 호스트하는 클래스입니다. <xref:System.Windows.Interop.HwndHost>에서 상속받습니다. 생성자는 ListBox 컨트롤을 호스팅하는 <xref:System.Windows.Controls.Border> 요소의 높이와 너비에 해당하는 높이와 너비라는 두 개의 매개 변수를 사용합니다. 이러한 값은 나중에 컨트롤의 크기가 요소와 <xref:System.Windows.Controls.Border> 일치하도록 하는 데 사용됩니다.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostclass)]
 [!code-vb[WPFHostingWin32Control#ControlHostClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostclass)]  
  
 또한 상수 집합도 있습니다. 이러한 상수는 주로 Winuser.h에서 가져온 것이며 Win32 함수를 호출할 때 기존 이름을 사용할 수 있습니다.  
  
 [!code-csharp[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#controlhostconstants)]
 [!code-vb[WPFHostingWin32Control#ControlHostConstants](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#controlhostconstants)]  
  
<a name="buildwindowcore"></a>
### <a name="override-buildwindowcore-to-create-the-microsoft-win32-window"></a>BuildWindowCore를 재정의하여 Microsoft Win32 창 만들기  
 이 메서드를 재정의하여 페이지에서 호스팅할 Win32 창을 만들고 창과 페이지 간에 연결합니다. 이 샘플에서는 ListBox 컨트롤을 호스트하므로 두 개의 창을 만듭니다. 첫 번째는 WPF 페이지에서 실제로 호스팅되는 창입니다. ListBox 컨트롤은 해당 창의 자식으로 만듭니다.  
  
 이 방법은 컨트롤에서 알림을 받는 프로세스를 간소화하기 위해서 사용합니다. 클래스를 <xref:System.Windows.Interop.HwndHost> 사용하면 호스팅하는 창으로 전송된 메시지를 처리할 수 있습니다. Win32 컨트롤을 직접 호스트하는 경우 컨트롤의 내부 메시지 루프로 전송된 메시지를 받게 됩니다. 컨트롤을 표시하고 메시지를 전송할 수 있지만 컨트롤이 해당 부모 창으로 전송된다는 알림은 받지 않습니다. 즉, 사용자가 컨트롤과 상호 작용하는 경우를 검색할 방법이 없습니다. 대신 호스트 창을 만들고 컨트롤을 해당 창의 자식으로 설정합니다. 이렇게 하면 컨트롤에서 전송한 알림을 포함하여 호스트 창에 대한 메시지를 처리할 수 있습니다. 호스트 창은 컨트롤에 대한 간단한 래퍼에 불과하므로 편의상 패키지를 ListBox 컨트롤이라고 합니다.  
  
<a name="create_the_window_and_listbox"></a>
#### <a name="create-the-host-window-and-listbox-control"></a>호스트 창 및 ListBox 컨트롤 만들기  
 PInvoke를 사용하여 창 클래스를 만들고 등록하여 컨트롤에 대한 호스트 창을 만들 수 있습니다. 그러나 미리 정의된 "정적" 창 클래스를 사용하여 창을 만드는 방법이 훨씬 더 간단합니다. 이 방법은 컨트롤에서 알림을 받기 위해 필요한 창 프로시저를 제공하며 최소한의 코딩이 필요합니다.  
  
 컨트롤의 HWND는 읽기 전용 속성을 통해 노출되므로 호스트 페이지에서 컨트롤로 메시지를 전송하는 데 사용할 수 있습니다.  
  
 [!code-csharp[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#intptrproperty)]
 [!code-vb[WPFHostingWin32Control#IntPtrProperty](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#intptrproperty)]  
  
 ListBox 컨트롤은 호스트 창의 자식으로 만듭니다. 두 창의 너비와 높이는 위에서 설명한 대로 생성자에 전달된 값으로 설정됩니다. 이렇게 하면 호스트 창과 컨트롤의 크기가 페이지에서 예약된 영역과 동일해집니다.  창을 만든 후 샘플은 <xref:System.Runtime.InteropServices.HandleRef> 호스트 창의 HWND를 포함하는 개체를 반환합니다.  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcore)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCore](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcore)]  
  
 [!code-csharp[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#buildwindowcorehelper)]
 [!code-vb[WPFHostingWin32Control#BuildWindowCoreHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#buildwindowcorehelper)]  
  
<a name="destroywindow_wndproc"></a>
### <a name="implement-destroywindow-and-wndproc"></a>DestroyWindow 및 WndProc 구현  
 은 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>의 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 메서드와 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 메서드도 재정의해야 <xref:System.Windows.Interop.HwndHost>합니다. 이 예제에서는 컨트롤에 대 한 메시지는 <xref:System.Windows.Interop.HwndHost.MessageHook> 처리기에 의해 <xref:System.Windows.Interop.HwndHost.WndProc%2A> 처리 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 되므로 구현 및 최소. 의 <xref:System.Windows.Interop.HwndHost.WndProc%2A>경우 메시지가 `handled` 처리되지 않음을 나타내고 0을 반환하도록 `false` 설정합니다. 에 <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A>대한, 단순히 창을 파괴.  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroy)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroy](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroy)]  
  
 [!code-csharp[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/ControlHost.cs#wndprocdestroyhelper)]
 [!code-vb[WPFHostingWin32Control#WndProcDestroyHelper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/ControlHost.vb#wndprocdestroyhelper)]  
  
<a name="host_the_control"></a>
## <a name="host-the-control-on-the-page"></a>페이지에서 컨트롤 호스트  
 페이지에서 컨트롤을 호스트하려면 먼저 클래스의 새 인스턴스를 `ControlHost` 만듭니다. 컨트롤() 컨트롤을`ControlHostElement`포함하는 테두리 요소의 높이와 `ControlHost` 너비를 생성자에게 전달합니다. 이렇게 하면 ListBox 크기가 정확하게 조정됩니다. 그런 다음 `ControlHost` 개체를 호스트의 <xref:System.Windows.Controls.Decorator.Child%2A> <xref:System.Windows.Controls.Border>속성에 할당하여 페이지에서 컨트롤을 호스트합니다.  
  
 샘플은 컨트롤에서 메시지를 <xref:System.Windows.Interop.HwndHost.MessageHook> 받을 `ControlHost` 이벤트의 처리기를 연결합니다. 이 이벤트는 호스트된 창으로 전송된 모든 메시지에 대해 발생됩니다. 이 경우 컨트롤의 알림을 포함하여 실제 ListBox 컨트롤을 래핑하는 창에 전송된 메시지입니다. 샘플에서는 SendMessage를 호출하여 컨트롤에서 정보를 가져오고 해당 내용을 수정합니다. 페이지가 컨트롤과 통신하는 방법에 대한 자세한 내용은 다음 섹션에서 설명합니다.  
  
> [!NOTE]
> SendMessage에 대한 두 개의 PInvoke 선언이 있습니다. 하나는 매개 변수를 `wParam` 사용하여 문자열을 전달하고 다른 하나는 정수전달을 사용하기 때문에 필요합니다. 데이터가 올바르게 마샬링되도록 하려면 각 시그니처에 대해 별도의 선언이 필요합니다.  
  
 [!code-csharp[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#hostwindowclass)]
 [!code-vb[WPFHostingWin32Control#HostWindowClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#hostwindowclass)]  
  
 [!code-csharp[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#controlmsgfiltersendmessage)]
 [!code-vb[WPFHostingWin32Control#ControlMsgFilterSendMessage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#controlmsgfiltersendmessage)]  
  
<a name="communication"></a>
## <a name="implement-communication-between-the-control-and-the-page"></a>컨트롤과 페이지 간의 통신 구현  
 Windows 메시지를 보내 컨트롤을 조작합니다. 컨트롤은 사용자가 호스트 창에 알림을 보내 상호 작용할 때 알려 줍니다. WPF 에서 [Win32 ListBox 컨트롤 호스팅](https://github.com/Microsoft/WPF-Samples/tree/master/Migration%20and%20Interoperability/WPFHostingWin32Control) 에는 작동 방식에 대한 몇 가지 예제를 제공하는 UI가 포함되어 있습니다.  
  
- 목록에 항목을 추가합니다.  
  
- 선택한 항목을 목록에서 삭제합니다.  
  
- 현재 선택한 항목의 텍스트를 표시합니다.  
  
- 목록의 항목 수를 표시합니다.  
  
 사용자는 또한 목록 상자에 있는 항목을 클릭하여 선택할 수 있습니다., 그들은 기존의 Win32 응용 프로그램에 대 한 것 처럼. 표시된 데이터는 사용자가 항목을 선택 또는 추가하여 목록 상자의 상태를 변경할 때마다 업데이트됩니다.  
  
 항목을 추가하려면 목록 상자에 [ `LB_ADDSTRING` 메시지를](/windows/desktop/Controls/lb-addstring)보냅니다. 항목을 삭제하려면 [`LB_GETCURSEL`](/windows/desktop/Controls/lb-getcursel) 현재 선택 항목의 인덱스를 [`LB_DELETESTRING`](/windows/desktop/Controls/lb-deletestring) 가져옵니다. 또한 샘플은 [`LB_GETCOUNT`](/windows/desktop/Controls/lb-getcount)을 보내고 반환된 값을 사용하여 항목 수를 표시하는 디스플레이를 업데이트합니다. 이전 섹션에서 [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) 설명한 PInvoke 선언 중 하나를 사용하는 두 인스턴스 모두.  
  
 [!code-csharp[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFHostingWin32Control/CSharp/Page1.xaml.cs#appenddeletetext)]
 [!code-vb[WPFHostingWin32Control#AppendDeleteText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFHostingWin32Control/VisualBasic/Page1.xaml.vb#appenddeletetext)]  
  
 사용자가 항목을 선택하거나 선택을 변경하면 컨트롤은 호스트 창에 [ `WM_COMMAND` 메시지를](/windows/desktop/menurc/wm-command)보내 페이지에 대한 <xref:System.Windows.Interop.HwndHost.MessageHook> 이벤트를 발생시도록 합니다. 처리기는 호스트 창의 주 창 프로시저와 같은 정보를 수신합니다. 또한 부울 값에 대한 참조를 `handled`전달합니다. 메시지를 `handled` 처리했으며 추가 처리가 필요하지 `true` 않음을 나타내도록 설정합니다.  
  
 [`WM_COMMAND`](/windows/desktop/menurc/wm-command)여러 가지 이유로 전송되므로 처리하려는 이벤트인지 여부를 확인하려면 알림 ID를 검사해야 합니다. ID는 매개 변수의 높은 `wParam` 단어에 포함되어 있습니다. 샘플은 비트 연산자에서 ID를 추출합니다. 사용자가 선택한 항목을 만들거나 변경한 경우 [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange)ID가 됩니다.  
  
 수신되면 샘플은 컨트롤에 [ `LB_GETCURSEL` 메시지를](/windows/desktop/Controls/lb-getcursel)전송하여 선택한 항목의 인덱스를 가져옵니다. [`LBN_SELCHANGE`](/windows/desktop/Controls/lbn-selchange) 텍스트를 얻으려면 먼저 <xref:System.Text.StringBuilder>을 만듭니다. 그런 다음 컨트롤에 [ `LB_GETTEXT` 메시지를](/windows/desktop/Controls/lb-gettext)보냅니다. 빈 <xref:System.Text.StringBuilder> 개체를 매개 `wParam` 변수로 전달합니다. 반환 [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) 할 <xref:System.Text.StringBuilder> 때 선택한 항목의 텍스트가 포함됩니다. 이러한 사용에는 [`SendMessage`](/windows/desktop/api/winuser/nf-winuser-sendmessage) 또 다른 PInvoke 선언이 필요합니다.  
  
 마지막으로 메시지가 `handled` `true` 처리되었음을 나타내도록 설정합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Interop.HwndHost>
- [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)
- [연습: 첫 번째 WPF 데스크톱 응용 프로그램](../getting-started/walkthrough-my-first-wpf-desktop-application.md)
