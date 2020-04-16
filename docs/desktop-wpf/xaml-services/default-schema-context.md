---
title: 기본 XAML 스키마 컨텍스트 및 WPF XAML 스키마 컨텍스트
ms.date: 03/30/2017
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
ms.openlocfilehash: 2e92372de61230a98a02282cc28fc3f479cd94eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433081"
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>기본 XAML 스키마 컨텍스트 및 WPF XAML 스키마 컨텍스트
XAML 스키마 컨텍스트는 특정 XAML 어휘를 사용하는 XAML 프로덕션이 형식 매핑 해결 방법, 어셈블리로드 방법, 특정 판독기 및 기록기 설정을 해석하는 방법을 포함하여 개체 쓰기 동작과 상호 작용하는 방법을 갖춘 개념적 엔터티입니다. 이 항목에서는 CLR 형식 시스템을 기반으로 하는 .NET XAML 서비스의 기능 및 관련 기본 XAML 스키마 컨텍스트에 대해 설명합니다. 이 항목에서는 WPF에 사용되는 XAML 스키마 컨텍스트에 대해서도 설명합니다.

## <a name="default-xaml-schema-context"></a>기본 XAML 스키마 컨텍스트

.NET XAML 서비스는 기본 XAML 스키마 컨텍스트를 구현하고 사용합니다. 기본 XAML 스키마 컨텍스트 동작이 <xref:System.Xaml.XamlSchemaContext> 클래스의 API에 항상 완전히 표시되는 것은 아닙니다. 그러나 대부분의 경우 기본 XAML 스키마 컨텍스트가 영향을 주는 동작은 XAML 형식 시스템의 공통 API(예: 멤버 <xref:System.Xaml.XamlMember> 또는 <xref:System.Xaml.XamlType>또는 기본 XAML 스키마 컨텍스트를 사용하는 XAML 판독기 및 XAML 작성기에 노출된 API를 통해)를 통해 관찰할 수 있습니다.

생성자를 호출하여 기본 동작을 캡슐화하는 a를 <xref:System.Xaml.XamlSchemaContext> <xref:System.Xaml.XamlSchemaContext> 만들 수 있습니다. 이렇게 하면 기본 XAML 스키마 컨텍스트가 명시적으로 만들어집니다. <xref:System.Xaml.XamlSchemaContext> 입력 매개 변수를 명시적으로 사용하지 않는 API를 사용하여 XAML 리더 또는 XAML 라이터를 초기화하면 동일한 기본 XAML 스키마 컨텍스트가 암시적으로 만들어집니다.

기본 XAML 스키마 컨텍스트는 형식 매핑 동작에 대한 CLR 리플렉션을 기반으로 합니다. 여기에는 정의 CLR <xref:System.Type>및 <xref:System.Reflection.PropertyInfo> 관련 <xref:System.Reflection.MethodInfo>또는 에 대한 검사가 포함됩니다. 또한 형식 또는 멤버에 대한 CLR 기여는 CLR 백업 유형을 사용하는 XAML 형식 또는 XAML 멤버 정보에 대한 세부 정보를 채우기 위해 사용됩니다. 기본 XAML 스키마 컨텍스트에는 CLR 형식 시스템에서 `Invoker` 필요한 정보를 사용할 수 있으므로 패턴과 같은 형식 시스템 확장 기술이 필요하지 않습니다.

어셈블리 로드 논리의 경우 기본 XAML 스키마 컨텍스트는 주로 XAML 네임스페이스 매핑에 제공된 모든 어셈블리 값에 의존합니다. 또한 <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> 내부 형식 로드와 같은 시나리오의 경우 어셈블리를 로드하도록 암시할 수 있습니다.

## <a name="wpf-xaml-schema-context"></a>WPF XAML 스키마 컨텍스트

WPF 구현은 기본이 아닌 XAML 스키마 컨텍스트를 구현하여 도입할 수 있는 기능의 종류에 대한 흥미로운 그림을 제공하기 때문에 WPF XAML 스키마 컨텍스트는 이 항목에서 설명합니다. 또한 XAML 스키마 컨텍스트 개념은 WPF XAML을 다루는 WPF 설명서에서 별로 설명되지 않습니다. XAML 스키마 컨텍스트에서 사용할 수 있는 동작은 기본 XAML 스키마 컨텍스트가 작동하는 방식에 대한 설명과 통합된 경우에만 완전히 이해할 수 있습니다. WPF XAML 스키마 컨텍스트는 다음 동작을 구현합니다.

