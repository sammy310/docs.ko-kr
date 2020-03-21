---
title: 문서
ms.date: 03/30/2017
helpviewer_keywords:
- documents [WPF], packaging
- documents [WPF], text layout
- documents [WPF], XPS
- 'XPS documents [WPF], , '
- documents [WPF], controls
- documents [WPF], types of
- documents [WPF], browser-viewable
ms.assetid: 6e8db7bc-050a-4070-aa72-bb8c46e87ff8
ms.openlocfilehash: e88604c42b253b48ee605f42f24fe301e339f74b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174682"
---
# <a name="documents-in-wpf"></a>WPF의 문서
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]이전 세대의 Windows보다 더 쉽게 액세스하고 읽을 수 있도록 설계된 고충실도 콘텐츠를 만들 수 있는 광범위한 문서 기능을 제공합니다. 고급 기능 및 품질 외에도 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 문서 표시, 패키징 및 보안을 위한 통합 서비스도 제공합니다. 이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 문서 형식 및 문서 패키징을 소개합니다.  

<a name="types_of_documents"></a>
## <a name="types-of-documents"></a>문서 종류  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 용도에 따라 문서를 두 개의 광범위한 범주로 구분합니다. 이러한 문서 범주를 “고정 문서”와 “유동 문서”라고 합니다.  
  
 고정 문서는 사용되는 디스플레이 또는 프린터 하드웨어와 는 별개로 정확한 "당신이 보는 것은 당신이 얻는 것"(WYSIWYG) 프리젠 테이션을 필요로하는 응용 프로그램을 위한 것입니다. 일반적으로 고정 문서는 데스크톱 출판, 워드 프로세싱 및 양식 레이아웃에 사용되며, 이 경우 원래 페이지 디자인을 고수하는 것이 중요합니다. 고정 문서에서는 사용 중인 디스플레이나 인쇄 디바이스와 무관하게 콘텐츠 요소의 정확한 위치를 레이아웃의 일부로 유지합니다. 예를 들어, 96dpi 디스플레이에 보이는 고정 문서 페이지는 600dpi 레이저 프린터로 출력할 때와 4800dpi 사진 식자기로 출력할 때 모두 똑같이 표시됩니다. 어느 경우에든 페이지 레이아웃은 동일하며, 문서 품질은 각 디바이스의 기능에 따라 최대화됩니다.  
  
 이에 비해 유동 문서는 보기와 가독성을 최적화하도록 설계되어 있으며, 문서 이용 시 용이한 가독성이 주된 요인인 시나리오에서 최적으로 활용할 수 있습니다. 유동 문서는 미리 정의된 하나의 레이아웃으로 설정되는 것이 아니라, 창 크기, 디바이스 해상도 및 선택적 사용자 기본 설정 등의 런타임 변수에 따라 동적으로 콘텐츠를 조정하고 리플로우합니다. 웹 페이지는 페이지 콘텐츠를 현재 창에 맞게 동적으로 형식화하는 유동 문서의 간단한 예입니다. 유동 문서는 런타임 환경을 기반으로 사용자의 보기 및 읽기 환경을 최적화합니다. 예를 들어, 동일한 유동 문서가 고해상도 19인치 디스플레이나 소형 2x3인치 PDA 화면에서 최적의 가독성을 제공하기 위해 동적으로 서식을 다시 지정합니다. 또한 유동 문서에는 검색, 가독성을 최적화하는 보기 모드 및 글꼴의 모양과 크기를 변경하는 기능 등의 여러 기본 제공 기능이 포함되어 있습니다.  플로우 문서에 대한 그림, 예제 및 자세한 정보는 [유동 문서 개요](flow-document-overview.md)를 참조하세요.  
  
