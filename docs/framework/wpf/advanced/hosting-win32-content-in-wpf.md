---
title: WPF에서 Win32 콘텐츠 호스팅
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 3cc8644a-34f3-4082-9ddc-77623e4df2d8
ms.openlocfilehash: 8773cac1e421ecdca036e88d79797dae16f72b17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59055081"
---
# <a name="hosting-win32-content-in-wpf"></a><span data-ttu-id="aed16-102">WPF에서 Win32 콘텐츠 호스팅</span><span class="sxs-lookup"><span data-stu-id="aed16-102">Hosting Win32 Content in WPF</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aed16-103">전제 조건</span><span class="sxs-lookup"><span data-stu-id="aed16-103">Prerequisites</span></span>

<span data-ttu-id="aed16-104">참조 [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-104">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="a-walkthrough-of-win32-inside-windows-presentation-framework-hwndhost"></a><span data-ttu-id="aed16-105">Windows Presentation Framework (HwndHost) 내에서 win32 연습</span><span class="sxs-lookup"><span data-stu-id="aed16-105">A Walkthrough of Win32 Inside Windows Presentation Framework (HwndHost)</span></span>

<span data-ttu-id="aed16-106">다시 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 내의 콘텐츠 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 사용 하 여 <xref:System.Windows.Interop.HwndHost>, Hwnd 같이 하는 컨트롤인 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-106">To reuse [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] content inside [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] applications, use <xref:System.Windows.Interop.HwndHost>, which is a control that makes HWNDs look like [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="aed16-107">같은 <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> 사용 하기는 간단 하지만:에서 파생 <xref:System.Windows.Interop.HwndHost> 하 고 구현 `BuildWindowCore` 및 `DestroyWindowCore` 메서드를 인스턴스화할에 <xref:System.Windows.Interop.HwndHost> 클래스를 파생 하 고 내부에 배치 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-107">Like <xref:System.Windows.Interop.HwndSource>, <xref:System.Windows.Interop.HwndHost> is straightforward to use: derive from <xref:System.Windows.Interop.HwndHost> and implement `BuildWindowCore` and `DestroyWindowCore` methods, then instantiate your <xref:System.Windows.Interop.HwndHost> derived class and place it inside your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>

<span data-ttu-id="aed16-108">경우에 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 컨트롤로 이미 패키지 된 논리에 `BuildWindowCore` 구현에 대 한 호출 보다 약간 더 `CreateWindow`합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-108">If your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] logic is already packaged as a control, then your `BuildWindowCore` implementation is little more than a call to `CreateWindow`.</span></span> <span data-ttu-id="aed16-109">예를 들어 한 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 에서 LISTBOX 컨트롤 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="aed16-109">For example, to create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] LISTBOX control in [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]:</span></span>

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

<span data-ttu-id="aed16-110">가정 하지만 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 코드는 독립적인 그렇게 하지?</span><span class="sxs-lookup"><span data-stu-id="aed16-110">But suppose the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] code is not quite so self-contained?</span></span> <span data-ttu-id="aed16-111">따라서 만들 수 있는 경우는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 대화 상자 및 해당 내용을 더 큰 포함 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-111">If so, you can create a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog box and embed its contents into a larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="aed16-112">이 샘플에서이 보여 줍니다 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 및 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]이지만 다른 언어에서 또는 명령줄에서이 작업을 수행할 수 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-112">The sample shows this in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)], although it is also possible to do this in a different language or at the command line.</span></span>

<span data-ttu-id="aed16-113">컴파일되는 간단한 대화 상자를 사용 하 여 시작 된 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-113">Start with a simple dialog, which is compiled into a [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] project.</span></span>

<span data-ttu-id="aed16-114">다음으로,이 대화 상자를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램:</span><span class="sxs-lookup"><span data-stu-id="aed16-114">Next, introduce the dialog into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application:</span></span>

- <span data-ttu-id="aed16-115">컴파일 합니다 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] 관리 되는 (`/clr`)</span><span class="sxs-lookup"><span data-stu-id="aed16-115">Compile the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] as managed (`/clr`)</span></span>

- <span data-ttu-id="aed16-116">대화 상자 컨트롤에 설정</span><span class="sxs-lookup"><span data-stu-id="aed16-116">Turn the dialog into a control</span></span>

