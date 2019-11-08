---
title: '성능 최적화: 데이터 바인딩'
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], performance
- data binding [WPF], performance
ms.assetid: 1506a35d-c009-43db-9f1e-4e230ad5be73
ms.openlocfilehash: 9b302be3ed9f01ccd27470063f49966dc7d74708
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740803"
---
# <a name="optimizing-performance-data-binding"></a>성능 최적화: 데이터 바인딩
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩은 애플리케이션이 데이터를 제공하고 상호 작용할 수 있는 간단하고 일관된 방법을 제공합니다. 요소는 CLR 개체 및 XML 형식으로 다양 한 데이터 원본에서 데이터에 바인딩할 수 있습니다.  
  
 이 항목에서는 데이터 바인딩과 관련된 성능 권장 사항을 제공합니다.  

<a name="HowDataBindingReferencesAreResolved"></a>   
## <a name="how-data-binding-references-are-resolved"></a>데이터 바인딩 참조를 확인하는 방법  
 데이터 바인딩 성능 문제를 다루기 전에 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩 엔진에서 바인딩의 개체 참조를 확인하는 방법을 살펴보는 것이 좋습니다.  
  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩의 소스는 임의의 CLR 개체 일 수 있습니다. CLR 개체의 속성, 하위 속성 또는 인덱서에 바인딩할 수 있습니다. Microsoft .NET Framework 리플렉션 또는 <xref:System.ComponentModel.ICustomTypeDescriptor>를 사용 하 여 바인딩 참조를 확인 합니다. 다음은 바인딩의 개체 참조를 확인하는 세 가지 방법입니다.  
  
 첫 번째 방법에서는 리플렉션을 사용합니다. 이 경우 <xref:System.Reflection.PropertyInfo> 개체를 사용 하 여 속성의 특성을 검색 하 고 속성 메타 데이터에 대 한 액세스를 제공 합니다. <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스를 사용 하는 경우 데이터 바인딩 엔진은이 인터페이스를 사용 하 여 속성 값에 액세스 합니다. <xref:System.ComponentModel.ICustomTypeDescriptor> 인터페이스는 개체에 정적 속성 집합이 없는 경우에 특히 유용 합니다.  
  
 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현 하거나 <xref:System.ComponentModel.TypeDescriptor>와 연결 된 변경 알림을 사용 하 여 속성 변경 알림을 제공할 수 있습니다. 그러나 속성 변경 알림을 구현 하는 기본 전략은 <xref:System.ComponentModel.INotifyPropertyChanged>를 사용 하는 것입니다.  
  
 원본 개체가 CLR 개체이 고 소스 속성이 CLR 속성인 경우 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 데이터 바인딩 엔진은 먼저 원본 개체에서 리플렉션을 사용 하 여 <xref:System.ComponentModel.TypeDescriptor>를 가져온 다음 <xref:System.ComponentModel.PropertyDescriptor>를 쿼리해야 합니다. 이러한 일련의 리플렉션 작업은 너무 많은 시간을 소비할 수 있으므로 성능 면에서 좋지 않습니다.  
  
 개체 참조를 확인 하는 두 번째 방법에는 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스를 구현 하는 CLR 소스 개체와 CLR 속성인 소스 속성이 포함 됩니다. 이 경우 데이터 바인딩 엔진에서는 소스 형식에 대해 직접 리플렉션을 사용하여 필요한 속성을 가져옵니다. 이 또한 최적의 방법은 아니지만 첫 번째 방법보다 작업 집합 요구 사항이 적어 비용이 적게 듭니다.  
  
 개체 참조를 확인 하는 세 번째 방법에는 <xref:System.Windows.DependencyObject> 원본 개체와 <xref:System.Windows.DependencyProperty>원본 속성이 포함 됩니다. 이 경우 데이터 바인딩 엔진에서 리플렉션을 사용할 필요가 없습니다. 대신 속성 엔진과 데이터 바인딩 엔진이 함께 속성 참조를 독립적으로 확인합니다. 이것이 데이터 바인딩에서 사용되는 개체 참조를 확인하는 최적의 방법입니다.  
  
 아래 표에서는 이러한 세 가지 방법을 사용 하 여 1000 <xref:System.Windows.Controls.TextBlock> 요소의 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성을 바인딩하는 속도를 비교 합니다.  
  
