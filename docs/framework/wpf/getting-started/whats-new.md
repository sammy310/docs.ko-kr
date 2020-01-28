---
title: WPF 버전 4.5의 새로운 기능
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Presentation Foundation [WPF], what's new
- WPF [WPF], what's new
ms.assetid: db086ae4-70bb-4862-95db-2eaca5216bc3
ms.openlocfilehash: 8eff8da7746047c450b2e23af63d43b13f3b970c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746924"
---
# <a name="whats-new-in-wpf-version-45"></a>WPF 버전 4.5의 새로운 기능
<a name="introduction"></a>이 항목에는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 버전 4.5의 새로운 기능과 향상 된 기능에 대 한 정보가 포함 되어 있습니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
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
 WPF 4.5는 빠른 실행 도구 모음, 응용 프로그램 메뉴 및 탭을 호스트 하는 <xref:System.Windows.Controls.Ribbon.Ribbon> 컨트롤과 함께 제공 됩니다.  자세한 내용은 [리본 개요](/visualstudio/vsto/ribbon-overview)를 참조하세요.  
  
<a name="grouped_virtualization"></a>   
## <a name="improved-performance-when-displaying-large-sets-of-grouped-data"></a>그룹화된 큰 데이터 집합을 표시할 때의 성능 개선  
 화면에 표시되는 항목에 따라 많은 수의 데이터 항목에서 사용자 인터페이스(UI) 요소의 하위 집합이 생성될 때 UI 가상화가 발생합니다. <xref:System.Windows.Controls.VirtualizingPanel>는 그룹화 된 데이터에 대 한 UI 가상화를 사용 하는 <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> 연결 된 속성을 정의 합니다.  데이터 그룹화에 대한 자세한 내용은 방법: XAML에서 뷰를 사용하여 데이터 정렬 및 그룹화를 참조하세요.  그룹화 된 데이터를 가상화 하는 방법에 대 한 자세한 내용은 연결 된 <xref:System.Windows.Controls.VirtualizingPanel.IsVirtualizingWhenGrouping%2A> 속성을 참조 하세요.  
  
<a name="VirtualizingPanel"></a>   
## <a name="new-features-for-the-virtualizingpanel"></a>VirtualizingPanel의 새로운 기능  
  
1. <xref:System.Windows.Controls.VirtualizingStackPanel>와 같은 <xref:System.Windows.Controls.VirtualizingPanel><xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A> 연결 된 속성을 사용 하 여 부분 항목을 표시할지 여부를 지정할 수 있습니다. <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>을 <xref:System.Windows.Controls.ScrollUnit.Item>로 설정 하면 <xref:System.Windows.Controls.VirtualizingPanel>에는 완전히 표시 되는 항목만 표시 됩니다. <xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>을 <xref:System.Windows.Controls.ScrollUnit.Pixel>로 설정 하면 <xref:System.Windows.Controls.VirtualizingPanel>에서 부분적으로 표시 되는 항목을 표시할 수 있습니다.  
  
2. <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A> 연결 된 속성을 사용 하 여 <xref:System.Windows.Controls.VirtualizingPanel>를 가상화 할 때 뷰포트 전후에 캐시 크기를 지정할 수 있습니다.  캐시는 항목이 가상화되지 않는 뷰포트 위 또는 아래 공간 양입니다.  캐시를 사용하면 뷰로 스크롤하는 동안 UI 요소가 생성되지 않도록 하여 성능을 향상시킬 수 있습니다. 캐시는 낮은 우선 순위에서 채워지므로 작업 중에는 애플리케이션이 응답하지 않게 됩니다. 합니다 <xref:System.Windows.Controls.VirtualizingPanel.CacheLengthUnit%2A?displayProperty=nameWithType> 속성에서 사용 되는 측정 단위를 결정 <xref:System.Windows.Controls.VirtualizingPanel.CacheLength%2A?displayProperty=nameWithType>합니다.  
  
