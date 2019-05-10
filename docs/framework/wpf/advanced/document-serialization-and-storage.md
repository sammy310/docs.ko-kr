---
title: 문서 serialization 및 스토리지
ms.date: 03/30/2017
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
ms.openlocfilehash: 3f7db329d6400366d21dcc246be8aeb4d3528766
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663375"
---
# <a name="document-serialization-and-storage"></a>문서 serialization 및 스토리지
Microsoft.NET Framework는 만들고 고품질 문서를 표시 하기 위한 강력한 환경을 제공 합니다.  고정 문서 및 유동 문서를 고급 모두 지 원하는 향상 된 기능은 강력한 2D 함께 보기 컨트롤을 및 3D 그래픽 기능과.NET Framework 응용 프로그램의 품질과 사용자 환경 향상할 수 있습니다.  문서의 메모리 내 표현을 유연 하 게 관리할 수.NET Framework의 핵심 기능은 이며을 효율적으로 저장 하 고 데이터 저장소에서 문서를 로드할 수 있는 거의 모든 응용 프로그램의 필요 합니다.  내부 메모리 내 표현에서 외부 데이터 저장소로 문서를 변환하는 프로세스를 serialization이라고 합니다.  데이터 저장소를 읽고 원래 메모리 내 인스턴스를 다시 만드는 역프로세스는 deserialization이라고 합니다.  

<a name="AboutSerialization"></a>   
## <a name="about-document-serialization"></a>문서 Serialization 정보  
 원칙적으로 애플리케이션에서 문서를 메모리에서 serialize하고 다시 메모리로 deserialize하는 프로세스는 명확하게 수행됩니다.  애플리케이션에서는 serializer “write” 메서드를 호출하여 문서를 저장하는 한편, deserializer “read” 메서드는 데이터 저장소에 액세스하여 원래 인스턴스를 메모리에 다시 만듭니다.  serialize 및 deserialize 프로세스를 통해 원래 양식으로 문서를 다시 만드는 경우 데이터가 저장되는 특정 형식은 일반적으로 애플리케이션에서 문제가 되지 않습니다.  
  
 대부분의 애플리케이션에서는 사용자가 여러 다른 매체 또는 다른 형식으로 문서를 저장할 수 있도록 하는 여러 serialization 옵션을 제공합니다.  예를 들어, 애플리케이션에서 “다른 이름으로 저장” 옵션을 제공하여 문서를 디스크 파일, 데이터베이스 또는 웹 서비스에 저장하도록 지원할 수 있습니다.  마찬가지로 서로 다른 serializer마다 HTML, RTF, XML, XPS 등의 다른 형식 또는 타사 형식으로 문서를 저장할 수 있습니다.  애플리케이션에서는 serialization을 통해 각 특정 serializer의 구현 작업에서 저장소 매체의 세부 정보를 격리하는 인터페이스를 정의합니다.  .NET Framework 저장소 세부 정보를 캡슐화 하는 이점 외에도 <xref:System.Windows.Documents.Serialization> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 다른 몇 가지 중요 한 기능을 제공 합니다.  
  
### <a name="features-of-net-framework-30-document-serializers"></a>.NET Framework 3.0 문서 Serializer의 기능  
  
- 전반적인 문서 개체(논리적 트리 및 시각적 개체)에 직접 액세스하면 페이지를 매긴 콘텐츠, 2D/3D 요소, 이미지, 매체, 하이퍼링크, 주석 및 기타 지원 콘텐츠를 효율적으로 저장할 수 있습니다.  
  
- 동기 및 비동기 작업.  
  
- 다음과 같은 고급 기능이 포함된 플러그 인 serializer 지원:  
  
    - 모든.NET Framework 응용 프로그램에서 사용 하 여에 대 한 시스템 차원 액세스.  
  
    - 간단한 애플리케이션 플러그 인 검색 기능.  
  
    - 사용자 지정 타사 플러그 인의 간단한 배포, 설치 및 업데이트.  
  
    - 사용자 지정 런타임 설정 및 옵션에 맞는 사용자 인터페이스 지원.  
  
