---
title: 프레임워크 속성 메타데이터
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WPF], framework properties
- framework property metadata [WPF]
ms.assetid: 9962f380-b885-4b61-a62e-457397083fea
ms.openlocfilehash: 81c1941ffd95afb01dcb6ebda2634832a91cd876
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859855"
---
# <a name="framework-property-metadata"></a>프레임워크 속성 메타데이터
프레임워크 속성 메타데이터는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 아키텍처의 WPF 프레임워크 수준에 있는 것으로 간주되는 개체 요소의 속성용으로 보고됩니다. 일반적 WPF 프레임 워크 수준 지정에서는 렌더링, 데이터 바인딩와 같은 해당 기능 및 속성 시스템 미세 조정과에서 처리 되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프레젠테이션 Api 및 실행 합니다. 이러한 시스템에서 프레임워크 속성 메타데이터를 쿼리하여 특정 요소 속성의 기능별 특성을 결정합니다.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>필수 구성 요소  
 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 클래스에서 기존 종속성 속성의 소비자 관점에서 종속성 속성을 이해하고 [종속성 속성 개요](dependency-properties-overview.md)를 읽었다고 가정합니다. [종속성 속성 메타데이터](dependency-property-metadata.md)도 읽어야 합니다.  
  
<a name="What_Is_Communicated_by_Framework_Property"></a>   
## <a name="what-is-communicated-by-framework-property-metadata"></a>프레임워크 속성 메타데이터로 통신하는 내용  
 프레임워크 속성 메타데이터는 다음 범주로 구분할 수 있습니다.  
  
- 요소에 영향을 미치는 레이아웃 속성 보고 (<xref:System.Windows.FrameworkPropertyMetadata.AffectsArrange%2A>하십시오 <xref:System.Windows.FrameworkPropertyMetadata.AffectsMeasure%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsRender%2A>). 속성에 해당 측면에 영향을 구현 하는 경우 메타 데이터에서 이러한 플래그를 설정할 수는 <xref:System.Windows.FrameworkElement.MeasureOverride%2A>  /  <xref:System.Windows.FrameworkElement.ArrangeOverride%2A> 특정 렌더링 동작 및 레이아웃 정보를 제공 하기 위해 클래스에서 메서드 시스템입니다. 일반적으로 이러한 구현에서는 해당 레이아웃 속성이 속성 메타데이터에서 참인 종속성 속성의 속성 무효화를 확인하고 해당 무효화만 새로운 레이아웃 전달을 요청해야 합니다.  
  
- 요소의 부모 요소에 영향을 미치는 레이아웃 속성 보고 (<xref:System.Windows.FrameworkPropertyMetadata.AffectsParentArrange%2A>, <xref:System.Windows.FrameworkPropertyMetadata.AffectsParentMeasure%2A>). 기본적으로 이러한 플래그가 설정 되어 있는 몇 가지 예는 <xref:System.Windows.Documents.FixedPage.Left%2A?displayProperty=nameWithType> 고 <xref:System.Windows.Documents.Paragraph.KeepWithNext%2A?displayProperty=nameWithType>입니다.  
  
- <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A>. 기본적으로 종속성 속성은 값을 상속하지 않습니다. <xref:System.Windows.FrameworkPropertyMetadata.OverridesInheritanceBehavior%2A> 또한 컨트롤 합성 시나리오에 필요한 시각적 트리로 이동 하는 상속 경로 허용 합니다.  
  
    > [!NOTE]
    >  속성 값 컨텍스트에서 “상속”이라는 용어는 종속성 속성에 특정한 것입니다. 즉, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 속성 시스템의 WPF 프레임워크 수준 기능때문에 자식 요소가 부모 요소에서 실제 종속성 속성 값을 상속할 수 있습니다. 파생된 유형을 통한 멤버 상속 및 관리된 코드 유형과는 직접적인 관련이 없습니다. 자세한 내용은 [속성 값 상속](property-value-inheritance.md)을 참조하십시오.  
  
