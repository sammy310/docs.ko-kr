---
title: XAMLServices 클래스 및 기본 XAML 읽기 또는 쓰기
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], XamlServices class
- XamlServices class [XAML Services], how to use
ms.assetid: 6ac27fad-3687-4d7a-add1-3e90675fdfde
ms.openlocfilehash: 264a8c4abcf9a7efceb7c7accd786495d35476e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "81433093"
---
# <a name="xamlservices-class-and-basic-xaml-reading-or-writing"></a>XAMLServices 클래스 및 기본 XAML 읽기 또는 쓰기

<xref:System.Xaml.XamlServices>는 .NET에서 제공하는 클래스로, XAML 노드 스트림또는 해당 노드에서 얻은 XAML 형식 시스템 정보에 대한 특정 액세스가 필요하지 않은 XAML 시나리오를 해결하는 데 사용할 수 있습니다. <xref:System.Xaml.XamlServices>API는 다음과 같이 `Load` 요약할 `Parse` 수 있습니다: 또는 XAML 로드 경로를 지원하거나, `Save` XAML 저장 경로를 지원하고, 로드 경로를 조인하고 경로를 저장하는 기술을 제공하기 `Transform` 위해. `Transform` 은 XAML 스키마를 다른 스키마로 변경하는 데 사용할 수 있습니다. 이 항목에서는 이러한 각 API 분류를 요약하고 특정 메서드 오버로드 간의 차이점을 설명합니다.

## <a name="load"></a>로드

<xref:System.Xaml.XamlServices.Load%2A> 의 다양한 오버로드가 로드 경로에 대한 완전한 논리를 구현합니다. 로드 경로는 일부 형식의 XAML을 사용하여 XAML 노드 스트림을 출력합니다. 이 로드 경로 중 대부분은 인코딩된 XML 텍스트 파일 형태로 XAML을 사용합니다. 그러나 일반 스트림을 로드하거나 기존에 다른 <xref:System.Xaml.XamlReader> 구현에 포함되어 미리 로드된 XAML 소스를 로드할 수도 있습니다.

대부분의 시나리오에서 가장 간단한 오버로드는 <xref:System.Xaml.XamlServices.Load%28System.String%29>입니다. 이 오버로드에는 로드할 XAML이 포함된 텍스트 파일의 이름인 `fileName` 매개 변수가 있습니다. 이는 이전에 로컬 컴퓨터에 상태나 데이터를 직렬화했던 완전 신뢰 애플리케이션과 같은 애플리케이션 시나리오에 적합합니다. 또한 애플리케이션 모델을 정의할 때 애플리케이션 동작, 시작 UI 또는 XAML을 사용하는 다른 프레임워크 정의 기능 등을 정의하는 표준 파일 중 하나를 로드하는 프레임워크에도 유용합니다.