**조회 재정의:** WPF에는 <xref:System.Windows.Markup.ContentPropertyAttribute> 어트리뷰션되지 않고 작동하는 XAML 콘텐츠 속성이 있는 XAML에 대한 몇 가지 콘텐츠 모델이 있습니다. <xref:System.Xaml.XamlType.LookupContentProperty%2A>WPF에 대한 재정의는 이 동작을 구현합니다.

**WPF 식에 대한 지연:** WPF에는 런타임 컨텍스트를 사용할 수 있게 될 때까지 값을 연기하는 여러 식 클래스가 있습니다. 또한 템플릿 확장은 지연 기술에 의존하는 런타임 동작입니다.

**시스템 조회 최적화 유형:** WPF에는 말 그대로 수백 개의 WPF 정의 클래스에 상속되는 기본 클래스 멤버 정의를 포함하여 광범위한 XAML 어휘 및 개체 모델이 있습니다. 또한 WPF 자체는 여러 어셈블리에 분산되어 있습니다. WPF는 조회 테이블 및 기타 기술을 사용하여 형식 조회를 최적화합니다. 이렇게 하면 기본 XAML 스키마 컨텍스트 및 CLR 기반 형식 조회에 대한 성능이 향상됩니다. 형식이 조회 테이블에 없는 경우 동작은 기본 XAML 스키마 컨텍스트와 유사한 XAML 스키마 컨텍스트 기술을 사용합니다.

**XamlType 및 XamlMember 확장:** WPF는 종속성 속성을 사용하여 속성 개념을 확장하고 라우트된 이벤트를 사용하여 이벤트 개념을 확장합니다. 이러한 개념에 XAML 처리 작업에 대한 가시성을 높이기 <xref:System.Xaml.XamlType> <xref:System.Xaml.XamlMember>위해 WPF는 종속성 속성 및 라우팅된 이벤트 특성을 보고하는 내부 속성을 확장하고 추가합니다.

### <a name="accessing-the-wpf-xaml-schema-context"></a>WPF XAML 스키마 컨텍스트 액세스

WPF <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 또는 <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>WPF를 기반으로 하는 XAML 기술을 사용하는 경우 해당 XAML 판독기 및 XAML 기록기 구현에서 WPF XAML 스키마 컨텍스트가 이미 사용 중입니다.

WPF XAML 스키마 컨텍스트로 초기화하지 않는 다른 XAML 판독기 또는 XAML 기록기 구현을 사용하는 경우 에서 <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>작업 중인 WPF XAML 스키마 컨텍스트를 얻을 수 있습니다. 그런 다음 이 값을 <xref:System.Xaml.XamlSchemaContext>을 사용하는 다른 API의 초기화로 사용할 수 있습니다. 예를 들어 초기화를 <xref:System.Xaml.XamlXmlReader.%23ctor%2A> 호출하고 WPF XAML 스키마 컨텍스트를 전달할 수 있습니다. 또는 XAML 형식 시스템 작업에 WPF XAML 스키마 컨텍스트를 사용할 수 있습니다. 여기에는 <xref:System.Xaml.XamlType> 또는 <xref:System.Xaml.XamlMember>의 시공 초기화가 <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>포함될 수 있습니다.

순수한 XAML 노드 스트림 관점에서 WPF XAML의 특정 측면에 액세스하는 경우 일부 WPF 프레임워크 기능이 아직 작동하지 않았을 수 있습니다. 예를 들어 컨트롤에 대한 WPF 템플릿은 아직 적용되지 않습니다. 따라서 런타임에 전체 시각적 트리로 채워질 수 있는 속성에 액세스하는 경우 템플릿을 참조하는 속성 값만 표시될 수 있습니다. WPF 태그 확장에 대해 제공된 서비스 컨텍스트는 런타임이 아닌 상황에서 제공된 경우 정확하지 않을 수 있으며 개체 그래프를 작성하려고 할 때 예외가 발생할 수 있습니다.

## <a name="xaml-and-assembly-loading"></a>XAML 및 어셈블리 로딩