### <a name="xps-print-path"></a>XPS 인쇄 경로  
 Microsoft.NET Framework [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 인쇄 경로 인쇄 출력을 통해 문서를 작성 하기 위한 확장 가능한 메커니즘을 제공 합니다.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]는 문서 파일 형식으로 사용되며 [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]의 기본 인쇄 스풀 형식이기도 합니다.  중간 형식으로 변환하지 않아도 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 문서를 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 호환 프린터로 직접 보낼 수 있습니다.  인쇄 경로 출력 옵션과 기능에 대한 추가 정보는 [인쇄 개요](printing-overview.md)를 참조하세요.  
  
<a name="PluginSerializers"></a>   
## <a name="plug-in-serializers"></a>플러그 인 Serializer  
 <xref:System.Windows.Documents.Serialization> Api 응용 프로그램에서 개별적으로 설치 되는 연결된 serializer와 플러그 인 serializer에 대 한 지원을 제공, 런타임 시 바인딩 및 사용 하 여 액세스 되는 <xref:System.Windows.Documents.Serialization.SerializerProvider> 검색 메커니즘입니다.  플러그 인 serializer는 쉽게 배포하여 시스템 전체에서 사용할 수 있는 향상된 이점을 제공합니다.  플러그 인 serializer에 액세스할 수 없는 [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] 등의 부분 신뢰 환경용으로도 연결된 serializer를 구현할 수 있습니다.  연결 된 serializer의 파생 된 구현에 기반한는 <xref:System.Windows.Documents.Serialization.SerializerWriter> 클래스, 컴파일하고 하는 응용 프로그램에 직접 연결 합니다.  플러그 인 serializer와 연결된 serializer는 모두 동일한 공용 메서드와 이벤트를 통해 작동하므로 동일한 애플리케이션에서 두 serializer 유형 중 하나 또는 둘 다를 쉽게 사용할 수 있습니다.  
  
 플러그 인 serializer는 빌드 시 가능한 모든 형식에 맞게 직접 코딩할 필요가 없는 확장된 새로운 저장소 디자인과 파일 형식을 제공하여 애플리케이션 개발자를 지원합니다.  플러그 인 serializer는 사용자 지정 또는 독점 파일 형식에 맞게 시스템에서 액세스 가능한 플러그 인을 배포, 설치 및 업데이트하는 표준화된 방식을 제공하여 타사 개발자에게도 이점을 제공합니다.  
  