<xref:System.Xaml.XamlServices.Load%28System.IO.Stream%29> 에 비슷한 시나리오가 있습니다. 이 오버로드는 로드할 파일을 사용자가 선택하게 하는 경우에 유용할 수 있습니다. <xref:System.IO.Stream> 은 파일 시스템에 액세스할 수 있는 다른 <xref:System.IO> API에서 종종 나오는 출력이기 때문입니다. 또는 비동기 다운로드를 통해서나 스트림을 제공하는 다른 네트워크 기술을 통해 XAML 소스에 액세스할 수도 있습니다. (스트림이나 사용자가 선택한 소스에서 로드하면 보안상 문제가 있을 수 있습니다. 자세한 내용은 [XAML Security Considerations](security-considerations.md)을 참조하세요.

<xref:System.Xaml.XamlServices.Load%28System.IO.TextReader%29><xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29> 이전 버전의 .NET 형식의 독자에 의존하는 오버로드입니다. 이러한 오버로드를 사용하려면 이미 판독기 인스턴스를 `Create` 만들고 해당 API를 사용하여 관련 양식(텍스트 또는 XML)으로 XAML을 로드해야 합니다. 이미 다른 판독기에서 레코드 포인터를 이동했거나 다른 작업을 수행한 경우에는 이 과정이 중요하지 않습니다. <xref:System.Xaml.XamlServices.Load%2A> 에서 구현된 로드 경로 논리는 항상 루트에서 전체 XAML 입력을 처리합니다. 다음 시나리오는 이러한 오버로드의 사용을 보증할 수 있습니다.

- 기존 XML 특정 텍스트 편집기에서 간단한 XAML 편집 기능을 제공하는 디자인 화면을 사용하는 경우

- 전용 판독기를 사용하여 파일이나 스트림을 여는 핵심 <xref:System.IO> 시나리오의 변형. 논리가 XAML로 로드하기 전에 콘텐츠에 대해 기본적인 검사나 처리를 수행합니다.

파일 또는 스트림을 로드하거나 <xref:System.Xml.XmlReader>리더의 API로 <xref:System.IO.TextReader>로드하여 XAML 입력을 래핑하는 를 로드하거나 <xref:System.Xaml.XamlReader> XAML 입력을 래핑할 수 있습니다.

내부적으로, 앞의 각 오버로드는 궁극적으로 <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29>이고 전달된 <xref:System.Xml.XmlReader> 는 새 <xref:System.Xaml.XamlXmlReader>를 만드는 데 사용됩니다.

더 높은 수준의 시나리오를 가능하게 하는 `Load` 서명은 <xref:System.Xaml.XamlServices.Load%28System.Xaml.XamlReader%29>입니다. 다음 중 하나의 경우에 이 서명을 사용할 수 있습니다.

- 을 직접 <xref:System.Xaml.XamlReader>구현했습니다.

- 기본 설정과 다른 <xref:System.Xaml.XamlReader> 설정을 지정해야 하는 경우

기본이 아닌 설정의 예:

<xref:System.Xaml.XamlReaderSettings.AllowProtectedMembersOnRoot%2A>\
<xref:System.Xaml.XamlReaderSettings.BaseUri%2A>\
<xref:System.Xaml.XamlReaderSettings.IgnoreUidsOnPropertyElements%2A>\
<xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A>\
<xref:System.Xaml.XamlReaderSettings.ValuesMustBeString%2A>.

<xref:System.Xaml.XamlServices> 에 대한 기본 판독기는 <xref:System.Xaml.XamlXmlReader>입니다. 설정을 직접 <xref:System.Xaml.XamlXmlReader> 제공하는 경우 기본값이 <xref:System.Xaml.XamlXmlReaderSettings>아닌 설정 속성은 다음과 같습니다.

<xref:System.Xaml.XamlXmlReaderSettings.CloseInput%2A>\
<xref:System.Xaml.XamlXmlReaderSettings.SkipXmlCompatibilityProcessing%2A>\
<xref:System.Xaml.XamlXmlReaderSettings.XmlLang%2A>\
<xref:System.Xaml.XamlXmlReaderSettings.XmlSpacePreserve%2A>

## <a name="parse"></a>구문 분석

<xref:System.Xaml.XamlServices.Parse%2A> 은 XAML 입력에서 XAML 노드 스트림을 만드는 로드 경로 API이기 때문에 `Load` 와 비슷합니다. 그러나 이 경우 XAML 입력은 로드할 모든 XAML이 포함된 문자열로 직접 제공됩니다. <xref:System.Xaml.XamlServices.Parse%2A> 은 프레임워크 시나리오보다 애플리케이션 시나리오에 더 적합한 간편한 접근 방식입니다. 자세한 내용은 <xref:System.Xaml.XamlServices.Parse%2A>를 참조하세요. <xref:System.Xaml.XamlServices.Parse%2A>내부적으로 포함 <xref:System.Xaml.XamlServices.Load%28System.Xml.XmlReader%29> 된 호출입니다. <xref:System.IO.StringReader>

## <a name="save"></a>저장

저장 경로를 <xref:System.Xaml.XamlServices.Save%2A> 구현하는 다양한 오버로드입니다. 모든 <xref:System.Xaml.XamlServices.Save%2A> 메서드는 개체 그래프를 입력으로 사용하여 스트림, 파일 또는 <xref:System.Xml.XmlWriter>/<xref:System.IO.TextWriter> 인스턴스로 출력을 생성합니다.

입력 개체는 일부 개체 표현의 루트 개체여야 합니다. 비즈니스 개체의 단일 루트일 수 있으며 또는 UI 시나리오의 페이지, 디자인 도구의 작업 편집 화면 또는 시나리오에 적합한 기타 루트 개체 개념 등에 대한 개체 트리의 루트일 수 있습니다.

대부분의 시나리오에서 저장하는 개체 트리는 프레임워크/응용 프로그램 모델에 의해 구현된 다른 API와 함께 또는 다른 API와 함께 XAML을 로드한 원래 작업과 <xref:System.Xaml.XamlServices.Load%2A> 관련이 있습니다. 상태 변경, 애플리케이션이 사용자로부터 런타임 설정을 캡처한 변경, 애플리케이션이 XAML 디자인 화면이기 때문에 일어난 XAML 변경 등으로 인해 개체 트리에서 포착되는 차이점이 있을 수 있습니다. 변경이 있든 그렇지 않든 상관없이, 먼저 태그에서 XAML을 로드한 다음 이를 다시 저장하여 두 XAML 태그 형식을 비교하는 개념을 때때로 XAML 라운드트립 표현이라고 합니다.

태그 형식으로 설정된 복합 개체를 저장하고 직렬화할 때 문제는, 정보 손실 없는 완전한 표현과 사용자가 읽기 어려운 세부 표시 정도의 XAML 사이에 균형을 이루는 것입니다. 또한 XAML을 사용하는 다양한 고객들이 이런 균형을 찾을 방법에 대해 서로 다른 정의나 기대치를 가질 수 있습니다. <xref:System.Xaml.XamlServices.Save%2A> API는 이러한 균형에 대한 하나의 정의를 나타냅니다. <xref:System.Xaml.XamlServices.Save%2A> API는 사용 가능한 XAML 스키마 컨텍스트와 <xref:System.Xaml.XamlType>, <xref:System.Xaml.XamlMember>, 기타 XAML 내장/XAML 형식 시스템 개념의 기본 CLR 기반 특성을 사용하여 특정 XAML 노드 스트림 구문이 다시 태그에 저장될 때 최적화될 수 있는 위치를 결정할 수 있습니다. 예를 들어 <xref:System.Xaml.XamlServices> 저장 경로는 CLR 기반 기본 XAML 스키마 컨텍스트를 사용하여 개체에 대한 <xref:System.Xaml.XamlType> 을 확인할 수 있으며 <xref:System.Xaml.XamlType.ContentProperty%2A?displayProperty=nameWithType>를 확인한 후 개체의 XAML 콘텐츠에 속성을 쓸 때 속성 요소 태그를 생략할 수 있습니다.

<a name="transform"></a>
## <a name="transform"></a>변환

<xref:System.Xaml.XamlServices.Transform%2A> 는 로드 경로와 저장 경로를 단일 작업으로 연결하여 XAML을 변환합니다. <xref:System.Xaml.XamlReader> 및 <xref:System.Xaml.XamlWriter>에 대해 다른 스키마 컨텍스트 또는 다른 지원 형식 시스템을 사용할 수 있으며, 이에 따라 결과 XAML이 변환되는 방식이 달라집니다. 광범위한 변환 작업에 효율적입니다.

XAML 노드 스트림의 각 노드를 검사해야 하는 작업의 경우 일반적으로 <xref:System.Xaml.XamlServices.Transform%2A>를 사용하지 않습니다. 대신, 고유한 로드 경로-저장 경로 작업 계열을 정의하고 고유한 논리를 삽입해야 합니다. 경로 중 하나에서 고유한 노드 루프를 중심으로 XAML 판독기/XAML 기록기 쌍을 사용합니다. 예를 들어 <xref:System.Xaml.XamlXmlReader> 를 사용하여 초기 XAML을 로드하고 연속된 <xref:System.Xaml.XamlXmlReader.Read%2A> 호출을 사용하여 노드를 한 단계씩 실행합니다. XAML 노드 스트림 수준에서 작동하므로 이제 변환을 적용하도록 개별 노드(형식, 멤버, 다른 노드)를 조정하거나 노드를 그대로 둘 수 있습니다. 그런 다음, `Write` 의 관련 <xref:System.Xaml.XamlObjectWriter> API에 노드를 보내고 개체를 작성합니다. 자세한 내용은 [Understanding XAML Node Stream Structures and Concepts](understanding-xaml-node-stream-structures-and-concepts.md)을 참조하십시오.

## <a name="see-also"></a>참조

- <xref:System.Xaml.XamlObjectWriter>
- <xref:System.Xaml.XamlServices>
- [XAML 서비스](../../../api/index.md)
