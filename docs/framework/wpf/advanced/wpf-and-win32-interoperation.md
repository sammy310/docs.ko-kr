---
title: WPF 및 Win32 interop
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
- HWND interop [WPF]
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 0ffbde0d-701d-45a3-a6fa-dd71f4d9772e
ms.openlocfilehash: 7b7c3ed8f9833094ce1e836c11f84132ae84def2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735221"
---
# <a name="wpf-and-win32-interoperation"></a>WPF 및 Win32 상호 운용성

이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 Win32 코드를 상호 운용 하는 방법에 대 한 개요를 제공 합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서는 애플리케이션을 만들기 위한 다양한 환경을 제공합니다. 그러나 Win32 코드에 상당한 투자가 있으면 해당 코드의 일부를 다시 사용 하는 것이 더 효과적일 수 있습니다.

<a name="basics"></a>

## <a name="wpf-and-win32-interoperation-basics"></a>WPF 및 Win32 상호 운용성 기본 사항

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 Win32 코드 간의 상호 운용을 위한 두 가지 기본 기술이 있습니다.

- Win32 창에서 콘텐츠를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 호스팅합니다. 이 기술을 사용 하면 표준 Win32 창 및 응용 프로그램의 프레임 워크 내에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 고급 그래픽 기능을 사용할 수 있습니다.

- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠에서 Win32 창을 호스팅합니다. 이 기술을 사용 하면 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠의 컨텍스트에서 기존 사용자 지정 Win32 컨트롤을 사용 하 고 경계를 넘어 데이터를 전달할 수 있습니다.

이 항목에서는 이러한 각 기법을 개념적인 측면에서 소개합니다. Win32에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 호스트 하는 방법에 대 한 자세한 코드를 보려면 [연습: w i n 32에서 WPF 콘텐츠 호스팅](walkthrough-hosting-wpf-content-in-win32.md)을 참조 하세요. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 Win32를 호스트 하는 방법에 대 한 더 많은 코드 지향 그림은 [연습: WPF에서 Win32 컨트롤 호스팅](walkthrough-hosting-a-win32-control-in-wpf.md)을 참조 하세요.

<a name="projects"></a>

## <a name="wpf-interoperation-projects"></a>WPF 상호 운용 프로젝트

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Api는 관리 코드 이지만 대부분의 기존 Win32 프로그램은 관리 되지 않는 C++로 작성 됩니다.  실제 관리 되지 않는 프로그램에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Api를 호출할 수 없습니다. 그러나 `/clr` 옵션을 Microsoft Visual C++ 컴파일러와 함께 사용 하 여 관리 되는 관리 되지 않는 API 호출을 원활 하 게 혼합할 수 있는 관리 되지 않는 혼합형 프로그램을 만들 수 있습니다.

프로젝트 수준에 대 한 복잡 한 것은 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 파일을 C++ 프로젝트로 컴파일할 수 없다는 것입니다.  이 문제는 다음과 같은 몇 가지 프로젝트 분할 기법을 통해 해결할 수 있습니다.

- 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] C# 페이지를 컴파일된 어셈블리로 포함 하는 dll을 만든 다음 C++ 실행 파일에 해당 dll을 참조로 포함 합니다.

- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠에 C# 대 한 실행 파일을 만들고 Win32 콘텐츠를 포함 하 C++ 는 DLL을 참조 하도록 합니다.

- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 컴파일하는 대신 <xref:System.Windows.Markup.XamlReader.Load%2A>를 사용 하 여 런타임에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 로드 합니다.

