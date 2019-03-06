---
title: WPF에서 Win32 콘텐츠 호스팅
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: 9764b995cea0ba5c93625495509b7ee2dd8393ff
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57370035"
---
# <a name="hosting-win32-content-in-wpf"></a>WPF에서 Win32 콘텐츠 호스팅
## <a name="prerequisites"></a>전제 조건  
 참조 [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)합니다.  
  
## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>Windows Presentation Framework (HwndHost) 내에서 win32 연습  
 다시 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 내의 콘텐츠 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 사용 하 여 <xref:System.Windows.Interop.HwndHost>, Hwnd 같이 하는 컨트롤인 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠입니다.  같은 <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> 사용 하기는 간단 하지만:에서 파생 <xref:System.Windows.Interop.HwndHost> 하 고 구현 `BuildWindowCore` 및 `DestroyWindowCore` 메서드를 인스턴스화할에 <xref:System.Windows.Interop.HwndHost> 클래스를 파생 하 고 내부에 배치 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  
  
 경우에 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨트롤로 이미 패키지 된 논리에 `BuildWindowCore` 구현에 대 한 호출 보다 약간 더 `CreateWindow`합니다.  예를 들어 한 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 에서 LISTBOX 컨트롤 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:  
  
```  
virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {  
    HWND handle = CreateWindowEx(0, L"LISTBOX",   
    L"this is a Win32 listbox",  
    WS_CHILD | WS_VISIBLE | LBS_NOTIFY  
    | WS_VSCROLL | WS_BORDER,  
    0, 0, // x, y  
    30, 70, // height, width  
    (HWND) hwndParent.Handle.ToPointer(), // parent hwnd  
    0, // hmenu  
    0, // hinstance  
    0); // lparam  
  
    return HandleRef(this, IntPtr(handle));  
}  
  
virtual void DestroyWindowCore(HandleRef hwnd) override {  
    // HwndHost will dispose the hwnd for us  
}  
```  
  
 가정 하지만 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 코드는 독립적인 그렇게 하지? 따라서 만들 수 있는 경우는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 대화 상자 및 해당 내용을 더 큰 포함 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  이 샘플에서이 보여 줍니다 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 및 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]이지만 다른 언어에서 또는 명령줄에서이 작업을 수행할 수 이기도 합니다.  
  
 컴파일되는 간단한 대화 상자를 사용 하 여 시작 된 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 프로젝트입니다.  
  
 다음으로,이 대화 상자를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램:  
  
-   컴파일 합니다 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 관리 되는 (`/clr`)  
  
-   대화 상자 컨트롤에 설정  
  
-   파생된 클래스를 정의 <xref:System.Windows.Interop.HwndHost> 사용 하 여 `BuildWindowCore` 고 `DestroyWindowCore` 메서드  
  
-   재정의 `TranslateAccelerator` 대화 상자 키를 처리 하는 방법  
  
-   재정의 `TabInto` 탭 이동을 지 원하는 방법  
  
-   재정의 `OnMnemonic` 니모닉을 지원 방법  
  
-   인스턴스화하는 <xref:System.Windows.Interop.HwndHost> 서브 클래스 오른쪽 아래에 배치 하 고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소  
  
### <a name="turn-the-dialog-into-a-control"></a>대화 상자 컨트롤에 설정  
 WS_CHILD 및 DS_CONTROL 스타일 사용 HWND의 자식에 대화 상자를 설정할 수 있습니다.  대화가 정의 되어 있는 리소스 파일 (.rc)에 이동한 대화 상자의 정의의 시작 부분을 찾습니다.  
  
```  
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121  
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU  
```  
  
 두 번째 줄을 변경 합니다.  
  
```  
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL  
```  
  
 이 작업은 자체 포함 된 컨트롤에에 해당 패키지 완벽 하 게 호출 해야 `IsDialogMessage()` 있도록 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 특정 메시지를 처리할 수 있지만 컨트롤을 변경은 다른 HWND 내에서 이러한 컨트롤을 배치 하는 간단한 방법을 제공 합니다.  
  
## <a name="subclass-hwndhost"></a>서브 클래스 HwndHost  
 다음 네임스페이스를 가져옵니다.  
  
```  
namespace ManagedCpp  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Input;  
    using namespace System::Windows::Media;  
    using namespace System::Runtime::InteropServices;  
```  
  
 다음의 파생된 클래스를 만듭니다 <xref:System.Windows.Interop.HwndHost> 시키고 합니다 `BuildWindowCore` 및 `DestroyWindowCore` 메서드:  
  
