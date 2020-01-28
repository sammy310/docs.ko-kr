---
title: 제어 성능 최적화
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], improving performance
- container recycling [WPF]
- user interface virtualization [WPF]
ms.assetid: 45a31c43-ea8a-4546-96c8-0631b9934179
ms.openlocfilehash: d02fde7076cd6a24fdfb171ed54161b20f3d465e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746735"
---
# <a name="optimizing-performance-controls"></a>성능 최적화: 컨트롤

WPF (Windows Presentation Foundation)에는 대부분의 Windows 응용 프로그램에서 사용 되는 일반적인 UI (사용자 인터페이스) 구성 요소가 많이 포함 되어 있습니다. 이 항목에서는 UI의 성능을 향상시킬 수 있는 기술에 대해 설명합니다.

## <a name="displaying-large-data-sets"></a>대량 데이터 집합 표시

<xref:System.Windows.Controls.ListView> 및 <xref:System.Windows.Controls.ComboBox> 같은 WPF 컨트롤은 응용 프로그램에서 항목 목록을 표시 하는 데 사용 됩니다. 표시할 목록이 크면 애플리케이션의 성능에 영향을 줄 수 있습니다. 그 이유는 표준 레이아웃 시스템에서는 목록 컨트롤과 연결된 각 항목에 대해 레이아웃 컨테이너를 만들고 해당 레이아웃의 크기와 위치를 계산하기 때문입니다. 대개는 모든 항목을 동시에 표시할 필요가 없습니다. 대신 항목의 일부만 표시하고 사용자가 목록을 스크롤하면 됩니다. 이 경우에는 UI *가상화*를 사용하는 것이 적합합니다. 가상화를 사용하면 항목이 실제로 표시될 때까지 해당 항목에 대한 항목 컨테이너 생성 및 연결된 레이아웃에 대한 계산이 지연됩니다.

UI 가상화는 목록 컨트롤의 중요한 요소입니다. UI 가상화를 데이터 가상화와 혼동해서는 안 됩니다. UI 가상화의 경우 표시 가능한 항목만 메모리에 저장되지만 데이터 바인딩 시나리오에서는 전체 데이터 구조가 메모리에 저장됩니다. 반면 데이터 가상화의 경우 화면에 표시되는 데이터 항목만 메모리에 저장됩니다.

기본적으로 UI 가상화는 <xref:System.Windows.Controls.ListView>에 대해 사용 하도록 설정 되며 목록 항목이 데이터에 바인딩될 때 컨트롤을 <xref:System.Windows.Controls.ListBox> 합니다. <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=nameWithType> 연결 된 속성을 `true`로 설정 하 여 <xref:System.Windows.Controls.TreeView> 가상화를 사용 하도록 설정할 수 있습니다. <xref:System.Windows.Controls.ItemsControl> 또는 <xref:System.Windows.Controls.StackPanel> 클래스를 사용 하는 기존 항목 컨트롤 (예: <xref:System.Windows.Controls.ComboBox>)에서 파생 되는 사용자 지정 컨트롤에 대 한 UI 가상화를 사용 하도록 설정 하려면 <xref:System.Windows.Controls.ItemsControl.ItemsPanel%2A>를 <xref:System.Windows.Controls.VirtualizingStackPanel>로 설정 하 고 <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizing%2A>를 `true`로 설정 하면 됩니다. 그러나 자신도 모르게 이러한 컨트롤의 UI 가상화 기능이 해제될 수 있습니다. UI 가상화는 다음과 같은 경우에 해제됩니다.

- 항목 컨테이너는 <xref:System.Windows.Controls.ItemsControl>에 직접 추가 됩니다. 예를 들어 응용 프로그램에서 <xref:System.Windows.Controls.ListBoxItem> 개체를 <xref:System.Windows.Controls.ListBox>에 명시적으로 추가 하는 경우 <xref:System.Windows.Controls.ListBox>는 <xref:System.Windows.Controls.ListBoxItem> 개체를 가상화 하지 않습니다.