- <span data-ttu-id="aed16-117">파생된 클래스를 정의 <xref:System.Windows.Interop.HwndHost> 사용 하 여 `BuildWindowCore` 고 `DestroyWindowCore` 메서드</span><span class="sxs-lookup"><span data-stu-id="aed16-117">Define the derived class of <xref:System.Windows.Interop.HwndHost> with `BuildWindowCore` and `DestroyWindowCore` methods</span></span>

- <span data-ttu-id="aed16-118">재정의 `TranslateAccelerator` 대화 상자 키를 처리 하는 방법</span><span class="sxs-lookup"><span data-stu-id="aed16-118">Override `TranslateAccelerator` method to handle dialog keys</span></span>

- <span data-ttu-id="aed16-119">재정의 `TabInto` 탭 이동을 지 원하는 방법</span><span class="sxs-lookup"><span data-stu-id="aed16-119">Override `TabInto` method to support tabbing</span></span>

- <span data-ttu-id="aed16-120">재정의 `OnMnemonic` 니모닉을 지원 방법</span><span class="sxs-lookup"><span data-stu-id="aed16-120">Override `OnMnemonic` method to support mnemonics</span></span>

- <span data-ttu-id="aed16-121">인스턴스화하는 <xref:System.Windows.Interop.HwndHost> 서브 클래스 오른쪽 아래에 배치 하 고 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소</span><span class="sxs-lookup"><span data-stu-id="aed16-121">Instantiate the <xref:System.Windows.Interop.HwndHost> subclass and put it under the right [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element</span></span>

### <a name="turn-the-dialog-into-a-control"></a><span data-ttu-id="aed16-122">대화 상자 컨트롤에 설정</span><span class="sxs-lookup"><span data-stu-id="aed16-122">Turn the Dialog into a Control</span></span>

<span data-ttu-id="aed16-123">WS_CHILD 및 DS_CONTROL 스타일 사용 HWND의 자식에 대화 상자를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-123">You can turn a dialog box into a child HWND using the WS_CHILD and DS_CONTROL styles.</span></span> <span data-ttu-id="aed16-124">대화가 정의 되어 있는 리소스 파일 (.rc)에 이동한 대화 상자의 정의의 시작 부분을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-124">Go into the resource file (.rc) where the dialog is defined, and find the beginning of the definition of the dialog:</span></span>

```
IDD_DIALOG1 DIALOGEX 0, 0, 303, 121
STYLE DS_SETFONT | DS_MODALFRAME | DS_FIXEDSYS | WS_POPUP | WS_CAPTION | WS_SYSMENU
```

<span data-ttu-id="aed16-125">두 번째 줄을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-125">Change the second line to:</span></span>

```
STYLE DS_SETFONT | WS_CHILD | WS_BORDER | DS_CONTROL
```

<span data-ttu-id="aed16-126">이 작업은 자체 포함 된 컨트롤에에 해당 패키지 완벽 하 게 호출 해야 `IsDialogMessage()` 있도록 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 특정 메시지를 처리할 수 있지만 컨트롤을 변경은 다른 HWND 내에서 이러한 컨트롤을 배치 하는 간단한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-126">This action does not fully package it into a self-contained control; you still need to call `IsDialogMessage()` so [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] can process certain messages, but the control change does provide a straightforward way of putting those controls inside another HWND.</span></span>

## <a name="subclass-hwndhost"></a><span data-ttu-id="aed16-127">서브 클래스 HwndHost</span><span class="sxs-lookup"><span data-stu-id="aed16-127">Subclass HwndHost</span></span>

<span data-ttu-id="aed16-128">다음 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-128">Import the following namespaces:</span></span>

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

<span data-ttu-id="aed16-129">다음의 파생된 클래스를 만듭니다 <xref:System.Windows.Interop.HwndHost> 시키고 합니다 `BuildWindowCore` 및 `DestroyWindowCore` 메서드:</span><span class="sxs-lookup"><span data-stu-id="aed16-129">Then create a derived class of <xref:System.Windows.Interop.HwndHost> and override the `BuildWindowCore` and `DestroyWindowCore` methods:</span></span>

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

<span data-ttu-id="aed16-130">여기서 사용은 `CreateDialog` 컨트롤이 실제로 대화 상자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-130">Here you use the `CreateDialog` to create the dialog box that is really a control.</span></span> <span data-ttu-id="aed16-131">내에서 호출 하는 첫 번째 메서드 중 하나 이므로이 [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], 몇 가지 일반적인 수행 해야 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 나중에 정의 된 함수를 호출 하 여 초기화 라는 `InitializeGlobals()`:</span><span class="sxs-lookup"><span data-stu-id="aed16-131">Since this is one of the first methods called inside the [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], you should also do some standard [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] initialization by calling a function you will define later, called `InitializeGlobals()`:</span></span>

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

### <a name="override-translateaccelerator-method-to-handle-dialog-keys"></a><span data-ttu-id="aed16-132">TranslateAccelerator 대화 상자 키를 처리 하는 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-132">Override TranslateAccelerator Method to Handle Dialog Keys</span></span>

<span data-ttu-id="aed16-133">이 샘플을 실행 하는 경우 이제 표시 하는 대화 상자 컨트롤 얻지만 처리 하는 키보드의 모든 대화 상자 기능 대화 상자는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-133">If you ran this sample now, you would get a dialog control that displays, but it would ignore all of the keyboard processing that makes a dialog box a functional dialog box.</span></span> <span data-ttu-id="aed16-134">재정의 해야 합니다 `TranslateAccelerator` 구현 (에서 제공 되는 `IKeyboardInputSink`, 인터페이스는 <xref:System.Windows.Interop.HwndHost> 구현).</span><span class="sxs-lookup"><span data-stu-id="aed16-134">You should now override the `TranslateAccelerator` implementation (which comes from `IKeyboardInputSink`, an interface that <xref:System.Windows.Interop.HwndHost> implements).</span></span> <span data-ttu-id="aed16-135">이 메서드는 WM_KEYDOWN 및 WM_SYSKEYDOWN 응용 프로그램이 수신 하는 경우 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-135">This method gets called when the application receives WM_KEYDOWN and WM_SYSKEYDOWN.</span></span>

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

<span data-ttu-id="aed16-136">이 과정은 한 부분에서 코드의 보다 자세한 설명을 사용 하 여 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-136">This is a lot of code in one piece, so it could use some more detailed explanations.</span></span> <span data-ttu-id="aed16-137">먼저 사용 하는 코드가 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] 하 고 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] 매크로; 라는 매크로 이미 있는지 유의 해야 `TranslateAccelerator`, winuser.h에 정의 되어 있는:</span><span class="sxs-lookup"><span data-stu-id="aed16-137">First, the code using [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] macros; you need to be aware that there is already a macro named `TranslateAccelerator`, which is defined in winuser.h:</span></span>

```cpp
#define TranslateAccelerator  TranslateAcceleratorW
```

<span data-ttu-id="aed16-138">정의 해야는 `TranslateAccelerator` 메서드 및 not을 `TranslateAcceleratorW` 메서드.</span><span class="sxs-lookup"><span data-stu-id="aed16-138">So make sure to define a `TranslateAccelerator` method and not a `TranslateAcceleratorW` method.</span></span>

<span data-ttu-id="aed16-139">마찬가지로, 방법이 관리 되지 않는 winuser.h 메시지와 관리 되는 `Microsoft::Win32::MSG` 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-139">Similarly, there is both the unmanaged winuser.h MSG and the managed `Microsoft::Win32::MSG` struct.</span></span> <span data-ttu-id="aed16-140">사용 하 여 구분할 수 있습니다 합니다 [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-140">You can disambiguate between the two using the [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] `::` operator.</span></span>

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

<span data-ttu-id="aed16-141">다시 `TranslateAccelerator`입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-141">Back to `TranslateAccelerator`.</span></span> <span data-ttu-id="aed16-142">기본 원칙은 호출 하는 것을 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 함수 `IsDialogMessage` 최대한 많은 작업을 수행 하지만 `IsDialogMessage` 대화 상자 외부 항목에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-142">The basic principle is to call the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] function `IsDialogMessage` to do as much work as possible, but `IsDialogMessage` does not have access to anything outside the dialog.</span></span> <span data-ttu-id="aed16-143">포커스를 설정 해야 하는 대화 상자에서 탭 이동 하면 관련 사용자 탭 대화 상자에서 마지막 컨트롤을 실행 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 를 호출 하 여 부분 `IKeyboardInputSite::OnNoMoreStops`합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-143">As a user tab around the dialog, when tabbing runs past the last control in our dialog, you need to set focus to the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion by calling `IKeyboardInputSite::OnNoMoreStops`.</span></span>

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

