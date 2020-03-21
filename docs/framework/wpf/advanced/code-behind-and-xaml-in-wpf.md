---
title: 코드 숨미기 및 XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 32283d5b81bf92999a97711ded13a8b533ae3028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145347"
---
# <a name="code-behind-and-xaml-in-wpf"></a>WPF의 코드 숨김 및 XAML
<a name="introduction"></a>Code-behind는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 마크업 컴파일될 때 태그 정의 개체와 결합된 코드를 설명하는 데 사용되는 용어입니다. 이 항목에서는 코드 숨김에 대한 요구 사항과 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 코드에 대한 대체 인라인 코드 메커니즘에 대해 설명합니다.  
  
 이 항목에는 다음과 같은 섹션이 포함되어 있습니다.  
  
- [필수 조건](#Prerequisites)  
  
- [코드 숨미기 및 XAML 언어](#codebehind_and_the_xaml_language)  
  
- [WPF의 코드 숨김, 이벤트 처리기 및 부분 클래스 요구 사항](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [X:code](#x_Code)  
  
- [인라인 코드 제한](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 [XAML 개요(WPF)를](../../../desktop-wpf/fundamentals/xaml.md) 읽고 CLR 및 개체 지향 프로그래밍에 대한 몇 가지 기본 지식을 가지고 있다고 가정합니다.  
  
<a name="codebehind_and_the_xaml_language"></a>
## <a name="code-behind-and-the-xaml-language"></a>코드 숨미기 및 XAML 언어  
 XAML 언어에는 태그 파일 측에서 코드 파일을 태그 파일과 연결할 수 있는 언어 수준 기능이 포함되어 있습니다. 특히 XAML 언어는 언어 기능 [x:Class 지시문](../../../desktop-wpf/xaml-services/xclass-directive.md), [x:하위 클래스 지시문](../../../desktop-wpf/xaml-services/xsubclass-directive.md)및 [x:ClassModifier 지시문을](../../../desktop-wpf/xaml-services/xclassmodifier-directive.md)정의합니다. 코드를 생성하는 방법과 태그 및 코드를 통합하는 방법은 XAML 언어가 지정한 내용의 일부가 아닙니다. 코드를 통합하는 방법, 응용 프로그램 및 프로그래밍 모델에서 XAML을 사용하는 방법, 이 모든 것이 필요한 빌드 작업 또는 기타 지원을 결정하는 방법은 WPF와 같은 프레임워크에 달려 있습니다.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>WPF의 코드 숨김, 이벤트 처리기 및 부분 클래스 요구 사항  
  
- 부분 클래스는 루트 요소를 백업하는 형식에서 파생되어야 합니다.  
  
- 태그 컴파일 빌드 작업의 기본 동작에서 코드 뒤에 있는 부분 클래스 정의에 파생을 비워 둘 수 있습니다. 컴파일된 결과는 페이지 루트의 백업 형식이 지정되지 않은 경우에도 부분 클래스의 기준으로 가정합니다. 그러나 이 동작에 의존하는 것이 좋은 방법은 아닙니다.  
  
- 코드 숨김에 쓰는 이벤트 처리기는 인스턴스 메서드여야 하며 정적 메서드일 수 없습니다. 이러한 메서드는 에서 식별된 CLR 네임스페이스 `x:Class`내의 부분 클래스에 의해 정의되어야 합니다. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 다른 클래스 범위의 이벤트 배선에 대한 이벤트 처리기를 찾도록 지시하도록 이벤트 처리기의 이름을 한정할 수 없습니다.  
  
- 처리기는 백업 형식 시스템에서 적절한 이벤트에 대한 대리자를 일치시켜야 합니다.  
  
- 특히 Microsoft Visual Basic 언어의 경우 언어별 `Handles` 키워드를 사용하여 처리기에서 처리기를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 특성을 가진 처리기를 연결하는 대신 처리기 선언의 인스턴스 및 이벤트와 연결할 수 있습니다. 그러나 이 기술은 `Handles` 키워드가 특정 라우트된 이벤트 시나리오 또는 연결된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트와 같은 이벤트 시스템의 모든 특정 기능을 지원할 수 없기 때문에 몇 가지 제한사항이 있습니다. 자세한 내용은 [시각적 기본 및 WPF 이벤트 처리를](visual-basic-and-wpf-event-handling.md)참조하십시오.  
  
<a name="x_Code"></a>
## <a name="xcode"></a>X:code  
 [x:Code는](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md) 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]정의된 지시문 요소입니다. 지시문 요소에는 `x:Code` 인라인 프로그래밍 코드가 포함될 수 있습니다. 인라인으로 정의된 코드는 동일한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지에서 상호 작용할 수 있습니다. 다음 예제에서는 인라인 C# 코드를 보여 줍니다. 코드는 `x:Code` 요소 내부에 있으며 코드는 `<CDATA[`다음으로 둘러싸여야 합니다. `]]>` 프로세서(스키마 또는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스키마 를 해석하는)가 내용을 문자 그대로 XML로 해석하지 않도록 XML의 내용을 이스케이프합니다.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>
## <a name="inline-code-limitations"></a>인라인 코드 제한  
 인라인 코드 사용을 피하거나 제한하는 것이 좋습니다. 아키텍처 및 코딩 철학측면에서 태그와 코드 숨김을 구분하여 유지하면 디자이너와 개발자 역할이 훨씬 더 구별됩니다. 보다 기술적인 수준에서인라인 코드에 대해 작성하는 코드는 항상 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 생성된 부분 클래스에 쓰고 기본 XML 네임스페이스 매핑만 사용할 수 있기 때문에 작성하기가 어려울 수 있습니다. 문을 추가할 `using` 수 없으므로 많은 API 호출을 완전히 한정해야 합니다. 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 매핑에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리에 있는 대부분의 CLR 네임스페이스가 포함되지만 모든 CLR 네임스페이스는 포함되지 않습니다. 다른 CLR 네임스페이스에 포함된 형식 및 멤버에 대한 호출을 완전히 한정적으로 지정해야 합니다. 또한 인라인 코드의 부분 클래스 를 벗어난 것을 정의할 수 없으며 참조하는 모든 사용자 코드 엔터티는 생성된 부분 클래스 내에 멤버 또는 변수로 존재해야 합니다. 매크로 또는 전역 변수 또는 `#ifdef` 빌드 변수와 같은 다른 언어별 프로그래밍 기능도 사용할 수 없습니다. 자세한 내용은 [x:코드 고유 XAML 유형을](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [x:Code 내장 XAML 형식](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)
- [WPF 애플리케이션 빌드](../app-development/building-a-wpf-application-wpf.md)
- [XAML 구문 정보](xaml-syntax-in-detail.md)