|**TextBlock의 Text 속성 바인딩 대상**|**바인딩 시간(ms)**|**렌더링 시간 -- 바인딩 시간 포함(ms)**|  
|--------------------------------------------------|-----------------------------|--------------------------------------------------|  
|CLR 개체의 속성으로|115|314|  
|을 구현 하는 CLR 개체의 속성에 대 한 <xref:System.ComponentModel.INotifyPropertyChanged>|115|305|  
|<xref:System.Windows.DependencyObject><xref:System.Windows.DependencyProperty>입니다.|90|263|  
  
<a name="Binding_to_Large_CLR_Objects"></a>   
## <a name="binding-to-large-clr-objects"></a>대형 CLR 개체에 바인딩  
 수천 개의 속성이 있는 단일 CLR 개체에 데이터를 바인딩할 때 성능에 상당한 영향을 줍니다. 단일 개체를 속성이 작은 여러 CLR 개체로 나누면 이러한 영향을 최소화할 수 있습니다. 이 표에서는 단일의 작은 CLR 개체와 여러 개의 작은 개체에 대 한 데이터 바인딩의 바인딩 및 렌더링 시간을 보여 줍니다.  
  
|**1000개의 TextBlock 개체 데이터 바인딩 대상**|**바인딩 시간(ms)**|**렌더링 시간 -- 바인딩 시간 포함(ms)**|  
|---------------------------------------------|-----------------------------|--------------------------------------------------|  
|1000 속성이 있는 CLR 개체로|950|1200|  
|하나의 속성을 사용 하는 1000 CLR 개체|115|314|  
  
<a name="Binding_to_an_ItemsSource"></a>   
## <a name="binding-to-an-itemssource"></a>ItemsSource에 바인딩  
 <xref:System.Windows.Controls.ListBox>에 표시 하려는 직원 목록이 포함 된 CLR <xref:System.Collections.Generic.List%601> 개체가 있는 시나리오를 고려해 보세요. 이러한 두 개체 간의 대응을 만들려면 직원 목록을 <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성에 바인딩합니다. 그런데 그룹에 새 직원이 가입했다고 가정합니다. 이 새 사용자를 바인딩된 <xref:System.Windows.Controls.ListBox> 값에 삽입 하기 위해이 사용자를 직원 목록에 추가 하 고이 변경 내용을 데이터 바인딩 엔진에서 자동으로 인식 하 게 될 것으로 간주할 수 있습니다. 이 가정에서는 false를 증명 합니다. 실제로 변경 내용은 <xref:System.Windows.Controls.ListBox>에 자동으로 반영 되지 않습니다. 이는 CLR <xref:System.Collections.Generic.List%601> 개체가 컬렉션 변경 이벤트를 자동으로 발생 시 키 지 않기 때문입니다. 변경 내용을 선택 하는 <xref:System.Windows.Controls.ListBox>을 얻으려면 직원 목록을 다시 만들고이를 <xref:System.Windows.Controls.ListBox>의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성에 다시 연결 해야 합니다. 이 솔루션은 효과는 있지만 성능에 큰 영향을 줍니다. <xref:System.Windows.Controls.ListBox> <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>를 새 개체에 재할당할 때마다 <xref:System.Windows.Controls.ListBox>는 먼저 이전 항목을 throw 하 고 전체 목록을 다시 생성 합니다. <xref:System.Windows.Controls.ListBox> 복잡 한 <xref:System.Windows.DataTemplate>에 매핑되는 경우 성능 영향이 확대 됩니다.  
  
 이 문제에 대 한 매우 효율적인 해결책은 직원 목록을 <xref:System.Collections.ObjectModel.ObservableCollection%601>하는 것입니다. <xref:System.Collections.ObjectModel.ObservableCollection%601> 개체는 데이터 바인딩 엔진이 받을 수 있는 변경 알림을 발생 시킵니다. 이벤트는 전체 목록을 다시 생성할 필요 없이 <xref:System.Windows.Controls.ItemsControl>에서 항목을 추가 하거나 제거 합니다.  
  
 다음 표에서는 한 항목을 추가할 때 UI 가상화가 해제 된 상태에서 <xref:System.Windows.Controls.ListBox>를 업데이트 하는 데 걸리는 시간을 보여 줍니다. 첫 번째 행의 숫자는 CLR <xref:System.Collections.Generic.List%601> 개체가 <xref:System.Windows.Controls.ListBox> 요소의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>바인딩될 때 경과 된 시간을 나타냅니다. 두 번째 행의 숫자는 <xref:System.Collections.ObjectModel.ObservableCollection%601> <xref:System.Windows.Controls.ListBox> 요소의 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>바인딩될 때 경과 된 시간을 나타냅니다. <xref:System.Collections.ObjectModel.ObservableCollection%601> 데이터 바인딩 전략을 사용 하 여 상당한 시간 절약 효과를 확인 합니다.  
  
