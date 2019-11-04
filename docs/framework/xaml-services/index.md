---
title: XAML 서비스
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: a99b9f3cb8c008f72eaac7ee1b8790d63c547a8d
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453960"
---
# <a name="xaml-services"></a>XAML 서비스
이 항목에서는 .NET Framework XAML 서비스 라고 하는 기술 집합의 기능에 대해 설명 합니다. 설명 된 대부분의 서비스 및 Api는 .NET core 어셈블리의 .NET Framework 4 집합으로 도입 된 어셈블리인 어셈블리 System.xaml에 있습니다. 서비스에는 판독기와 작성기, 스키마 클래스 및 스키마 지원, 팩터리, 클래스의 특성, XAML 언어 내장 지원 및 기타 XAML 언어 기능이 포함 되어 있습니다.  
  
## <a name="about-this-documentation"></a>이 설명서 정보  
 .NET Framework XAML 서비스에 대 한 개념 설명서에서는 이전에 XAML 언어를 사용 하는 경험이 있고 특정 프레임 워크 (예: [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 또는 Windows Workflow Foundation 또는 특정 기술 기능 영역에 적용 될 수 있다고 가정 합니다. 예를 들어 <xref:Microsoft.Build.Framework.XamlTypes>의 빌드 사용자 지정 기능입니다. 이 설명서에서는 XAML의 기본 사항을 태그 언어, XAML 구문 용어 또는 기타 소개 자료로 설명 하지 않습니다. 대신이 설명서에서는 system.xaml 어셈블리 라이브러리에서 사용 되는 .NET Framework XAML 서비스를 사용 하는 방법을 집중적으로 설명 합니다. 이러한 Api의 대부분은 XAML 언어 통합 및 확장성 시나리오를 위한 것입니다. 여기에는 다음이 포함 될 수 있습니다.  
  
- 기본 XAML 판독기 또는 XAML 작성기의 기능 확장 (XAML 노드 스트림을 직접 처리, 고유한 XAML 판독기 또는 XAML 작성기 파생).  
  
- 특정 프레임 워크 종속성이 없는 XAML 사용 가능 사용자 지정 형식을 정의 하 고 xaml 형식 시스템 특성을 .NET Framework XAML 서비스에 전달 하도록 형식의 특성을 지정 합니다.  
  
- Xaml 판독기 또는 xaml 작성기를 비주얼 디자이너나 XAML 태그 소스에 대 한 대화형 편집기와 같은 응용 프로그램의 구성 요소로 호스팅  
  
- XAML 값 변환기 작성 (태그 확장, 사용자 지정 형식에 대 한 형식 변환기).  
  
- 사용자 지정 XAML 스키마 컨텍스트 정의 (형식 소스를 지원 하기 위한 대체 어셈블리 로드 기법 사용, 어셈블리를 항상 반영 하는 대신 알려진 형식 조회 기법 사용, CLR `AppDomain`를 사용 하지 않는 로드 된 어셈블리 개념 사용 및 해당 연결 된 보안 모델).  
  
- 기본 XAML 형식 시스템 확장  
  
- `Lookup` 또는 `Invoker` 기술을 사용 하 여 XAML 형식 시스템에 영향을 주거나 형식 백을 평가 하는 방법을 설명 합니다.  
  
 XAML에 대 한 소개 자료를 언어로 찾으려는 경우 [Xaml 개요 (WPF)](../../desktop-wpf/fundamentals/xaml.md)를 사용해 볼 수 있습니다. 이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]와 XAML 태그 및 XAML 언어 기능을 모두 사용 하는 것이 새로운 대상 사용자를 위한 XAML에 대해 설명 합니다. 또 다른 유용한 문서는 [XAML 언어 사양의](https://go.microsoft.com/fwlink/?LinkId=114525)소개 자료입니다.  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>.NET 아키텍처의 XAML 서비스 및 system.xaml .NET Framework  
 이전 버전의 Microsoft .NET Framework에서는 XAML 언어 기능에 대 한 지원이 Microsoft .NET Framework ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Windows Workflow Foundation 및 Windows Communication Foundation)를 기반으로 하는 프레임 워크에 의해 구현 되었습니다. 따라서 사용 중인 특정 프레임 워크에 따라 동작 및 API가 다양 하 게 사용 됩니다. 여기에는 XAML 파서 및 해당 개체 그래프 생성 메커니즘, XAML 언어 내장 함수, serialization 지원 등이 포함 됩니다.  
  
 .NET Framework 4에서 .NET Framework XAML 서비스와 system.xaml 어셈블리는 XAML 언어 기능을 지 원하는 데 필요한 많은 항목을 정의 합니다. 여기에는 XAML 판독기 및 XAML 작성기에 대 한 기본 클래스가 포함 됩니다. 프레임 워크 관련 XAML 구현에 없는 .NET Framework XAML 서비스에 추가 되는 가장 중요 한 기능은 XAML의 형식 시스템 표현입니다. 형식 시스템 표현은 프레임 워크의 특정 기능에 대 한 종속성을 취하지 않고 XAML 기능을 중심으로 하는 개체 지향 방식으로 XAML을 제공 합니다.  
  
 XAML 형식 시스템은 XAML 원본의 태그 형식 또는 런타임 세부 사항에 의해 제한 되지 않습니다. 특정 지원 유형 시스템에 의해 제한 되지 않습니다. XAML 형식 시스템은 형식, 멤버, XAML 스키마 컨텍스트, XML 수준 개념 및 기타 XAML 언어 개념 또는 XAML 내장 함수에 대 한 개체 표현을 포함 합니다. Xaml 형식 시스템을 사용 하거나 확장 하면 xaml 판독기와 XAML 작성기와 같은 클래스에서 파생 될 수 있으며, XAML 표현의 기능을 프레임 워크, 기술 또는 또는를 사용 하는 응용 프로그램에서 사용 하는 특정 기능으로 확장할 수 있습니다. XAML을 내보냅니다. XAML 스키마 컨텍스트의 개념은 XAML 개체 작성기 구현, 기술의 어셈블리 정보를 통해 전달 되는 기술의 지원 형식 시스템 및 XAML 노드를 조합 하 여 실용적인 개체 그래프 쓰기 작업을 수행할 수 있도록 합니다. 원본. XAML 스키마 개념에 대 한 자세한 내용은을 (를). [기본 Xaml 스키마 컨텍스트 및 WPF Xaml 스키마 컨텍스트를](default-xaml-schema-context-and-wpf-xaml-schema-context.md)참조 하세요.  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>Xaml 노드 스트림, XAML 판독기 및 XAML 작성기  
 Xaml 서비스와 xaml을 언어로 사용 하는 특정 기술 간의 관계에서 xaml 서비스를 사용 하 .NET Framework는 역할을 이해 하려면 XAML 노드 스트림의 개념과 해당 개념이 API를 어떻게 모양 지정 하는지 이해 하는 것이 좋습니다. 기술. Xaml 노드 스트림은 xaml 언어 표현과 XAML이 나타내거나 정의 하는 개체 그래프 사이의 개념적 중간입니다.  
  
- XAML 판독기는 특정 형식으로 XAML을 처리 하 고 XAML 노드 스트림을 생성 하는 엔터티입니다. API에서 XAML 판독기는 <xref:System.Xaml.XamlReader>기본 클래스로 표시 됩니다.  
  
- XAML 작성기는 XAML 노드 스트림을 처리 하 고 다른 항목을 생성 하는 엔터티입니다. API에서 XAML 작성기는 <xref:System.Xaml.XamlWriter>기본 클래스로 표시 됩니다.  
  
 XAML과 관련 된 가장 일반적인 두 가지 시나리오는 XAML을 로드 하 여 개체 그래프를 인스턴스화하고, 응용 프로그램 또는 도구에서 개체 그래프를 저장 하 고, XAML 표현 (일반적으로 태그 양식에서 텍스트 파일로 저장 됨)을 생성 합니다. 이 설명서에서는 XAML을 로드 하 고 개체 그래프를 만드는 것을 주로 로드 경로 라고 합니다. 이 설명서에서는 기존 개체 그래프를 XAML로 저장 하거나 serialize 하는 것을 일반적으로 저장 경로 라고 합니다.  
  
 가장 일반적인 형식의 로드 경로는 다음과 같이 설명할 수 있습니다.  
  
- UTF 인코딩 XML 형식의 XAML 표현으로 시작 하 여 텍스트 파일로 저장 합니다.  
  
- <xref:System.Xaml.XamlXmlReader>로 XAML을 로드 합니다. <xref:System.Xaml.XamlXmlReader>은 <xref:System.Xaml.XamlReader> 하위 클래스입니다.  
  
- 결과는 XAML 노드 스트림입니다. <xref:System.Xaml.XamlXmlReader> / <xref:System.Xaml.XamlReader> API를 사용 하 여 XAML 노드 스트림의 개별 노드에 액세스할 수 있습니다. 여기에서 가장 일반적인 작업은 XAML 노드 스트림을 진행 하면서 "현재 레코드" 메타포를 사용 하 여 각 노드를 처리 하는 것입니다.  
  
- XAML 노드 스트림에서 결과 노드를 <xref:System.Xaml.XamlObjectWriter> API에 전달 합니다. <xref:System.Xaml.XamlObjectWriter>은 <xref:System.Xaml.XamlWriter> 하위 클래스입니다.  
  
- <xref:System.Xaml.XamlObjectWriter>는 소스 XAML 노드 스트림의 진행에 따라 개체 그래프를 한 번에 하나씩 씁니다. 이 작업은 지원 형식 시스템 및 프레임 워크의 어셈블리와 형식에 액세스할 수 있는 XAML 스키마 컨텍스트 및 구현에서 지원 됩니다.  
  
- XAML 노드 스트림의 끝에서 <xref:System.Xaml.XamlObjectWriter.Result%2A>를 호출 하 여 개체 그래프의 루트 개체를 가져옵니다.  
  
 가장 일반적인 형식의 저장 경로는 다음과 같이 설명할 수 있습니다.  
  
- 전체 응용 프로그램 실행 시간, 실행 시간의 UI 콘텐츠 및 상태 또는 런타임에 전체 응용 프로그램 개체 표현의 작은 세그먼트의 개체 그래프로 시작 합니다.  
  
- 응용 프로그램 루트 또는 문서 루트와 같은 논리적 시작 개체에서 개체를 <xref:System.Xaml.XamlObjectReader>으로 로드 합니다. <xref:System.Xaml.XamlObjectReader>은 <xref:System.Xaml.XamlReader> 하위 클래스입니다.  
  
- 결과는 XAML 노드 스트림입니다. <xref:System.Xaml.XamlObjectReader> 및 <xref:System.Xaml.XamlReader> API를 사용 하 여 XAML 노드 스트림의 개별 노드에 액세스할 수 있습니다. 여기에서 가장 일반적인 작업은 XAML 노드 스트림을 진행 하면서 "현재 레코드" 메타포를 사용 하 여 각 노드를 처리 하는 것입니다.  
  
- XAML 노드 스트림에서 결과 노드를 <xref:System.Xaml.XamlXmlWriter> API에 전달 합니다. <xref:System.Xaml.XamlXmlWriter>은 <xref:System.Xaml.XamlWriter> 하위 클래스입니다.  
  
- <xref:System.Xaml.XamlXmlWriter>는 XML UTF 인코딩으로 XAML을 작성 합니다. 이를 텍스트 파일, 스트림 또는 다른 형식으로 저장할 수 있습니다.  
  
- <xref:System.Xaml.XamlXmlWriter.Flush%2A>를 호출 하 여 최종 출력을 가져옵니다.  
  
 XAML 노드 스트림 개념에 대 한 자세한 내용은 [Xaml 노드 스트림 구조 및 개념 이해](understanding-xaml-node-stream-structures-and-concepts.md)를 참조 하세요.  
  
### <a name="the-xamlservices-class"></a>XamlServices 클래스  
 XAML 노드 스트림을 반드시 처리 해야 하는 것은 아닙니다. 기본 로드 경로 또는 기본 저장 경로를 원하는 경우 <xref:System.Xaml.XamlServices> 클래스에서 Api를 사용할 수 있습니다.  
  
- <xref:System.Xaml.XamlServices.Load%2A>의 다양 한 시그니처는 로드 경로를 구현 합니다. 파일 또는 스트림을 로드 하거나, 판독기의 Api로 로드 하 여 XAML 입력을 래핑하는 <xref:System.Xml.XmlReader><xref:System.IO.TextReader> 또는 <xref:System.Xaml.XamlReader>를 로드할 수 있습니다.  
  
- <xref:System.Xaml.XamlServices.Save%2A>의 다양 한 시그니처는 개체 그래프를 저장 하 고 출력을 스트림, 파일 또는 <xref:System.Xml.XmlWriter>/<xref:System.IO.TextWriter> 인스턴스로 생성 합니다.  
  
- <xref:System.Xaml.XamlServices.Transform%2A>는 로드 경로와 저장 경로를 단일 작업으로 연결 하 여 XAML을 변환 합니다. 다른 스키마 컨텍스트 또는 다른 지원 형식 시스템을 <xref:System.Xaml.XamlReader> 및 <xref:System.Xaml.XamlWriter>에 사용할 수 있으며,이는 결과 XAML이 변환 되는 방법에 영향을 줍니다.  
  
 <xref:System.Xaml.XamlServices>를 사용 하는 방법에 대 한 자세한 내용은 [XAMLServices 클래스 및 기본 XAML 읽기 또는 쓰기](xamlservices-class-and-basic-xaml-reading-or-writing.md)를 참조 하세요.  
  
## <a name="xaml-type-system"></a>XAML 형식 시스템  
 XAML 형식 시스템은 XAML 노드 스트림의 지정 된 개별 노드를 사용 하는 데 필요한 Api를 제공 합니다.  
  
 <xref:System.Xaml.XamlType>는 개체에 대 한 표현입니다. 시작 개체 노드와 end 개체 노드 사이에서 처리 하는 작업입니다.  
  
 <xref:System.Xaml.XamlMember>은 개체의 멤버에 대 한 표현입니다. 시작 멤버 노드와 end 멤버 노드 사이에서 처리 하는 것입니다.  
  
 <xref:System.Xaml.XamlType.GetAllMembers%2A>, <xref:System.Xaml.XamlType.GetMember%2A> 및 <xref:System.Xaml.XamlMember.DeclaringType%2A>와 같은 Api는 <xref:System.Xaml.XamlType>와 <xref:System.Xaml.XamlMember>간의 관계를 보고 합니다.  
  
 .NET Framework XAML 서비스에 의해 구현 되는 XAML 형식 시스템의 기본 동작은 리플렉션을 사용 하 여 CLR (공용 언어 런타임) 및 어셈블리의 CLR 형식에 대 한 정적 분석을 기반으로 합니다. 따라서 특정 CLR 형식에 대해 XAML 형식 시스템의 기본 구현에서는 해당 형식 및 해당 멤버의 XAML 스키마를 노출 하 고 XAML 형식 시스템의 용어로 보고할 수 있습니다. 기본 XAML 형식 시스템에서 형식 할당 기능의 개념은 CLR 상속에 매핑되고 인스턴스, 값 형식 등의 개념은 CLR의 지원 동작 및 기능에도 매핑됩니다.  
  
## <a name="reference-for-xaml-language-features"></a>XAML 언어 기능에 대 한 참조  
 Xaml을 지원 하기 위해 .NET Framework xaml 서비스는 xaml 언어 XAML 네임 스페이스에 대해 정의 된 XAML 언어 개념의 특정 구현을 제공 합니다. 이러한 문서는 특정 참조 페이지로 문서화 되어 있습니다. 언어 기능은 .NET Framework XAML 서비스에 의해 정의 되는 xaml 판독기 또는 XAML 작성기에서 처리 될 때 이러한 언어 기능의 관점에서 설명 합니다. 자세한 내용은 [XAML Namespace (x:) Language Features](xaml-namespace-x-language-features.md)을 참조하세요.
