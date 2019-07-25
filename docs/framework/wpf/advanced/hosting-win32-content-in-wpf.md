---
title: WPF에서 Win32 콘텐츠 호스팅
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: ee260d58cdb4dc971fc32ca5c889b459b6a48489
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484733"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="314de-102">WPF에서 Win32 콘텐츠 호스팅</span><span class="sxs-lookup"><span data-stu-id="314de-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="314de-103">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="314de-103">Prerequisites</span></span>

<span data-ttu-id="314de-104">[WPF 및 Win32 상호 운용성을](wpf-and-win32-interoperation.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="314de-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="314de-105">System.windows.interop.hwndhost> (Windows Presentation Framework) 내의 Win32 연습</span><span class="sxs-lookup"><span data-stu-id="314de-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="314de-106">응용 프로그램 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 내 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 콘텐츠를 다시 <xref:System.Windows.Interop.HwndHost>사용 하려면 hwnd 모양을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 만드는 컨트롤인를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-106">To reuse [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="314de-107">와 <xref:System.Windows.Interop.HwndSource>마찬가지로 <xref:System.Windows.Interop.HwndHost> 는를 사용 하는 것이 <xref:System.Windows.Interop.HwndHost> 간단 합니다 `BuildWindowCore` . `DestroyWindowCore` 에서 파생 되 고 및 <xref:System.Windows.Interop.HwndHost> 메서드를 구현한 다음 파생 클래스 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 를 인스턴스화하고 프로그램별.</span><span class="sxs-lookup"><span data-stu-id="314de-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="314de-108">논리가 이미 컨트롤로 `BuildWindowCore` 패키지 된 경우 구현은에 대 `CreateWindow`한 호출 보다 약간 더 낮습니다. [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]</span><span class="sxs-lookup"><span data-stu-id="314de-108">If your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="314de-109">예를 들어에서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] C++LISTBOX 컨트롤을 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-109">For example, to create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX control in C++:</span></span>

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

<span data-ttu-id="314de-110">그러나 코드가 자체 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 포함 되지 않는 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-110">But suppose the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] code is not quite so self-contained?</span></span> <span data-ttu-id="314de-111">그렇다면 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 대화 상자를 만들고 해당 내용을 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-111">If so, you can create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="314de-112">이 샘플은 다른 언어나 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 명령줄 C++에서이 작업을 수행할 수도 있지만 및에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="314de-112">The sample shows this in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] and C++, although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="314de-113">[!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 프로젝트로 컴파일되 C++ 는 간단한 대화 상자에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-113">Start with a simple dialog, which is compiled into a C++ [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] project.</span></span>

<span data-ttu-id="314de-114">다음으로 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 대화 상자를 도입 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="314de-115">관리 되 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 는 (`/clr`)로 컴파일</span><span class="sxs-lookup"><span data-stu-id="314de-115">Compile the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] as managed (`/clr`)</span></span>

- <span data-ttu-id="314de-116">대화 상자를 컨트롤로 전환</span><span class="sxs-lookup"><span data-stu-id="314de-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="314de-117">및 `BuildWindowCore` <xref:System.Windows.Interop.HwndHost> 메서드`DestroyWindowCore` 를 사용 하 여의 파생 클래스 정의</span><span class="sxs-lookup"><span data-stu-id="314de-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="314de-118">대화 `TranslateAccelerator` 상자 키를 처리 하는 Override 메서드</span><span class="sxs-lookup"><span data-stu-id="314de-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="314de-119">탭 `TabInto` 이동을 지원 하도록 Override 메서드</span><span class="sxs-lookup"><span data-stu-id="314de-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="314de-120">니모닉을 `OnMnemonic` 지원 하기 위한 Override 메서드</span><span class="sxs-lookup"><span data-stu-id="314de-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="314de-121">하위 클래스 <xref:System.Windows.Interop.HwndHost> 를 인스턴스화하고 오른쪽 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 아래에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="314de-122">대화 상자를 컨트롤로 전환</span><span class="sxs-lookup"><span data-stu-id="314de-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="314de-123">WS_CHILD 및 DS_CONTROL 스타일을 사용 하 여 대화 상자를 자식 HWND로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="314de-124">대화 상자가 정의 된 리소스 파일 (.rc)로 이동 하 여 대화 상자 정의의 시작 부분을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="314de-125">두 번째 줄을 다음과 같이 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-125">Change the second line to:</span></span>

