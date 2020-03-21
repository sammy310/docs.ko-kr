---
title: '성능 최적화: 데이터 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 3128f453378f9d74f867b571e30f2be4e8add8a4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186754"
---
# <a name="optimizing-performance-data-binding"></a>성능 최적화: 데이터 바인딩
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩은 애플리케이션이 데이터를 제공하고 상호 작용할 수 있는 간단하고 일관된 방법을 제공합니다. 요소는 CLR 개체 및 XML 의 형태로 다양한 데이터 원본의 데이터에 바인딩할 수 있습니다.  
  
 이 항목에서는 데이터 바인딩과 관련된 성능 권장 사항을 제공합니다.  

<a name="HowDataBindingReferencesAreResolved"></a>
## <a name="how-data-binding-references-are-resolved"></a>데이터 바인딩 참조를 확인하는 방법  
 데이터 바인딩 성능 문제를 다루기 전에 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩 엔진에서 바인딩의 개체 참조를 확인하는 방법을 살펴보는 것이 좋습니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩의 소스는 모든 CLR 개체일 수 있습니다. CLR 개체의 속성, 하위 속성 또는 인덱서에 바인딩할 수 있습니다. 바인딩 참조는 Microsoft .NET Framework 리플렉션 <xref:System.ComponentModel.ICustomTypeDescriptor>또는 을 사용하여 해결됩니다. 다음은 바인딩의 개체 참조를 확인하는 세 가지 방법입니다.  
  
 첫 번째 방법에서는 리플렉션을 사용합니다. 이 경우 <xref:System.Reflection.PropertyInfo> 개체는 속성의 특성을 검색하는 데 사용되며 속성 메타데이터에 대한 액세스를 제공합니다. 인터페이스를 <xref:System.ComponentModel.ICustomTypeDescriptor> 사용하는 경우 데이터 바인딩 엔진은 이 인터페이스를 사용하여 속성 값에 액세스합니다. 인터페이스는 <xref:System.ComponentModel.ICustomTypeDescriptor> 개체에 정적 속성 집합이 없는 경우에 특히 유용합니다.  
  
 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하거나 <xref:System.ComponentModel.TypeDescriptor>와 연결된 변경 알림을 사용하여 속성 변경 알림을 제공할 수 있습니다. 그러나 속성 변경 알림을 구현 하기 위한 <xref:System.ComponentModel.INotifyPropertyChanged>기본 전략은 을 사용하는 것입니다.  
  
 원본 개체가 CLR 개체이고 원본 속성이 CLR 속성인 경우 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩 엔진은 먼저 소스 <xref:System.ComponentModel.TypeDescriptor>개체에 대한 리플렉션을 사용하여 <xref:System.ComponentModel.PropertyDescriptor>를 얻은 다음 을 쿼리해야 합니다. 이러한 일련의 리플렉션 작업은 너무 많은 시간을 소비할 수 있으므로 성능 면에서 좋지 않습니다.  
  
 개체 참조를 해결하는 두 번째 방법은 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현하는 CLR 원본 개체와 CLR 속성인 소스 속성을 포함합니다. 이 경우 데이터 바인딩 엔진에서는 소스 형식에 대해 직접 리플렉션을 사용하여 필요한 속성을 가져옵니다. 이 또한 최적의 방법은 아니지만 첫 번째 방법보다 작업 집합 요구 사항이 적어 비용이 적게 듭니다.  
  
 개체 참조를 해결하는 세 번째 방법은 a및 <xref:System.Windows.DependencyObject> 의 소스 속성인 소스 개체를 <xref:System.Windows.DependencyProperty>포함합니다. 이 경우 데이터 바인딩 엔진에서 리플렉션을 사용할 필요가 없습니다. 대신 속성 엔진과 데이터 바인딩 엔진이 함께 속성 참조를 독립적으로 확인합니다. 이것이 데이터 바인딩에서 사용되는 개체 참조를 확인하는 최적의 방법입니다.  
  
 아래 표는 이 세 가지 <xref:System.Windows.Controls.TextBlock.Text%2A> 방법을 사용하여 <xref:System.Windows.Controls.TextBlock> 1,000개 요소의 속성을 바인딩하는 데이터 속도를 비교합니다.  
  