- 보고 데이터 바인딩 특성 (<xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A>, <xref:System.Windows.FrameworkPropertyMetadata.BindsTwoWayByDefault%2A>). 기본적으로 프레임워크의 종속성 속성은 단방향 바인딩 동작을 통한 데이터 바인딩을 지원합니다. 전혀 시나리오가 있다면 데이터 바인딩을 사용 하지 않도록 설정 될 수 있습니다 (기본에서 이러한 속성의 많은 예가 없는 이므로 이러한는 유연 하며 확장 가능 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Api). 바인딩의 구성 요소 간에 컨트롤의 동작을 함께 연결 하는 속성에 대 한 양방향 기본값을 설정할 수 있습니다 (<xref:System.Windows.Controls.MenuItem.IsSubmenuOpen%2A> 예로) 나 사용자에 대 한 일반적인 예상된 시나리오인 경우 양방향 바인딩 (<xref:System.Windows.Controls.TextBox.Text%2A> 예로). 데이터 바인딩 관련 메타데이터를 변경하면 기본값에만 영향을 미칩니다. 바인딩별 변경에서는 해당 기본값을 항상 변경할 수 있습니다. 바인딩 모드와 일반적인 바인딩에 대한 자세한 내용은 [데이터 바인딩 개요](../data/data-binding-overview.md)를 참조하세요.  
  
- 속성을 저널링을 지 원하는 서비스 또는 응용 프로그램에서 저널링 해야 할지 여부를 보고 (<xref:System.Windows.FrameworkPropertyMetadata.Journal%2A>). 일반 요소에는 기본적으로 저널링을 사용하지 않지만, 특정 사용자 입력 컨트롤에 대해서는 선택적으로 사용합니다. 이 속성은 저널링의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현을 포함하여 저널링 서비스를 통해 읽어야 하며, 일반적으로 탐색 단계 간에 지속되어야 하는 목록의 사용자 선택 항목과 같은 사용자 컨트롤에 설정됩니다. 저널에 대한 자세한 내용은 [탐색 개요](../app-development/navigation-overview.md)를 참조하세요.  
  
<a name="Reading_FrameworkPropertyMetadata"></a>   
## <a name="reading-frameworkpropertymetadata"></a>FrameworkPropertyMetadata 읽기  
 각 위에 링크 된 속성은 특정 속성은 합니다 <xref:System.Windows.FrameworkPropertyMetadata> 즉시 기본 클래스에 추가 <xref:System.Windows.UIPropertyMetadata>합니다. 이러한 각 속성은 기본적으로 `false`입니다. 이러한 속성의 값을 아는 것이 중요 한 속성에 대 한 메타 데이터 요청에 반환된 된 메타 데이터를 캐스팅 하려고 시도해 야 <xref:System.Windows.FrameworkPropertyMetadata>, 한 다음 필요에 따라 개별 속성에 값을 확인 합니다.  
  
<a name="Specifying_Metadata"></a>   
## <a name="specifying-metadata"></a>메타데이터 지정  
 메타 데이터 클래스를 사용 하 여 선택할 수 있습니다 새 종속성 속성 등록에 메타 데이터를 적용 하는 목적에 대 한 새 메타 데이터 인스턴스를 만든 경우: 기본 <xref:System.Windows.PropertyMetadata> 와 같은 일부 파생 클래스 또는 <xref:System.Windows.FrameworkPropertyMetadata>합니다. 일반적으로 사용 해야 <xref:System.Windows.FrameworkPropertyMetadata>재산 속성 시스템과 상호 작용 하는 경우에 특히 및 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 및 데이터 바인딩과 같은 함수입니다. 파생 시키는 더 복잡 한 시나리오에 대 한 또 다른 옵션은 <xref:System.Windows.FrameworkPropertyMetadata> 고유 메타 데이터를 만들려면 해당 멤버에 전달 추가 정보를 사용 하 여 클래스를 보고 합니다. 사용할 수 있습니다 <xref:System.Windows.PropertyMetadata> 또는 <xref:System.Windows.UIPropertyMetadata> 구현의 기능에 대 한 지원 정도 통신할 수 있습니다.  
  
 기존 속성 (<xref:System.Windows.DependencyProperty.AddOwner%2A> 또는 <xref:System.Windows.DependencyProperty.OverrideMetadata%2A> 호출), 원래 등록에서 사용 하는 메타 데이터 형식을 사용 하 여 항상 재정의 해야 합니다.  
  
 만들려는 경우를 <xref:System.Windows.FrameworkPropertyMetadata> 인스턴스, 프레임 워크 속성 특성에 전달 하는 특정 속성에 대 한 값을 사용 하 여 해당 메타 데이터를 채우는 데는 두 가지 방법이 있습니다.  
  