<span data-ttu-id="aed16-144">마지막으로 `IsDialogMessage`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-144">Finally, call `IsDialogMessage`.</span></span> <span data-ttu-id="aed16-145">맡는 역할 중 하나만 제외 하 고는 `TranslateAccelerator` 메서드는 지시 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 했으면 처리 여부.</span><span class="sxs-lookup"><span data-stu-id="aed16-145">But one of the responsibilities of a `TranslateAccelerator` method is telling [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] whether you handled the keystroke or not.</span></span> <span data-ttu-id="aed16-146">입력된 이벤트를 처리 하지 않은 경우 터널링 및 응용 프로그램의 rest 통해 버블링 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-146">If you did not handle it, the input event can tunnel and bubble through the rest of the application.</span></span> <span data-ttu-id="aed16-147">이때를 노출할 수의 입력된 아키텍처의 특성과 키보드 기초적인 처리 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-147">Here, you will expose a quirk of keyboard messange handling and the nature of the input architecture in [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span></span> <span data-ttu-id="aed16-148">아쉽게도 `IsDialogMessage` 특정 키 입력을 처리 하는지 여부를 어떤 방식으로 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-148">Unfortunately, `IsDialogMessage` does not return in any way whether it handles a particular keystroke.</span></span> <span data-ttu-id="aed16-149">호출 설상가상으로 `DispatchMessage()` 처리 하지 않도록 하는 키 입력에!</span><span class="sxs-lookup"><span data-stu-id="aed16-149">Even worse, it will call `DispatchMessage()` on keystrokes it should not handle!</span></span>  <span data-ttu-id="aed16-150">리버스 엔지니어링 해야 하므로 `IsDialogMessage`만 알고 있는 키를 처리 하는 대 한 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-150">So you will have to reverse-engineer `IsDialogMessage`, and only call it for the keys you know it will handle:</span></span>

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

