---
title: 코드 숨김과 XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 212a37fb7fbcb7e66a669d96671333be793956df
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738097"
---
# <a name="code-behind-and-xaml-in-wpf"></a>WPF의 코드 숨김 및 XAML
<a name="introduction"></a>코드 숨김이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지가 태그 컴파일될 때 태그 정의 개체와 조인 된 코드를 설명 하는 데 사용 되는 용어입니다. 이 항목에서는 코드 숨김으로 사용할 요구 사항 뿐만 아니라 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]코드에 대 한 대체 인라인 코드 메커니즘에 대해 설명 합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
- [전제 조건](#Prerequisites)  
  
- [코드 숨김과 XAML 언어](#codebehind_and_the_xaml_language)  
  
- [WPF의 코드 숨겨진, 이벤트 처리기 및 Partial 클래스 요구 사항](#Code_behind__Event_Handler__and_Partial_Class)  
  
- [x:Code](#x_Code)  
  
- [인라인 코드 제한 사항](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 [XAML 개요 (WPF)](../../../desktop-wpf/fundamentals/xaml.md) 를 읽고 CLR 및 개체 지향 프로그래밍에 대 한 기본적인 지식이 있다고 가정 합니다.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>코드 숨김과 XAML 언어  
 XAML 언어에는 태그 파일에서 태그 파일과 코드 파일을 연결할 수 있도록 하는 언어 수준 기능이 포함 되어 있습니다. 특히 XAML 언어는 언어 기능인 [X:Class 지시문](../../../desktop-wpf/xaml-services/xclass-directive.md), [X:Subclass 지시문](../../../desktop-wpf/xaml-services/xsubclass-directive.md)및 [x:classmodifier 지시문](../../../desktop-wpf/xaml-services/xclassmodifier-directive.md)을 정의 합니다. 코드를 생성 하는 방법과 태그와 코드를 통합 하는 방법은 XAML 언어가 지정 하는 내용에 포함 되지 않습니다. 코드를 통합 하는 방법, 응용 프로그램 및 프로그래밍 모델에서 XAML을 사용 하는 방법, 빌드 작업 또는 모든 작업에 필요한 기타 지원을 결정 하는 WPF와 같은 프레임 워크를 사용 합니다.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>WPF의 코드 숨겨진, 이벤트 처리기 및 Partial 클래스 요구 사항  
  
- Partial 클래스는 루트 요소를 백업 하는 형식에서 파생 되어야 합니다.  
  
- 태그 컴파일 빌드 작업의 기본 동작에서 파생 된 코드를 partial 클래스의 partial 클래스 정의에서 비워 둘 수 있습니다. 컴파일된 결과는 지정 되지 않은 경우에도 페이지 루트의 지원 형식이 partial 클래스의 기반이 된다고 가정 합니다. 그러나이 동작에 의존 하는 것은 좋은 방법이 아닙니다.  
  
- 코드 숨김으로 작성 하는 이벤트 처리기는 인스턴스 메서드 여야 하며 정적 메서드가 될 수 없습니다. 이러한 메서드는 `x:Class`로 식별 된 CLR 네임 스페이스 내의 partial 클래스에서 정의 해야 합니다. 다른 클래스 범위의 이벤트 연결에 대 한 이벤트 처리기를 찾도록 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에 지시 하는 이벤트 처리기의 이름을 한정할 수 없습니다.  
  
- 처리기는 지원 형식 시스템의 해당 이벤트에 대 한 대리자와 일치 해야 합니다.  
  
- 특히 Microsoft Visual Basic 언어의 경우 언어별 `Handles` 키워드를 사용 하 여 처리기를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]특성에 연결 하는 대신 처리기 선언의 인스턴스 및 이벤트와 연결할 수 있습니다. 그러나 `Handles` 키워드는 특정 라우트된 이벤트 시나리오 또는 연결 된 이벤트와 같이 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 시스템의 모든 특정 기능을 지원할 수 없기 때문에이 방법에는 몇 가지 제한이 있습니다. 자세한 내용은 [Visual Basic 및 WPF 이벤트 처리](visual-basic-and-wpf-event-handling.md)를 참조 하세요.  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>x:Code  
 [x:Code](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md) 는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 정의 된 지시문 요소입니다. `x:Code` 지시문 요소는 인라인 프로그래밍 코드를 포함할 수 있습니다. 인라인으로 정의 된 코드는 같은 페이지의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 상호 작용할 수 있습니다. 다음 예제에서는 인라인 C# 코드를 보여 줍니다. 코드는 `x:Code` 요소 내에 있으며, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 ([!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 스키마 또는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스키마를 해석)가 내용을 그대로 XML로 해석 하지 않도록 `<CDATA[`...`]]>`에서 XML의 내용을 이스케이프 처리 해야 합니다.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](~/samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>인라인 코드 제한 사항  
 인라인 코드 사용을 방지 하거나 제한 하는 것을 고려해 야 합니다. 아키텍처 및 코딩 철학 측면에서 태그와 코드 숨김으로 분리를 유지 하면 디자이너와 개발자 역할이 훨씬 더 명확 하 게 유지 됩니다. 좀 더 기술적인 수준에서 인라인 코드에 대해 작성 하는 코드는 항상 생성 되는 partial 클래스 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 작성 하 고 기본 XML 네임 스페이스 매핑만 사용할 수 있기 때문에 작성 하기 불편할 수 있습니다. `using` 문을 추가할 수 없으므로 많은 API 호출을 정규화 해야 합니다. 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 매핑은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리에 있는 CLR 네임 스페이스를 모두 포함 하지만 대부분은 포함 하지 않습니다. 다른 CLR 네임 스페이스 내에 포함 된 형식 및 멤버에 대 한 호출을 정규화 해야 합니다. 또한 인라인 코드에서 partial 클래스 이외의 모든 항목을 정의할 수 없으며, 사용자가 참조 하는 모든 사용자 코드 엔터티는 생성 된 partial 클래스 내에 멤버 또는 변수로 존재 해야 합니다. 매크로, 전역 변수 또는 빌드 변수에 대 한 `#ifdef` 같은 다른 언어 관련 프로그래밍 기능을 사용할 수도 없습니다. 자세한 내용은 [X:Code 내장 XAML 형식](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)을 참조 하세요.  
  
## <a name="see-also"></a>참조

- [XAML 개요(WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [x:Code 내장 XAML 형식](../../../desktop-wpf/xaml-services/xcode-intrinsic-xaml-type.md)
- [WPF 애플리케이션 빌드](../app-development/building-a-wpf-application-wpf.md)
- [XAML 구문 정보](xaml-syntax-in-detail.md)