1. 사용 된 <xref:System.Windows.FrameworkPropertyMetadata> 허용 하는 생성자 시그니처를 `flags` 매개 변수입니다. 값이 필요한 모든 조합된으로이 매개 변수를 채워야 합니다 <xref:System.Windows.FrameworkPropertyMetadataOptions> 열거형 플래그입니다.  
  
2. 없이 시그니처 중 하나를 사용 하 여는 `flags` 매개 변수를 각 보고 부울 속성을 설정한 후 <xref:System.Windows.FrameworkPropertyMetadata> 에 `true` 원하는 각 특성 변경에 대 한 합니다. 이 작업을 수행하는 경우 이 종속성 속성이 있는 요소를 생성하기 전에 이러한 속성을 설정해야 합니다. `flags` 매개 변수를 방지하는 동작을 허용하기 위해 부울 속성은 읽기-쓰기가 되며 여전히 메타데이터를 채우지만, 속성을 사용하기 전에 메타데이터를 적절하게 봉인해야 합니다. 따라서 메타데이터를 요청한 후에 속성을 설정하려는 것은 올바른 작업이 아닙니다.  
  
<a name="Framework_Property_Metadata_Merge_Behavior"></a>   
## <a name="framework-property-metadata-merge-behavior"></a>프레임워크 속성 메타데이터 병합 동작  
 프레임워크 속성 메타데이터를 재정의할 때, 여러 다른 메타데이터 특성을 병합하거나 대체합니다.  
  
- <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 병합 됩니다. 새로 추가 하는 경우 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A>, 해당 콜백은 메타 데이터에 저장 됩니다. 지정 하지 않으면 경우는 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 재정의 값에 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 메타 데이터에 지정 된 가장 가까운 상위 항목에서 참조로 승격 됩니다.  
  
- 에 대 한 실제 속성 시스템 동작은 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 는 구현 계층의 모든 메타 데이터 소유자는 유지 하 고 테이블에 추가 하는 가장 많이 파생된 된 클래스의 콜백 되는 속성 시스템에서 실행 순서를 사용 하 여 먼저 호출 됩니다. 상속된 콜백은 한 번만 실행되며, 메타데이터에 해당 콜백을 둔 클래스가 소유하는 것으로 계산됩니다.  
  
- <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 대체 됩니다. 지정 하지 않으면 경우는 <xref:System.Windows.PropertyMetadata.PropertyChangedCallback%2A> 재정의 값에 <xref:System.Windows.PropertyMetadata.DefaultValue%2A> 메타 데이터에 지정 된 가장 가까운 상위 항목에서 제공 됩니다.  
  
- <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 구현이 대체 됩니다. 새로 추가 하는 경우 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A>, 해당 콜백은 메타 데이터에 저장 됩니다. 지정 하지 않으면 경우는 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 재정의 값에 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 메타 데이터에 지정 된 가장 가까운 상위 항목에서 참조로 승격 됩니다.  
  
- 속성 시스템 동작은는 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 직접 메타 데이터에서 호출 됩니다. 다른 참조가 없는 <xref:System.Windows.PropertyMetadata.CoerceValueCallback%2A> 구현 계층 구조에서 유지 됩니다.  
  
- 플래그 <xref:System.Windows.FrameworkPropertyMetadataOptions> 열거형을 비트 OR 연산으로 결합 됩니다.  지정 하는 경우 <xref:System.Windows.FrameworkPropertyMetadataOptions>, 원래 옵션을 덮어쓰지 않습니다.  옵션을 변경 하려면 해당 속성에 설정 <xref:System.Windows.FrameworkPropertyMetadata>합니다. 예를 들어 경우 원래 <xref:System.Windows.FrameworkPropertyMetadata> 집합 개체를 <xref:System.Windows.FrameworkPropertyMetadataOptions.NotDataBindable?displayProperty=nameWithType> 플래그를 설정 하 여 변경할 수 있습니다 <xref:System.Windows.FrameworkPropertyMetadata.IsNotDataBindable%2A?displayProperty=nameWithType> 에 `false`입니다.  
  
 이 동작을 구현 하 여 <xref:System.Windows.FrameworkPropertyMetadata.Merge%2A>, 파생 된 메타 데이터 클래스에서 재정의할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.DependencyProperty.GetMetadata%2A>
- [종속성 속성 메타데이터](dependency-property-metadata.md)
- [종속성 속성 개요](dependency-properties-overview.md)
- [사용자 지정 종속성 속성](custom-dependency-properties.md)
