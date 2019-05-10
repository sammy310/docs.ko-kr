---
title: '연습: Win32에서 WPF 시계 호스팅'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 4001c34f6673e036bdbf731baed782c6dc0a16b0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64755912"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a>연습: Win32에서 WPF 시계 호스팅

삽입할 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램을 사용 하 여 <xref:System.Windows.Interop.HwndSource>를 포함 하는 HWND를 제공 하는 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠. 먼저 만듭니다는 <xref:System.Windows.Interop.HwndSource>, CreateWindow와 유사한 매개 변수를 제공 합니다. 그런 합니다 <xref:System.Windows.Interop.HwndSource> 에 대 한는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 내부에 넣으려는 콘텐츠입니다. HWND를 마지막으로 표시 된 <xref:System.Windows.Interop.HwndSource>합니다. 이 연습에는 혼합을 만드는 방법을 보여 줍니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 안쪽 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 운영 체제를 다시 구현 하는 응용 프로그램 **날짜 및 시간 속성** 대화 합니다.

## <a name="prerequisites"></a>전제 조건

참조 [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)합니다.

## <a name="how-to-use-this-tutorial"></a>이 자습서를 사용하는 방법

이 자습서는 상호 운용 애플리케이션을 생성하는 중요한 단계에 대해 중점적으로 설명합니다. 자습서 샘플을 받으며 [Win32 시계 상호 운용 샘플](https://go.microsoft.com/fwlink/?LinkID=160051)하지만 샘플은 최종 제품의 반사 합니다. 기존 시작 된 것 처럼이 자습서의 단계를 설명 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 자신만의 프로젝트 및 아마도 기존 프로젝트를 추가 하는 호스팅된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다. 최종 제품을 비교할 수 있습니다 [Win32 시계 상호 운용 샘플](https://go.microsoft.com/fwlink/?LinkID=160051)합니다.

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a>Win32 내에서 Windows Presentation Framework의 연습(HwndSource)

다음 그래픽에서는 이 자습서의 의도된 최종 제품을 보여 줍니다.

![날짜 및 시간 속성 대화 상자를 보여 주는 스크린샷.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

이 대화 상자를 만들어 다시 만들 수 있습니다는 C++ 대화 상자 편집기를 사용 하 여 다음을 만들려면 Visual Studio에서 Win32 프로젝트:

![다시 만들어진된 날짜 및 시간 속성 대화 상자](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

(사용할 필요가 없습니다 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 데 <xref:System.Windows.Interop.HwndSource>를 사용할 필요가 없습니다 C++ 쓸 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로그램 이지만이 수행 하는 일반적인 방식 이며 단계별 자습서 설명에 적합).

넣으려면 5 개의 배치 하기 위해 수행 해야 할는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계를 대화 상자:

1. 사용 하도록 설정 하 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 관리 되는 코드를 호출 하는 프로젝트 (**/clr**)에서 프로젝트 설정을 변경 하 여 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]입니다.

2. 만들기는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 별도의 DLL입니다.

3. 에 넣을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 안에 <xref:System.Windows.Interop.HwndSource>합니다.

4. 에 대 한 HWND를 가져오려면 <xref:System.Windows.Controls.Page> 를 사용 하는 <xref:System.Windows.Interop.HwndSource.Handle%2A> 속성입니다.

5. 사용 하 여 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 클수록 내의 HWND를 배치할 위치를 결정 하 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램

## <a name="clr"></a>/clr

이 관리 되지 않는 첫 번째 단계는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 관리 코드를 호출할 수 있는 프로젝트입니다. 사용 및 사용에 대 한 기본 메서드를 조정 하려면 필요한 Dll에 연결 하는 /clr 컴파일러 옵션을 사용 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.

관리 코드 내에서 사용할 수 있도록 합니다 C++ 프로젝트: Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 에 **일반적인** 속성 페이지 (기본값), 공용 언어 런타임 지원 변경 `/clr`합니다.

그런 다음에 대 한 필요한 Dll에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll 및 UIAutomationTypes.dll 합니다. 다음 지침에서는 운영 체제가 C: 드라이브에 설치되어 있다고 가정합니다.

1. Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 하는 중...** , 및 해당 대화 상자 내에서:

2. Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 하는 중...** .

3. 클릭 **새 참조 추가**찾아보기 탭 클릭, C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll을 입력 한 확인을 클릭 합니다.

4. PresentationFramework.dll를 반복 합니다. C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.

5. WindowsBase.dll를 반복 합니다. C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.

6. UIAutomationTypes.dll를 반복 합니다. C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.

7. UIAutomationProvider.dll를 반복 합니다. C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.

8. 클릭 **새 참조 추가**System.dll을 선택 하 고 클릭 **확인**합니다.

9. 클릭 **확인** 참조를 추가 하기 위한 win32clock 속성 페이지를 종료 합니다.

 마지막으로 추가 합니다 `STAThreadAttribute` 에 `_tWinMain` 메서드 사용에 대 한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

이 특성은는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 는 초기화할 때 [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)]에 필요한 단일 스레드 아파트 모델 (STA)를 사용 해야 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (및 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).

## <a name="create-a-windows-presentation-framework-page"></a>Windows Presentation Framework 페이지 만들기

정의 하는 DLL을 만든 다음에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>합니다. 만드는 가장 쉬운 경우가 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> 는 독립 실행형 응용 프로그램을 작성 하 고 디버그로는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이런 방식으로 부분. 해당 프로젝트를 클릭 하 고 프로젝트를 마우스 오른쪽 단추로 클릭 하 여 DLL로 설정할 수 있습니다 완료 되 면 **속성**, 응용 프로그램으로 이동 하 고 출력 형식을 Windows 클래스 라이브러리로 변경 합니다.

합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll 프로젝트와 결합할 수 있습니다 합니다 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 선택 솔루션을 마우스 오른쪽 단추로 클릭 (하나의 솔루션에 두 프로젝트가 포함 된) – 프로젝트 **추가 \ 기존 프로젝트**합니다.

사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll에서는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 프로젝트 참조를 추가 해야 합니다.

1. Win32clock 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 하는 중...** .

2. 클릭 **새 참조 추가**합니다.

3. **프로젝트** 탭을 클릭합니다. WPFClock을 선택하고 [확인]을 클릭합니다.

4. 클릭 **확인** 참조를 추가 하기 위한 win32clock 속성 페이지를 종료 합니다.

## <a name="hwndsource"></a>HwndSource

다음을 사용 하 여 <xref:System.Windows.Interop.HwndSource> 수 있도록 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> HWND와 같습니다. 다음 코드 블록을 C++ 파일에 추가합니다.

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;

    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
        HwndSource^ source = gcnew HwndSource(
            0, // class style
            WS_VISIBLE | WS_CHILD, // style
            0, // exstyle
            x, y, width, height,
            "hi", // NAME
            IntPtr(parent)        // parent window
            );

        UIElement^ page = gcnew WPFClock::Clock();
        source->RootVisual = page;
        return (HWND) source->Handle.ToPointer();
    }
}
}
```

 다음은 약간의 설명이 필요할 수 있는 긴 코드 조각입니다. 첫 번째 부분은 다양한 절이어서 모든 호출을 정규화할 필요가 없습니다.

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 만드는 함수를 정의한 다음를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 콘텐츠를 넣습니다는 <xref:System.Windows.Interop.HwndSource> , 및 HWND 반환 합니다.

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

먼저 만듭니다는 <xref:System.Windows.Interop.HwndSource>, 매개 변수를 가진 CreateWindow와 유사한는:

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

만든 후의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클래스 생성자를 호출 하 여 콘텐츠:

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

페이지를 다음으로 연결 된 <xref:System.Windows.Interop.HwndSource>:

```cpp
source->RootVisual = page;
```

 마지막 줄에 대 한 HWND를 반환 하 고는 <xref:System.Windows.Interop.HwndSource>:

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a>Hwnd 위치 지정

포함 하는 HWND 했으므로 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계를 적용 해야 해당 HWND 내에서 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 대화 합니다. HWND를 배치할 위치를 알고 있는 경우 전달 하면 해당 크기 및 위치를 `GetHwnd` 앞에서 정의한 함수입니다. 그러나 리소스 파일을 사용하여 대화 상자를 정의했으므로 HWND를 배치할 위치를 정확하게 알 수 없습니다. 사용할 수는 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 삽입할 대화 상자 편집기를 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 시계가 들어갈 하려는 정적 컨트롤 ("여기에 시계 삽입"), 위치로 사용 및는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록.

WM_INITDIALOG를 처리 하는 경우 사용할 `GetDlgItem` 자리 표시자 STATIC에 대 한 HWND를 검색 하려면:

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

계산한 다음에 크기와 해당 자리 표시자 STATIC의 위치를 활용할 수 있도록는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계를 합니다.

RECT 사각형의 경우입니다.

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

그런 다음 자리 표시자 STATIC을 숨깁니다.

```cpp
ShowWindow(placeholder, SW_HIDE);
```

만들고는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시계 HWND 해당 위치에서:

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

자습서를 흥미를 확인 하는 데 실제 생성 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 만들려고 해야 클록을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이 시점에서 시계 컨트롤입니다. 코드 숨김에서 몇 개의 이벤트 처리기만 사용하여 태그에서 거의 모든 작업을 수행할 수 있습니다. 이 자습서 컨트롤 디자인에 상호 운용성 정보 이므로 전체에 대 한 코드를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 클록 제공 됩니다 작성 또는 각 부분의 의미에 대 한 개별적인 지침 없이 코드 블록으로 여기입니다. 이 코드를 자유롭게 사용하여 컨트롤의 모양과 느낌 또는 기능을 변경해 보세요.

다음은 태그입니다.

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

다음은 함께 제공되는 코드 숨김입니다.

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

최종 결과는 다음과 같습니다.

![최종 결과 날짜 및 시간 속성 대화 상자](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

이 스크린샷에서 생성 하는 코드를 최종 결과 비교 하려면 참조 [Win32 시계 상호 운용 샘플](https://go.microsoft.com/fwlink/?LinkID=160051)합니다.

## <a name="see-also"></a>참고자료

- <xref:System.Windows.Interop.HwndSource>
- [WPF 및 Win32 상호 운용성](wpf-and-win32-interoperation.md)
- [Win32 시계 상호 운용 샘플](https://go.microsoft.com/fwlink/?LinkID=160051)