|**ItemsSource 데이터 바인딩 대상**|**1개 항목의 업데이트 시간(ms)**|  
|--------------------------------------|---------------------------------------|  
|CLR <xref:System.Collections.Generic.List%601> 개체로|1656|  
|<xref:System.Collections.ObjectModel.ObservableCollection%601>|20|  
  
<a name="Binding_IList_to_ItemsControl_not_IEnumerable"></a>   
## <a name="bind-ilist-to-itemscontrol-not-ienumerable"></a>IList를 IEnumerable이 아닌 ItemsControl에 바인딩  
 <xref:System.Collections.Generic.IList%601> 또는 <xref:System.Collections.IEnumerable>를 <xref:System.Windows.Controls.ItemsControl> 개체에 바인딩하는 중 하나를 선택 하는 경우에는 <xref:System.Collections.Generic.IList%601> 개체를 선택 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.ItemsControl>에 대 한 <xref:System.Collections.IEnumerable>를 바인딩하면 래퍼 <xref:System.Collections.Generic.IList%601> 개체가 만들어집니다. 즉, 성능이 두 번째 개체의 불필요 한 오버 헤드로 인해 영향을 받습니다.  
  
<a name="Do_not_Convert_CLR_objects_to_Xml_Just_For_Data_Binding"></a>   
## <a name="do-not-convert-clr-objects-to-xml-just-for-data-binding"></a>데이터 바인딩만을 위해 CLR 개체를 XML로 변환 안 함  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 사용 하 여 XML 콘텐츠에 데이터 바인딩할 수 있습니다. 그러나 XML 콘텐츠에 대 한 데이터 바인딩은 CLR 개체에 대 한 데이터 바인딩 보다 속도가 느립니다. 데이터 바인딩을 위한 유일한 용도 이면 CLR 개체 데이터를 XML로 변환 하지 마십시오.  
  
## <a name="see-also"></a>참조

- [WPF 애플리케이션 성능 최적화](optimizing-wpf-application-performance.md)
- [애플리케이션 성능 계획](planning-for-application-performance.md)
- [하드웨어 이용](optimizing-performance-taking-advantage-of-hardware.md)
- [레이아웃 및 디자인](optimizing-performance-layout-and-design.md)
- [2차원 그래픽 및 이미징](optimizing-performance-2d-graphics-and-imaging.md)
- [개체 동작](optimizing-performance-object-behavior.md)
- [애플리케이션 리소스](optimizing-performance-application-resources.md)
- [텍스트](optimizing-performance-text.md)
- [기타 성능 권장 사항](optimizing-performance-other-recommendations.md)
- [데이터 바인딩 개요](../../../desktop-wpf/data/data-binding-overview.md)
- [연습: WPF 애플리케이션에서 애플리케이션 데이터 캐싱](walkthrough-caching-application-data-in-a-wpf-application.md)
