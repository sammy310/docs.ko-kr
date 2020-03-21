---
title: XAML 로드 및 종속성 속성
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom dependency properties [WPF]
- dependency properties [WPF], XAML loading and
- loading XML data [WPF]
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
ms.openlocfilehash: de8050e582f5b1a5a288c350c179cfa24fb5471c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186245"
---
# <a name="xaml-loading-and-dependency-properties"></a>XAML 로드 및 종속성 속성
현재 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 구현할 때는 기본적으로 종속성 속성을 인식합니다. 프로세서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이진 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 을 로드할 때 종속성 속성에 속성 시스템 메서드를 사용 하 고 종속성 속성인 특성을 처리 합니다. 이렇게 하면 속성 래퍼를 효과적으로 우회할 수 있습니다. 사용자 지정 종속성 속성을 구현할 때이 동작을 설명 해야 하 고 속성 시스템 메서드 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A>.  

<a name="prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 사용자가 소비자와 작성자의 입장에서 종속성 속성을 이해하고 있으며 [종속성 속성 개요](dependency-properties-overview.md) 및 [사용자 지정 종속성 속성](custom-dependency-properties.md)을 읽었다고 가정합니다. 또한 [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md) 및 [XAML 구문 정보](xaml-syntax-in-detail.md)도 읽어야 합니다.  
  
<a name="implementation"></a>
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>WPF XAML 로더 구현 및 성능  
 구현상의 이유로 속성 래퍼와 setter를 사용하는 대신 속성을 종속성 속성으로 <xref:System.Windows.DependencyObject.SetValue%2A> 식별하고 속성 시스템 메서드에 액세스하여 속성을 설정하는 것이 계산비용이 줄어듭니다. 이는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 태그 구조 및 여러 문자열로 나타나는 형식과 멤버 관계만 보고 백업 코드의 전체 개체 모델을 유추해야 하기 때문입니다.  
  
 형식은 xmlns 및 어셈블리 특성의 조합을 통해 조회되지만 멤버를 식별하고, 속성으로 설정되는 것을 결정하고, 지원되는 속성 값을 해결하는 <xref:System.Reflection.PropertyInfo>데 는 을 사용하여 광범위한 리플렉션이 필요합니다. 지정된 형식의 종속성 속성은 속성 시스템을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 통해 저장소 테이블로 액세스할 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 수 있으므로 프로세서 구현에서는 이 테이블을 사용하고 종속성 속성 <xref:System.Windows.DependencyObject.SetValue%2A> 식별자 *ABCProperty를*사용하여 포함된 <xref:System.Windows.DependencyObject> 파생 형식을 호출하여 지정된 *속성 ABC를* 보다 효율적으로 설정할 수 있음을 유추합니다.  
  
<a name="implications"></a>
## <a name="implications-for-custom-dependency-properties"></a>사용자 지정 종속성 속성의 의미  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서의 속성 설정 동작으로 현재 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 구현할 때는 래퍼를 완전히 우회하기 때문에 사용자 지정 종속성 속성에 대한 래퍼 집합 정의에 추가 논리를 넣지 않아야 합니다. 집합 정의에 이러한 논리를 넣으면 속성이 코드가 아닌 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]로 설정된 경우 논리가 실행되지 않습니다.  
  
 마찬가지로 처리에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 속성 값을 가져오는 프로세서의 다른 <xref:System.Windows.DependencyObject.GetValue%2A> 측면도 래퍼를 사용하는 대신 사용합니다. 따라서 `get` <xref:System.Windows.DependencyObject.GetValue%2A> 호출 을 넘어 정의에 추가 구현을 방지 해야 합니다.  
  
 다음 예제는 속성 식별자가 `public` `static` `readonly` 필드로 저장되고 `get` 및 `set` 정의에는 종속성 속성 백업을 정의하는 필요한 속성 시스템 메서드 를 초과하는 코드가 없는 래퍼가 있는 것이 좋습니다.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>참고 항목

- [종속성 속성 개요](dependency-properties-overview.md)
- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [종속성 속성 메타데이터](dependency-property-metadata.md)
- [컬렉션 형식 종속성 속성](collection-type-dependency-properties.md)
- [종속성 속성 보안](dependency-property-security.md)
- [DependencyObject의 안전한 생성자 패턴](safe-constructor-patterns-for-dependencyobjects.md)
