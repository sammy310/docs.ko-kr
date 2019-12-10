---
title: 표준 컨트롤에 대한 UI 자동화 지원
ms.date: 03/30/2017
helpviewer_keywords:
- controls, UI Automation support for
- UI Automation, support for standard controls
ms.assetid: 3770ea8a-2655-4add-9c59-fe0610ad5084
ms.openlocfilehash: 314526c1164f70e6b261df1a6f11ddce2b5fa240
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74960073"
---
# <a name="ui-automation-support-for-standard-controls"></a>표준 컨트롤에 대한 UI 자동화 지원
> [!NOTE]
> 이 설명서는 <xref:System.Windows.Automation> 네임스페이스에 정의된 관리되는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] 클래스를 사용하려는 .NET Framework 개발자를 위한 것입니다. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 최신 정보는 [Windows 자동화 API: UI 자동화](/windows/win32/winauto/entry-uiauto-win32)를 참조하세요.  
  
 이 항목에는 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] , [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]및 [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]프레임워크용으로 개발된 애플리케이션에서 표준 컨트롤에 대한 [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)] 지원 정보가 들어 있습니다.  
  
<a name="Windows_Presentation_Foundation_Controls"></a>   
## <a name="windows-presentation-foundation-controls"></a>WPF(Windows Presentation Foundation) 컨트롤  
 사용자 상호 작용 지원 또는 정보를 제공하는 모든 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 컨트롤 요소에는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 대한 전체 기본 지원이 있습니다. 패널 등과 같은 기타 요소는 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에 표시되지 않습니다.  
  
<a name="Win32_Controls"></a>   
## <a name="win32-controls"></a>Win32 컨트롤  
 대부분의 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 컨트롤은 UIAutomationClientsideProviders.dll의 클라이언트쪽 공급자를 통해 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 에 노출됩니다. 이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.  
  
 *지원은 comctrl32.dll*버전 6의 컨트롤에 대해서만 전체 지원이 제공 됩니다.  
  
 다음과 같은 컨트롤이 지원됩니다.  
  
|클래스 이름|컨트롤 종류|  
|----------------|------------------|  
|단추|단추|  
|단추|RadioButton|  
|단추|그룹|  
|단추|CheckBox|  
|단추|하이퍼링크|  
|단추|SplitButton|  
|단추|CheckBox|  
|ComboBoxEx32|ComboBox|  
|ComboBox|ComboBox|  
|Edit|문서|  
|Edit|Edit|  
|SysLink|하이퍼링크|  
|Static|텍스트|  
|Static|이미지|  
|SysIPAddress32|사용자 지정|  
|SysHeader32|Header/HeaderItem|  
|SysListView32|DataGrid|  
|SysListView32|목록|  
|ListBox|목록|  
|ListBox|ListItem|  
|#32768|메뉴|  
|#32768|MenuItem|  
|msctls_progress32|ProgressBar|  
|RichEdit|문서입니다. 메모를 참조하세요.|  
|RichEdit20A|문서|  
|RichEdit20W|문서|  
|RichEdit50W|문서|  
|ScrollBar|슬라이더|  
|msctls_trackbar32|슬라이더|  
|msctls_updown32|Spinner|  
|msctls_statusbar32|StatusBar|  
|SysTabControl32|탭|  
|SysTabControl32|TabItem|  
|ToolbarWindow32|ToolBar|  
|ToolbarWindow32|MenuItem|  
|ToolbarWindow32|단추|  
|ToolbarWindow32|CheckBox|  
|ToolbarWindow32|RadioButton|  
|ToolbarWindow32|구분 기호|  
|tooltips_class32|도구 설명|  
|#32774|도구 설명|  
|ReBarWindow32|ToolBar|  
|SysTreeView32|Tree|  
|SysTreeView32|TreeItem|  
  
 **참고** RichEdit 컨트롤은 Windows Vista와 함께 제공 되는 버전에 대해서만 지원 됩니다 (Riched20.dll 버전 3.1 이상 및 Msftedit.dll 버전 4.1 이상).  
  
 다음 컨트롤은 지원되지 않습니다.  
  
|클래스 이름|컨트롤 형식|  
|----------------|------------------|  
|SysAnimate32|이미지|  
|SysPager|Spinner|  
|SysDateTimePick32|사용자 지정|  
|SysMonthCal32|일정|  
|MS_WINNOTE|도구 설명|  
|VBBubble|도구 설명|  
|스크롤 막대(독립 실행형 컨트롤로 사용되는 경우)|슬라이더|  
|SuperGrid|사용자 지정|  
  
<a name="Windows_Forms_Controls"></a>   
## <a name="windows-forms-controls"></a>Windows Forms 컨트롤  
 Windows Forms 컨트롤은 Uiautomationclientsideproviders.dll의 클라이언트 쪽 공급자를 통해 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]에 노출 됩니다. 이 어셈블리는 UI 자동화 클라이언트 애플리케이션과 함께 사용할 수 있도록 자동으로 등록됩니다.  
  
 일반적으로 [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)] 공용 컨트롤에 대해 관리 되는 래퍼 Windows Forms 컨트롤은 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]에서 지원 됩니다. 다음과 같은 컨트롤이 지원됩니다.  
  
|클래스 이름|  
|----------------|  
|단추|  
|CheckBox|  
|CheckedListBox|  
|ColorDialog|  
|ComboBox|  
|FolderBrowser|  
|FontDialog|  
|GroupBox|  
|HscrollBar|  
|ImageList|  
|레이블|  
|ListBox|  
|ListView|  
|MainMenu/ContextMenu|  
|MonthCalendar|  
|NotifyIcon|  
|OpenFileDialog|  
|PageSetupDialog|  
|PrintDialog|  
|ProgressBar|  
|RadioButton|  
|RichTextBox|  
|SaveFileDialog|  
|ScrollableControl|  
|SoundPlayer|  
|StatusBar|  
|TabControl/TabPage|  
|TextBox|  
|Timer|  
|ToolBar|  
|도구 설명|  
|TrackBar|  
|TreeView|  
|VscrollBar|  
|웹 브라우저|  
  
 다음 컨트롤은 Microsoft Active Accessibility에 대 한 지원을 통해서만 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] 제공 됩니다. 일부 기능은 사용하지 못할 수도 있습니다.  
  
|컨트롤 이름|  
|------------------|  
|BindingSource|  
|DataGrid|  
|DataGridView|  
|DataNavigator|  
|DomainUpDown|  
|ErrorProvider|  
|FlowLayoutPanel|  
|Form|  
|LinkLabel|  
|HelpProvider|  
|MaskedTextBox|  
|MenuStrip/ContextMenuStrip|  
|NumericUpDown|  
|패널|  
|PictureBox|  
|PrintDocument|  
|PrintPreview-Control|  
|PrintPreview-Dialog|  
|PropertyGrid|  
|UserControl|  
|ToolStrip|  
|TableLayoutPanel|  
|SplitContainer/SplitterPanel|  
|분할자|  
|RaftingContainer|  
|StatusStrip|  
  
## <a name="see-also"></a>참조

- [UI 자동화 컨트롤 형식](ui-automation-control-types.md)