### <a name="override-tabinto-method-to-support-tabbing"></a><span data-ttu-id="aed16-151">지원 탭을 TabInto 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-151">Override TabInto Method to Support Tabbing</span></span>

<span data-ttu-id="aed16-152">구현한 했으므로 `TranslateAccelerator`, 사용자는 대화 상자 내에서 관련 탭 수 상자와 탭 외부로 큼에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-152">Now that you have implemented `TranslateAccelerator`, a user can tab around inside the dialog box and tab out of it into the greater [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="aed16-153">하지만 사용자는 대화 상자를 다시 탭 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-153">But a user cannot tab back into the dialog box.</span></span> <span data-ttu-id="aed16-154">이 해결 하려면 재정의 `TabInto`:</span><span class="sxs-lookup"><span data-stu-id="aed16-154">To solve that, you override `TabInto`:</span></span>

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

<span data-ttu-id="aed16-155">`TraversalRequest` 매개 변수 알려 탭 작업 탭 또는 shift 탭 인지 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-155">The `TraversalRequest` parameter tells you whether the tab action is a tab or shift tab.</span></span>

### <a name="override-onmnemonic-method-to-support-mnemonics"></a><span data-ttu-id="aed16-156">니모닉을 지원 하도록 OnMnemonic 메서드 재정의</span><span class="sxs-lookup"><span data-stu-id="aed16-156">Override OnMnemonic Method to Support Mnemonics</span></span>

<span data-ttu-id="aed16-157">키보드 처리는 거의 완료 되었지만 한 가지 빠진 니모닉 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-157">Keyboard handling is almost complete, but there is one thing missing – mnemonics do not work.</span></span> <span data-ttu-id="aed16-158">사용자가 alt-F를 누르면 포커스가 doe 이동 하지는 "이름:" 입력란입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-158">If a user presses alt-F, focus doe not jump to the "First name:" edit box.</span></span> <span data-ttu-id="aed16-159">따라서 재정의 하 여 `OnMnemonic` 메서드:</span><span class="sxs-lookup"><span data-stu-id="aed16-159">So, you override the `OnMnemonic` method:</span></span>

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