<a name="static_properties"></a>   
## <a name="binding-to-static-properties"></a>정적 속성에 바인딩  
 데이터 바인딩 원본으로 정적 속성을 사용할 수 있습니다. 데이터 바인딩 엔진은 정적 이벤트가 발생할 경우 속성 값이 변경되는 것을 인식합니다.  예를 들어 `SomeClass` 클래스가 `MyProperty`라는 정적 속성을 정의하는 경우 `SomeClass`는 `MyProperty` 값이 변경될 때 발생하는 정적 이벤트를 정의할 수 있습니다.  정적 이벤트는 다음 서명 중 하나를 사용할 수 있습니다.  
  
- `public static event EventHandler MyPropertyChanged;`  
  
- `public static event EventHandler<PropertyChangedEventArgs> StaticPropertyChanged;`  
  
 첫 번째 경우에 클래스는 이벤트 처리기에 <xref:System.EventArgs>를 전달 하는 *PropertyName*`Changed` 이라는 정적 이벤트를 노출 합니다.  두 번째 경우 클래스는 이벤트 처리기에 <xref:System.ComponentModel.PropertyChangedEventArgs>를 전달 하는 `StaticPropertyChanged` 이라는 정적 이벤트를 노출 합니다. 정적 속성을 구현하는 클래스에서 두 메서드 중 하나를 사용하여 속성-변경 알림이 발생하도록 선택할 수 있습니다.  
  
<a name="xthread_access"></a>   
## <a name="accessing-collections-on-non-ui-threads"></a>UI가 아닌 스레드에서 컬렉션 액세스  
 WPF를 사용하면 컬렉션을 만들지 않은 스레드에서 데이터 컬렉션을 액세스하고 수정할 수 있습니다.  이를 통해 데이터베이스와 같은 외부 원본에서 데이터를 수신하는 데 백그라운드 스레드를 사용하고 UI 스레드에 데이터를 표시할 수 있습니다.  다른 스레드를 사용하여 콜렉션을 수정하면 사용자 인터페이스는 사용자 상호 작용에 응답성을 유지합니다.  
  
<a name="INotifyDataErrorInfo"></a>   
## <a name="synchronously-and-asynchronously-validating-data"></a>동기적 및 비동기적으로 데이터 유효성 검사  
 <xref:System.ComponentModel.INotifyDataErrorInfo> 인터페이스를 사용 하면 데이터 엔터티 클래스에서 사용자 지정 유효성 검사 규칙을 구현 하 고 유효성 검사 결과를 비동기적으로 표시할 수 있습니다. 또한 이 인터페이스는 사용자 지정 오류 개체, 속성당 여러 오류, 속성 간 오류 및 엔터티 수준 오류도 지원합니다.  자세한 내용은 <xref:System.ComponentModel.INotifyDataErrorInfo>를 참조하세요.  
  
<a name="delay"></a>   
## <a name="automatically-updating-the-source-of-a-data-binding"></a>데이터 바인딩 원본을 자동으로 업데이트  
 데이터 바인딩을 사용 하 여 데이터 소스를 업데이트 하는 경우 <xref:System.Windows.Data.BindingBase.Delay%2A> 속성을 사용 하 여 소스가 업데이트 되기 전에 대상에서 속성이 변경 된 후에 전달할 시간을 지정할 수 있습니다.  예를 들어, 데이터 개체의 속성에 양방향 바인딩된 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 속성 데이터를 가진 <xref:System.Windows.Controls.Slider> 있고 <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> 속성이 <xref:System.Windows.Data.UpdateSourceTrigger.PropertyChanged>로 설정 되어 있다고 가정 합니다.  이 예제에서 사용자가 <xref:System.Windows.Controls.Slider>이동 하면 <xref:System.Windows.Controls.Slider> 이동 하는 각 픽셀에 대 한 소스가 업데이트 됩니다.  일반적으로 소스 개체는 슬라이더의 <xref:System.Windows.Controls.Primitives.RangeBase.Value%2A> 변경을 중지 하는 경우에만 슬라이더의 값이 필요 합니다.  소스를 너무 자주 업데이트 하지 않도록 하려면 <xref:System.Windows.Data.BindingBase.Delay%2A>를 사용 하 여 thumb이 이동이 중지 된 후 특정 시간이 경과할 때까지 원본을 업데이트 하지 않도록 지정 합니다.  
  
