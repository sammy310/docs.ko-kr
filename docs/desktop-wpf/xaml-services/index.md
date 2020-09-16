---
title: XAML 서비스
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: 313cb46813d8c0cfa9f1f317a65d2e21298ecff9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90552853"
---
# <a name="xaml-services"></a>XAML 서비스

이 항목에서는 .NET XAML 서비스라는 기술 세트의 기능을 설명합니다. 설명하는 대다수 서비스 및 API는 `System.Xaml` 어셈블리에 있습니다. 서비스로는 판독기와 작성기, 스키마 클래스 및 스키마 지원, 팩터리, 클래스 특성 설정, XAML 언어 내장 지원 및 기타 XAML 언어 기능 등이 있습니다.

## <a name="about-this-documentation"></a>설명서 정보

.NET XAML 서비스의 개념 설명서는 이전에 XAML 언어를 사용한 적이 있고 이 언어가 WPF(Windows Presentation Foundation) 또는 Windows Workflow Foundation과 같은 특정 프레임워크나 <xref:Microsoft.Build.Framework.XamlTypes>의 빌드 사용자 지정 기능과 같은 특정 기술 기능 영역에 적용되는 방법을 알고 있다고 가정합니다. 이 설명서에서는 XAML의 기본 사항을 태그 언어, XAML 구문 용어 또는 기타 소개 자료로 기술하지 않습니다. 대신, 이 설명서는 System.Xaml 어셈블리 라이브러리에서 사용하도록 설정된 .NET XAML 서비스의 사용에 특별히 초점을 맞춥니다. 이 API의 대부분은 XAML 언어 통합 및 확장성 시나리오에서 사용됩니다. 다음과 같은 시나리오가 포함될 수 있습니다.

- 기본 XAML 판독기 또는 XAML 작성기의 기능 확장(XAML 노드 스트림 직접 처리, 고유한 XAML 판독기 또는 XAML 작성기 파생)

- 특정 프레임워크 종속성이 없는 XAML 사용 가능 사용자 지정 형식 정의 및 .NET XAML 서비스에 XAML 형식 시스템 특성을 전달하도록 형식의 특성 정의

- XAML 판독기 또는 XAML 작성기를 XAML 태그 소스용 비주얼 디자이너 또는 대화형 편집기와 같은 애플리케이션의 구성 요소로 호스트

- XAML 값 변환기 작성(태그 확장, 사용자 지정 형식용 형식 변환기)

- 사용자 지정 XAML 스키마 컨텍스트 정의(지원 형식 소스용 대체 어셈블리 로딩 기술 사용, 항상 어셈블리를 반영하는 대신 알려진 형식 조회 기술 사용, CLR(공용 언어 런타임) `AppDomain` 및 관련 보안 모델을 사용하지 않는 로드된 어셈블리 개념 사용)

- 기본 XAML 형식 시스템 확장

- `Lookup` 또는 `Invoker` 기술을 사용하여 XAML 형식 시스템 및 형식 지원을 평가하는 방법에 적용

언어로서 XAML의 소개 자료를 찾는 경우에는 [XAML 개요(WPF)](../fundamentals/xaml.md)를 사용해 볼 수 있습니다. 이 항목에서는 WPF(Windows Presentation Foundation)와 XAML 태그 및 XAML 언어 기능을 둘 다 처음 사용하는 대상 그룹을 위해 XAML을 설명합니다. 또 다른 유용한 문서는 [XAML 언어 사양](/previous-versions/msp-n-p/ff650760(v=pandp.10))의 소개 자료입니다.

## <a name="net-xaml-services-and-systemxaml-in-the-net-architecture"></a>.Net 아키텍처의 .NET XAML 서비스 및 `System.Xaml`

.NET XAML 서비스 및 `System.Xaml` 어셈블리는 XAML 언어 기능을 지원하는 데 필요한 많은 항목을 정의합니다. 여기에는 XAML 판독기 및 XAML 작성기의 기본 클래스가 포함됩니다. 프레임워크 관련 XAML 구현에 없었고 .NET XAML 서비스에 추가된 가장 중요한 기능은 XAML의 형식 시스템 표현입니다. 형식 시스템 표현은 프레임워크의 특정 기능에서 종속성을 사용하지 않고 XAML 기능을 중심으로 하는 개체 지향 방식으로 XAML을 제공합니다.

