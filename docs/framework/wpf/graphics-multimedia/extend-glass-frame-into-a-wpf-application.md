---
title: 투명 효과 프레임을 WPF 애플리케이션으로 확장
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
ms.openlocfilehash: 11c872767b5e3595da1fb4982d3b12e0fc77db98
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68238597"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="2dc4d-102">투명 효과 프레임을 WPF 애플리케이션으로 확장</span><span class="sxs-lookup"><span data-stu-id="2dc4d-102">Extend Glass Frame Into a WPF Application</span></span>

<span data-ttu-id="2dc4d-103">이 항목을 확장 하는 방법에 설명 합니다 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] Windows Presentation Foundation (WPF) 응용 프로그램의 클라이언트 영역에 투명 효과 프레임입니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-103">This topic demonstrates how to extend the [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] glass frame into the client area of a Windows Presentation Foundation (WPF) application.</span></span>

> [!NOTE]
> <span data-ttu-id="2dc4d-104">이 예제는 투명 효과가 사용되도록 설정된 DWM(바탕 화면 창 관리자)를 실행하는 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] 컴퓨터에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-104">This example will only work on a [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] <span data-ttu-id="2dc4d-105">Home Basic Edition에서는 투명 효과를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-105">Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="2dc4d-106">일반적으로 [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]의 다른 버전에서 투명 효과로 렌더링되는 영역은 불투명하게 렌더링됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-106">Areas that would typically render with the transparent glass effect on other editions of [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] are rendered opaque.</span></span>

## <a name="example"></a><span data-ttu-id="2dc4d-107">예제</span><span class="sxs-lookup"><span data-stu-id="2dc4d-107">Example</span></span>

<span data-ttu-id="2dc4d-108">다음 이미지에 주소 표시줄의 Internet Explorer 7의 확장 된 투명 효과 프레임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7:</span></span>

![확장 IE7 주소 표시줄 뒤로 투명 효과 프레임을 보여 주는 스크린샷.](./media/extend-glass-frame-into-a-wpf-application/internet-explorer-glass-frame-extended-address-bar.png)

<span data-ttu-id="2dc4d-110">투명 효과 프레임을 확장 하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 관리 되지 않는 API에 대 한 액세스는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-110">To extend the glass frame on a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, access to unmanaged API is needed.</span></span> <span data-ttu-id="2dc4d-111">다음 코드 예제에서는 클라이언트 영역으로 프레임을 확장 하는 데 필요한 두 API에 대 한 플랫폼 호출 (pinvoke)을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-111">The following code example does a Platform Invoke (pinvoke) for the two API needed to extend the frame into the client area.</span></span> <span data-ttu-id="2dc4d-112">라는 클래스에 선언 된 이러한 API의 각 **NonClientRegionAPI**합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-112">Each of these API are declared in a class called **NonClientRegionAPI**.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential)]
public struct MARGINS
{
    public int cxLeftWidth;      // width of left border that retains its size
    public int cxRightWidth;     // width of right border that retains its size
    public int cyTopHeight;      // height of top border that retains its size
    public int cyBottomHeight;   // height of bottom border that retains its size
};

[DllImport("DwmApi.dll")]
public static extern int DwmExtendFrameIntoClientArea(
    IntPtr hwnd,
    ref MARGINS pMarInset);
```

```vb
<StructLayout(LayoutKind.Sequential)>
Public Structure MARGINS
    Public cxLeftWidth As Integer ' width of left border that retains its size
    Public cxRightWidth As Integer ' width of right border that retains its size
    Public cyTopHeight As Integer ' height of top border that retains its size
    Public cyBottomHeight As Integer ' height of bottom border that retains its size
End Structure