- <xref:System.Windows.Controls.ItemsControl>의 항목 컨테이너는 서로 다른 형식입니다. 예를 들어 <xref:System.Windows.Controls.Separator> 개체를 사용 하는 <xref:System.Windows.Controls.Menu>는 <xref:System.Windows.Controls.Menu>에 <xref:System.Windows.Controls.Separator> 및 <xref:System.Windows.Controls.MenuItem>형식의 개체가 포함 되어 있으므로 항목 재생을 구현할 수 없습니다.

- `false`<xref:System.Windows.Controls.ScrollViewer.CanContentScroll%2A>를 설정 합니다.

- `false`<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A>를 설정 합니다.

항목 컨테이너를 가상화할 때 항목에 속한 항목 컨테이너와 관련된 추가 상태 정보가 있는지 여부를 고려해야 합니다. 이 경우 추가 상태를 저장해야 합니다. 예를 들어 <xref:System.Windows.Controls.Expander> 컨트롤에 포함 된 항목이 있고 <xref:System.Windows.Controls.Expander.IsExpanded%2A> 상태가 항목의 컨테이너에 바인딩되고 항목 자체에는 바인딩되지 않을 수 있습니다. 새 항목에 대해 컨테이너를 다시 사용 하는 경우 <xref:System.Windows.Controls.Expander.IsExpanded%2A>의 현재 값이 새 항목에 사용 됩니다. 또한 이전 항목이 올바른 <xref:System.Windows.Controls.Expander.IsExpanded%2A> 값을 잃게 됩니다.

현재 모든 WPF 컨트롤은 데이터 가상화를 기본적으로 지원하지 않습니다.

## <a name="container-recycling"></a>컨테이너 재활용

<xref:System.Windows.Controls.ItemsControl>에서 상속 되는 컨트롤에 대해 .NET Framework 3.5 s p 1에 추가 된 UI 가상화에 대 한 최적화는 *컨테이너 재활용으로,* 스크롤 성능을 향상 시킬 수도 있습니다. UI 가상화를 사용 하는 <xref:System.Windows.Controls.ItemsControl> 채워진 경우 뷰로 스크롤 하는 각 항목에 대 한 항목 컨테이너를 만들고 보기에서 스크롤 하는 각 항목에 대 한 항목 컨테이너를 삭제 합니다. *컨테이너를 재활용* 하면 컨트롤이 다른 데이터 항목에 대해 기존 항목 컨테이너를 다시 사용할 수 있으므로 사용자가 <xref:System.Windows.Controls.ItemsControl>을 스크롤하면 항목 컨테이너가 지속적으로 생성 되 고 제거 되지 않습니다. <xref:System.Windows.Controls.VirtualizationMode.Recycling><xref:System.Windows.Controls.VirtualizingPanel.VirtualizationMode%2A> 연결 된 속성을 설정 하 여 항목 재활용을 사용 하도록 선택할 수 있습니다.

가상화를 지 원하는 모든 <xref:System.Windows.Controls.ItemsControl> 컨테이너 재활용을 사용할 수 있습니다. <xref:System.Windows.Controls.ListBox>에서 컨테이너 재활용을 사용 하도록 설정 하는 방법에 대 한 예제는 [ListBox의 스크롤 성능 향상](../controls/how-to-improve-the-scrolling-performance-of-a-listbox.md)을 참조 하세요.

## <a name="supporting-bidirectional-virtualization"></a>양방향 가상화 지원

<xref:System.Windows.Controls.VirtualizingStackPanel>는 가로 또는 세로 방향으로 UI 가상화에 대 한 기본 제공 지원을 제공 합니다. 컨트롤에 양방향 가상화를 사용 하려는 경우 <xref:System.Windows.Controls.VirtualizingStackPanel> 클래스를 확장 하는 사용자 지정 패널을 구현 해야 합니다. <xref:System.Windows.Controls.VirtualizingStackPanel> 클래스는 <xref:System.Windows.Controls.VirtualizingStackPanel.OnViewportSizeChanged%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.LineUp%2A>, <xref:System.Windows.Controls.VirtualizingStackPanel.PageUp%2A>및 <xref:System.Windows.Controls.VirtualizingStackPanel.MouseWheelUp%2A>와 같은 가상 메서드를 노출 합니다. 이러한 가상 메서드를 사용 하 여 목록에서 표시 되는 부분에 대 한 변경 내용을 감지 하 고 적절 하 게 처리할 수 있습니다.

