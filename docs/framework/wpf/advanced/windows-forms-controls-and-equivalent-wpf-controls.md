---
title: Windows Forms 컨트롤 및 해당 WPF 컨트롤
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: 7f531b60d8b31181688f3d0a6753b234ffc6c7dd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735213"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="5f5e4-102">Windows Forms 컨트롤 및 해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5f5e4-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="5f5e4-103">많은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에는 동일한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 있지만 일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 해당 하는 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="5f5e4-104">이 항목에서는 두 기술에서 제공 하는 컨트롤 형식을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="5f5e4-105">항상 상호 운용을 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램에 해당 항목이 없는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="5f5e4-106">다음 표에서는 컨트롤과 구성 요소에 해당 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제어 기능이 있는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="5f5e4-107">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5f5e4-107">Windows Forms control</span></span>|<span data-ttu-id="5f5e4-108">WPF 동일한 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5f5e4-108">WPF equivalent control</span></span>|<span data-ttu-id="5f5e4-109">주의</span><span class="sxs-lookup"><span data-stu-id="5f5e4-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="5f5e4-110">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<span data-ttu-id="5f5e4-111">컴퍼지션을 사용 하 여 <xref:System.Windows.Controls.ListBox> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-111"><xref:System.Windows.Controls.ListBox> with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="5f5e4-112">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<span data-ttu-id="5f5e4-113"><xref:System.Windows.Controls.ComboBox>는 자동 완성을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-113"><xref:System.Windows.Controls.ComboBox> does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<span data-ttu-id="5f5e4-114"><xref:System.Windows.Controls.TextBox> 및 두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-114"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="5f5e4-115">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<span data-ttu-id="5f5e4-116"><xref:System.Windows.Controls.WrapPanel> 또는 <xref:System.Windows.Controls.StackPanel></span><span class="sxs-lookup"><span data-stu-id="5f5e4-116"><xref:System.Windows.Controls.WrapPanel> or <xref:System.Windows.Controls.StackPanel></span></span>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="5f5e4-117">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="5f5e4-118">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<span data-ttu-id="5f5e4-119"><xref:System.Windows.Window>는 자식 창을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-119"><xref:System.Windows.Window> does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="5f5e4-120">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-120">No equivalent control.</span></span>|<span data-ttu-id="5f5e4-121">F1 도움말이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-121">No F1 Help.</span></span> <span data-ttu-id="5f5e4-122">"What 's 's" 도움말은 도구 설명으로 대체 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="5f5e4-123">스크롤은 컨테이너 컨트롤에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="5f5e4-124">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="5f5e4-125">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-125">No equivalent control.</span></span>|<span data-ttu-id="5f5e4-126"><xref:System.Windows.Documents.Hyperlink> 클래스를 사용 하 여 유동 콘텐츠 내에서 하이퍼링크를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="5f5e4-127"><xref:System.Windows.Controls.ListView> 컨트롤은 읽기 전용 세부 정보 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="5f5e4-128">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<span data-ttu-id="5f5e4-129">컨트롤 스타일을 <xref:System.Windows.Controls.Menu> <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> 클래스의 동작과 모양을 대략적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-129"><xref:System.Windows.Controls.Menu> control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="5f5e4-130">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<span data-ttu-id="5f5e4-131"><xref:System.Windows.Controls.TextBox> 및 두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-131"><xref:System.Windows.Controls.TextBox> and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="5f5e4-132"><xref:Microsoft.Win32.OpenFileDialog> 클래스는 Win32 컨트롤 주위의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the Win32 control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="5f5e4-133">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="5f5e4-134">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="5f5e4-135">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="5f5e4-136">해당 하는 컨트롤이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="5f5e4-137"><xref:Microsoft.Win32.SaveFileDialog> 클래스는 Win32 컨트롤 주위의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the Win32 control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<span data-ttu-id="5f5e4-138">컴퍼지션을 사용 하 여 <xref:System.Windows.Controls.ToolBar> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-138"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<span data-ttu-id="5f5e4-139">컴퍼지션을 사용 하 여 <xref:System.Windows.Controls.ToolBar> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-139"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<span data-ttu-id="5f5e4-140">컴퍼지션을 사용 하 여 <xref:System.Windows.Controls.ToolBar> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-140"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<span data-ttu-id="5f5e4-141">컴퍼지션을 사용 하 여 <xref:System.Windows.Controls.ToolBar> 합니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-141"><xref:System.Windows.Controls.ToolBar> with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="5f5e4-142">스크롤은 컨테이너 컨트롤에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<span data-ttu-id="5f5e4-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="5f5e4-143"><xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType></span></span>|<span data-ttu-id="5f5e4-144"><xref:System.Windows.Controls.Frame> 컨트롤은 HTML 페이지를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="5f5e4-145">.NET Framework 3.5 s p 1부터 <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> 컨트롤은 HTML 페이지를 호스트 하 고 <xref:System.Windows.Controls.Frame> 컨트롤을 백업할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5f5e4-145">Starting in the .NET Framework 3.5 SP1, the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5f5e4-146">참조</span><span class="sxs-lookup"><span data-stu-id="5f5e4-146">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- <span data-ttu-id="5f5e4-147">[Windows Forms 개발자를 위한 WPF 디자이너](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5f5e4-147">[WPF Designer for Windows Forms Developers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))</span></span>
- [<span data-ttu-id="5f5e4-148">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="5f5e4-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="5f5e4-149">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="5f5e4-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="5f5e4-150">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="5f5e4-150">Migration and Interoperability</span></span>](migration-and-interoperability.md)
