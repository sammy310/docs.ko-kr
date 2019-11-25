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
ms.openlocfilehash: ae4d7f23729f5bd39558902a58d33c6c45572d85
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977015"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="e51ea-102">투명 효과 프레임을 WPF 애플리케이션으로 확장</span><span class="sxs-lookup"><span data-stu-id="e51ea-102">Extend Glass Frame Into a WPF Application</span></span>

<span data-ttu-id="e51ea-103">이 항목에서는 Windows Vista 투명 프레임을 Windows Presentation Foundation (WPF) 응용 프로그램의 클라이언트 영역으로 확장 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-103">This topic demonstrates how to extend the Windows Vista glass frame into the client area of a Windows Presentation Foundation (WPF) application.</span></span>

> [!NOTE]
> <span data-ttu-id="e51ea-104">이 예제는 투명 효과가 설정 된 상태에서 DWM (바탕 화면 창 관리자)을 실행 하는 Windows Vista 컴퓨터 에서만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-104">This example will only work on a Windows Vista machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> <span data-ttu-id="e51ea-105">Windows Vista Home Basic edition은 투명 효과를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-105">Windows Vista Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="e51ea-106">일반적으로 다른 버전의 Windows Vista에 투명 투명 효과를 적용 하 여 렌더링 되는 영역은 불투명 하 게 렌더링 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-106">Areas that would typically render with the transparent glass effect on other editions of Windows Vista are rendered opaque.</span></span>

## <a name="example"></a><span data-ttu-id="e51ea-107">예제</span><span class="sxs-lookup"><span data-stu-id="e51ea-107">Example</span></span>

<span data-ttu-id="e51ea-108">다음 이미지는 Internet Explorer 7의 주소 표시줄로 확장 된 투명 효과 프레임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7:</span></span>

![IE7 주소 표시줄에서 확장 된 투명 효과 프레임을 보여 주는 스크린샷](./media/extend-glass-frame-into-a-wpf-application/internet-explorer-glass-frame-extended-address-bar.png)

<span data-ttu-id="e51ea-110">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에서 투명 효과 프레임을 확장 하려면 관리 되지 않는 API에 대 한 액세스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-110">To extend the glass frame on a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, access to unmanaged API is needed.</span></span> <span data-ttu-id="e51ea-111">다음 코드 예제에서는 프레임을 클라이언트 영역으로 확장 하는 데 필요한 두 API에 대 한 플랫폼 호출 (pinvoke)을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-111">The following code example does a Platform Invoke (pinvoke) for the two API needed to extend the frame into the client area.</span></span> <span data-ttu-id="e51ea-112">이러한 각 API는 **Nonclient지역 api**라는 클래스에서 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-112">Each of these API are declared in a class called **NonClientRegionAPI**.</span></span>

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

<span data-ttu-id="e51ea-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)는 프레임을 클라이언트 영역으로 확장하는 DWM 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="e51ea-114">이 함수는 창 핸들 및 [MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) 구조체의 두 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-114">It takes two parameters; a window handle and a [MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) structure.</span></span> <span data-ttu-id="e51ea-115">[MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins)는 프레임을 클라이언트 영역으로 얼마나 추가로 확장해야 하는지를 나타내는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-115">[MARGINS](/windows/win32/api/uxtheme/ns-uxtheme-margins) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>

## <a name="example"></a><span data-ttu-id="e51ea-116">예제</span><span class="sxs-lookup"><span data-stu-id="e51ea-116">Example</span></span>

<span data-ttu-id="e51ea-117">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) 함수를 사용하려면 창 핸들을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-117">To use the [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) function, a window handle must be obtained.</span></span> <span data-ttu-id="e51ea-118">[!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]에서 창 핸들은 <xref:System.Windows.Interop.HwndSource>의 <xref:System.Windows.Interop.HwndSource.Handle%2A> 속성에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-118">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="e51ea-119">다음 예제에서 프레임은 창의 <xref:System.Windows.FrameworkElement.Loaded> 이벤트에서 클라이언트 영역으로 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-119">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>

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

## <a name="example"></a><span data-ttu-id="e51ea-120">예제</span><span class="sxs-lookup"><span data-stu-id="e51ea-120">Example</span></span>

<span data-ttu-id="e51ea-121">다음 예제는 프레임이 클라이언트 영역으로 확장되는 간단한 창을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-121">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="e51ea-122">프레임은 두 <xref:System.Windows.Controls.TextBox> 개체를 포함 하는 위쪽 테두리 뒤에 확장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-122">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>

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

<span data-ttu-id="e51ea-123">다음 이미지는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램으로 확장 된 투명 효과 프레임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e51ea-123">The following image illustrates the glass frame extended into a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application:</span></span>

![WPF 응용 프로그램으로 확장 된 투명 효과 프레임을 보여 주는 스크린샷](./media/extend-glass-frame-into-a-wpf-application/glass-frame-extended-wpf-application.png)

## <a name="see-also"></a><span data-ttu-id="e51ea-125">참조</span><span class="sxs-lookup"><span data-stu-id="e51ea-125">See also</span></span>

- [<span data-ttu-id="e51ea-126">바탕 화면 창 관리자 개요</span><span class="sxs-lookup"><span data-stu-id="e51ea-126">Desktop Window Manager Overview</span></span>](/windows/desktop/dwm/dwm-overview)
- [<span data-ttu-id="e51ea-127">바탕 화면 창 관리자 흐림 효과 개요</span><span class="sxs-lookup"><span data-stu-id="e51ea-127">Desktop Window Manager Blur Overview</span></span>](/windows/desktop/dwm/blur-ovw)
- [<span data-ttu-id="e51ea-128">DwmExtendFrameIntoClientArea</span><span class="sxs-lookup"><span data-stu-id="e51ea-128">DwmExtendFrameIntoClientArea</span></span>](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)
