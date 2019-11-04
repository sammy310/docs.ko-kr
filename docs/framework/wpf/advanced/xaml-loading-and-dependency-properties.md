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
ms.openlocfilehash: 57c25297f995acd1ef307466258b5f4e03cc3098
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459536"
---
# <a name="xaml-loading-and-dependency-properties"></a>XAML 로드 및 종속성 속성
현재 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 구현할 때는 기본적으로 종속성 속성을 인식합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서는 이진 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 로드하고 종속성 속성인 특성을 처리할 때 종속성 속성에 대해 속성 시스템 메서드를 사용합니다. 이렇게 하면 속성 래퍼를 효과적으로 우회할 수 있습니다. 사용자 지정 종속성 속성을 구현 하는 경우이 동작을 고려해 야 하며, <xref:System.Windows.DependencyObject.GetValue%2A> 하 고 <xref:System.Windows.DependencyObject.SetValue%2A>속성 시스템 메서드 외에 다른 코드를 속성 래퍼에 배치 하지 않아야 합니다.  

<a name="prerequisites"></a>   
## <a name="prerequisites"></a>Prerequisites  
 이 항목에서는 사용자가 소비자와 작성자의 입장에서 종속성 속성을 이해하고 있으며 [종속성 속성 개요](dependency-properties-overview.md) 및 [사용자 지정 종속성 속성](custom-dependency-properties.md)을 읽었다고 가정합니다. 또한 [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md) 및 [XAML 구문 정보](xaml-syntax-in-detail.md)도 읽어야 합니다.  
  
<a name="implementation"></a>   
## <a name="the-wpf-xaml-loader-implementation-and-performance"></a>WPF XAML 로더 구현 및 성능  
 구현 상의 이유로 속성 래퍼 및 setter를 사용 하는 대신 속성을 종속성 속성으로 식별 하 고 속성 시스템 <xref:System.Windows.DependencyObject.SetValue%2A> 메서드에 액세스 하 여 속성을 설정 하는 것이 더 저렴 합니다. 이는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에서 태그 구조 및 여러 문자열로 나타나는 형식과 멤버 관계만 보고 백업 코드의 전체 개체 모델을 유추해야 하기 때문입니다.  
  
 이 형식은 xmlns 및 어셈블리 특성의 조합을 통해 조회 되지만, 멤버를 식별 하 고, 특성으로 설정 될 수 있는 형식을 확인 하 고, 속성 값이 지 원하는 형식을 확인 하면 광범위 한 리플렉션이 필요 합니다. <xref:System.Reflection.PropertyInfo>사용. 지정 된 형식의 종속성 속성은 속성 시스템을 통해 저장소 테이블로 액세스할 수 있으므로 해당 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현에서는이 테이블을 사용 하 고 지정 된 속성 *ABC* 가 보다 효율적으로 설정 될 수 있음을 유추 합니다. *ABCProperty*종속성 속성 식별자를 사용 하 여 포함 하는 <xref:System.Windows.DependencyObject> 파생 형식에서 <xref:System.Windows.DependencyObject.SetValue%2A>를 호출 합니다.  
  
<a name="implications"></a>   
## <a name="implications-for-custom-dependency-properties"></a>사용자 지정 종속성 속성의 의미  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서의 속성 설정 동작으로 현재 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 구현할 때는 래퍼를 완전히 우회하기 때문에 사용자 지정 종속성 속성에 대한 래퍼 집합 정의에 추가 논리를 넣지 않아야 합니다. 집합 정의에 이러한 논리를 넣으면 속성이 코드가 아닌 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]로 설정된 경우 논리가 실행되지 않습니다.  
  
 마찬가지로 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 처리에서 속성 값을 가져오는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서의 다른 측면 에서도 래퍼를 사용 하는 대신 <xref:System.Windows.DependencyObject.GetValue%2A>를 사용 합니다. 따라서 <xref:System.Windows.DependencyObject.GetValue%2A> 호출 외에도 `get` 정의에서 추가적인 구현을 방지 해야 합니다.  
  
 다음 예제는 래퍼에 권장되는 종속성 속성 정의로서, 여기서 속성 식별자는 `public` `static` `readonly` 필드로 저장되고 `get` 및 `set` 정의에는 종속성 속성 백업을 정의하는 필수 속성 시스템 메서드 이외의 코드는 포함되어 있지 않습니다.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## <a name="see-also"></a>참조

- [종속성 속성 개요](dependency-properties-overview.md)
- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [종속성 속성 메타데이터](dependency-property-metadata.md)
- [컬렉션 형식 종속성 속성](collection-type-dependency-properties.md)
- [종속성 속성 보안](dependency-property-security.md)
- [DependencyObjects의 안전한 생성자 패턴](safe-constructor-patterns-for-dependencyobjects.md)