XAML 및 .NET XAML 서비스에 대한 어셈블리 로드는 <xref:System.AppDomain>CLR 정의 개념과 통합됩니다. XAML 스키마 컨텍스트는 사용 <xref:System.AppDomain> 및 기타 요인에 따라 어셈블리를 로드하거나 런타임 또는 디자인 시간에 형식을 찾는 방법을 해석합니다. 논리는 XAML이 XAML 판독기의 느슨한 XAML인지, XAML이 DLL로 `XamlBuildTask`컴파일되었는지 또는 WPF에 의해 생성된 `PresentationBuildTask`BAML인지에 따라 약간 다릅니다.

WPF에 대한 XAML 스키마 컨텍스트는 WPF 응용 프로그램 모델과 통합되며, WPF 구현 세부 정보인 다른 요소도 사용합니다. <xref:System.AppDomain>

#### <a name="xaml-reader-input-loose-xaml"></a>XAML 리더 입력(느슨한 XAML)

01. XAML 스키마 컨텍스트는 응용 프로그램을 <xref:System.AppDomain> 통해 가장 최근에 로드된 어셈블리부터 시작하여 이름의 모든 측면과 일치하는 이미 로드된 어셈블리를 찾습니다. 일치하는 검색어가 발견되면 해당 어셈블리가 해상도에 사용됩니다.

02. 그렇지 않으면 CLR <xref:System.Reflection.Assembly> API를 기반으로 하는 다음 기술 중 하나가 어셈블리를 로드하는 데 사용됩니다.

    - 이름이 매핑에서 한정된 경우 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 정규화된 이름을 호출합니다.

    - 이전 단계가 실패하면 짧은 이름(및 공개 키 토큰이 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>있는 경우)을 사용하여 을 호출합니다.

    - 이름이 매핑에서 정규화되지 않은 <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>경우 를 호출합니다.

#### <a name="xamlbuildtask"></a>XamlBuildTask

`XamlBuildTask`는 WCF(Windows 통신 재단) 및 Windows 워크플로 파운데이션에 사용됩니다.

어셈블리 `XamlBuildTask` 참조는 항상 정규화됩니다.

1. 정규화된 이름을 호출합니다. <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>

2. 이전 단계가 실패하면 짧은 이름(및 공개 키 토큰이 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>있는 경우)을 사용하여 을 호출합니다.

#### <a name="baml-presentationbuildtask"></a>BAML (프레젠테이션 빌드 태스크)

BAML에 대한 어셈블리 로드에는 BAML이 포함된 초기 어셈블리를 구성 요소로 로드하고 BAML 프로덕션에서 참조하는 모든 형식에 대해 형식 백업 어셈블리를 로드하는 두 가지 측면이 있습니다.

##### <a name="assembly-load-for-initial-markup"></a>초기 태그에 대한 어셈블리 로드:

태그에서 태그를 로드하는 어셈블리에 대한 참조는 항상 정규화되지 않습니다.

1. WPF XAML 스키마 컨텍스트는 WPF <xref:System.AppDomain> 응용 프로그램을 통해 변경되어 가장 최근에 로드된 어셈블리부터 시작하여 이름의 모든 측면과 일치하는 이미 로드된 어셈블리를 찾습니다. 일치하는 검색어가 발견되면 해당 어셈블리가 해상도에 사용됩니다.

2. 이전 단계가 실패하면 짧은 이름(및 공개 키 토큰이 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>있는 경우)을 사용하여 을 호출합니다.

##### <a name="assembly-references-by-baml-types"></a>BAML 형식별 어셈블리 참조:

BAML 프로덕션에 사용되는 형식에 대한 어셈블리 참조는 빌드 작업의 출력으로 항상 정규화됩니다.

01. WPF XAML 스키마 컨텍스트는 WPF <xref:System.AppDomain> 응용 프로그램을 통해 변경되어 가장 최근에 로드된 어셈블리부터 시작하여 이름의 모든 측면과 일치하는 이미 로드된 어셈블리를 찾습니다. 일치하는 검색어가 발견되면 해당 어셈블리가 해상도에 사용됩니다.

02. 그렇지 않으면 다음 기술 중 하나가 어셈블리를 로드하는 데 사용됩니다.

    - 정규화된 이름을 호출합니다. <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>
  
    - 짧은 이름 + 공개 키 토큰 조합이 BAML에서 로드된 어셈블리와 일치하는 경우 해당 어셈블리를 사용합니다.

    - 짧은 이름 + 공개 키 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>토큰을 사용하여 을 호출합니다.

## <a name="see-also"></a>참조

- [XAML 노드 스트림 구조 및 개념 이해](understanding-xaml-node-stream-structures-and-concepts.md)
