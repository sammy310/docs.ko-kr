---
title: WPF 버전 4.5의 새로운 기능
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 708b2fc231bfe7a9bc1f52872a0ec41c91931f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174708"
---
# <a name="whats-new-in-wpf-version-45"></a>WPF 버전 4.5의 새로운 기능
<a name="introduction"></a>이 항목에는 버전 4.5의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 새롭고 향상된 기능에 대한 정보가 포함되어 있습니다.  
  
 이 항목에는 다음과 같은 섹션이 포함되어 있습니다.  
  
- [리본 컨트롤](#ribbon_control)  
  
- [그룹화된 큰 데이터 집합을 표시할 때의 성능 개선](#grouped_virtualization)  
  
- [VirtualizingPanel의 새로운 기능](#VirtualizingPanel)  
  
- [정적 속성에 바인딩](#static_properties)  
  
- [UI가 아닌 스레드에서 컬렉션 액세스](#xthread_access)  
  
- [동기적 및 비동기적으로 데이터 유효성 검사](#INotifyDataErrorInfo)  
  
- [데이터 바인딩 원본을 자동으로 업데이트](#delay)  
  
- [ICustomTypeProvider를 구현하는 형식에 바인딩](#ICustomTypeProvider)  
  
- [바인딩 식에서 데이터 바인딩 정보 검색](#binding_state)  
  
- [유효한 DataContext 개체 확인](#DisconnectedSource)  
  
- [데이터 값이 변경될 때 데이터의 위치 변경(라이브 셰이핑)](#live_shaping)  
  
- [이벤트에 대한 약한 참조 설정을 위한 지원 개선](#weak_event_pattern)  
  
- [Dispatcher 클래스에 대한 새로운 메서드](#async)  
  
- [이벤트에 대한 태그 확장](#events_markup_extenions)  
  
<a name="ribbon_control"></a>
## <a name="ribbon-control"></a>리본 컨트롤  
 WPF 4.5는 <xref:System.Windows.Controls.Ribbon.Ribbon> 빠른 액세스 도구 모음, 응용 프로그램 메뉴 및 탭을 호스팅하는 컨트롤과 함께 제공됩니다.  자세한 내용은 [리본 개요](/visualstudio/vsto/ribbon-overview)를 참조하세요.  
  
<a name="grouped_virtualization"></a>
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>그룹화된 큰 데이터 집합을 표시할 때의 성능 개선  
 화면에 표시되는 항목에 따라 많은 수의 데이터 항목에서 사용자 인터페이스(UI) 요소의 하위 집합이 생성될 때 UI 가상화가 발생합니다. 는 <xref:System.Windows.Controls.VirtualizingPanel> 그룹화 <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> 된 데이터에 대 한 UI 가상화를 활성화 하는 연결 된 속성을 정의 합니다.  데이터 그룹화에 대한 자세한 내용은 방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화를 참조하세요.  그룹화된 데이터를 가상화하는 것에 <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> 대한 자세한 내용은 연결된 속성을 참조하십시오.  
  
<a name="VirtualizingPanel"></a>
## <a name="new-features-for-the-virtualizingpanel"></a>VirtualizingPanel의 새로운 기능  
  
1. 연결된 속성을 <xref:System.Windows.Controls.VirtualizingPanel>사용하여 <xref:System.Windows.Controls.VirtualizingStackPanel>"의 "의"와 같은 <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> 부분 항목이 표시되는지 여부를 지정할 수 있습니다. 로 설정된 경우 <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> 완전히 표시되는 항목만 표시됩니다. <xref:System.Windows.Controls.VirtualizingPanel> <xref:System.Windows.Controls.ScrollUnit.Item> 로 설정된 경우 <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> <xref:System.Windows.Controls.VirtualizingPanel> 부분적으로 표시되는 항목을 표시할 수 있습니다. <xref:System.Windows.Controls.ScrollUnit.Pixel>  
  
2. 연결된 속성을 사용하여 가상화할 때 <xref:System.Windows.Controls.VirtualizingPanel> 뷰포트 앞과 후에 캐시 <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> 크기를 지정할 수 있습니다.  캐시는 항목이 가상화되지 않는 뷰포트 위 또는 아래 공간 양입니다.  캐시를 사용하면 뷰로 스크롤하는 동안 UI 요소가 생성되지 않도록 하여 성능을 향상시킬 수 있습니다. 캐시는 낮은 우선 순위에서 채워지므로 작업 중에는 애플리케이션이 응답하지 않게 됩니다. 속성에 <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> 의해 <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>사용되는 측정 단위가 결정됩니다.  
  
<a name="static_properties"></a>
## <a name="binding-to-static-properties"></a>정적 속성에 바인딩  
 데이터 바인딩 원본으로 정적 속성을 사용할 수 있습니다. 데이터 바인딩 엔진은 정적 이벤트가 발생할 경우 속성 값이 변경되는 것을 인식합니다.  예를 들어 `SomeClass` 클래스가 `MyProperty`라는 정적 속성을 정의하는 경우 `SomeClass`는 `MyProperty` 값이 변경될 때 발생하는 정적 이벤트를 정의할 수 있습니다.  정적 이벤트는 다음 서명 중 하나를 사용할 수 있습니다.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 첫 번째 경우 클래스는 Event 처리기에 전달 <xref:System.EventArgs> 되는 *PropertyName* `Changed` 라는 정적 이벤트를 노출 합니다.  두 번째 경우 클래스는 이벤트 처리기에 `StaticPropertyChanged` 전달하는 <xref:System.ComponentModel.PropertyChangedEventArgs> 정적 이벤트를 노출합니다. 정적 속성을 구현하는 클래스에서 두 메서드 중 하나를 사용하여 속성-변경 알림이 발생하도록 선택할 수 있습니다.  
  
<a name="xthread_access"></a>
## <a name="accessing-collections-on-non-ui-threads"></a>UI가 아닌 스레드에서 컬렉션 액세스  
 WPF를 사용하면 컬렉션을 만들지 않은 스레드에서 데이터 컬렉션을 액세스하고 수정할 수 있습니다.  이를 통해 데이터베이스와 같은 외부 원본에서 데이터를 수신하는 데 백그라운드 스레드를 사용하고 UI 스레드에 데이터를 표시할 수 있습니다.  다른 스레드를 사용하여 콜렉션을 수정하면 사용자 인터페이스는 사용자 상호 작용에 응답성을 유지합니다.  
  
<a name="INotifyDataErrorInfo"></a>
## <a name="synchronously-and-asynchronously-validating-data"></a>동기적 및 비동기적으로 데이터 유효성 검사  
 이 <xref:System.ComponentModel.INotifyDataErrorInfo> 인터페이스를 사용하면 데이터 엔터티 클래스가 사용자 지정 유효성 검사 규칙을 구현하고 유효성 검사 결과를 비동기적으로 노출할 수 있습니다. 또한 이 인터페이스는 사용자 지정 오류 개체, 속성당 여러 오류, 속성 간 오류 및 엔터티 수준 오류도 지원합니다.  자세한 내용은 <xref:System.ComponentModel.INotifyDataErrorInfo>을 참조하세요.  
  
<a name="delay"></a>
## <a name="automatically-updating-the-source-of-a-data-binding"></a>데이터 바인딩 원본을 자동으로 업데이트  
 데이터 바인딩을 사용하여 데이터 원본을 업데이트하는 경우 <xref:System.Windows.Data.BindingBase.Delay%2A> 속성을 사용하여 원본이 업데이트되기 전에 속성이 대상에서 변경된 후 전달할 시간을 지정할 수 있습니다.  예를 들어 데이터 개체의 <xref:System.Windows.Controls.Slider> 속성에 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 양방향 바인딩된 속성이 있는 a가 있고 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>로 설정되었다고 가정합니다.  이 예제에서는 사용자가 <xref:System.Windows.Controls.Slider>이동할 때 이동 하는 각 픽셀에 <xref:System.Windows.Controls.Slider> 대 한 소스 업데이트 됩니다.  일반적으로 소스 개체는 슬라이더의 변경을 중지할 때만 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 슬라이더 값이 필요합니다.  소스를 너무 자주 업데이트하지 않도록 <xref:System.Windows.Data.BindingBase.Delay%2A> 하려면 엄지 손가락이 이동을 중지한 후 일정 시간이 경과할 때까지 소스를 업데이트하지 않도록 지정하는 데 사용합니다.  
  
<a name="ICustomTypeProvider"></a>
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>ICustomTypeProvider를 구현하는 형식에 바인딩  
 WPF는 사용자 지정 형식이라고도 하는 구현하는 <xref:System.Reflection.ICustomTypeProvider>개체에 대한 데이터 바인딩을 지원합니다.  다음과 같은 경우 사용자 지정 형식을 사용할 수 있습니다.  
  
1. <xref:System.Windows.PropertyPath> 데이터 바인딩에서. 예를 들어 <xref:System.Windows.Data.Binding.Path%2A> a의 <xref:System.Windows.Data.Binding> 속성은 사용자 지정 형식의 속성을 참조할 수 있습니다.  
  
2. <xref:System.Windows.DataTemplate.DataType%2A> 속성의 값으로.  
  
3. 에서 자동으로 생성된 열을 결정하는 형식입니다. <xref:System.Windows.Controls.DataGrid>  
  
<a name="binding_state"></a>
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>바인딩 식에서 데이터 바인딩 정보 검색  
 경우에 따라 <xref:System.Windows.Data.BindingExpression> 바인딩의 <xref:System.Windows.Data.Binding> 소스 및 대상 개체에 대한 정보를 얻을 수 있습니다.  원본 또는 대상 개체나 연결된 속성을 얻도록 새로운 API가 추가되었습니다.  <xref:System.Windows.Data.BindingExpression>이 API가 있는 경우 다음 API를 사용하여 대상 및 소스에 대한 정보를 가져옵니다.  
  
|바인딩의 다음 값을 찾으려면|다음 API 사용|  
|---------------------------------------|------------------|  
|대상 개체|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|대상 속성|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|소스 개체|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|원본 속성|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|에 <xref:System.Windows.Data.BindingExpression> 속하는지 여부<xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|의 소유자<xref:System.Windows.Data.BindingGroup>|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>
## <a name="checking-for-a-valid-datacontext-object"></a>유효한 DataContext 개체 확인  
 에 <xref:System.Windows.Controls.ItemsControl> 있는 항목 <xref:System.Windows.FrameworkElement.DataContext%2A> 컨테이너의 연결이 끊어지는 경우가 있습니다.  항목 컨테이너는 <xref:System.Windows.Controls.ItemsControl>에 항목을 표시하는 UI 요소입니다.  is가 <xref:System.Windows.Controls.ItemsControl> 컬렉션에 바인딩된 경우 각 항목에 대해 항목 컨테이너가 생성됩니다. 경우에 따라 항목 컨테이너는 시각적 트리에서 제거됩니다. 항목 컨테이너가 제거되는 두 가지 일반적인 경우는 기본 컬렉션에서 항목이 제거되고 <xref:System.Windows.Controls.ItemsControl>에서 가상화가 활성화된 경우입니다. 이러한 경우 항목 <xref:System.Windows.FrameworkElement.DataContext%2A> 컨테이너의 속성은 정적 속성에 의해 반환 되는 sentinel 개체로 <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> 설정 됩니다.  항목 컨테이너에 <xref:System.Windows.FrameworkElement.DataContext%2A> <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> 액세스하기 <xref:System.Windows.FrameworkElement.DataContext%2A> 전에 개체와 동일한지 확인해야 합니다.  
  
<a name="live_shaping"></a>
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>데이터 값이 변경될 때 데이터의 위치 변경(라이브 셰이핑)  
 데이터의 컬렉션을 그룹화, 정렬 또는 필터링할 수 있습니다. WPF 4.5에서는 데이터가 수정되면 데이터를 다시 배열할 수 있습니다. 예를 들어, 애플리케이션에서 사용 하는 <xref:System.Windows.Controls.DataGrid> 따라 주식 시장에 주식, 주식을 나열 하려면 정렬 합니다. 주식에서 실시간 정렬을 사용 하도록 설정 하는 경우 <xref:System.Windows.Data.CollectionView>에서 주식의 위치는 <xref:System.Windows.Controls.DataGrid> 재고 값이 큰 이동 또는 보다 작은 다른 주식의 값입니다.   자세한 내용은 인터페이스를 <xref:System.ComponentModel.ICollectionViewLiveShaping> 참조하십시오.  
  
<a name="weak_event_pattern"></a>
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>이벤트에 대한 약한 참조 설정을 위한 지원 개선  
 이벤트 구독자가 추가 인터페이스 구현 없이 참여할 수 있으므로 약한 이벤트 패턴을 구현하기가 더 쉬워졌습니다.  또한 <xref:System.Windows.WeakEventManager> 제네릭 클래스를 사용하면 특정 이벤트에 전용이 <xref:System.Windows.WeakEventManager> 없는 경우 구독자가 약한 이벤트 패턴에 참여할 수 있습니다.  자세한 내용은 [약한 이벤트 패턴](../advanced/weak-event-patterns.md)을 참조하세요.  
  
<a name="async"></a>
## <a name="new-methods-for-the-dispatcher-class"></a>Dispatcher 클래스에 대한 새로운 메서드  
 Dispatcher 클래스는 동기 및 비동기 작업에 대해 새로운 메서드를 정의합니다.  동기 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 메서드는 또는 <xref:System.Action> <xref:System.Func%601> 매개 변수를 사용하는 오버로드를 정의합니다. 새 비동기 메서드는 <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>을 <xref:System.Action> 호출 <xref:System.Func%601> 하거나 콜백 매개 변수로 <xref:System.Windows.Threading.DispatcherOperation> <xref:System.Windows.Threading.DispatcherOperation%601>사용 하 고 또는 를 반환 합니다.   및 클래스는 속성을 정의합니다. <xref:System.Threading.Tasks.Task> <xref:System.Windows.Threading.DispatcherOperation> <xref:System.Windows.Threading.DispatcherOperation%601>  호출할 <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>때 또는 연결된 `await` <xref:System.Windows.Threading.DispatcherOperation> <xref:System.Threading.Tasks.Task>키워드를 사용할 수 있습니다. <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>에서 반환되는 <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> <xref:System.Threading.Tasks.Task> 에 대해 동기적으로 기다려야 하는 경우 확장 메서드를 호출합니다. 작업이 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> 호출 스레드에서 큐에 대기 중인 경우 호출하면 교착 상태가 발생합니다. 비동기 작업을 수행하기 <xref:System.Threading.Tasks.Task> 위해 를 사용하는 것에 대한 자세한 내용은 [작업 병렬 처리(작업 병렬 라이브러리)를](../../../standard/parallel-programming/task-based-asynchronous-programming.md)참조하십시오.  
  
<a name="events_markup_extenions"></a>
## <a name="markup-extensions-for-events"></a>이벤트에 대한 태그 확장  
 WPF 4.5에서는 이벤트에 대한 태그 확장을 지원합니다.  WPF는 이벤트에 사용될 태그 확장을 정의하지 않지만 타사에서 이벤트에 사용할 수 있는 태그 확장을 만들 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [.NET 프레임워크의 새로운 내용](../../whats-new/index.md)