## <a name="optimizing-templates"></a>템플릿 최적화

시각적 트리에는 애플리케이션의 모든 시각적 요소가 포함됩니다. 여기에는 직접 만든 개체뿐만 아니라 템플릿 확장에 따른 개체도 포함됩니다. 예를 들어 <xref:System.Windows.Controls.Button>를 만들 때 시각적 트리에서 <xref:Microsoft.Windows.Themes.ClassicBorderDecorator> 및 <xref:System.Windows.Controls.ContentPresenter> 개체도 가져올 수 있습니다. 컨트롤 템플릿을 최적화하지 않으면 시각적 트리에 수많은 불필요한 개체가 만들어질 수 있습니다. 시각적 트리에 대한 자세한 내용은 [WPF 그래픽 렌더링 개요](../graphics-multimedia/wpf-graphics-rendering-overview.md)를 참조하세요.

## <a name="deferred-scrolling"></a>스크롤 지연

기본적으로 사용자가 스크롤 막대의 위치 조정 컨트롤을 끌면 콘텐츠 뷰가 지속적으로 업데이트됩니다. 컨트롤의 스크롤 속도가 느린 경우에는 스크롤 지연을 사용하는 것이 좋습니다. 스크롤 지연을 사용하면 사용자가 위치 조정 컨트롤을 놓을 때만 콘텐츠가 업데이트됩니다.

지연 된 스크롤을 구현 하려면 <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A> 속성을 `true`로 설정 합니다. <xref:System.Windows.Controls.ScrollViewer.IsDeferredScrollingEnabled%2A>는 연결 된 속성 이며 <xref:System.Windows.Controls.ScrollViewer> 및 해당 컨트롤 템플릿에 <xref:System.Windows.Controls.ScrollViewer> 있는 모든 컨트롤에 대해 설정할 수 있습니다.

## <a name="controls-that-implement-performance-features"></a>성능 기능을 구현 하는 컨트롤

다음 표에서는 데이터를 표시하는 일반적인 컨트롤 및 각 컨트롤에 성능 기능이 지원되는지 여부를 보여 줍니다. 이러한 기능을 설정하는 방법은 이전 섹션을 참조하세요.

|Control|가상화|컨테이너 재활용|스크롤 지연|
|-------------|--------------------|-------------------------|------------------------|
|<xref:System.Windows.Controls.ComboBox>|사용할 수 있음|사용할 수 있음|사용할 수 있음|
|<xref:System.Windows.Controls.ContextMenu>|사용할 수 있음|사용할 수 있음|사용할 수 있음|
|<xref:System.Windows.Controls.DocumentViewer>|사용할 수 없음|사용할 수 없음|사용할 수 있음|
|<xref:System.Windows.Controls.ListBox>|기본|사용할 수 있음|사용할 수 있음|
|<xref:System.Windows.Controls.ListView>|기본|사용할 수 있음|사용할 수 있음|
|<xref:System.Windows.Controls.TreeView>|사용할 수 있음|사용할 수 있음|사용할 수 있음|
|<xref:System.Windows.Controls.ToolBar>|사용할 수 없음|사용할 수 없음|사용할 수 있음|

> [!NOTE]
> <xref:System.Windows.Controls.TreeView>에서 가상화 및 컨테이너 재활용을 사용 하도록 설정 하는 방법에 대 한 예제는 [TreeView의 성능 향상](../controls/how-to-improve-the-performance-of-a-treeview.md)을 참조 하세요.

## <a name="see-also"></a>참조

- [레이아웃](layout.md)
- [레이아웃 및 디자인](optimizing-performance-layout-and-design.md)
- [데이터 바인딩](optimizing-performance-data-binding.md)
- [컨트롤](../controls/index.md)
- [스타일 지정 및 템플릿](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [연습: WPF 애플리케이션에서 애플리케이션 데이터 캐싱](walkthrough-caching-application-data-in-a-wpf-application.md)