```
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="314de-126">이 작업은 자체 포함 컨트롤로 완전히 패키지 하지 않습니다. 여전히을 호출 `IsDialogMessage()` [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 하 여 특정 메시지를 처리할 수 있지만 컨트롤 변경 내용으로 인해 해당 컨트롤을 다른 HWND 내에 배치 하는 간단한 방법이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="314de-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="314de-127">서브 클래스 System.windows.interop.hwndhost></span><span class="sxs-lookup"><span data-stu-id="314de-127">Subclass HwndHost</span></span>

<span data-ttu-id="314de-128">다음 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="314de-128">Import the following namespaces:</span></span>

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

<span data-ttu-id="314de-129">그런 다음의 <xref:System.Windows.Interop.HwndHost> 파생 클래스를 만들고 및 `DestroyWindowCore` 메서드 `BuildWindowCore` 를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

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

<span data-ttu-id="314de-130">여기서는 `CreateDialog` 를 사용 하 여 실제 컨트롤 인 대화 상자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="314de-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="314de-131">이는 내부 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]에서 호출 되는 첫 번째 메서드 중 하나 이므로 나중에 정의 하 `InitializeGlobals()`는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수를 호출 하 여 표준 초기화를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-131">Since this is one of the first methods called inside the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], you should also do some standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="314de-132">TranslateAccelerator 메서드를 재정의 하 여 대화 상자 키를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="314de-133">지금이 샘플을 실행 한 경우를 표시 하는 대화 상자 컨트롤을 가져오지만 대화 상자를 기능 대화 상자로 만드는 모든 키보드 처리를 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="314de-134">이제 `TranslateAccelerator` 구현을 구현 `IKeyboardInputSink` 하<xref:System.Windows.Interop.HwndHost> 는 인터페이스 (에서 제공)를 재정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="314de-135">이 메서드는 응용 프로그램에서 WM_KEYDOWN 및 WM_SYSKEYDOWN를 받을 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="314de-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

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

<span data-ttu-id="314de-136">이는 한 부분에서 많은 코드 이므로 좀 더 자세한 설명을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="314de-137">먼저 및 C++ 매크로를 사용 C++ 하는 코드 winuser.h에 정의 된 라는 `TranslateAccelerator`매크로가 이미 있음을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-137">First, the code using C++ and C++ macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="314de-138">따라서 메서드가 `TranslateAccelerator` `TranslateAcceleratorW` 아닌 메서드를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="314de-139">마찬가지로 관리 되지 않는 winuser.h 메시지와 관리 되 `Microsoft::Win32::MSG` 는 구조체가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="314de-140">연산자를 C++ `::` 사용 하 여 두 가지를 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-140">You can disambiguate between the two using the C++ `::` operator.</span></span>

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

<span data-ttu-id="314de-141">로 `TranslateAccelerator`돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="314de-141">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="314de-142">기본 원칙은 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수 `IsDialogMessage` 를 호출 하 여 가능한 한 많은 작업을 수행 하는 것 이지만 `IsDialogMessage` 대화 상자 외부의 모든 항목에 대 한 액세스 권한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-142">The basic principle is to call the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="314de-143">대화 상자를 표시 하는 사용자 탭으로 대화 상자에서 마지막 컨트롤을 지나서 탭 이동 하면을 호출 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] `IKeyboardInputSite::OnNoMoreStops`하 여 부분으로 포커스를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-143">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

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

<span data-ttu-id="314de-144">마지막으로 `IsDialogMessage`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-144">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="314de-145">그러나 `TranslateAccelerator` 메서드의 책임 중 하나는 키 입력을 처리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 했는지 여부를 알려 주는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="314de-145">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="314de-146">이를 처리 하지 않은 경우 입력 이벤트는 응용 프로그램의 나머지 부분을 통해 터널링 및 버블링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-146">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="314de-147">여기서는 키보드 messange 처리의 쿼크 및의 입력 아키텍처 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]특성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-147">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span></span> <span data-ttu-id="314de-148">아쉽게도는 `IsDialogMessage` 특정 키 입력을 처리 하는지 여부에 관계 없이를 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-148">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="314de-149">또한 처리 하지 않아야 하는 `DispatchMessage()` 키 입력에 대해를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-149">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="314de-150">따라서 리버스 엔지니어링 `IsDialogMessage`하 고이를 처리 하는 것을 알고 있는 키에 대해서만 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-150">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="314de-151">TabInto 메서드를 재정의 하 여 탭 이동 지원</span><span class="sxs-lookup"><span data-stu-id="314de-151">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="314de-152">이제를 구현 `TranslateAccelerator`했으므로 사용자는 대화 상자 내에서 탭 하 여 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램으로 탭 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-152">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="314de-153">그러나 사용자는 대화 상자로 다시 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-153">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="314de-154">이를 해결 하려면 다음을 `TabInto`재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-154">To solve that, you override `TabInto`:</span></span>

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

<span data-ttu-id="314de-155">매개 `TraversalRequest` 변수는 탭 동작이 탭 인지 또는 이동 탭 인지를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="314de-155">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="314de-156">니모닉을 지원 하도록 OnMnemonic 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="314de-156">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="314de-157">키보드 처리가 거의 완료 되었지만 누락 된 사항이 있습니다. 니모닉이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-157">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="314de-158">사용자가 alt + F를 누르면 포커스 doe가 "First name:" 입력란으로 이동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-158">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="314de-159">따라서 메서드를 재정의 합니다 `OnMnemonic` .</span><span class="sxs-lookup"><span data-stu-id="314de-159">So, you override the `OnMnemonic` method:</span></span>

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

<span data-ttu-id="314de-160">여기에서를 `IsDialogMessage` 호출 하지 않는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="314de-160">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="314de-161">이전에와 동일한 문제가 있습니다. 코드에서 키 입력 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] `IsDialogMessage` 을 처리 했는지 여부를 코드에 알릴 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-161">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="314de-162">에서 포커스가 있는 HWND가 대화 상자 내 `IsDialogMessage` 에 없는 경우에서 니모닉 처리를 거부 하기 때문에 두 번째 문제도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-162">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="314de-163">System.windows.interop.hwndhost> 파생 클래스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="314de-163">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="314de-164">마지막으로, 이제 모든 키와 탭 지원이 준비 되었으므로를 더 큰 <xref:System.Windows.Interop.HwndHost> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="314de-164">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="314de-165">주 응용 프로그램을 작성 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]하는 경우를 적절 한 위치에 배치 하는 가장 쉬운 방법은을 <xref:System.Windows.Interop.HwndHost>배치 하려는 빈 <xref:System.Windows.Controls.Border> 요소를 유지 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="314de-165">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="314de-166">여기서는 라는 `insertHwndHostHere`을 <xref:System.Windows.Controls.Border> 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="314de-166">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

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

<span data-ttu-id="314de-167">그런 다음를 인스턴스화하고 <xref:System.Windows.Interop.HwndHost> 에 연결 <xref:System.Windows.Controls.Border>하기 위해 코드 시퀀스에서 적절 한 장소를 찾는 것은입니다.</span><span class="sxs-lookup"><span data-stu-id="314de-167">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="314de-168">이 예제에서는 <xref:System.Windows.Window> 파생 클래스에 대 한 생성자 내에이를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-168">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

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

<span data-ttu-id="314de-169">다음을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="314de-169">Which gives you:</span></span>

![실행 중인 WPF 앱의 스크린샷](./media/hosting-win32-content-in-wpf/windows-presentation-foundation-application.png)

## <a name="see-also"></a><span data-ttu-id="314de-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="314de-171">See also</span></span>

- [<span data-ttu-id="314de-172">WPF 및 Win32 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="314de-172">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