<a name="ICustomTypeProvider"></a>   
## <a name="binding-to-types-that-implement-icustomtypeprovider"></a>ICustomTypeProvider를 구현하는 형식에 바인딩  
 WPF는 사용자 지정 형식이 라고도 하는 <xref:System.Reflection.ICustomTypeProvider>를 구현 하는 개체에 대 한 데이터 바인딩을 지원 합니다.  다음과 같은 경우 사용자 지정 형식을 사용할 수 있습니다.  
  
1. 데이터 바인딩에서의 <xref:System.Windows.PropertyPath>입니다. 예를 들어 <xref:System.Windows.Data.Binding>의 <xref:System.Windows.Data.Binding.Path%2A> 속성은 사용자 지정 형식의 속성을 참조할 수 있습니다.  
  
2. <xref:System.Windows.DataTemplate.DataType%2A> 속성의 값입니다.  
  
3. <xref:System.Windows.Controls.DataGrid>에서 자동으로 생성 된 열을 결정 하는 형식입니다.  
  
<a name="binding_state"></a>   
## <a name="retrieving-data-binding-information-from-a-binding-expression"></a>바인딩 식에서 데이터 바인딩 정보 검색  
 특정 한 경우에는 <xref:System.Windows.Data.Binding> <xref:System.Windows.Data.BindingExpression>를 가져오고 바인딩의 원본 및 대상 개체에 대 한 정보가 필요할 수 있습니다.  원본 또는 대상 개체나 연결된 속성을 얻도록 새로운 API가 추가되었습니다.  <xref:System.Windows.Data.BindingExpression>있는 경우 다음 Api를 사용 하 여 대상 및 원본에 대 한 정보를 가져옵니다.  
  
|바인딩의 다음 값을 찾으려면|다음 API 사용|  
|---------------------------------------|------------------|  
|대상 개체|<xref:System.Windows.Data.BindingExpressionBase.Target%2A?displayProperty=nameWithType>|  
|대상 속성|<xref:System.Windows.Data.BindingExpressionBase.TargetProperty%2A?displayProperty=nameWithType>|  
|소스 개체|<xref:System.Windows.Data.BindingExpression.ResolvedSource%2A?displayProperty=nameWithType>|  
|원본 속성|<xref:System.Windows.Data.BindingExpression.ResolvedSourcePropertyName%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Data.BindingExpression> <xref:System.Windows.Data.BindingGroup>에 속하는지 여부|<xref:System.Windows.Data.BindingExpressionBase.BindingGroup%2A?displayProperty=nameWithType>|  
|<xref:System.Windows.Data.BindingGroup>의 소유자입니다.|<xref:System.Windows.Data.BindingGroup.Owner%2A>|  
  
<a name="DisconnectedSource"></a>   
## <a name="checking-for-a-valid-datacontext-object"></a>유효한 DataContext 개체 확인  
 <xref:System.Windows.Controls.ItemsControl>의 항목 컨테이너 <xref:System.Windows.FrameworkElement.DataContext%2A>의 연결을 해제 하는 경우가 있습니다.  항목 컨테이너에 있는 항목을 표시 하는 UI 요소는는 <xref:System.Windows.Controls.ItemsControl>합니다.  경우는 <xref:System.Windows.Controls.ItemsControl> 데이터가 컬렉션에 바인딩된 각 항목에 대해 항목 컨테이너가 생성 됩니다. 경우에 따라 항목 컨테이너는 시각적 트리에서 제거됩니다. 항목 컨테이너는 제거 되는 두 가지 일반적인 경우는 기본 컬렉션에서 항목이 제거 될 때 및에 가상화가 사용 하는 경우는 <xref:System.Windows.Controls.ItemsControl>합니다. 이러한 경우 항목 컨테이너의 <xref:System.Windows.FrameworkElement.DataContext%2A> 속성은 <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A?displayProperty=nameWithType> 정적 속성에서 반환 되는 센티널 개체로 설정 됩니다.  항목 컨테이너의 <xref:System.Windows.FrameworkElement.DataContext%2A>에 액세스 하기 전에 <xref:System.Windows.FrameworkElement.DataContext%2A> <xref:System.Windows.Data.BindingOperations.DisconnectedSource%2A> 개체와 같은지 여부를 확인 해야 합니다.  
  