### <a name="using-a-plug-in-serializer"></a>플러그 인 Serializer 사용  
 플러그 인 serializer는 사용하기가 쉽습니다.  합니다 <xref:System.Windows.Documents.Serialization.SerializerProvider> 클래스 열거는 <xref:System.Windows.Documents.Serialization.SerializerDescriptor> 시스템에 각 플러그 인 설치에 대 한 개체입니다.  <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> 속성 현재 구성에 따라 설치 된 플러그 인을 필터링 하 고 serializer를 로드 및 응용 프로그램에서 사용할 수를 확인 합니다.  합니다 <xref:System.Windows.Documents.Serialization.SerializerDescriptor> 와 같은 다른 속성도 제공 <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> 및 <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, 응용 프로그램에서 사용 가능한 출력 형식에 대 한 serializer를 선택 하 라는 메시지를 하는 데 사용할 수 있는 합니다.  기본 플러그 인 serializer는 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 는.NET Framework와 함께 제공 되며 항상 열거 합니다.  사용자가 출력 형식으로, 선택는 <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> 메서드는 만드는 데는 <xref:System.Windows.Documents.Serialization.SerializerWriter> 특정 형식에 대 한 합니다.  <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> 데이터 저장소에 문서 스트림을 출력할 메서드를 호출할 수 있습니다.  
  
 다음 예제를 사용 하는 응용 프로그램을 <xref:System.Windows.Documents.Serialization.SerializerProvider> "PlugInFileFilter" 속성에는 메서드.  Pluginfilefilter에서는 설치 된 플러그 인을 열거 하 고 사용 가능한 파일 옵션을 사용 하 여 필터 문자열을 작성 한 <xref:Microsoft.Win32.SaveFileDialog>합니다.  
  
 [!code-csharp[DocumentSerialize#DocSerializeFileFilter](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]  
  
 출력 파일 이름을 선택한 후에 사용자를 다음 예제에 사용 된 <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> 지정 된 형식으로 지정된 된 문서를 저장 하는 방법입니다.  
  
 [!code-csharp[DocumentSerialize#DocSerializePlugIn](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]  
  
<a name="InstallingPluginSerializers"></a>   
### <a name="installing-plug-in-serializers"></a>플러그 인 Serializer 설치  
 <xref:System.Windows.Documents.Serialization.SerializerProvider> 클래스는 플러그 인 serializer 검색 및 액세스에 대 한 상위 수준 응용 프로그램 인터페이스를 제공 합니다.  <xref:System.Windows.Documents.Serialization.SerializerProvider> 키를 찾아 응용 프로그램을 설치 하 고 시스템에 액세스할 수 있는 serializer의 목록을 제공 합니다.  설치된 serializer의 구체적인 내용은 레지스트리 설정을 통해 정의됩니다.  플러그 인 serializer는 사용 하 여 레지스트리에 추가할 수 있습니다는 <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A> 메서드 또는 레지스트리 값 자체 경우.NET Framework 되지 않으므로 설치 된 플러그 인 설치 스크립트를 직접 설정할 수 있습니다.  <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> 메서드 이전에 설치 된 제거할 수 플러그 인 또는 스크립트를 제거 하 여 레지스트리 설정을 비슷하게 재설정할 수 있습니다.  
  
### <a name="creating-a-plug-in-serializer"></a>플러그 인 Serializer 만들기  
 플러그 인 serializer와 연결 serializer는 모두 노출된 동일한 공용 메서드와 이벤트를 사용하며, 동기식 또는 비동기식으로 작동하도록 비슷하게 설계될 수 있습니다.  일반적으로 플러그 인 serializer를 만들기 위해 수행하는 기본 단계는 다음 세 가지입니다.  
  
1. 먼저 serializer를 연결 serializer로 구현하고 디버깅합니다.  처음에 테스트 애플리케이션에서 직접 컴파일 및 연결된 serializer를 만들면 테스트에 유용한 중단점 및 기타 디버그 서비스에 완벽하게 액세스할 수 있습니다.  
  
2. Serializer가 완전히 테스트 한 후는 <xref:System.Windows.Documents.Serialization.ISerializerFactory> 인터페이스 플러그 인을 만들어에 추가 됩니다.  합니다 <xref:System.Windows.Documents.Serialization.ISerializerFactory> 논리적 트리를 포함 하는 모든.NET Framework 개체에 전체 액세스를 허용 하는 인터페이스 <xref:System.Windows.UIElement> 개체를 <xref:System.Windows.Documents.IDocumentPaginatorSource>, 및 <xref:System.Windows.Media.Visual> 요소입니다.  또한 <xref:System.Windows.Documents.Serialization.ISerializerFactory> 동일한 동기 및 비동기 메서드 및 연결된 serializer에서 사용 하는 이벤트를 제공 합니다.  큰 문서는 출력하는 데 시간이 걸리므로, 비동기 작업을 통해 반응이 빠른 사용자 조작을 유지 관리하고 데이터 저장소에 문제가 발생하면 “취소” 옵션을 제공하는 것이 좋습니다.  
  
3. 플러그 인 serializer가 만들어지면 플러그 인을 배포하고 설치(및 제거)하기 위한 설치 스크립트가 구현됩니다(위의 “[플러그 인 Serializer 설치](#InstallingPluginSerializers)” 참조).  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Documents.Serialization>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- [WPF의 문서](documents-in-wpf.md)
- [인쇄 개요](printing-overview.md)
- [XML Paper Specification: 개요](https://go.microsoft.com/fwlink?LinkID=106246)