```  
public ref class MyHwndHost : public HwndHost, IKeyboardInputSink {  
    private:  
        HWND dialog;  
  
    protected:   
        virtual HandleRef BuildWindowCore(HandleRef hwndParent) override {  
            InitializeGlobals();   
            dialog = CreateDialog(hInstance,   
                MAKEINTRESOURCE(IDD_DIALOG1),   
                (HWND) hwndParent.Handle.ToPointer(),  
                (DLGPROC) About);   
            return HandleRef(this, IntPtr(dialog));  
        }  
  
        virtual void DestroyWindowCore(HandleRef hwnd) override {  
            // hwnd will be disposed for us  
        }  
```  
  
 여기서 사용은 `CreateDialog` 컨트롤이 실제로 대화 상자를 만듭니다.  내에서 호출 하는 첫 번째 메서드 중 하나 이므로이 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], 몇 가지 일반적인 수행 해야 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 나중에 정의 된 함수를 호출 하 여 초기화 라는 `InitializeGlobals()`:  
  
```  
bool initialized = false;  
    void InitializeGlobals() {  
        if (initialized) return;  
        initialized = true;  
  
        // TODO: Place code here.  
        MSG msg;  
        HACCEL hAccelTable;  
  
        // Initialize global strings  
        LoadString(hInstance, IDS_APP_TITLE, szTitle, MAX_LOADSTRING);  
        LoadString(hInstance, IDC_TYPICALWIN32DIALOG, szWindowClass, MAX_LOADSTRING);  
        MyRegisterClass(hInstance);  
```  
  
### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>TranslateAccelerator 대화 상자 키를 처리 하는 메서드를 재정의 합니다.  
 이 샘플을 실행 하는 경우 이제 표시 하는 대화 상자 컨트롤 얻지만 처리 하는 키보드의 모든 대화 상자 기능 대화 상자는 무시 됩니다.  재정의 해야 합니다 `TranslateAccelerator` 구현 (에서 제공 되는 `IKeyboardInputSink`, 인터페이스는 <xref:System.Windows.Interop.HwndHost> 구현).  이 메서드는 WM_KEYDOWN 및 WM_SYSKEYDOWN 응용 프로그램이 수신 하는 경우 호출 됩니다.  
  
```  
#undef TranslateAccelerator  
        virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
            ModifierKeys modifiers) override   
        {  
            ::MSG m = ConvertMessage(msg);  
  
            // Win32's IsDialogMessage() will handle most of our tabbing, but doesn't know   
            // what to do when it reaches the last tab stop  
            if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {  
                HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
                HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
                TraversalRequest^ request = nullptr;  
  
                if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {  
                    // this code should work, but there’s a bug with interop shift-tab in current builds                      
                    request = gcnew TraversalRequest(FocusNavigationDirection::Last);  
                }  
                else if (!GetKeyState(VK_SHIFT) && GetFocus() == lastTabStop) {  
                    request = gcnew TraversalRequest(FocusNavigationDirection::Next);  
                }  
  
                if (request != nullptr)  
                    return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);  
  
            }  
  
            // Only call IsDialogMessage for keys it will do something with.  
            if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {  
                switch (m.wParam) {  
                    case VK_TAB:  
                    case VK_LEFT:  
                    case VK_UP:  
                    case VK_RIGHT:  
                    case VK_DOWN:  
                    case VK_EXECUTE:  
                    case VK_RETURN:  
                    case VK_ESCAPE:  
                    case VK_CANCEL:  
                        IsDialogMessage(dialog, &m);  
                        // IsDialogMessage should be called ProcessDialogMessage --  
                        // it processes messages without ever really telling you  
                        // if it handled a specific message or not  
                        return true;  
                }  
            }  
  
            return false; // not a key we handled  
        }  
```  
  
 이 과정은 한 부분에서 코드의 보다 자세한 설명을 사용 하 여 수 있도록 합니다.  먼저 사용 하는 코드가 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] 하 고 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] 매크로; 라는 매크로 이미 있는지 유의 해야 `TranslateAccelerator`, winuser.h에 정의 되어 있는:  
  
