---
title: Windows Forms 컨트롤 및 해당 WPF 컨트롤
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms [WPF], interoperability with
- Windows Forms [WPF], WPF interoperation
- interoperability [WPF], Windows Forms
ms.assetid: 8a157e6b-8054-46db-a5cf-a78966acc7a1
ms.openlocfilehash: 729f893a94688f4a1d8b0a770a3624b27ddfe1c1
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794078"
---
# <a name="windows-forms-controls-and-equivalent-wpf-controls"></a>Windows Forms 컨트롤 및 해당 WPF 컨트롤
많은 Windows Forms 컨트롤에는 동일한 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤이 있지만 일부 Windows Forms 컨트롤에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 해당 하는 항목이 없습니다. 이 항목에서는 두 기술에서 제공 하는 컨트롤 형식을 비교 합니다.  
  
 항상 상호 운용을 사용 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]기반 응용 프로그램에 해당 항목이 없는 Windows Forms 컨트롤을 호스트할 수 있습니다.  
  
 다음 표에서는 컨트롤과 구성 요소에 해당 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 제어 기능이 있는 Windows Forms 보여 줍니다.  
  
|Windows Forms 컨트롤|WPF 동일한 컨트롤|주의|  
|---------------------------|----------------------------|-------------|  
|<xref:System.Windows.Forms.BindingNavigator>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.BindingSource>|<xref:System.Windows.Data.CollectionViewSource>||  
|<xref:System.Windows.Forms.Button>|<xref:System.Windows.Controls.Button>||  
|<xref:System.Windows.Forms.CheckBox>|<xref:System.Windows.Controls.CheckBox>||  
|<xref:System.Windows.Forms.CheckedListBox>|컴퍼지션을 사용 하 여 <xref:System.Windows.Controls.ListBox> 합니다.||  
|<xref:System.Windows.Forms.ColorDialog>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.ComboBox>|<xref:System.Windows.Controls.ComboBox>|<xref:System.Windows.Controls.ComboBox>는 자동 완성을 지원 하지 않습니다.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|<xref:System.Windows.Controls.ContextMenu>||  
|<xref:System.Windows.Forms.DataGridView>|<xref:System.Windows.Controls.DataGrid>||  
|<xref:System.Windows.Forms.DateTimePicker>|<xref:System.Windows.Controls.DatePicker>||  
|<xref:System.Windows.Forms.DomainUpDown>|<xref:System.Windows.Controls.TextBox> 및 두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤입니다.||  
|<xref:System.Windows.Forms.ErrorProvider>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.FlowLayoutPanel>|<xref:System.Windows.Controls.WrapPanel> 또는 <xref:System.Windows.Controls.StackPanel>||  
|<xref:System.Windows.Forms.FolderBrowserDialog>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.FontDialog>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.Form>|<xref:System.Windows.Window>|<xref:System.Windows.Window>는 자식 창을 지원 하지 않습니다.|  
|<xref:System.Windows.Forms.GroupBox>|<xref:System.Windows.Controls.GroupBox>||  
|<xref:System.Windows.Forms.HelpProvider>|해당 하는 컨트롤이 없습니다.|F1 도움말이 없습니다. "What 's 's" 도움말은 도구 설명으로 대체 되었습니다.|  
|<xref:System.Windows.Forms.HScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|스크롤은 컨테이너 컨트롤에 기본 제공 됩니다.|  
|<xref:System.Windows.Forms.ImageList>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.Label>|<xref:System.Windows.Controls.Label>||  
|<xref:System.Windows.Forms.LinkLabel>|해당 하는 컨트롤이 없습니다.|<xref:System.Windows.Documents.Hyperlink> 클래스를 사용 하 여 유동 콘텐츠 내에서 하이퍼링크를 호스트할 수 있습니다.|  
|<xref:System.Windows.Forms.ListBox>|<xref:System.Windows.Controls.ListBox>||  
|<xref:System.Windows.Forms.ListView>|<xref:System.Windows.Controls.ListView>|<xref:System.Windows.Controls.ListView> 컨트롤은 읽기 전용 세부 정보 보기를 제공 합니다.|  
|<xref:System.Windows.Forms.MaskedTextBox>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.MenuStrip>|<xref:System.Windows.Controls.Menu>|컨트롤 스타일을 <xref:System.Windows.Controls.Menu> <xref:System.Windows.Forms.ToolStripProfessionalRenderer?displayProperty=nameWithType> 클래스의 동작과 모양을 대략적으로 지정할 수 있습니다.|  
|<xref:System.Windows.Forms.MonthCalendar>|<xref:System.Windows.Controls.Calendar>||  
|<xref:System.Windows.Forms.NotifyIcon>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.NumericUpDown>|<xref:System.Windows.Controls.TextBox> 및 두 개의 <xref:System.Windows.Controls.Primitives.RepeatButton> 컨트롤입니다.||  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog>|<xref:Microsoft.Win32.OpenFileDialog> 클래스는 Win32 컨트롤 주위의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼입니다.|  
|<xref:System.Windows.Forms.PageSetupDialog>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.Panel>|<xref:System.Windows.Controls.Canvas>||  
|<xref:System.Windows.Forms.PictureBox>|<xref:System.Windows.Controls.Image>||  
|<xref:System.Windows.Forms.PrintDialog>|<xref:System.Windows.Controls.PrintDialog>||  
|<xref:System.Drawing.Printing.PrintDocument>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.PrintPreviewControl>|<xref:System.Windows.Controls.DocumentViewer>||  
|<xref:System.Windows.Forms.PrintPreviewDialog>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.ProgressBar>|<xref:System.Windows.Controls.ProgressBar>||  
|<xref:System.Windows.Forms.PropertyGrid>|해당 하는 컨트롤이 없습니다.||  
|<xref:System.Windows.Forms.RadioButton>|<xref:System.Windows.Controls.RadioButton>||  
|<xref:System.Windows.Forms.RichTextBox>|<xref:System.Windows.Controls.RichTextBox>||  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog>|<xref:Microsoft.Win32.SaveFileDialog> 클래스는 Win32 컨트롤 주위의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 래퍼입니다.|  
|<xref:System.Windows.Forms.ScrollableControl>|<xref:System.Windows.Controls.ScrollViewer>||  
|<xref:System.Media.SoundPlayer>|<xref:System.Windows.Media.MediaPlayer>||  
|<xref:System.Windows.Forms.SplitContainer>|<xref:System.Windows.Controls.GridSplitter>||  
|<xref:System.Windows.Forms.StatusStrip>|<xref:System.Windows.Controls.Primitives.StatusBar>||  
|<xref:System.Windows.Forms.TabControl>|<xref:System.Windows.Controls.TabControl>||  
|<xref:System.Windows.Forms.TableLayoutPanel>|<xref:System.Windows.Controls.Grid>||  
|<xref:System.Windows.Forms.TextBox>|<xref:System.Windows.Controls.TextBox>||  
|<xref:System.Windows.Forms.Timer>|<xref:System.Windows.Threading.DispatcherTimer>||  
|<xref:System.Windows.Forms.ToolStrip>|<xref:System.Windows.Controls.ToolBar>||  
|<xref:System.Windows.Forms.ToolStripContainer>|컴퍼지션을 사용 하 여 <xref:System.Windows.Controls.ToolBar> 합니다.||  
|<xref:System.Windows.Forms.ToolStripDropDown>|컴퍼지션을 사용 하 여 <xref:System.Windows.Controls.ToolBar> 합니다.||  
|<xref:System.Windows.Forms.ToolStripDropDownMenu>|컴퍼지션을 사용 하 여 <xref:System.Windows.Controls.ToolBar> 합니다.||  
|<xref:System.Windows.Forms.ToolStripPanel>|컴퍼지션을 사용 하 여 <xref:System.Windows.Controls.ToolBar> 합니다.||  
|<xref:System.Windows.Forms.ToolTip>|<xref:System.Windows.Controls.ToolTip>||  
|<xref:System.Windows.Forms.TrackBar>|<xref:System.Windows.Controls.Slider>||  
|<xref:System.Windows.Forms.TreeView>|<xref:System.Windows.Controls.TreeView>||  
|<xref:System.Windows.Forms.UserControl>|<xref:System.Windows.Controls.UserControl>||  
|<xref:System.Windows.Forms.VScrollBar>|<xref:System.Windows.Controls.Primitives.ScrollBar>|스크롤은 컨테이너 컨트롤에 기본 제공 됩니다.|  
|<xref:System.Windows.Forms.WebBrowser>|<xref:System.Windows.Controls.Frame>, <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType>|<xref:System.Windows.Controls.Frame> 컨트롤은 HTML 페이지를 호스팅할 수 있습니다.<br /><br /> .NET Framework 3.5 s p 1부터 <xref:System.Windows.Controls.WebBrowser?displayProperty=nameWithType> 컨트롤은 HTML 페이지를 호스트 하 고 <xref:System.Windows.Controls.Frame> 컨트롤을 백업할 수도 있습니다.|  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Windows Forms 개발자를 위한 WPF 디자이너](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/cc165605(v=vs.100))
- [연습: WPF에서 Windows Forms 컨트롤 호스팅](walkthrough-hosting-a-windows-forms-control-in-wpf.md)
- [연습: Windows Forms에서 WPF 복합 컨트롤 호스팅](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [마이그레이션 및 상호 운용성](migration-and-interoperability.md)