- [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 전혀 사용 하지 않고 코드에서 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 작성 하 여 <xref:System.Windows.Application>에서 요소 트리를 빌드합니다.

가장 적합한 방법을 사용하세요.

> [!NOTE]
> /Cli를 이전에 사용 C++하지 않은 경우에는 상호 운용 코드 예제에서 `gcnew` 및 `nullptr`와 같은 일부 "새" 키워드를 확인할 수 있습니다. 이러한 키워드는 이전 이중 밑줄 구문 (`__gc`)을 대체 하 고에서 C++관리 코드에 대 한 보다 자연 스러운 구문을 제공 합니다.  C++/Cli 관리 기능에 대해 자세히 알아보려면 [런타임 플랫폼용 구성 요소 확장](/cpp/windows/component-extensions-for-runtime-platforms)을 참조 하세요.

<a name="hwnds"></a>

## <a name="how-wpf-uses-hwnds"></a>WPF에서 HWND를 사용하는 방법

[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] "HWND interop"를 최대한 활용하려면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 HWND를 사용하는 방법을 이해해야 합니다. 모든 HWND의 경우 DirectX 렌더링 또는 GDI/GDI + 렌더링을 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 렌더링을 혼합할 수 없습니다. 여기에는 여러 가지 의미가 내포되어 있습니다. 기본적으로 이러한 렌더링 모델을 혼합하려면 상호 운용 솔루션을 만들고, 사용하도록 선택하는 각 렌더링 모델에 지정된 상호 운용 세그먼트를 사용해야 합니다. 또한, 렌더링 동작은 상호 운용 솔루션에서 수행할 수 있는 작업에 대한 “에어스페이스” 제한 사항도 만듭니다. “에어스페이스” 개념은 [기술 영역 개요](technology-regions-overview.md) 항목에 자세히 설명되어 있습니다.

화면의 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소는 궁극적으로 HWND를 통해 지원됩니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window>를 만들 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 최상위 HWND를 만들고 <xref:System.Windows.Interop.HwndSource>를 사용 하 여 <xref:System.Windows.Window> 및 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 HWND 내에 배치 합니다.  애플리케이션의 나머지 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠에서 이 단일 HWND를 공유합니다. 예외는 메뉴, 콤보 상자 드롭다운 및 기타 팝업입니다. 이러한 요소는 고유한 최상위 창을 만듭니다. 따라서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메뉴가 포함된 창 HWND의 가장자리를 넘어 이동할 수 있습니다. <xref:System.Windows.Interop.HwndHost>를 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]내부에 HWND를 배치할 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> HWND를 기준으로 새 자식 HWND를 배치 하는 방법을 Win32에 알립니다.

HWND와 관련된 개념은 각 HWND 내에서, 그리고 각 HWND 간에 투명합니다. 이 내용도 [기술 영역 개요](technology-regions-overview.md) 항목에서 설명되어 있습니다.

<a name="hosting_a_wpf_page"></a>

## <a name="hosting-wpf-content-in-a-microsoft-win32-window"></a>Microsoft Win32 창에서 WPF 콘텐츠 호스팅

Win32 창에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]을 호스트 하는 데 대 한 핵심은 <xref:System.Windows.Interop.HwndSource> 클래스입니다. 이 클래스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 Win32 창에 래핑하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 자식 창으로 통합할 수 있습니다. 다음 방법은 단일 응용 프로그램에서 Win32와 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 결합 한 것입니다.

1. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠(콘텐츠 루트 요소)를 관리 클래스로 구현합니다. 일반적으로 클래스는 여러 자식 요소를 포함 하거나 루트 요소로 사용할 수 있는 클래스 (예: <xref:System.Windows.Controls.DockPanel> 또는 <xref:System.Windows.Controls.Page>) 중 하나에서 상속 됩니다. 후속 단계에서는 이 클래스를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스라고 하며, 클래스 인스턴스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체라고 합니다.

2. /Cli를 사용 하 여 C++Windows 응용 프로그램 구현 기존의 관리 되지 않는 C++ 응용 프로그램으로 시작 하는 경우에는 일반적으로 `/clr` 컴파일러 플래그를 포함 하도록 프로젝트 설정을 변경 하 여 관리 코드를 호출할 수 있습니다 (`/clr` 컴파일을 지원 하기 위해 필요한 모든 범위는이 항목에서 설명 하지 않음).

3. 스레딩 모델을 STA(단일 스레드 아파트)로 설정합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 이 스레딩 모델을 사용합니다.

4. 창 프로시저에서 WM_CREATE 알림을 처리합니다.

5. 처리기(또는 처리기에서 호출하는 함수)에서 다음을 수행합니다.

    1. 부모 창 HWND를 `parent` 매개 변수로 사용 하 여 새 <xref:System.Windows.Interop.HwndSource> 개체를 만듭니다.

    2. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스의 인스턴스를 만듭니다.

    3. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체에 대 한 참조를 <xref:System.Windows.Interop.HwndSource> 개체 <xref:System.Windows.Interop.HwndSource.RootVisual%2A> 속성에 할당 합니다.

    4. <xref:System.Windows.Interop.HwndSource> 개체 <xref:System.Windows.Interop.HwndSource.Handle%2A> 속성에는 창 핸들 (HWND)이 포함 되어 있습니다. 애플리케이션의 관리되지 않는 부분에서 사용할 수 있는 HWND를 가져오려면 `Handle.ToPointer()`를 HWND로 캐스팅합니다.

6. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체에 대한 참조를 보유하는 정적 필드가 포함된 관리 클래스를 구현합니다. 이 클래스를 사용 하면 Win32 코드에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체에 대 한 참조를 가져올 수 있지만, <xref:System.Windows.Interop.HwndSource> 실수로 가비지 수집 되지 않도록 하는 것이 더 중요 합니다.

7. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체 이벤트 중 하나 이상에 처리기를 연결하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체에서 알림을 받습니다.

8. 속성, 호출 메서드 등을 설정하기 위해 정적 필드에 저장한 참조를 사용하여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 개체와 통신합니다.

> [!NOTE]
> 별도의 어셈블리를 생성한 다음 이를 참조하는 경우 콘텐츠 클래스의 기본 부분 클래스를 사용하여 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 1단계용 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 클래스 정의 중 일부 또는 모두를 수행할 수 있습니다. 일반적으로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]를 어셈블리로 컴파일하는 과정의 일부로 <xref:System.Windows.Application> 개체를 포함 하지만, 상호 운용의 일부로 <xref:System.Windows.Application> 사용 하지 않는 것이 아니라 응용 프로그램에서 참조 하는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에 대해 루트 클래스를 하나 이상 사용 하 고 partial 클래스를 참조 하기만 하면 됩니다. 프로시저의 나머지 부분은 기본적으로 위에서 설명한 것과 비슷합니다.
>
> 이러한 각 단계는 [연습: Win32에서 WPF 콘텐츠 호스팅](walkthrough-hosting-wpf-content-in-win32.md) 항목에서 코드를 통해 설명되어 있습니다.

<a name="hosting_an_hwnd"></a>

## <a name="hosting-a-microsoft-win32-window-in-wpf"></a>WPF에서 Microsoft Win32 창 호스팅

다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠 내에서 Win32 창을 호스트 하는 핵심은 <xref:System.Windows.Interop.HwndHost> 클래스입니다. 이 클래스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 트리에 추가될 수 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소에 창을 래핑합니다. <xref:System.Windows.Interop.HwndHost>는 호스트 된 창에 대 한 메시지 처리와 같은 작업을 수행할 수 있는 Api도 지원 합니다. 기본 절차는 다음과 같습니다.

1. 코드 또는 태그를 통해 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 애플리케이션의 요소 트리를 만듭니다. <xref:System.Windows.Interop.HwndHost> 구현을 자식 요소로 추가할 수 있는 요소 트리에서 적절 하 고 적합 한 지점을 찾습니다. 이 단계의 나머지 부분에서는 이 요소를 예약 요소라고 합니다.

2. <xref:System.Windows.Interop.HwndHost>에서 파생 하 여 Win32 콘텐츠를 포함 하는 개체를 만듭니다.

3. 해당 호스트 클래스에서 <xref:System.Windows.Interop.HwndHost> 메서드 <xref:System.Windows.Interop.HwndHost.BuildWindowCore%2A>를 재정의 합니다. 호스팅된 창의 HWND를 반환합니다. 실제 컨트롤을 반환된 창의 자식 창으로 래핑해야 할 수도 있습니다. 호스트 창에서 컨트롤을 래핑하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠가 간단한 방식으로 컨트롤에서 알림을 받을 수 있습니다. 이 기법은 호스팅된 제어 경계의 메시지 처리와 관련 된 일부 Win32 문제를 해결 하는 데 도움이 됩니다.

4. <xref:System.Windows.Interop.HwndHost.DestroyWindowCore%2A> 및 <xref:System.Windows.Interop.HwndHost.WndProc%2A><xref:System.Windows.Interop.HwndHost> 메서드를 재정의 합니다. 이렇게 하는 이유는 프로세스를 정리하고 호스팅된 콘텐츠에 대한 참조를 정리하기 위해서입니다. 특히 관리되지 않는 개체의 참조를 만든 경우에 필요합니다.

5. 코드 숨김 파일에서 컨트롤 호스팅 클래스의 인스턴스를 만들고 예약 요소의 하위로 설정합니다. 일반적으로 <xref:System.Windows.FrameworkElement.Loaded>와 같은 이벤트 처리기를 사용 하거나 partial 클래스 생성자를 사용 합니다. 런타임 동작을 통해 상호 운용 콘텐츠도 추가할 수 있습니다.