```  
#define TranslateAccelerator  TranslateAcceleratorW  
```  
  
 정의 해야는 `TranslateAccelerator` 메서드 및 not을 `TranslateAcceleratorW` 메서드.  
  
 마찬가지로, 방법이 관리 되지 않는 winuser.h 메시지와 관리 되는 `Microsoft::Win32::MSG` 구조체입니다.  사용 하 여 구분할 수 있습니다 합니다 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` 연산자입니다.  
  
```  
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,   
    ModifierKeys modifiers) override   
{  
    ::MSG m = ConvertMessage(msg);  
```  
  
 모두 MSGs 동일한 데이터를 갖지만이 샘플에서 명확한 변환 루틴을 정의할 수 있습니다 관리 되지 않는 정의 함께 사용 하도록 쉽게:  
  
```  
::MSG ConvertMessage(System::Windows::Interop::MSG% msg) {  
    ::MSG m;  
    m.hwnd = (HWND) msg.hwnd.ToPointer();  
    m.lParam = (LPARAM) msg.lParam.ToPointer();  
    m.message = msg.message;  
    m.wParam = (WPARAM) msg.wParam.ToPointer();  
  
    m.time = msg.time;  
  
    POINT pt;  
    pt.x = msg.pt_x;  
    pt.y = msg.pt_y;  
    m.pt = pt;  
  
    return m;  
}  
```  
  
 다시 `TranslateAccelerator`입니다.  기본 원칙은 호출 하는 것을 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수 `IsDialogMessage` 최대한 많은 작업을 수행 하지만 `IsDialogMessage` 대화 상자 외부 항목에 액세스할 수 없습니다. 포커스를 설정 해야 하는 대화 상자에서 탭 이동 하면 관련 사용자 탭 대화 상자에서 마지막 컨트롤을 실행 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 를 호출 하 여 부분 `IKeyboardInputSite::OnNoMoreStops`합니다.  
  
```  
// Win32's IsDialogMessage() will handle most of the tabbing, but doesn't know   
// what to do when it reaches the last tab stop  
if (m.message == WM_KEYDOWN && m.wParam == VK_TAB) {  
    HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
    HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
    TraversalRequest^ request = nullptr;  
  
    if (GetKeyState(VK_SHIFT) && GetFocus() == firstTabStop) {  
        request = gcnew TraversalRequest(FocusNavigationDirection::Last);  
    }  
    else if (!GetKeyState(VK_SHIFT) && GetFocus() ==  lastTabStop) { {  
        request = gcnew TraversalRequest(FocusNavigationDirection::Next);  
    }  
  
    if (request != nullptr)  
        return ((IKeyboardInputSink^) this)->KeyboardInputSite->OnNoMoreTabStops(request);  
}  
```  
  
 마지막으로 `IsDialogMessage`를 호출합니다.  맡는 역할 중 하나만 제외 하 고는 `TranslateAccelerator` 메서드는 지시 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 했으면 처리 여부. 입력된 이벤트를 처리 하지 않은 경우 터널링 및 응용 프로그램의 rest 통해 버블링 합니다. 이때를 노출할 수의 입력된 아키텍처의 특성과 키보드 기초적인 처리 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]합니다. 아쉽게도 `IsDialogMessage` 특정 키 입력을 처리 하는지 여부를 어떤 방식으로 반환 하지 않습니다.  호출 설상가상으로 `DispatchMessage()` 처리 하지 않도록 하는 키 입력에!  리버스 엔지니어링 해야 하므로 `IsDialogMessage`만 알고 있는 키를 처리 하는 대 한 호출 합니다.  
  
```  
// Only call IsDialogMessage for keys it will do something with.  
if (msg.message == WM_SYSKEYDOWN || msg.message == WM_KEYDOWN) {  
    switch (m.wParam) {  
        case VK_TAB:  
        case VK_LEFT:  
        case VK_UP:  
        case VK_RIGHT:  
        case VK_DOWN:  
        case VK_EXECUTE:  
        case VK_RETURN:  
        case VK_ESCAPE:  
        case VK_CANCEL:  
            IsDialogMessage(dialog, &m);  
            // IsDialogMessage should be called ProcessDialogMessage --  
            // it processes messages without ever really telling you  
            // if it handled a specific message or not  
            return true;  
    }  
```  
  
### <a name="override-tabinto-method-to-support-tabbing"></a>지원 탭을 TabInto 메서드를 재정의 합니다.  
 구현한 했으므로 `TranslateAccelerator`, 사용자는 대화 상자 내에서 관련 탭 수 상자와 탭 외부로 큼에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  하지만 사용자는 대화 상자를 다시 탭 수 없습니다.  이 해결 하려면 재정의 `TabInto`:  
  
```  
public:   
    virtual bool TabInto(TraversalRequest^ request) override {  
        if (request->FocusNavigationDirection == FocusNavigationDirection::Last) {  
            HWND lastTabStop = GetDlgItem(dialog, IDCANCEL);  
            SetFocus(lastTabStop);  
        }  
        else {  
            HWND firstTabStop = GetDlgItem(dialog, IDC_EDIT1);  
            SetFocus(firstTabStop);  
        }  
        return true;  
    }  
```  
  
 `TraversalRequest` 매개 변수 알려 탭 작업 탭 또는 shift 탭 인지 합니다.  
  
### <a name="override-onmnemonic-method-to-support-mnemonics"></a>니모닉을 지원 하도록 OnMnemonic 메서드 재정의  
 키보드 처리는 거의 완료 되었지만 한 가지 빠진 니모닉 작동 하지 않습니다.  사용자가 alt-F를 누르면 포커스가 doe 이동 하지는 "이름:" 입력란입니다. 따라서 재정의 하 여 `OnMnemonic` 메서드:  
  
```  
virtual bool OnMnemonic(System::Windows::Interop::MSG% msg, ModifierKeys modifiers) override {  
    ::MSG m = ConvertMessage(msg);  
  
    // If it's one of our mnemonics, set focus to the appropriate hwnd  
    if (msg.message == WM_SYSCHAR && GetKeyState(VK_MENU /*alt*/)) {  
        int dialogitem = 9999;  
        switch (m.wParam) {  
            case 's': dialogitem = IDOK; break;  
            case 'c': dialogitem = IDCANCEL; break;  
            case 'f': dialogitem = IDC_EDIT1; break;  
            case 'l': dialogitem = IDC_EDIT2; break;  
            case 'p': dialogitem = IDC_EDIT3; break;  
            case 'a': dialogitem = IDC_EDIT4; break;  
            case 'i': dialogitem = IDC_EDIT5; break;  
            case 't': dialogitem = IDC_EDIT6; break;  
            case 'z': dialogitem = IDC_EDIT7; break;  
        }  
        if (dialogitem != 9999) {  
            HWND hwnd = GetDlgItem(dialog, dialogitem);  
            SetFocus(hwnd);  
            return true;  
        }  
    }  
    return false; // key unhandled  
};  
```  
  
 호출 하지 않는 이유 `IsDialogMessage` 여기?  -하기 전에 해야 할 때 알릴 수 있으려면 동일한 문제가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 코드를 키 입력을 처리 하는지 여부를 코드 및 `IsDialogMessage` 그렇게 할 수 없습니다.  이기도 한 두 번째 문제 때문에 `IsDialogMessage` 대화 상자 내에서 포커스가 있는 HWND 없으면 니모닉 처리를 거부 합니다.  
  
### <a name="instantiate-the-hwndhost-derived-class"></a>인스턴스화할 HwndHost 파생 클래스  
 마지막으로, 이제 모든 키 및 탭 지원이 위치에 넣을 수 있습니다 하 <xref:System.Windows.Interop.HwndHost> 를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.  주 응용 프로그램 작성 된 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 빈 유지 하는 적절 한 위치에 배치 하는 가장 쉬운 방법은 <xref:System.Windows.Controls.Border> 실시 하려는 요소를 <xref:System.Windows.Interop.HwndHost>입니다.  만들려면 여기를 <xref:System.Windows.Controls.Border> 라는 `insertHwndHostHere`:  
  
```  
<Window x:Class="WPFApplication1.Window1"  
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
    Title="Windows Presentation Framework Application"  
    Loaded="Window1_Loaded"  
    >  
    <StackPanel>  
        <Button Content="WPF button"/>  
        <Border Name="insertHwndHostHere" Height="200" Width="500"/>  
        <Button Content="WPF button"/>  
    </StackPanel>  
</Window>  
```  
  
 다음에 좋은 출발점이를 인스턴스화하는 코드 시퀀스에서 찾을 수는 <xref:System.Windows.Interop.HwndHost> 연결 된 <xref:System.Windows.Controls.Border>합니다.  이 예에서 배치할 것에 대 한 생성자 내부를 <xref:System.Windows.Window> 클래스를 파생 합니다.  
  
```  
public partial class Window1 : Window {  
    public Window1() {  
    }  
  
    void Window1_Loaded(object sender, RoutedEventArgs e) {  
        HwndHost host = new ManagedCpp.MyHwndHost();  
        insertHwndHostHere.Child = host;  
    }  
}  
```  
  
 하면:  
  
 ![WPF 응용 프로그램 스크린 샷](./media/interoparch09.PNG "InteropArch09")  
  
## <a name="see-also"></a>참고자료
- [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)
