---
title: Windows Forms 컨트롤 및 해당 WPF 컨트롤
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: abfcb9f5398a6a8d264985543df585bea93a0446
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075277"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a><span data-ttu-id="803dd-102">Windows Forms 컨트롤 및 해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="803dd-102">Windows Forms Controls and Equivalent WPF Controls</span></span>
<span data-ttu-id="803dd-103">많은 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 해당 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 이지만 일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 해당 있는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-103">Many [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] controls, but some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have no equivalents in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span> <span data-ttu-id="803dd-104">이 항목에서는 두 기술에서 제공 하는 컨트롤 형식을 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-104">This topic compares control types provided by the two technologies.</span></span>  
  
 <span data-ttu-id="803dd-105">호스트에 대 한 상호 운용성을 항상 사용할 수 있습니다 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 에 해당 하는 없는 컨트롤에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-105">You can always use interoperation to host [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls that do not have equivalents in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
 <span data-ttu-id="803dd-106">다음 표에 나와 있는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 및 구성 요소가 같으면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-106">The following table shows which [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and components have equivalent [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control functionality.</span></span>  
  
|<span data-ttu-id="803dd-107">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="803dd-107">Windows Forms control</span></span>|<span data-ttu-id="803dd-108">해당 WPF 컨트롤</span><span class="sxs-lookup"><span data-stu-id="803dd-108">WPF equivalent control</span></span>|<span data-ttu-id="803dd-109">설명</span><span class="sxs-lookup"><span data-stu-id="803dd-109">Remarks</span></span>|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|<span data-ttu-id="803dd-110">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-110">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|<xref:System.Windows.Controls.ListBox> <span data-ttu-id="803dd-111">컴포지션과 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-111">with composition.</span></span>||  
|<xref:System.Windows.Forms.ColorDialog>|<span data-ttu-id="803dd-112">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-112">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<xref:System.Windows.Controls.ComboBox> <span data-ttu-id="803dd-113">자동 완성을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-113">does not support auto-complete.</span></span>|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<xref:System.Windows.Controls.TextBox> <span data-ttu-id="803dd-114">두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-114">and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.ErrorProvider>|<span data-ttu-id="803dd-115">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-115">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<xref:System.Windows.Controls.WrapPanel> <span data-ttu-id="803dd-116">또는</span><span class="sxs-lookup"><span data-stu-id="803dd-116">or</span></span> <xref:System.Windows.Controls.StackPanel>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|<span data-ttu-id="803dd-117">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-117">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.FontDialog>|<span data-ttu-id="803dd-118">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-118">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<xref:System.Windows.Window> <span data-ttu-id="803dd-119">자식 창을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-119">does not support child windows.</span></span>|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|<span data-ttu-id="803dd-120">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-120">No equivalent control.</span></span>|<span data-ttu-id="803dd-121">F1 도움말이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-121">No F1 Help.</span></span> <span data-ttu-id="803dd-122">"What is/이" 도움말 도구 설명으로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-122">"What's This" Help is replaced by ToolTips.</span></span>|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="803dd-123">컨테이너 컨트롤에 스크롤가 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-123">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.ImageList>|<span data-ttu-id="803dd-124">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-124">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|<span data-ttu-id="803dd-125">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-125">No equivalent control.</span></span>|<span data-ttu-id="803dd-126">사용할 수는 <xref:System.Windows.Documents.Hyperlink> 유동 콘텐츠 내에서 하이퍼링크를 호스트할 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-126">You can use the <xref:System.Windows.Documents.Hyperlink> class to host hyperlinks within flow content.</span></span>|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<span data-ttu-id="803dd-127"><xref:System.Windows.Controls.ListView> 컨트롤은 읽기 전용으로 세부 정보 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-127">The <xref:System.Windows.Controls.ListView> control provides a read-only details view.</span></span>|  
|<xref:System.Windows.Forms.MaskedTextBox>|<span data-ttu-id="803dd-128">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-128">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|<xref:System.Windows.Controls.Menu> <span data-ttu-id="803dd-129">동작 및 모양 컨트롤 스타일 지정 대략적인 수를 <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-129">control styling can approximate the behavior and appearance of the <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> class.</span></span>|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|<span data-ttu-id="803dd-130">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-130">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.NumericUpDown>|<xref:System.Windows.Controls.TextBox> <span data-ttu-id="803dd-131">두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-131">and two <xref:System.Windows.Controls.Primitives.RepeatButton> controls.</span></span>||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<span data-ttu-id="803dd-132">합니다 <xref:Microsoft.Win32.OpenFileDialog> 클래스는를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-132">The <xref:Microsoft.Win32.OpenFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.PageSetupDialog>|<span data-ttu-id="803dd-133">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-133">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|<span data-ttu-id="803dd-134">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-134">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|<span data-ttu-id="803dd-135">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-135">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|<span data-ttu-id="803dd-136">해당 하는 제어 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-136">No equivalent control.</span></span>||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<span data-ttu-id="803dd-137">합니다 <xref:Microsoft.Win32.SaveFileDialog> 클래스는를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼는 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-137">The <xref:Microsoft.Win32.SaveFileDialog> class is a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wrapper around the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control.</span></span>|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|<xref:System.Windows.Controls.ToolBar> <span data-ttu-id="803dd-138">컴포지션과 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-138">with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDown>|<xref:System.Windows.Controls.ToolBar> <span data-ttu-id="803dd-139">컴포지션과 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-139">with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|<xref:System.Windows.Controls.ToolBar> <span data-ttu-id="803dd-140">컴포지션과 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-140">with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolStripPanel>|<xref:System.Windows.Controls.ToolBar> <span data-ttu-id="803dd-141">컴포지션과 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-141">with composition.</span></span>||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|<span data-ttu-id="803dd-142">컨테이너 컨트롤에 스크롤가 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-142">Scrolling is built into container controls.</span></span>|  
|<xref:System.Windows.Forms.WebBrowser>|<xref:System.Windows.Controls.Frame><span data-ttu-id="803dd-143">,</span><span class="sxs-lookup"><span data-stu-id="803dd-143">,</span></span> <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType>|<span data-ttu-id="803dd-144"><xref:System.Windows.Controls.Frame> 컨트롤 HTML 페이지를 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-144">The <xref:System.Windows.Controls.Frame> control can host HTML pages.</span></span><br /><br /> <span data-ttu-id="803dd-145">부터 합니다 [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> HTML 페이지 및 백업 컨트롤 호스팅할 수 있습니다는 <xref:System.Windows.Controls.Frame> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="803dd-145">Starting in the [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], the <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> control can host HTML pages and also backs the <xref:System.Windows.Controls.Frame> control.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="803dd-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="803dd-146">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="803dd-147">Windows 용 WPF 디자이너 Forms 개발자</span><span class="sxs-lookup"><span data-stu-id="803dd-147">WPF Designer for Windows Forms Developers</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))
- [<span data-ttu-id="803dd-148">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="803dd-148">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [<span data-ttu-id="803dd-149">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="803dd-149">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="803dd-150">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="803dd-150">Migration and Interoperability</span></span>](migration-and-interoperability.md)
