---
title: WPF에서 Win32 콘텐츠 호스팅
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: a9d9de1f35375e48981f895d096e46fd501ef8ec
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740367"
---
# <a name="hosting-win32-content-in-wpf"></a>WPF에서 Win32 콘텐츠 호스팅

## <a name="prerequisites"></a>전제 조건

[WPF 및 Win32 상호 운용성을](wpf-and-win32-interoperation.md)참조 하세요.

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a>System.windows.interop.hwndhost> (Windows Presentation Framework) 내의 Win32 연습

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 내에서 Win32 콘텐츠를 다시 사용 하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠와 같이 Hwnd 보이도록 <xref:System.Windows.Interop.HwndHost>를 사용 합니다. <xref:System.Windows.Interop.HwndSource>처럼 <xref:System.Windows.Interop.HwndHost>를 사용 하는 것은 간단 합니다. <xref:System.Windows.Interop.HwndHost>에서 파생 시키고 `BuildWindowCore` 및 `DestroyWindowCore` 메서드를 구현한 다음 <xref:System.Windows.Interop.HwndHost> 파생 클래스를 인스턴스화하고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 내에 저장 합니다.

Win32 논리가 이미 컨트롤로 패키지 된 경우 `BuildWindowCore` 구현은 `CreateWindow`에 대 한 호출 보다 약간 더 낮습니다. 예를 들어에서 C++Win32 LISTBOX 컨트롤을 만들려면 다음을 수행 합니다.

```cpp
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

하지만 Win32 코드가 자체 포함 되지 않은 것으로 가정 합니다. 그렇다면 Win32 대화 상자를 만들고 해당 콘텐츠를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 포함할 수 있습니다. 이 샘플은 Visual Studio 및 C++에서 이러한 작업을 수행 하는 것이 좋습니다. 하지만 다른 언어나 명령줄에서이 작업을 수행할 수도 있습니다.

C++ DLL 프로젝트로 컴파일되는 간단한 대화 상자를 사용 하 여 시작 합니다.

다음으로 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 대화 상자를 도입 합니다.

- 관리 되는 DLL (`/clr`)로 컴파일

- 대화 상자를 컨트롤로 전환

- `BuildWindowCore` 및 `DestroyWindowCore` 메서드를 사용 하 여 <xref:System.Windows.Interop.HwndHost>의 파생 클래스를 정의 합니다.

- `TranslateAccelerator` 메서드를 재정의 하 여 대화 상자 키를 처리 합니다.

- 탭 이동을 지원 하도록 `TabInto` 메서드 재정의

- 니모닉을 지원 하도록 `OnMnemonic` 메서드 재정의

- <xref:System.Windows.Interop.HwndHost> 하위 클래스를 인스턴스화하고 오른쪽 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 아래에 배치 합니다.

### <a name="turn-the-dialog-into-a-control"></a>대화 상자를 컨트롤로 전환

WS_CHILD 및 DS_CONTROL 스타일을 사용 하 여 대화 상자를 자식 HWND로 전환할 수 있습니다. 대화 상자가 정의 된 리소스 파일 (.rc)로 이동 하 여 대화 상자 정의의 시작 부분을 찾습니다.

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

두 번째 줄을 다음과 같이 변경 합니다.

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

이 작업은 자체 포함 컨트롤로 완전히 패키지 하지 않습니다. Win32가 특정 메시지를 처리할 수 있도록 `IsDialogMessage()`를 호출 해야 하지만 컨트롤 변경 내용으로 인해 해당 컨트롤을 다른 HWND 내에 배치 하는 간단한 방법이 제공 됩니다.

## <a name="subclass-hwndhost"></a>서브 클래스 System.windows.interop.hwndhost>

다음 네임스페이스를 가져옵니다.

```cpp
namespace ManagedCpp
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Input;
    using namespace System::Windows::Media;
    using namespace System::Runtime::InteropServices;
```

그런 다음 <xref:System.Windows.Interop.HwndHost>의 파생 클래스를 만들고 `BuildWindowCore` 및 `DestroyWindowCore` 메서드를 재정의 합니다.

```cpp
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

여기서는 `CreateDialog`을 사용 하 여 컨트롤 인 대화 상자를 만듭니다. 이 메서드는 DLL 내에서 호출 되는 첫 번째 메서드 중 하나 이므로 나중에 정의 하는 함수를 호출 하 여 `InitializeGlobals()`라고 합니다.

```cpp
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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a>TranslateAccelerator 메서드를 재정의 하 여 대화 상자 키를 처리 합니다.

지금이 샘플을 실행 한 경우를 표시 하는 대화 상자 컨트롤을 가져오지만 대화 상자를 기능 대화 상자로 만드는 모든 키보드 처리를 무시 합니다. 이제 `IKeyboardInputSink`에서 제공 하는 `TranslateAccelerator` 구현 (<xref:System.Windows.Interop.HwndHost> 구현 하는 인터페이스)을 재정의 해야 합니다. 이 메서드는 응용 프로그램이 WM_KEYDOWN를 받고 WM_SYSKEYDOWN 때 호출 됩니다.

```cpp
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

이는 한 부분에서 많은 코드 이므로 좀 더 자세한 설명을 사용할 수 있습니다. 먼저 및 C++ 매크로를 사용 C++ 하는 코드 winuser.h에 정의 된 `TranslateAccelerator`매크로가 이미 있는 것을 알고 있어야 합니다.

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