<span data-ttu-id="aed16-160">호출 하지 않는 이유 `IsDialogMessage` 여기?</span><span class="sxs-lookup"><span data-stu-id="aed16-160">Why not call `IsDialogMessage` here?</span></span>  <span data-ttu-id="aed16-161">-하기 전에 해야 할 때 알릴 수 있으려면 동일한 문제가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 코드를 키 입력을 처리 하는지 여부를 코드 및 `IsDialogMessage` 그렇게 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-161">You have the same issue as before--you need to be able to inform [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] code whether your code handled the keystroke or not, and `IsDialogMessage` cannot do that.</span></span> <span data-ttu-id="aed16-162">이기도 한 두 번째 문제 때문에 `IsDialogMessage` 대화 상자 내에서 포커스가 있는 HWND 없으면 니모닉 처리를 거부 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-162">There is also a second issue, because `IsDialogMessage` refuses to process the mnemonic if the focused HWND is not inside the dialog box.</span></span>

### <a name="instantiate-the-hwndhost-derived-class"></a><span data-ttu-id="aed16-163">인스턴스화할 HwndHost 파생 클래스</span><span class="sxs-lookup"><span data-stu-id="aed16-163">Instantiate the HwndHost Derived Class</span></span>

<span data-ttu-id="aed16-164">마지막으로, 이제 모든 키 및 탭 지원이 위치에 넣을 수 있습니다 하 <xref:System.Windows.Interop.HwndHost> 를 더 큰 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-164">Finally, now that all the key and tab support is in place, you can put your <xref:System.Windows.Interop.HwndHost> into the larger [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="aed16-165">주 응용 프로그램 작성 된 경우 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], 빈 유지 하는 적절 한 위치에 배치 하는 가장 쉬운 방법은 <xref:System.Windows.Controls.Border> 실시 하려는 요소를 <xref:System.Windows.Interop.HwndHost>입니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-165">If the main application is written in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], the easiest way to put it in the right place is to leave an empty <xref:System.Windows.Controls.Border> element where you want to put the <xref:System.Windows.Interop.HwndHost>.</span></span> <span data-ttu-id="aed16-166">만들려면 여기를 <xref:System.Windows.Controls.Border> 라는 `insertHwndHostHere`:</span><span class="sxs-lookup"><span data-stu-id="aed16-166">Here you create a <xref:System.Windows.Controls.Border> named `insertHwndHostHere`:</span></span>

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

<span data-ttu-id="aed16-167">다음에 좋은 출발점이를 인스턴스화하는 코드 시퀀스에서 찾을 수는 <xref:System.Windows.Interop.HwndHost> 연결 된 <xref:System.Windows.Controls.Border>합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-167">Then all that remains is to find a good place in code sequence to instantiate the <xref:System.Windows.Interop.HwndHost> and connect it to the <xref:System.Windows.Controls.Border>.</span></span> <span data-ttu-id="aed16-168">이 예에서 배치할 것에 대 한 생성자 내부를 <xref:System.Windows.Window> 클래스를 파생 합니다.</span><span class="sxs-lookup"><span data-stu-id="aed16-168">In this example, you will put it inside the constructor for the <xref:System.Windows.Window> derived class:</span></span>

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

<span data-ttu-id="aed16-169">하면:</span><span class="sxs-lookup"><span data-stu-id="aed16-169">Which gives you:</span></span>

<span data-ttu-id="aed16-170">![WPF 응용 프로그램 스크린 샷](./media/interoparch09.PNG "InteropArch09")</span><span class="sxs-lookup"><span data-stu-id="aed16-170">![WPF application screenshot](./media/interoparch09.PNG "InteropArch09")</span></span>

## <a name="see-also"></a><span data-ttu-id="aed16-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="aed16-171">See also</span></span>

- [<span data-ttu-id="aed16-172">WPF 및 Win32 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="aed16-172">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