6. 컨트롤 알림과 같은 선택된 창 메시지를 처리합니다. 다음과 같이 두 가지 방법이 있습니다. 두 방법 모두 메시지 스트림에 대해 동일한 액세스 권한을 제공하므로, 프로그래밍 편리성에 따라 선택하면 됩니다.

    - <xref:System.Windows.Interop.HwndHost> 메서드 <xref:System.Windows.Interop.HwndHost.WndProc%2A>재정의에서 모든 메시지 (종료 메시지 아님)에 대 한 메시지 처리를 구현 합니다.

    - 호스팅 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소가 <xref:System.Windows.Interop.HwndHost.MessageHook> 이벤트를 처리 하 여 메시지를 처리 하도록 합니다. 이 이벤트는 호스팅된 창의 기본 창 프로시저에 전송된 모든 메시지에서 발생합니다.

    - <xref:System.Windows.Interop.HwndHost.WndProc%2A>를 사용 하 여 처리 되지 않은 windows의 메시지를 처리할 수 없습니다.

7. 관리되지 않는 `SendMessage` 함수를 호출하는 플랫폼 호출을 사용하여 호스팅된 창과 통신합니다.

다음 단계에 따라 마우스 입력을 사용하는 애플리케이션을 만듭니다. <xref:System.Windows.Interop.IKeyboardInputSink> 인터페이스를 구현 하 여 호스트 된 창에 대 한 탭 이동 지원을 추가할 수 있습니다.

이러한 각 단계는 [연습: WPF에서 Win32 컨트롤 호스팅](walkthrough-hosting-a-win32-control-in-wpf.md) 항목에서 코드를 통해 설명되어 있습니다.

### <a name="hwnds-inside-wpf"></a>WPF 내의 HWND

<xref:System.Windows.Interop.HwndHost>를 특수 컨트롤로 간주할 수 있습니다. 기술적으로 <xref:System.Windows.Interop.HwndHost>는 <xref:System.Windows.Controls.Control> 파생 클래스가 아니라 <xref:System.Windows.FrameworkElement> 파생 클래스 이지만 상호 운용성을 위해 컨트롤로 간주할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 나머지 부분에서는 호스팅된 콘텐츠를 다른 컨트롤 형식 개체 (입력을 렌더링 하 고 처리 해야 함)로 간주 하는 호스트 된 콘텐츠의 기본 Win32 특성을 추상화 <xref:System.Windows.Interop.HwndHost> 합니다. <xref:System.Windows.Interop.HwndHost>은 일반적으로 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.FrameworkElement>처럼 동작 하지만, 기본 Hwnd 지원 될 수 있는 항목의 제한에 따라 출력 (그리기 및 그래픽) 및 입력 (마우스 및 키보드)에 대 한 몇 가지 중요 한 차이점이 있습니다.

#### <a name="notable-differences-in-output-behavior"></a>출력 동작의 주요 차이점

- <xref:System.Windows.Interop.HwndHost> 기본 클래스인 <xref:System.Windows.FrameworkElement>에는 UI에 대 한 변경을 의미 하는 몇 가지 속성이 있습니다. 여기에는 해당 요소 내의 요소 레이아웃을 부모로 변경 하는 <xref:System.Windows.FrameworkElement.FlowDirection%2A?displayProperty=nameWithType>와 같은 속성이 포함 됩니다. 그러나 이러한 속성이 존재할 수 있는 경우에도 이러한 속성 중 대부분은 가능한 Win32 해당 항목에 매핑되지 않습니다. 이러한 속성 및 해당 의미는 렌더링 기술에 따라 많이 달라지므로 매핑이 실용적이지 않게 됩니다. 따라서 <xref:System.Windows.Interop.HwndHost>에서 <xref:System.Windows.FrameworkElement.FlowDirection%2A>와 같은 속성을 설정 해도 아무런 효과가 없습니다.

- <xref:System.Windows.Interop.HwndHost>는 회전, 크기 조정, 기울이기 또는 변환의 영향을 받을 수 없습니다.