따라서 `TranslateAcceleratorW` 메서드가 아니라 `TranslateAccelerator` 메서드를 정의 해야 합니다.

마찬가지로 관리 되지 않는 winuser.h 메시지와 관리 되는 `Microsoft::Win32::MSG` 구조체가 모두 있습니다. `::` 연산자를 C++ 사용 하 여 두 가지를 구분할 수 있습니다.

```cpp
virtual bool TranslateAccelerator(System::Windows::Interop::MSG% msg,
    ModifierKeys modifiers) override
{
    ::MSG m = ConvertMessage(msg);
}

Both MSGs have the same data, but sometimes it is easier to work with the unmanaged definition, so in this sample you can define the obvious conversion routine:

```cpp
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

`TranslateAccelerator`로 돌아갑니다. 기본 원칙은 `IsDialogMessage` Win32 함수를 호출 하 여 가능한 한 많은 작업을 수행 하는 것 이지만 `IsDialogMessage`는 대화 상자 외부의 모든 항목에 액세스할 수 없습니다. 대화 상자를 표시 하는 사용자 탭으로 대화 상자에서 마지막 컨트롤을 지나서 탭 이동 하면 `IKeyboardInputSite::OnNoMoreStops`를 호출 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 부분으로 포커스를 설정 해야 합니다.

```cpp
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

마지막으로 `IsDialogMessage`를 호출합니다. 그러나 `TranslateAccelerator` 방법의 책임 중 하나는 키 입력을 처리 했는지 여부를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 알려 주는 것입니다. 이를 처리 하지 않은 경우 입력 이벤트는 응용 프로그램의 나머지 부분을 통해 터널링 및 버블링 할 수 있습니다. 여기서는 쿼크 키보드 messange 처리 및 Win32의 입력 아키텍처 특성을 노출 합니다. 그러나 `IsDialogMessage`는 특정 키 입력을 처리 하는지 여부에 관계 없이 반환 되지 않습니다. 또한 처리 하지 않아야 하는 키 입력에 대 한 `DispatchMessage()`를 호출 합니다.  따라서 `IsDialogMessage`를 리버스 엔지니어링 하 고이를 처리 하는 것으로 알고 있는 키에 대해서만 호출 해야 합니다.

```cpp
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

### <a name="override-tabinto-method-to-support-tabbing"></a>TabInto 메서드를 재정의 하 여 탭 이동 지원

`TranslateAccelerator`를 구현 했으므로 사용자는 대화 상자 내에서 탭 하 여 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램으로 이동할 수 있습니다. 그러나 사용자는 대화 상자로 다시 이동할 수 없습니다. 이를 해결 하려면 `TabInto`를 재정의 합니다.

```cpp
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

`TraversalRequest` 매개 변수는 탭 동작이 탭 인지 또는 이동 탭 인지를 알려 줍니다.

### <a name="override-onmnemonic-method-to-support-mnemonics"></a>니모닉을 지원 하도록 OnMnemonic 메서드 재정의

키보드 처리가 거의 완료 되었지만 누락 된 사항이 있습니다. 니모닉이 작동 하지 않습니다. 사용자가 alt + F를 누르면 포커스 doe가 "First name:" 입력란으로 이동 하지 않습니다. 따라서 `OnMnemonic` 메서드를 재정의 합니다.

```cpp
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

여기에서 `IsDialogMessage`를 호출 하지 않는 이유는 무엇 인가요?  이전에와 동일한 문제가 발생 했습니다. 코드에서 키 입력을 처리 했는지 여부를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 코드에 알릴 수 있어야 하며 `IsDialogMessage`는 수행할 수 없습니다. 또한 포커스가 있는 HWND가 대화 상자 내에 없는 경우 `IsDialogMessage`에서 니모닉 처리를 거부 하기 때문에 두 번째 문제가 있습니다.

### <a name="instantiate-the-hwndhost-derived-class"></a>System.windows.interop.hwndhost> 파생 클래스 인스턴스화

마지막으로, 이제 모든 키와 탭 지원이 준비 되었으므로 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 <xref:System.Windows.Interop.HwndHost>을 배치할 수 있습니다. 주 응용 프로그램을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]으로 작성 하는 경우에는 <xref:System.Windows.Interop.HwndHost>을 배치할 수 있는 빈 <xref:System.Windows.Controls.Border> 요소를 유지 하는 것이 가장 쉬운 방법입니다. 여기서는 `insertHwndHostHere`라는 <xref:System.Windows.Controls.Border>를 만듭니다.

```xaml
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

그런 다음 <xref:System.Windows.Interop.HwndHost>를 인스턴스화하고 <xref:System.Windows.Controls.Border>에 연결 하기 위해 코드 시퀀스에서 적절 한 장소를 찾는 것입니다. 이 예제에서는 <xref:System.Windows.Window> 파생 클래스에 대 한 생성자 내에 추가 합니다.

```csharp
public partial class Window1 : Window {
    public Window1() {
    }

    void Window1_Loaded(object sender, RoutedEventArgs e) {
        HwndHost host = new ManagedCpp.MyHwndHost();
        insertHwndHostHere.Child = host;
    }
}
```

다음을 제공 합니다.

![실행 중인 WPF 앱의 스크린샷](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a>참조

- [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)