<a name="document_viewer"></a>
## <a name="document-controls-and-text-layout"></a>문서 컨트롤 및 텍스트 레이아웃  
 .NET Framework는 응용 프로그램 내에서 고정 문서, 흐름 문서 및 일반 텍스트를 사용하여 단순화하는 미리 빌드된 컨트롤 집합을 제공합니다.  고정 문서 콘텐츠의 표시는 <xref:System.Windows.Controls.DocumentViewer> 컨트롤을 사용하여 지원됩니다.  흐름 문서 콘텐츠 의 표시는 세 <xref:System.Windows.Controls.FlowDocumentReader> <xref:System.Windows.Controls.FlowDocumentPageViewer>가지 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 다른 컨트롤에 의해 지원됩니다: 및 다른 사용자 시나리오에 매핑(아래 섹션 참조).  기타 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤에서는 일반 텍스트 사용을 지원하는 간소화된 레이아웃을 제공합니다(아래 [사용자 인터페이스의 텍스트](#text_in_the_user_interface) 참조).  
  
### <a name="fixed-document-control---documentviewer"></a>고정 문서 컨트롤 - DocumentViewer  
 컨트롤은 <xref:System.Windows.Controls.DocumentViewer> 콘텐츠를 표시하도록 <xref:System.Windows.Documents.FixedDocument> 설계되었습니다. 이 <xref:System.Windows.Controls.DocumentViewer> 컨트롤은 인쇄 출력, 클립보드 복사, 확대/축소 및 텍스트 검색 기능을 비롯한 일반적인 작업에 대한 기본 제공 지원을 제공하는 직관적인 사용자 인터페이스를 제공합니다. 컨트롤에서는 친숙한 스크롤링 메커니즘을 통해 콘텐츠 페이지에 액세스하는 권한을 제공합니다. 모든 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 컨트롤과 <xref:System.Windows.Controls.DocumentViewer> 마찬가지로 완전 또는 부분 재지정을 지원하므로 컨트롤을 거의 모든 응용 프로그램이나 환경에 시각적으로 통합할 수 있습니다.  
  
 <xref:System.Windows.Controls.DocumentViewer>읽기 전용 방식으로 콘텐츠를 표시하도록 설계되었습니다. 콘텐츠의 편집 또는 수정은 사용할 수 없으며 지원되지 않습니다.  
  
<a name="flow_document"></a>
### <a name="flow-document-controls"></a>유동 문서 컨트롤  

> [!NOTE]
> 흐름 문서 피처 및 생성 방법에 대한 자세한 내용은 [흐름 문서 개요를](flow-document-overview.md)참조하십시오.  
  
 흐름 문서 콘텐츠 표시는 세 <xref:System.Windows.Controls.FlowDocumentReader>가지 <xref:System.Windows.Controls.FlowDocumentPageViewer>컨트롤에서 지원됩니다. <xref:System.Windows.Controls.FlowDocumentScrollViewer>  
  
#### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader>사용자가 단일 페이지(한 번에 한 페이지씩) 보기 모드, 한 번에 2페이지씩(책 읽기 형식) 보기 모드, 연속 스크롤(바닥없는) 보기 모드 등 다양한 보기 모드 중에서 동적으로 선택할 수 있는 기능이 포함되어 있습니다.  이러한 보기 모드에 대한 자세한 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>내용은 을 참조하십시오.  다른 보기 모드 간에 동적으로 전환할 수 있는 <xref:System.Windows.Controls.FlowDocumentPageViewer> 기능이 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 필요하지 않은 경우, 특정 보기 모드에 고정된 경량 흐름 콘텐츠 뷰어를 제공합니다.  
  
#### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer 및 FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>은 한 번에 한 페이지로 보기 모드로 콘텐츠를 표시하고 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 연속 스크롤 모드에서 콘텐츠를 표시합니다.  둘 <xref:System.Windows.Controls.FlowDocumentPageViewer> <xref:System.Windows.Controls.FlowDocumentScrollViewer> 다 특정 보기 모드로 고정되어 있습니다. 을 사용하면 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> 다양한 보기 모드(열거형에서 제공하는 대로)를 동적으로 선택할 수 있는 기능이 포함되어 있는 것과 <xref:System.Windows.Controls.FlowDocumentPageViewer> 비교하면 리소스 집약적일 수록 비용이 많이 <xref:System.Windows.Controls.FlowDocumentScrollViewer>듭니다. <xref:System.Windows.Controls.FlowDocumentReader>  
  
 기본적으로 세로 스크롤 막대는 항상 표시되며 가로 스크롤 막대는 필요한 경우 표시됩니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 기본값에는 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 도구 모음이 포함되지 않습니다. 그러나 속성을 <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> 사용하여 기본 제공 도구 모음을 활성화할 수 있습니다.  
  
<a name="text_in_the_user_interface"></a>
### <a name="text-in-the-user-interface"></a>사용자 인터페이스의 텍스트  
 문서에 텍스트를 추가하는 외에도 양식과 같은 애플리케이션 UI에서 명확하게 텍스트를 사용할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 화면에 텍스트를 그리는 데 사용하는 여러 컨트롤이 포함되어 있습니다. 각 컨트롤은 다른 시나리오를 대상으로 하며 고유 기능 및 제한 사항 목록을 가지고 있습니다. 일반적으로 <xref:System.Windows.Controls.TextBlock> 요소는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]에서 간단한 문장과 같이 제한된 텍스트 지원이 필요한 경우에 사용해야 합니다. <xref:System.Windows.Controls.Label>최소한의 텍스트 지원이 필요한 경우에 사용할 수 있습니다. 자세한 내용은 [TextBlock 개요](../controls/textblock-overview.md)를 참조하세요.  
  
<a name="packaging"></a>
## <a name="document-packaging"></a>문서 패키징  
 API는 <xref:System.IO.Packaging> 액세스가 간편하고 이식가능하며 배포하기 쉬운 단일 컨테이너에서 응용 프로그램 데이터, 문서 콘텐츠 및 관련 리소스를 구성하는 효율적인 수단을 제공합니다. ZIP 파일은 여러 개체를 단일 단위로 보유할 수 있는 <xref:System.IO.Packaging.Package> 형식의 예입니다. 패키징 API는 <xref:System.IO.Packaging.ZipPackage> XML 및 ZIP 파일 아키텍처를 사용하여 개방형 패키징 규칙 표준을 사용하여 설계된 기본 구현을 제공합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패키징 API를 통해 패키지를 만들고 패키지를 쉽게 저장하고 객체에 액세스할 수 있습니다. a에 <xref:System.IO.Packaging.Package> 저장된 객체를 <xref:System.IO.Packaging.PackagePart> "부품"이라고 합니다. 패키지에는 파트의 작성기를 식별하고 패키지의 콘텐츠가 수정되지 않았는지 유효성을 검사하는 데 사용할 수 있는 서명된 디지털 인증서도 포함될 수 있습니다.  패키지에는 기존 <xref:System.IO.Packaging.PackageRelationship> 부품의 컨텐츠를 실제로 수정하지 않고도 패키지에 추가 정보를 추가하거나 특정 부품과 연관된 추가 정보를 허용하는 기능도 포함되어 있습니다.  패키지 서비스는 RM(Microsoft Windows 권한 관리)도 지원합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패키지 아키텍처는 다음과 같은 여러 주요 기술의 기반 역할을 합니다.  
  
- XpS 문서는 XML 용지 사양(XPS)을 준수합니다.  
  
- Microsoft Office “12” Open XML 형식 문서(.docx).  
  
- 고유 애플리케이션 디자인에 맞는 사용자 지정 스토리지 형식.  
  
 패키징 API를 기반으로 <xref:System.Windows.Xps.Packaging.XpsDocument> 고정 콘텐츠 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 문서를 저장하도록 특별히 설계되었습니다. A는 <xref:System.Windows.Xps.Packaging.XpsDocument> 뷰어에서 열거나, <xref:System.Windows.Controls.DocumentViewer> 컨트롤에 표시하거나, 인쇄 스풀로 라우팅하거나, XPS 호환 프린터로 직접 출력할 수 있는 독립형 문서입니다.  
  
 다음 섹션에서는 <xref:System.IO.Packaging.Package> <xref:System.Windows.Xps.Packaging.XpsDocument> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 제공된 API 및 API에 대한 추가 정보를 제공합니다.  
  
<a name="packages"></a>
### <a name="package-components"></a>패키지 구성 요소  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 패키징 API를 사용하면 애플리케이션 데이터와 문서를 이식 가능한 단일 단위로 구성할 수 있습니다. ZIP 파일은 가장 일반적인 패키지 유형 중 하나이고, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 제공하는 기본 패키지 유형입니다.  <xref:System.IO.Packaging.Package>자체는 개방형 표준 XML 및 ZIP 파일 아키텍처를 사용하여 구현되는 <xref:System.IO.Packaging.ZipPackage> 추상 클래스입니다.  이 <xref:System.IO.Packaging.Package.Open%2A> 메서드는 기본적으로 ZIP 파일을 만들고 사용하는 데 사용합니다. <xref:System.IO.Packaging.ZipPackage> 패키지에는 다음과 같은 세 가지 기본 유형의 항목이 포함될 수 있습니다.  
  
|||  
|-|-|  
|<xref:System.IO.Packaging.PackagePart>|애플리케이션 콘텐츠, 데이터, 문서 및 리소스 파일.|  
|<xref:System.IO.Packaging.PackageDigitalSignature>|ID, 인증 및 유효성 검사용 [X.509 인증서].|  
|<xref:System.IO.Packaging.PackageRelationship>|패키지 또는 특정 파트와 관련된 추가 정보.|  
  
<a name="PackageParts"></a>
#### <a name="packageparts"></a>PackageParts  
 A("part")는 <xref:System.IO.Packaging.PackagePart> <xref:System.IO.Packaging.Package>에 저장된 개체를 참조하는 추상 클래스입니다. ZIP 파일에서 패키지 파트는 ZIP 파일에 저장된 개별 파일에 해당합니다.  <xref:System.IO.Packaging.ZipPackagePart>에 저장된 직렬화 가능한 개체에 <xref:System.IO.Packaging.ZipPackage>대한 기본 구현을 제공합니다.  파일 시스템과 마찬가지로 패키지에 포함된 파트는 계층 구조 디렉터리 또는 “폴더 스타일” 조직에 저장됩니다.  응용 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 프로그램은 패키징 API를 사용하여 단일 ZIP <xref:System.IO.Packaging.PackagePart> 파일 컨테이너를 사용하여 여러 개체를 작성, 저장 및 읽을 수 있습니다.  
  
<a name="PackageDigitalSignatures"></a>
#### <a name="packagedigitalsignatures"></a>PackageDigitalSignatures  
 보안을 위해 <xref:System.IO.Packaging.PackageDigitalSignature> ("디지털 서명")을 패키지 내의 부품과 연결할 수 있습니다. A는 <xref:System.IO.Packaging.PackageDigitalSignature> 다음 두 가지 기능을 제공하는 [509]를 통합합니다.  
  
1. 파트의 작성기를 식별하고 인증합니다.  
  
2. 파트가 수정되지 않았는지 유효성을 검사합니다.  
  
 디지털 시그니처는 파트를 수정하지 못하게 하지는 않지만, 파트를 임의 방식으로 변경하면 디지털 시그니처의 유효성 검사 확인이 실패합니다. 그러면 애플리케이션에서 파트 열기를 차단하거나 사용자에게 파트가 수정되어 안전하지 않음을 알리는 등의 적절한 조치를 수행할 수 있습니다.  
  
<a name="PackageRelationships"></a>
#### <a name="packagerelationships"></a>PackageRelationships  
 A("관계")는 <xref:System.IO.Packaging.PackageRelationship> 추가 정보를 패키지 또는 패키지 내의 부품과 연결하는 메커니즘을 제공합니다. 관계는 실제 파트 콘텐츠를 수정하지 않고 파트와 추가 정보를 연결할 수 있는 패키지 수준 기능입니다. 대부분의 경우 새 데이터를 파트 콘텐츠에 직접 삽입하는 것은 실용적이지 않습니다.  
  
- 파트의 실제 형식 및 해당 콘텐츠 스키마는 알 수 없습니다.  
  
- 알려진 경우에도 콘텐츠 스키마에서는 새 정보를 추가하는 방법을 제공하지 않습니다.  
  
- 파트는 디지털 방식으로 서명되거나 암호화될 수 있으며, 수정은 불가능합니다.  
  
 패키지 관계에서는 자세한 정보를 추가하여 개별 파트 또는 전체 패키지와 연결하는 검색 가능한 방법을 제공합니다. 패키지 관계는 다음 두 개의 주요 기능에 사용합니다.  
  
1. 파트 간 종속성 관계 정의.  
  
2. 메모 또는 파트와 관련된 다른 데이터를 추가하는 정보 관계 정의.  
  
 A는 <xref:System.IO.Packaging.PackageRelationship> 종속성을 정의하고 패키지의 일부 또는 패키지 전체와 관련된 기타 정보를 추가하는 빠르고 검색 가능한 수단을 제공합니다.  
  
<a name="Dependency_Relationships"></a>
##### <a name="dependency-relationships"></a>종속성 관계  
 종속성 관계는 한 파트가 다른 파트에 지정하는 종속성을 설명하는 데 사용됩니다. 예를 들어, 패키지에는 하나 이상의 \<img> 이미지 태그를 포함하는 HTML 파트가 포함될 수 있습니다. 이미지 태그는 패키지 내부의 다른 파트 또는 패키지 외부의 다른 파트(예: 인터넷을 통해 액세스 가능)로 있는 이미지를 참조합니다. HTML <xref:System.IO.Packaging.PackageRelationship> 파일과 연결된 파일을 만들면 종속 리소스를 빠르고 쉽게 검색하고 액세스할 수 있습니다. 브라우저 또는 뷰어 애플리케이션에서 파트 관계에 직접 액세스하고 스키마를 모르거나 문서를 구문 분석하지 않아도 종속 리소스의 어셈블링을 즉시 시작할 수 있습니다.  
  
<a name="Information_Relationships"></a>
##### <a name="information-relationships"></a>정보 관계  
 메모 또는 어구와 마찬가지로 <xref:System.IO.Packaging.PackageRelationship> 부품 컨텐터 자체를 실제로 수정하지 않고도 부품과 연관되는 다른 유형의 정보를 저장하는 데도 사용할 수 있습니다.  
  
<a name="XPS_Documents"></a>
## <a name="xps-documents"></a>XPS 문서  
 XML 용지 사양(XPS) 문서는 렌더링에 필요한 모든 리소스 및 정보와 함께 하나 이상의 고정 문서가 포함된 패키지입니다.  XPS는 또한 기본 Windows Vista 인쇄 스풀 파일 형식입니다.  An은 <xref:System.Windows.Xps.Packaging.XpsDocument> 표준 ZIP 데이터 집합에 저장되며 이미지 및 글꼴 파일과 같은 XML 및 이진 구성 요소의 조합을 포함할 수 있습니다. [PackageRelationships](#PackageRelationships)는 문서를 완전하게 렌더링하는 데 필요한 리소스와 콘텐츠 사이의 종속성을 정의하는 데 사용합니다.  이 <xref:System.Windows.Xps.Packaging.XpsDocument> 설계는 여러 용도를 지원하는 단일 고충실도 문서 솔루션을 제공합니다.  
  
- 고정 문서 콘텐츠와 리소스를 읽고 쓰며, 이식 가능하고 배포하기 쉬운 단일 파일로 저장.  
  
- XPS 뷰어 응용 프로그램과 함께 문서를 표시합니다.  
  
- Windows Vista의 기본 인쇄 스풀 출력 형식으로 문서를 출력합니다.  
  
- XPS 호환 프린터로 직접 문서를 라우팅합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Documents.FixedDocument>
- <xref:System.Windows.Documents.FlowDocument>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.IO.Packaging.ZipPackage>
- <xref:System.IO.Packaging.ZipPackagePart>
- <xref:System.IO.Packaging.PackageRelationship>
- <xref:System.Windows.Controls.DocumentViewer>
- [텍스트](optimizing-performance-text.md)
- [유동 문서 개요](flow-document-overview.md)
- [인쇄 개요](printing-overview.md)
- [문서 Serialization 및 스토리지](document-serialization-and-storage.md)