- <xref:System.Windows.Interop.HwndHost>는 <xref:System.Windows.UIElement.Opacity%2A> 속성 (알파 혼합)을 지원 하지 않습니다. <xref:System.Windows.Interop.HwndHost> 내의 콘텐츠가 알파 정보를 포함 하는 <xref:System.Drawing> 작업을 수행 하는 경우 자체는 위반이 아니지만 전체적으로 <xref:System.Windows.Interop.HwndHost>는 Opacity = 1.0 (100%)만 지원 합니다.

- <xref:System.Windows.Interop.HwndHost>는 동일한 최상위 창의 다른 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 위에 표시 됩니다. 그러나 <xref:System.Windows.Controls.ToolTip> 또는 <xref:System.Windows.Controls.ContextMenu> 생성 된 메뉴는 별도의 최상위 창 이므로 <xref:System.Windows.Interop.HwndHost>에서 제대로 작동 합니다.

- <xref:System.Windows.Interop.HwndHost>는 부모 <xref:System.Windows.UIElement>의 클리핑 영역을 고려 하지 않습니다. 이는 <xref:System.Windows.Interop.HwndHost> 클래스를 스크롤 영역 또는 <xref:System.Windows.Controls.Canvas>내부에 배치 하려는 경우에 발생할 수 있습니다.

#### <a name="notable-differences-in-input-behavior"></a>입력 동작의 주요 차이점

- 일반적으로 입력 장치는 <xref:System.Windows.Interop.HwndHost> 호스팅된 Win32 지역 내에서 범위가 지정 되 고, 입력 이벤트는 Win32로 직접 이동 합니다.

- 마우스가 <xref:System.Windows.Interop.HwndHost>위에 있는 동안에는 응용 프로그램에서 마우스 이벤트 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 받지 않으며 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 <xref:System.Windows.UIElement.IsMouseOver%2A>의 값이 `false`됩니다.

- <xref:System.Windows.Interop.HwndHost>에 키보드 포커스가 있는 동안 응용 프로그램은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 키보드 이벤트를 수신 하지 않으며 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 값 <xref:System.Windows.UIElement.IsKeyboardFocusWithin%2A> `false`됩니다.

- 포커스가 <xref:System.Windows.Interop.HwndHost> 내에 있고 <xref:System.Windows.Interop.HwndHost>내의 다른 컨트롤을 변경 하는 경우 응용 프로그램은 <xref:System.Windows.UIElement.GotFocus> 또는 <xref:System.Windows.UIElement.LostFocus>[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트를 받지 않습니다.

- 관련 스타일러스 속성 및 이벤트는 유사 하며, 스타일러스가 <xref:System.Windows.Interop.HwndHost>하는 동안 정보를 보고 하지 않습니다.

<a name="tabbing_mnemonics_accelerators"></a>

## <a name="tabbing-mnemonics-and-accelerators"></a>탭 이동, 니모닉 및 액셀러레이터 키

<xref:System.Windows.Interop.IKeyboardInputSink> 및 <xref:System.Windows.Interop.IKeyboardInputSite> 인터페이스를 사용 하 여 혼합 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 및 Win32 응용 프로그램에 대 한 원활한 키보드 환경을 만들 수 있습니다.

- Win32 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구성 요소 간 탭 이동

- 포커스가 Win32 구성 요소 내에 있을 때와 WPF 구성 요소에 있을 때 모두 작동하는 니모닉 및 액셀러레이터 키.

<xref:System.Windows.Interop.HwndHost> 및 <xref:System.Windows.Interop.HwndSource> 클래스는 모두 <xref:System.Windows.Interop.IKeyboardInputSink>의 구현을 제공 하지만 고급 시나리오에 대해 원하는 모든 입력 메시지를 처리 하지 않을 수 있습니다. 원하는 키보드 동작을 얻기 위해 적절한 메서드를 재정의합니다.

인터페이스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]와 Win32 지역 간의 전환에 발생 하는 상황에 대 한 지원도 제공 합니다. Win32 지역 내에서 탭 이동 동작은 모두 탭 이동에 대 한 Win32 구현 논리에 의해 완전히 제어 됩니다 (있는 경우).

## <a name="see-also"></a>참조

- <xref:System.Windows.Interop.HwndHost>
- <xref:System.Windows.Interop.HwndSource>
- <xref:System.Windows.Interop>
- [연습: WPF에서 Win32 컨트롤 호스팅](walkthrough-hosting-a-win32-control-in-wpf.md)
- [연습: Win32에서 WPF 콘텐츠 호스팅](walkthrough-hosting-wpf-content-in-win32.md)