<DllImport("DwmApi.dll")>
Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer
End Function
```

<span data-ttu-id="2dc4d-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)는 프레임을 클라이언트 영역으로 확장하는 DWM 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="2dc4d-114">이 함수는 창 핸들 및 [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) 구조체의 두 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-114">It takes two parameters; a window handle and a [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) structure.</span></span> <span data-ttu-id="2dc4d-115">[MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins)는 프레임을 클라이언트 영역으로 얼마나 추가로 확장해야 하는지를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-115">[MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>

## <a name="example"></a><span data-ttu-id="2dc4d-116">예제</span><span class="sxs-lookup"><span data-stu-id="2dc4d-116">Example</span></span>

<span data-ttu-id="2dc4d-117">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) 함수를 사용하려면 창 핸들을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-117">To use the [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) function, a window handle must be obtained.</span></span> <span data-ttu-id="2dc4d-118">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 창 핸들을 가져올 수 있습니다 합니다 <xref:System.Windows.Interop.HwndSource.Handle%2A> 의 속성을 <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-118">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="2dc4d-119">다음 예제에서는 프레임은 확장을 클라이언트 영역으로에 <xref:System.Windows.FrameworkElement.Loaded> 창의 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-119">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>

```csharp
void OnLoaded(object sender, RoutedEventArgs e)
{
   try
   {
      // Obtain the window handle for WPF application
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);

      // Get System Dpi
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);
      float DesktopDpiX = desktop.DpiX;
      float DesktopDpiY = desktop.DpiY;

      // Set Margins
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();

      // Extend glass frame into client area
      // Note that the default desktop Dpi is 96dpi. The  margins are
      // adjusted for the system Dpi.
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));

      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);
      //
      if (hr < 0)
      {
         //DwmExtendFrameIntoClientArea Failed
      }
   }
   // If not Vista, paint background white.
   catch (DllNotFoundException)
   {
      Application.Current.MainWindow.Background = Brushes.White;
   }
}
```

## <a name="example"></a><span data-ttu-id="2dc4d-120">예제</span><span class="sxs-lookup"><span data-stu-id="2dc4d-120">Example</span></span>

<span data-ttu-id="2dc4d-121">다음 예제는 프레임이 클라이언트 영역으로 확장되는 간단한 창을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-121">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="2dc4d-122">프레임은 두 가지를 포함 하는 위쪽 테두리 뒤로 확장 됩니다 <xref:System.Windows.Controls.TextBox> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2dc4d-122">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>

```xaml
<Window x:Class="SDKSample.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Title="Extended Glass in WPF" Height="300" Width="400"
    Loaded="OnLoaded" Background="Transparent"
    >
  <Grid ShowGridLines="True">
    <DockPanel Name="mainDock">
      <!-- The border is used to compute the rendered height with margins.
           topBar contents will be displayed on the extended glass frame.-->
      <Border Name="topBar" DockPanel.Dock="Top" >
        <Grid Name="grid">
          <Grid.ColumnDefinitions>
            <ColumnDefinition MinWidth="100" Width="*"/>
            <ColumnDefinition Width="Auto"/>
          </Grid.ColumnDefinitions>
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>
        </Grid>
      </Border>
      <Grid DockPanel.Dock="Top" >
        <Grid.ColumnDefinitions>
          <ColumnDefinition/>
        </Grid.ColumnDefinitions>
        <TextBox Grid.Column="0" AcceptsReturn="True"/>
      </Grid>
    </DockPanel>
  </Grid>
</Window>
```

<span data-ttu-id="2dc4d-123">다음 이미지는 보여줍니다로 확장 된 투명 효과 프레임을 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램:</span><span class="sxs-lookup"><span data-stu-id="2dc4d-123">The following image illustrates the glass frame extended into a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application:</span></span>

![WPF 응용 프로그램으로 확장 된 투명 효과 프레임을 보여주는 스크린샷.](./media/extend-glass-frame-into-a-wpf-application/glass-frame-extended-wpf-application.png)

## <a name="see-also"></a><span data-ttu-id="2dc4d-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="2dc4d-125">See also</span></span>

- [<span data-ttu-id="2dc4d-126">바탕 화면 창 관리자 개요</span><span class="sxs-lookup"><span data-stu-id="2dc4d-126">Desktop Window Manager Overview</span></span>](/windows/desktop/dwm/dwm-overview)
- [<span data-ttu-id="2dc4d-127">바탕 화면 창 관리자 흐림 효과 개요</span><span class="sxs-lookup"><span data-stu-id="2dc4d-127">Desktop Window Manager Blur Overview</span></span>](/windows/desktop/dwm/blur-ovw)
- [<span data-ttu-id="2dc4d-128">DwmExtendFrameIntoClientArea</span><span class="sxs-lookup"><span data-stu-id="2dc4d-128">DwmExtendFrameIntoClientArea</span></span>](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)