|**TextBlock의 Text 속성 바인딩 대상**|**바인딩 시간(ms)**|**렌더링 시간 -- 바인딩 시간 포함(ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|CLR 개체의 속성에|115|314|  
|구현하는 CLR 개체의 속성에<xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|의 <xref:System.Windows.DependencyProperty> <xref:System.Windows.DependencyObject>에.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>
## <a name="binding-to-large-clr-objects"></a>대형 CLR 개체에 바인딩  
 데이터가 수천 개의 속성이 있는 단일 CLR 개체에 바인딩할 때 성능에 큰 영향을 미칩니다. 단일 개체를 속성이 적은 여러 CLR 개체로 나누어 이러한 영향을 최소화할 수 있습니다. 이 표에서는 단일 큰 CLR 개체에 대한 데이터 바인딩 및 렌더링 시간을 여러 개의 작은 개체와 비교합니다.  
  
|**1000개의 TextBlock 개체 데이터 바인딩 대상**|**바인딩 시간(ms)**|**렌더링 시간 -- 바인딩 시간 포함(ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|속성이 1000인 CLR 개체에|950|1200|  
|하나의 속성이 있는 1000개의 CLR 개체에|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>
## <a name="binding-to-an-itemssource"></a>ItemsSource에 바인딩  
 에 표시할 직원 목록을 포함하는 <xref:System.Collections.Generic.List%601> CLR 개체가 있는 시나리오를 생각해 보십시오. <xref:System.Windows.Controls.ListBox> 이 두 개체 간의 통신을 만들려면 직원 목록을 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox>의 속성에 바인딩합니다. 그런데 그룹에 새 직원이 가입했다고 가정합니다. 이 새 사람을 바인딩된 <xref:System.Windows.Controls.ListBox> 값에 삽입하기 위해 이 사람을 직원 목록에 추가하고 데이터 바인딩 엔진에서 이 변경 이 변경 사항을 자동으로 인식할 수 있다고 생각할 수 있습니다. 그 가정은 거짓으로 증명될 것입니다. 실제로 변경 사항은 <xref:System.Windows.Controls.ListBox> 자동으로 반영되지 않습니다. 이는 CLR <xref:System.Collections.Generic.List%601> 개체가 컬렉션 변경 이벤트를 자동으로 발생시키지 않기 때문입니다. 변경 <xref:System.Windows.Controls.ListBox> 내용을 선택하려면 직원 목록을 다시 만들고 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox>의 속성에 다시 연결해야 합니다. 이 솔루션은 효과는 있지만 성능에 큰 영향을 줍니다. 을 새 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> <xref:System.Windows.Controls.ListBox> 개체에 다시 할당할 때마다 <xref:System.Windows.Controls.ListBox> 첫 번째 개체는 이전 항목을 버리고 전체 목록을 다시 생성합니다. <xref:System.Windows.Controls.ListBox> 맵이 복잡한 <xref:System.Windows.DataTemplate>경우 성능 에 미치는 영향이 확대됩니다.  
  
 이 문제에 대한 매우 효율적인 해결책은 직원 <xref:System.Collections.ObjectModel.ObservableCollection%601>목록을 . 개체는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 데이터 바인딩 엔진이 받을 수 있는 변경 알림을 발생 시요. 이 이벤트는 전체 목록을 다시 <xref:System.Windows.Controls.ItemsControl> 생성할 필요 없이 항목을 추가하거나 제거합니다.  
  
 아래 표는 한 항목이 추가될 때 UI 가상화가 꺼져 있는 <xref:System.Windows.Controls.ListBox> 업데이트를 수행하는 데 걸리는 시간을 보여 주었습니다. 첫 번째 행의 숫자는 CLR <xref:System.Collections.Generic.List%601> 개체가 요소의 <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>에 바인딩된 경과 시간을 나타냅니다. 두 번째 행의 숫자는 <xref:System.Collections.ObjectModel.ObservableCollection%601> <xref:System.Windows.Controls.ListBox> 요소가 요소의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>에 바인딩된 경과 시간을 나타냅니다. 데이터 바인딩 전략을 사용하여 <xref:System.Collections.ObjectModel.ObservableCollection%601> 상당한 시간을 절약할 수 있습니다.  
  
|**ItemsSource 데이터 바인딩 대상**|**1개 항목의 업데이트 시간(ms)**|  
|--------------------------------------|---------------------------------------|  
|CLR <xref:System.Collections.Generic.List%601> 개체에|1656|  
|<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>IList를 IEnumerable이 아닌 ItemsControl에 바인딩  
 개체에 <xref:System.Collections.Generic.IList%601> 바인딩하거나 <xref:System.Collections.IEnumerable> 개체에 바인딩할 <xref:System.Windows.Controls.ItemsControl> 수 있는 <xref:System.Collections.Generic.IList%601> 경우 개체를 선택합니다. 래퍼 <xref:System.Collections.Generic.IList%601> 오브젝트를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 만들기 위해 힘에 바인딩하면 <xref:System.Collections.IEnumerable> 두 번째 개체의 불필요한 오버헤드로 인해 성능이 저하됩니다. <xref:System.Windows.Controls.ItemsControl>  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>데이터 바인딩만을 위해 CLR 개체를 XML로 변환 안 함  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]XML 콘텐츠에 데이터를 바인딩할 수 있습니다. 그러나 XML 콘텐츠에 대한 데이터 바인딩은 CLR 개체에 대한 데이터 바인딩보다 느립니다. 데이터 바인딩을 위한 유일한 목적인 경우 CLR 개체 데이터를 XML로 변환하지 마십시오.  
  
## <a name="see-also"></a>참고 항목

- [WPF 애플리케이션 성능 최적화](optimizing-wpf-application-performance.md)
- [애플리케이션 성능 계획](planning-for-application-performance.md)
- [하드웨어 활용](optimizing-performance-taking-advantage-of-hardware.md)
- [레이아웃 및 디자인](optimizing-performance-layout-and-design.md)
- [2D 그래픽 및 이미징](optimizing-performance-2d-graphics-and-imaging.md)
- [개체 동작](optimizing-performance-object-behavior.md)
- [응용 프로그램 리소스](optimizing-performance-application-resources.md)
- [텍스트](optimizing-performance-text.md)
- [기타 성능 추천 사항](optimizing-performance-other-recommendations.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [연습: WPF 애플리케이션에서 애플리케이션 데이터 캐싱](walkthrough-caching-application-data-in-a-wpf-application.md)