<a name="live_shaping"></a>   
## <a name="repositioning-data-as-the-datas-values-change-live-shaping"></a>데이터 값이 변경될 때 데이터의 위치 변경(라이브 셰이핑)  
 데이터의 컬렉션을 그룹화, 정렬 또는 필터링할 수 있습니다. WPF 4.5에서는 데이터가 수정되면 데이터를 다시 배열할 수 있습니다. 예를 들어, 애플리케이션에서 사용 하는 <xref:System.Windows.Controls.DataGrid> 따라 주식 시장에 주식, 주식을 나열 하려면 정렬 합니다. 주식에서 실시간 정렬을 사용 하도록 설정 하는 경우 <xref:System.Windows.Data.CollectionView>에서 주식의 위치는 <xref:System.Windows.Controls.DataGrid> 재고 값이 큰 이동 또는 보다 작은 다른 주식의 값입니다.   자세한 내용은 참조는 <xref:System.ComponentModel.ICollectionViewLiveShaping> 인터페이스입니다.  
  
<a name="weak_event_pattern"></a>   
## <a name="improved-support-for-establishing-a-weak-reference-to-an-event"></a>이벤트에 대한 약한 참조 설정을 위한 지원 개선  
 이벤트 구독자가 추가 인터페이스 구현 없이 참여할 수 있으므로 약한 이벤트 패턴을 구현하기가 더 쉬워졌습니다.  제네릭 <xref:System.Windows.WeakEventManager> 클래스를 사용 하면 특정 이벤트에 대 한 전용 <xref:System.Windows.WeakEventManager> 없는 경우에도 구독자가 weak 이벤트 패턴에 참여할 수 있습니다.  자세한 내용은 [약한 이벤트 패턴](../advanced/weak-event-patterns.md)을 참조하세요.  
  
<a name="async"></a>   
## <a name="new-methods-for-the-dispatcher-class"></a>Dispatcher 클래스에 대한 새로운 메서드  
 Dispatcher 클래스는 동기 및 비동기 작업에 대해 새로운 메서드를 정의합니다.  동기 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 메서드는 <xref:System.Action> 또는 <xref:System.Func%601> 매개 변수를 사용 하는 오버 로드를 정의 합니다. 새 비동기 메서드인 <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>은 콜백 매개 변수로 <xref:System.Action> 또는 <xref:System.Func%601>를 사용 하 고 <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>를 반환 합니다.   <xref:System.Windows.Threading.DispatcherOperation> 및 <xref:System.Windows.Threading.DispatcherOperation%601> 클래스는 <xref:System.Threading.Tasks.Task> 속성을 정의 합니다.  <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A>를 호출 하는 경우 `await` 키워드를 <xref:System.Windows.Threading.DispatcherOperation> 또는 연결 된 <xref:System.Threading.Tasks.Task>사용할 수 있습니다. <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>에서 반환 된 <xref:System.Threading.Tasks.Task>를 동기적으로 대기 해야 하는 경우 <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> 확장 메서드를 호출 합니다. 작업이 호출 스레드에서 대기 중인 경우 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>를 호출 하면 교착 상태가 발생 합니다. <xref:System.Threading.Tasks.Task>를 사용 하 여 비동기 작업을 수행 하는 방법에 대 한 자세한 내용은 [작업 병렬 처리 (작업 병렬 라이브러리)](../../../standard/parallel-programming/task-based-asynchronous-programming.md)를 참조 하세요.  
  
<a name="events_markup_extenions"></a>   
## <a name="markup-extensions-for-events"></a>이벤트에 대한 태그 확장  
 WPF 4.5에서는 이벤트에 대한 태그 확장을 지원합니다.  WPF는 이벤트에 사용될 태그 확장을 정의하지 않지만 타사에서 이벤트에 사용할 수 있는 태그 확장을 만들 수 있습니다.  
  
## <a name="see-also"></a>참조

- [.NET Framework의 새로운 기능](../../whats-new/index.md)