XAML 형식 시스템은 XAML 원본의 태그 형식 또는 런타임 세부 정보에 따라 제한되지 않으며 특정 지원 형식 시스템에 따라 제한되지 않습니다. XAML 형식 시스템은 형식, 멤버, XAML 스키마 컨텍스트, XML 수준 개념 및 기타 XAML 언어 개념이나 XAML 내장에 대한 개체 표현을 포함합니다. XAML 형식 시스템을 사용하거나 확장하면 XAML 판독기 및 XAML 작성기와 같은 클래스에서 파생시킬 수 있으며 XAML을 사용하거나 내보내는 프레임워크, 기술 또는 애플리케이션에서 사용 가능한 특정 기능으로 XAML 표현의 기능을 확장할 수 있습니다. XAML 스키마 컨텍스트의 개념은 XAML 개체 작성기 구현, 컨텍스트에서 어셈블리 정보를 통해 전달되는 기술의 지원 형식 시스템 및 XAML 노드 소스의 조합에서 실용적인 개체 그래프 작성 작업을 가능하게 합니다. XAML 스키마 개념에 관한 자세한 내용은 [기본 XAML 스키마 컨텍스트 및 WPF XAML 스키마 컨텍스트](default-schema-context.md)를 참조하세요.

## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>XAML 노드 스트림, XAML 판독기 및 XAML 작성기

XAML 언어와 XAML을 언어로 사용하는 특정 기술 간 관계에서 .NET XAML 서비스의 역할을 이해하려면 XAML 노드 스트림의 개념을 이해하고 이 개념이 API와 용어를 어떻게 형성하는지 알아보는 것이 좋습니다. XAML 노드 스트림은 XAML 언어 표현과 XAML이 표현하고 정의하는 개체 그래프 간 개념적 매개체입니다.

- XAML 판독기는 특정 형식으로 XAML을 처리하고 XAML 노드 스트림을 생성하는 엔터티입니다. API에서 XAML 판독기는 <xref:System.Xaml.XamlReader> 기본 클래스로 표현됩니다.

- XAML 작성기는 XAML 노드 스트림을 처리하고 다른 항목을 생성하는 엔터티입니다. API에서 XAML 작성기는 <xref:System.Xaml.XamlWriter> 기본 클래스로 표현됩니다.

  XAML과 관련된 가장 일반적인 두 가지 시나리오는 XAML을 로드하여 개체 그래프를 인스턴스화하는 경우와 애플리케이션 또는 도구에서 개체 그래프를 저장하고 XAML 표현(일반적으로 텍스트 파일로 저장되는 태그 형식)을 생성하는 경우입니다. XAML을 로드하고 개체 그래프를 만드는 것을 이 설명서에서는 로드 경로라고 합니다. 기존 개체 그래프를 XAML로 저장하거나 직렬화하는 것을 이 설명서에서는 저장 경로라고 합니다.

  가장 일반적인 형식의 로드 경로는 다음과 같이 설명할 수 있습니다.

- UTF 인코딩된 XML 형식이며 텍스트 파일로 저장된 XAML 표현으로 시작합니다.

- XAML을 <xref:System.Xaml.XamlXmlReader>로 로드합니다. <xref:System.Xaml.XamlXmlReader>는 <xref:System.Xaml.XamlReader> 서브클래스입니다.

- 결과는 XAML 노드 스트림입니다. <xref:System.Xaml.XamlXmlReader> / <xref:System.Xaml.XamlReader> API를 사용하여 XAML 노드 스트림의 개별 노드에 액세스할 수 있습니다. 여기에서 가장 일반적인 작업은 XAML 노드 스트림을 통해 진행하면서 “현재 레코드” 메타포를 사용하여 각 노드를 처리하는 것입니다.

- XAML 노드 스트림에서 <xref:System.Xaml.XamlObjectWriter> API로 결과 노드를 전달합니다. <xref:System.Xaml.XamlObjectWriter>는 <xref:System.Xaml.XamlWriter> 서브클래스입니다.

- <xref:System.Xaml.XamlObjectWriter>는 소스 XAML 노드 스트림을 통해 진행함에 따라 한 번에 한 개체씩 개체 그래프를 작성합니다. 개체 쓰기는 지원 형식 시스템 및 프레임워크의 어셈블리와 형식에 액세스할 수 있는 구현 및 XAML 스키마 컨텍스트의 지원을 통해 수행됩니다.

- XAML 노드 스트림의 끝에서 <xref:System.Xaml.XamlObjectWriter.Result%2A>를 호출하여 개체 그래프의 루트 개체를 가져옵니다.

  가장 일반적인 형식의 저장 경로는 다음과 같이 설명할 수 있습니다.

- 전체 애플리케이션 런타임, 런타임의 UI 콘텐츠와 상태 또는 런타임에 전체 애플리케이션 개체 표현의 더 작은 세그먼트에 관한 개체 그래프로 시작합니다.

- 애플리케이션 루트 또는 문서 루트와 같은 논리적 시작 개체에서 <xref:System.Xaml.XamlObjectReader>로 개체를 로드합니다. <xref:System.Xaml.XamlObjectReader>는 <xref:System.Xaml.XamlReader> 서브클래스입니다.

- 결과는 XAML 노드 스트림입니다. <xref:System.Xaml.XamlObjectReader> 및 <xref:System.Xaml.XamlReader> API를 사용하여 XAML 노드 스트림의 개별 노드에 액세스할 수 있습니다. 여기에서 가장 일반적인 작업은 XAML 노드 스트림을 통해 진행하면서 “현재 레코드” 메타포를 사용하여 각 노드를 처리하는 것입니다.

