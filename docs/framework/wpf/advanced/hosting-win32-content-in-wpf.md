---
title: Win32 콘텐츠 호스팅
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: b3113d9f3146e1590363dc9db6f751a429dda74b
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747017"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="3805d-102">WPF에서 Win32 콘텐츠 호스팅</span><span class="sxs-lookup"><span data-stu-id="3805d-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3805d-103">전제 조건</span><span class="sxs-lookup"><span data-stu-id="3805d-103">Prerequisites</span></span>

<span data-ttu-id="3805d-104">[WPF 및 Win32 상호 운용성을](wpf-and-win32-interoperation.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3805d-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="3805d-105">System.windows.interop.hwndhost> (Windows Presentation Framework) 내의 Win32 연습</span><span class="sxs-lookup"><span data-stu-id="3805d-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="3805d-106">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 내에서 Win32 콘텐츠를 다시 사용 하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠와 같이 Hwnd 보이도록 <xref:System.Windows.Interop.HwndHost>를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-106">To reuse Win32 content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="3805d-107"><xref:System.Windows.Interop.HwndSource>처럼 <xref:System.Windows.Interop.HwndHost>를 사용 하는 것은 간단 합니다. <xref:System.Windows.Interop.HwndHost>에서 파생 시키고 `BuildWindowCore` 및 `DestroyWindowCore` 메서드를 구현한 다음 <xref:System.Windows.Interop.HwndHost> 파생 클래스를 인스턴스화하고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 내에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="3805d-108">Win32 논리가 이미 컨트롤로 패키지 된 경우 `BuildWindowCore` 구현은 `CreateWindow`에 대 한 호출 보다 약간 더 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-108">If your Win32 logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="3805d-109">예를 들어에서 C++Win32 LISTBOX 컨트롤을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-109">For example, to create a Win32 LISTBOX control in C++:</span></span>

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

<span data-ttu-id="3805d-110">하지만 Win32 코드가 자체 포함 되지 않은 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-110">But suppose the Win32 code is not quite so self-contained?</span></span> <span data-ttu-id="3805d-111">그렇다면 Win32 대화 상자를 만들고 해당 콘텐츠를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-111">If so, you can create a Win32 dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="3805d-112">이 샘플은 Visual Studio 및 C++에서 이러한 작업을 수행 하는 것이 좋습니다. 하지만 다른 언어나 명령줄에서이 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-112">The sample shows this in Visual Studio and C++, although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="3805d-113">C++ DLL 프로젝트로 컴파일되는 간단한 대화 상자를 사용 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-113">Start with a simple dialog, which is compiled into a C++ DLL project.</span></span>

<span data-ttu-id="3805d-114">다음으로 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 대화 상자를 도입 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="3805d-115">관리 되는 DLL (`/clr`)로 컴파일</span><span class="sxs-lookup"><span data-stu-id="3805d-115">Compile the DLL as managed (`/clr`)</span></span>

- <span data-ttu-id="3805d-116">대화 상자를 컨트롤로 전환</span><span class="sxs-lookup"><span data-stu-id="3805d-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="3805d-117">`BuildWindowCore` 및 `DestroyWindowCore` 메서드를 사용 하 여 <xref:System.Windows.Interop.HwndHost>의 파생 클래스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="3805d-118">`TranslateAccelerator` 메서드를 재정의 하 여 대화 상자 키를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="3805d-119">탭 이동을 지원 하도록 `TabInto` 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="3805d-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="3805d-120">니모닉을 지원 하도록 `OnMnemonic` 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="3805d-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="3805d-121"><xref:System.Windows.Interop.HwndHost> 하위 클래스를 인스턴스화하고 오른쪽 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 아래에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="3805d-122">대화 상자를 컨트롤로 전환</span><span class="sxs-lookup"><span data-stu-id="3805d-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="3805d-123">WS_CHILD 및 DS_CONTROL 스타일을 사용 하 여 대화 상자를 자식 HWND로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="3805d-124">대화 상자가 정의 된 리소스 파일 (.rc)로 이동 하 여 대화 상자 정의의 시작 부분을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```text
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="3805d-125">두 번째 줄을 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-125">Change the second line to:</span></span>

```text
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="3805d-126">이 작업은 자체 포함 컨트롤로 완전히 패키지 하지 않습니다. Win32가 특정 메시지를 처리할 수 있도록 `IsDialogMessage()`를 호출 해야 하지만 컨트롤 변경 내용으로 인해 해당 컨트롤을 다른 HWND 내에 배치 하는 간단한 방법이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so Win32 can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="3805d-127">서브 클래스 System.windows.interop.hwndhost></span><span class="sxs-lookup"><span data-stu-id="3805d-127">Subclass HwndHost</span></span>

<span data-ttu-id="3805d-128">다음 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-128">Import the following namespaces:</span></span>

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

<span data-ttu-id="3805d-129">그런 다음 <xref:System.Windows.Interop.HwndHost>의 파생 클래스를 만들고 `BuildWindowCore` 및 `DestroyWindowCore` 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

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

<span data-ttu-id="3805d-130">여기서는 `CreateDialog`을 사용 하 여 컨트롤 인 대화 상자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="3805d-131">이 메서드는 DLL 내에서 호출 되는 첫 번째 메서드 중 하나 이므로 나중에 정의 하는 함수를 호출 하 여 `InitializeGlobals()`라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-131">Since this is one of the first methods called inside the DLL, you should also do some standard Win32 initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="3805d-132">TranslateAccelerator 메서드를 재정의 하 여 대화 상자 키를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="3805d-133">지금이 샘플을 실행 한 경우를 표시 하는 대화 상자 컨트롤을 가져오지만 대화 상자를 기능 대화 상자로 만드는 모든 키보드 처리를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="3805d-134">이제 `IKeyboardInputSink`에서 제공 하는 `TranslateAccelerator` 구현 (<xref:System.Windows.Interop.HwndHost> 구현 하는 인터페이스)을 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="3805d-135">이 메서드는 응용 프로그램이 WM_KEYDOWN를 받고 WM_SYSKEYDOWN 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

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

<span data-ttu-id="3805d-136">이는 한 부분에서 많은 코드 이므로 좀 더 자세한 설명을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="3805d-137">먼저 및 C++ 매크로를 사용 C++ 하는 코드 winuser.h에 정의 된 `TranslateAccelerator`매크로가 이미 있는 것을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-137">First, the code using C++ and C++ macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="3805d-138">따라서 `TranslateAcceleratorW` 메서드가 아니라 `TranslateAccelerator` 메서드를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="3805d-139">마찬가지로 관리 되지 않는 winuser.h 메시지와 관리 되는 `Microsoft::Win32::MSG` 구조체가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="3805d-140">`::` 연산자를 C++ 사용 하 여 두 가지를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-140">You can disambiguate between the two using the C++ `::` operator.</span></span>

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

<span data-ttu-id="3805d-141">`TranslateAccelerator`로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-141">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="3805d-142">기본 원칙은 `IsDialogMessage` Win32 함수를 호출 하 여 가능한 한 많은 작업을 수행 하는 것 이지만 `IsDialogMessage`는 대화 상자 외부의 모든 항목에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-142">The basic principle is to call the Win32 function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="3805d-143">대화 상자를 표시 하는 사용자 탭으로 대화 상자에서 마지막 컨트롤을 지나서 탭 이동 하면 `IKeyboardInputSite::OnNoMoreStops`를 호출 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 부분으로 포커스를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-143">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

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

<span data-ttu-id="3805d-144">마지막으로 `IsDialogMessage`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-144">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="3805d-145">그러나 `TranslateAccelerator` 방법의 책임 중 하나는 키 입력을 처리 했는지 여부를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 알려 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-145">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="3805d-146">이를 처리 하지 않은 경우 입력 이벤트는 응용 프로그램의 나머지 부분을 통해 터널링 및 버블링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-146">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="3805d-147">여기서는 쿼크 키보드 messange 처리 및 Win32의 입력 아키텍처 특성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-147">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in Win32.</span></span> <span data-ttu-id="3805d-148">그러나 `IsDialogMessage`는 특정 키 입력을 처리 하는지 여부에 관계 없이 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-148">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="3805d-149">또한 처리 하지 않아야 하는 키 입력에 대 한 `DispatchMessage()`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-149">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="3805d-150">따라서 `IsDialogMessage`를 리버스 엔지니어링 하 고이를 처리 하는 것으로 알고 있는 키에 대해서만 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-150">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="3805d-151">TabInto 메서드를 재정의 하 여 탭 이동 지원</span><span class="sxs-lookup"><span data-stu-id="3805d-151">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="3805d-152">`TranslateAccelerator`를 구현 했으므로 사용자는 대화 상자 내에서 탭 하 여 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-152">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="3805d-153">그러나 사용자는 대화 상자로 다시 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-153">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="3805d-154">이를 해결 하려면 `TabInto`를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-154">To solve that, you override `TabInto`:</span></span>

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

<span data-ttu-id="3805d-155">`TraversalRequest` 매개 변수는 탭 동작이 탭 인지 또는 이동 탭 인지를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-155">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="3805d-156">니모닉을 지원 하도록 OnMnemonic 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="3805d-156">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="3805d-157">키보드 처리가 거의 완료 되었지만 누락 된 사항이 있습니다. 니모닉이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-157">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="3805d-158">사용자가 alt + F를 누르면 포커스 doe가 "First name:" 입력란으로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-158">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="3805d-159">따라서 `OnMnemonic` 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-159">So, you override the `OnMnemonic` method:</span></span>

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

<span data-ttu-id="3805d-160">여기에서 `IsDialogMessage`를 호출 하지 않는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="3805d-160">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="3805d-161">이전에와 동일한 문제가 발생 했습니다. 코드에서 키 입력을 처리 했는지 여부를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 코드에 알릴 수 있어야 하며 `IsDialogMessage`는 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-161">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="3805d-162">또한 포커스가 있는 HWND가 대화 상자 내에 없는 경우 `IsDialogMessage`에서 니모닉 처리를 거부 하기 때문에 두 번째 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-162">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="3805d-163">System.windows.interop.hwndhost> 파생 클래스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="3805d-163">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="3805d-164">마지막으로, 이제 모든 키와 탭 지원이 준비 되었으므로 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 <xref:System.Windows.Interop.HwndHost>을 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-164">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="3805d-165">주 응용 프로그램을 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]으로 작성 하는 경우에는 <xref:System.Windows.Interop.HwndHost>을 배치할 수 있는 빈 <xref:System.Windows.Controls.Border> 요소를 유지 하는 것이 가장 쉬운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-165">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="3805d-166">여기서는 `insertHwndHostHere`라는 <xref:System.Windows.Controls.Border>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-166">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

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

<span data-ttu-id="3805d-167">그런 다음 <xref:System.Windows.Interop.HwndHost>를 인스턴스화하고 <xref:System.Windows.Controls.Border>에 연결 하기 위해 코드 시퀀스에서 적절 한 장소를 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-167">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="3805d-168">이 예제에서는 <xref:System.Windows.Window> 파생 클래스에 대 한 생성자 내에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-168">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

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

<span data-ttu-id="3805d-169">다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3805d-169">Which gives you:</span></span>

![실행 중인 WPF 앱의 스크린샷](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="3805d-171">참조</span><span class="sxs-lookup"><span data-stu-id="3805d-171">See also</span></span>

- [<span data-ttu-id="3805d-172">WPF 및 Win32 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="3805d-172">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
