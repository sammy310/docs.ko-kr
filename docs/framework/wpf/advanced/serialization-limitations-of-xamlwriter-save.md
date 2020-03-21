---
title: XamlWriter.Save의 serialization 제한
ms.date: 03/30/2017
helpviewer_keywords:
- XamlWriter.Save [WPF], serialization limitations of
- limitations of XamlWriter.Save
- serialization limitations of XamlWriter.Save
ms.assetid: f86acc91-2b67-4039-8555-505734491d36
ms.openlocfilehash: 96e917898320fb5d49f4e7dfc27daa7750af9d41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174370"
---
# <a name="serialization-limitations-of-xamlwritersave"></a>XamlWriter.Save의 serialization 제한
API를 <xref:System.Windows.Markup.XamlWriter.Save%2A> 사용하여 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램의 내용을 파일로 직렬화할 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 수 있습니다. 하지만 정확히 serialize되는 항목에 대한 눈에 띄는 몇 가지 제한 사항이 있습니다. 이러한 제한 사항과 몇몇 일반적인 고려 사항은 이 항목에서 설명합니다.  

<a name="Run_Time__Not_Design_Time_Representation"></a>
## <a name="run-time-not-design-time-representation"></a>런타임으로, 디자인 타임 표현이 아님  
 호출에 <xref:System.Windows.Markup.XamlWriter.Save%2A> 의해 직렬화되는 기본 철학은 결과가 런타임에 직렬화되는 개체를 나타내는 것입니다. 원본 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일의 많은 디자인 타임 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 속성은 메모리 내 개체로 로드될 때까지 이미 최적화되거나 손실될 <xref:System.Windows.Markup.XamlWriter.Save%2A> 수 있으며 직렬화를 호출할 때 보존되지 않습니다. serialize된 결과는 생성된 애플리케이션 논리 트리의 효과적인 표현이지만 논리 트리를 생성한 원래 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에는 효과적인 표현이 아닐 수 있습니다. 이러한 문제로 인해 <xref:System.Windows.Markup.XamlWriter.Save%2A> 광범위한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 설계 표면의 일부로 직렬화를 사용하기가 매우 어려워요.  
  
<a name="Serialization_is_Self_Contained"></a>
## <a name="serialization-is-self-contained"></a>Serialization은 자체 포함됨  
 직렬화된 <xref:System.Windows.Markup.XamlWriter.Save%2A> 출력은 독립적입니다. 직렬화되는 모든 것은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 단일 루트 요소와 URI 이외의 외부 참조가 없는 단일 페이지 내에 포함됩니다. 예를 들어 페이지에서 애플리케이션 리소스의 리소스를 참조한 경우 리소스는 serialize되는 페이지의 구성 요소인 것처럼 표시됩니다.  
  
<a name="Extension_References_are_Dereferenced"></a>
## <a name="extension-references-are-dereferenced"></a>확장 참조가 역참조됨  
 `StaticResource` 또는 `Binding`과 같은 다양한 태그 확장 서식으로 만들어진 개체에 대한 일반 참조는 serialization 프로세스에서 역참조됩니다. 이러한 개체는 응용 프로그램 런타임에 의해 메모리 내 개체가 생성된 <xref:System.Windows.Markup.XamlWriter.Save%2A> 시점에 이미 역참조되었으며 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 논리는 원본을 다시 방문하여 직렬화된 출력에 대한 이러한 참조를 복원하지 않습니다. 이로 인해 데이터 바인딩된 값이나 리소스에서 얻은 값은 해당 값을 로컬에서 설정된 다른 값과 구분하는 제한되거나 간접적인 기능만으로 런타임 표현에서 마지막으로 사용된 값으로 고정될 수 있습니다. 이미지는 원본 소스 참조가 아니라 프로젝트에 있는 이미지에 대한 개체 참조로 직렬화되어 원래 참조된 파일 이름이나 URI가 손실됩니다. 같은 페이지에서 선언된 리소스도 리소스 컬렉션의 키로 유지되지 않고 참조된 지점으로 serialize된 것으로 보입니다.  
  
<a name="Event_Handling_is_Not_Preserved"></a>
## <a name="event-handling-is-not-preserved"></a>이벤트 처리가 유지되지 않음  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 통해 이벤트 처리기가 serialize될 경우 이벤트 처리기는 유지되지 않습니다. 코드 숨김이 없고 관련 x:Code 메커니즘이 없는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]은 런타임 절차 논리를 serialize할 수 없습니다. serialization은 자체 포함되고 논리 트리로 제한되므로 이벤트 처리기를 저장하는 기능이 없습니다. 따라서 이벤트 처리기 특성(특성 자체 및 처리기를 명명하는 문자열 값)이 출력 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 제거됩니다.  
  
<a name="Realistic_Scenarios_for_Use_of_XAMLWriter_Save"></a>
## <a name="realistic-scenarios-for-use-of-xamlwritersave"></a>XAMLWriter.Save 사용에 대한 실제 시나리오  
 여기에 나열된 제한 사항은 상당히 상당하지만 직렬화에 <xref:System.Windows.Markup.XamlWriter.Save%2A> 사용하기 에 적합한 몇 가지 시나리오가 있습니다.  
  
- 벡터 또는 그래픽 출력: 렌더링된 영역의 출력은 다시 로드될 때 같은 벡터나 그래픽을 재현하는 데 사용할 수 있습니다.  
  
- 서식 있는 텍스트 및 유동 문서: 텍스트 및 텍스트 내의 모든 요소 서식 및 요소 포함은 출력에서 유지됩니다. 이는 클립보드 기능과 비슷한 메커니즘에 유용할 수 있습니다.  
  
- 비즈니스 개체 데이터 보존: 비즈니스 개체가 참조 별 속성 값에 대한 사용자 지정 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 생성자 및 변환을 제공하는 등의 기본 규칙을 따르는 한 XML 데이터와 같은 사용자 지정 요소에 데이터를 저장한 경우 이러한 비즈니스 개체는 직렬화를 통해 영구적으로 사용할 수 있습니다.