- XAML 노드 스트림에서 <xref:System.Xaml.XamlXmlWriter> API로 결과 노드를 전달합니다. <xref:System.Xaml.XamlXmlWriter>는 <xref:System.Xaml.XamlWriter> 서브클래스입니다.

- <xref:System.Xaml.XamlXmlWriter>는 XML UTF 인코딩으로 XAML을 작성합니다. 이를 텍스트 파일, 스트림 또는 다른 형식으로 저장할 수 있습니다.

- <xref:System.Xaml.XamlXmlWriter.Flush%2A>를 호출하여 최종 출력을 얻습니다.

XAML 노드 스트림 개념에 관한 자세한 내용은 [XAML 노드 스트림 구조 및 개념 이해](understanding-xaml-node-stream-structures-and-concepts.md)를 참조하세요.

### <a name="the-xamlservices-class"></a>XamlServices 클래스

항상 XAML 노드 스트림을 처리해야 하는 것은 아닙니다. 기본 로드 경로 또는 기본 저장 경로를 원하는 경우 <xref:System.Xaml.XamlServices> 클래스에서 API를 사용할 수 있습니다.

- <xref:System.Xaml.XamlServices.Load%2A>의 다양한 시그니처는 로드 경로를 구현합니다. 파일 또는 스트림을 로드하거나, 판독기 API와 함께 로드하여 XAML 입력을 래핑하는 <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader>또는 <xref:System.Xaml.XamlReader>를 로드할 수 있습니다.

- <xref:System.Xaml.XamlServices.Save%2A>의 다양한 시그니처는 개체 그래프를 저장하고 스트림, 파일 또는 <xref:System.Xml.XmlWriter>/<xref:System.IO.TextWriter> 인스턴스로 출력을 생성합니다.

- <xref:System.Xaml.XamlServices.Transform%2A>은 로드 경로 및 저장 경로를 단일 작업으로 연결하여 XAML을 변환합니다. <xref:System.Xaml.XamlReader> 및 <xref:System.Xaml.XamlWriter>에 다른 스키마 컨텍스트 또는 다른 지원 형식 시스템을 사용할 수 있으며, 이는 결과 XAML이 변환되는 방식에 영향을 줍니다.

<xref:System.Xaml.XamlServices>를 사용하는 방법에 관한 자세한 내용은 [XAMLServices 클래스 및 기본 XAML 읽기 또는 쓰기](basic-reading-writing.md)를 참조하세요.

## <a name="xaml-type-system"></a>XAML 형식 시스템

XAML 형식 시스템은 XAML 노드 스트림의 지정된 개별 노드를 사용하는 데 필요한 API를 제공합니다.

<xref:System.Xaml.XamlType>은 개체의 표현이며 시작 개체 노드와 끝 개체 노드 사이에서 처리하는 항목입니다.

<xref:System.Xaml.XamlMember>는 개체 멤버의 표현이며 시작 멤버 노드와 끝 멤버 노드 사이에서 처리하는 항목입니다.

<xref:System.Xaml.XamlType.GetAllMembers%2A>, <xref:System.Xaml.XamlType.GetMember%2A> 및 <xref:System.Xaml.XamlMember.DeclaringType%2A>과 같은 API는 <xref:System.Xaml.XamlType>와 <xref:System.Xaml.XamlMember> 간 관계를 보고합니다.

.NET XAML 서비스에서 구현되는 XAML 형식 시스템의 기본 동작은 CLR(공용 언어 런타임) 및 어셈블리에서 리플렉션을 통한 CLR 형식의 정적 분석을 기반으로 합니다. 따라서 특정 CLR 형식의 경우 XAML 형식 시스템의 기본 구현은 해당 형식 및 해당 멤버의 XAML 스키마를 공개하고 XAML 형식 시스템 측면에서 보고할 수 있습니다. 기본 XAML 형식 시스템에서 형식 할당 가능성의 개념은 CLR 상속에 매핑되고 인스턴스, 값 형식 등의 개념은 CLR의 지원 동작 및 기능에 매핑됩니다.

## <a name="reference-for-xaml-language-features"></a>XAML 언어 기능의 참조

XAML을 지원하기 위해 .NET XAML 서비스는 XAML 언어 XAML 네임스페이스에 대해 정의된 대로 XAML 언어 개념의 특정 구현을 제공합니다. 이 내용은 특정 참조 페이지로 문서화됩니다. 언어 기능은 .NET XAML 서비스에서 정의된 XAML 판독기 또는 XAML 작성기에서 이 언어 기능이 처리될 때 동작하는 방식의 관점에서 문서화됩니다. 자세한 내용은 [XAML 네임스페이스(x:) 언어 기능](namespace-language-features.md)을 참조하세요.
