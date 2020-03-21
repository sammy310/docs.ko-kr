---
title: 인쇄 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print path [WPF], XPS
- printers [WPF], XPSDrv-based
- printing [WPF]
- PrintQueue class PrintServer class [WPF]
- XML Paper Specification (XPS) file format
- XPS (XML Paper Specification) file format
- XPSDrv-based printers
- GDI print path [WPF]
ms.assetid: 0de8ac41-9aa6-413d-a121-7aa6f41539b1
ms.openlocfilehash: 902d51341850b5245b9fa6410b1954b2ab373bbc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187207"
---
# <a name="printing-overview"></a>인쇄 개요
Microsoft .NET 프레임워크를 사용하면 WPF(Windows 프레젠테이션 기반)를 사용하는 응용 프로그램 개발자는 풍부한 새 인쇄 및 인쇄 시스템 관리 API를 사용합니다. Windows Vista에서는 관리되지 않는 코드를 사용하여 Windows Forms 응용 프로그램을 만드는 개발자와 개발자가 이러한 인쇄 시스템 개선 사항 중 일부를 사용할 수 있습니다. 이 새로운 기능의 핵심은 새로운 XML 용지 사양(XPS) 파일 형식과 XPS 인쇄 경로입니다.  
  
 이 항목에는 다음과 같은 섹션이 포함되어 있습니다.  
  
<a name="introduction_to_XPS"></a>
## <a name="about-xps"></a>XPS 정보  
 XPS는 전자 문서 형식, 스풀 파일 형식 및 페이지 설명 언어입니다. XML, 개방형 패키징 규칙(OPC) 및 기타 업계 표준을 사용하여 플랫폼 간 문서를 만드는 개방형 문서 형식입니다. XPS는 디지털 문서를 생성, 공유, 인쇄, 조회 및 보관하는 프로세스를 간소화합니다. XPS에 대한 자세한 내용은 [XPS 문서를](/windows/desktop/printdocs/documents)참조하십시오.  
  
 WPF를 사용하여 XPS 기반 콘텐츠를 인쇄하는 몇 가지 기술은 [프로그래밍 방식으로 XPS 파일을 인쇄할 때](how-to-programmatically-print-xps-files.md)설명합니다. 이 항목에 포함된 내용을 검토하는 동안 이러한 예제를 참조하는 것이 유용할 수도 있습니다. 관리되지 않는 코드 개발자는 [MXDC_ESCAPE 함수에](/windows/desktop/printdocs/mxdc-escape)대한 설명서를 표시해야 합니다. Windows Forms 개발자는 전체 XPS 인쇄 경로를 지원하지 않지만 하이브리드 GDI-XPS 인쇄 경로를 지원하는 <xref:System.Drawing.Printing> 네임스페이스에서 API를 사용해야 합니다. 아래의 **인쇄 경로 아키텍처**를 참조하세요.  
  
<a name="XPS_print_path_intro"></a>
## <a name="xps-print-path"></a>XPS 인쇄 경로  
 XpS(XML 용지 사양) 인쇄 경로는 Windows 응용 프로그램에서 인쇄를 처리하는 방법을 재정의하는 새로운 Windows 기능입니다. XPS는 문서 프레젠테이션 언어(예: RTF), 인쇄 스풀러 형식(예: WMF) 및 페이지 설명 언어(예: PCL 또는 Postscript)를 대체할 수 있습니다. 새 인쇄 경로는 응용 프로그램 발행물에서 인쇄 드라이버 또는 장치의 최종 처리에 이르기까지 XPS 형식을 유지합니다.  
  
 XPS 인쇄 경로는 XPS 프린터 드라이버 모델(XPSDrv)을 기반으로 구축되어 있으며, 이는 "WYSIWYG) 인쇄, 향상된 색상 지원 및 인쇄 성능 과 같은 개발자에게 몇 가지 이점을 제공합니다. (XPSDrv에 대한 자세한 내용은 [Windows 드라이버 키트 설명서를](/windows-hardware/drivers/)참조하십시오.)  
  
 XPS 문서에 대한 인쇄 스풀러의 작동은 기본적으로 이전 버전의 Windows와 동일합니다. 그러나 기존 GDI 인쇄 경로 외에도 XPS 인쇄 경로를 지원하도록 개선되었습니다. 새 인쇄 경로는 기본적으로 XPS 스풀 파일을 사용합니다. 이전 버전의 Windows용으로 작성된 사용자 모드 프린터 드라이버는 계속 작동하지만 XPS 인쇄 경로를 사용하려면 XPS 프린터 드라이버(XPSDrv)가 필요합니다.  
  
 XPS 인쇄 경로의 이점은 다음과 같습니다.  
  
- 와이지그 인쇄 지원  
  
- 32bpc(채널당 비트), CMYK, 명명된 색, n-잉크 및 투명도와 그라데이션 기본 지원을 포함하는 고급 색 프로필에 대한 기본 지원입니다.  
  
- .NET Framework 및 Win32 기반 응용 프로그램 모두에서 인쇄 성능이 향상되었습니다.  
  
- 업계 표준 XPS 형식입니다.  
  
 기본 인쇄 시나리오의 경우 사용자 인터페이스, 구성 및 작업 제출을 위한 단일 진입점에서 간단하고 직관적인 API를 사용할 수 있습니다. 고급 시나리오에서는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 사용자 지정(또는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 없음), 동기 또는 비동기 인쇄 및 일괄 처리 인쇄 기능을 위한 추가 지원이 추가됩니다. 두 옵션 모두 완전 신뢰 또는 부분 신뢰 모드로 인쇄 지원을 제공합니다.  
  
 XPS는 확장성을 염두에 두고 설계되었습니다. 확장성 프레임워크를 사용하면 모듈식으로 XPS에 기능과 기능을 추가할 수 있습니다. 확장성 기능은 다음과 같습니다.  
  
- 인쇄 스키마. 공용 스키마는 정기적으로 업데이트되며 디바이스 기능을 빠르게 확장할 수 있게 해줍니다. 아래의 **PrintTicket 및 PrintCapabilities**를 참조하세요.  
  
- 확장 가능한 필터 파이프라인. XPS 프린터 드라이버(XPSDrv) 필터 파이프라인은 XPS 문서의 직접 및 확장 가능한 인쇄를 모두 가능하게 하도록 설계되었습니다. 자세한 내용은 [XPSDrv 프린터 드라이버를](/windows-hardware/drivers/print/xpsdrv-printer-drivers)참조하십시오.
  
### <a name="print-path-architecture"></a>인쇄 경로 아키텍처  
 Win32 및 .NET Framework 응용 프로그램 모두 XPS를 지원하지만 Win32 및 Windows Forms 응용 프로그램은 XPS 프린터 드라이버(XPSDrv)에 대한 XPS 형식의 콘텐츠를 만들기 위해 GDI에서 XPS로 변환합니다. 이러한 응용 프로그램은 XPS 인쇄 경로를 사용할 필요가 없으며 EMF(향상된 메타파일) 기반 인쇄를 계속 사용할 수 있습니다. 그러나 대부분의 XPS 기능 및 향상된 기능은 XPS 인쇄 경로를 대상으로 하는 응용 프로그램에서만 사용할 수 있습니다.  
  
 Win32 및 Windows Forms 응용 프로그램에서 XPSDrv 기반 프린터를 사용할 수 있도록 XPS 프린터 드라이버(XPSDrv)는 GDI를 XPS 형식으로 변환하는 것을 지원합니다. 또한 XPSDrv 모델은 Win32 응용 프로그램이 XPS 문서를 인쇄할 수 있도록 XPS에서 GDI 형식으로 변환기를 제공합니다. WPF 응용 프로그램의 경우 쓰기 작업의 대상 인쇄 대기열에 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> XPSDrv <xref:System.Windows.Xps.XpsDocumentWriter> 드라이버가 없을 때마다 클래스및 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 메서드에 의해 XPS를 GDI 형식으로 변환하는 작업이 자동으로 수행됩니다. (Windows Forms 응용 프로그램은 XPS 문서를 인쇄할 수 없습니다.)  
  
 다음 그림에서는 인쇄 하위 시스템을 묘사하고 Microsoft에서 제공하는 부분과 소프트웨어 및 하드웨어 공급업체에서 정의한 부분을 정의합니다.  
  
 ![스크린샷은 XPS 인쇄 시스템을 보여줍니다.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>기본 XPS 인쇄  
 WPF는 기본 API와 고급 API를 모두 정의합니다. 광범위한 인쇄 사용자 지정 또는 전체 XPS 기능 집합에 대한 액세스가 필요하지 않은 응용 프로그램의 경우 기본 인쇄 지원을 사용할 수 있습니다. 기본 인쇄 지원은 최소한의 구성이 필요하며 익숙한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 제공하는 인쇄 대화 상자 컨트롤을 통해 노출됩니다. 이 간소화된 인쇄 모델을 사용하여 많은 XPS 기능을 사용할 수 있습니다.  
  
#### <a name="printdialog"></a>PrintDialog  
 컨트롤은 <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> 구성 및 XPS 작업 제출에 대한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]단일 진입점을 제공합니다. 컨트롤을 인스턴스화하고 사용하는 방법에 대한 자세한 내용은 [인쇄 대화 상자 호출](how-to-invoke-a-print-dialog.md)을 참조하세요.  
  
### <a name="advanced-xps-printing"></a>고급 XPS 인쇄  
 XPS 기능의 전체 집합에 액세스하려면 고급 인쇄 API를 사용해야 합니다. 몇 가지 관련 API는 아래에 자세히 설명되어 있습니다. XPS 인쇄 경로 API의 전체 목록은 <xref:System.Windows.Xps> 및 <xref:System.Printing> 네임스페이스 참조를 참조하십시오.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket 및 PrintCapabilities  
 <xref:System.Printing.PrintTicket> 클래스는 <xref:System.Printing.PrintCapabilities> 고급 XPS 기능의 기초입니다. 두 가지 유형의 개체는 데이터 정렬, 양면 인쇄, 스테이플링 등과 같은 인쇄 지향 피처의 XML 형식 구조입니다. 이러한 구조는 인쇄 스키마에 의해 정의됩니다. <xref:System.Printing.PrintTicket>은 인쇄 작업을 처리하는 방법을 프린터에 지시합니다. <xref:System.Printing.PrintCapabilities> 클래스는 프린터 기능을 정의합니다. 프린터 기능 쿼리를 통해 프린터에서 지원하는 기능을 완전히 활용하는 <xref:System.Printing.PrintTicket>을 만들 수 있습니다. 마찬가지로, 지원되지 않는 기능을 방지할 수 있습니다.  
  
 다음 예제에서는 코드를 사용하여 프린터의 <xref:System.Printing.PrintCapabilities>를 쿼리하고 <xref:System.Printing.PrintTicket>을 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer 및 PrintQueue  
 <xref:System.Printing.PrintServer> 클래스는 네트워크 인쇄 서버를 나타내고 <xref:System.Printing.PrintQueue> 클래스는 프린터 및 프린터와 연결된 출력 작업 큐를 나타냅니다. 이러한 API를 통해 서버의 인쇄 작업을 고급으로 관리할 수 있습니다. <xref:System.Printing.PrintServer> 또는 해당 파생 클래스 중 하나는 <xref:System.Printing.PrintQueue>를 관리하는 데 사용됩니다. <xref:System.Printing.PrintQueue.AddJob%2A> 메서드는 새 인쇄 작업을 대기열에 삽입하는 데 사용됩니다.  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Printing.LocalPrintServer>를 만들고 기본 <xref:System.Printing.PrintQueue>에 액세스하는 방법을 보여 줍니다.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 의 <xref:System.Windows.Xps.XpsDocumentWriter>여러 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> 메서드와 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 메서드를 사용하여 XPS 문서를 <xref:System.Printing.PrintQueue>에 작성하는 데 사용됩니다. 예를 들어 <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> 이 메서드는 XPS 문서를 <xref:System.Printing.PrintTicket> 동기적으로 출력하는 데 사용됩니다. 이 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> 메서드는 XPS 문서를 <xref:System.Printing.PrintTicket> 비동기적으로 출력하는 데 사용됩니다.  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Windows.Xps.XpsDocumentWriter>를 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 <xref:System.Printing.PrintQueue.AddJob%2A> 메서드는 다양한 인쇄 방법도 제공합니다. [프로그래밍 방식으로 XPS 파일 인쇄](how-to-programmatically-print-xps-files.md)를 참조하세요. 참조하세요.  
  
<a name="GDI_Print_Path_intro"></a>
## <a name="gdi-print-path"></a>GDI 인쇄 경로  
 WPF 응용 프로그램은 기본적으로 XPS 인쇄 경로를 지원하지만 Win32 및 Windows Forms 응용 프로그램은 일부 XPS 기능을 활용할 수도 있습니다. XPS 프린터 드라이버(XPSDrv)는 GDI 기반 출력을 XPS 형식으로 변환할 수 있습니다. 고급 시나리오의 경우 [MXDC(Microsoft XPS 문서 변환기)를](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)사용하여 콘텐츠의 사용자 지정 변환이 지원됩니다. 마찬가지로 WPF 응용 프로그램은 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> <xref:System.Windows.Xps.XpsDocumentWriter> 클래스의 또는 메서드 중 하나를 호출하고 비 XpsDrv 프린터를 대상 인쇄 대기열로 지정하여 GDI 인쇄 경로로 출력할 수도 있습니다.  

XPS 기능이나 지원이 필요하지 않은 응용 프로그램의 경우 현재 GDI 인쇄 경로는 변경되지 않습니다.  
  
- GDI 인쇄 경로 및 다양한 XPS 변환 옵션에 대한 추가 참조 자료는 [Microsoft XPS 문서 변환기(MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) 및 [XPSDrv 프린터 드라이버를](/windows-hardware/drivers/print/xpsdrv-printer-drivers)참조하십시오.  
  
<a name="XPS_Driver_Model_intro"></a>
## <a name="xpsdrv-driver-model"></a>XPSDrv 드라이버 모델  
 XPS 인쇄 경로는 XPS 지원 프린터 또는 드라이버로 인쇄할 때 XPS를 기본 인쇄 스풀 형식으로 사용하여 스풀러 효율성을 향상시킵니다. 간소화된 스풀링 프로세스를 통해 문서가 스풀링되기 전에 EMF 데이터 파일과 같은 중간 스풀 파일을 생성할 필요가 없습니다. XPS 인쇄 경로는 작은 스풀 파일 크기를 통해 네트워크 트래픽을 줄이고 인쇄 성능을 향상시킬 수 있습니다.  
  
 EMF는 서비스 렌더링을 위해 GDI에 대한 일련의 호출로 응용 프로그램 출력을 나타내는 닫힌 형식입니다. EMF와 달리 XPS 스풀 형식은 XPS 기반 프린터 드라이버(XPSDrv)로 출력할 때 추가 해석없이 실제 문서를 나타냅니다. 드라이버가 형식의 데이터에 대해 직접 작동할 수 있습니다. 이 기능은 EMF 파일 및 GDI 기반 인쇄 드라이버를 사용할 때 필요한 데이터 및 색상 공간 변환을 제거합니다.  
  
 일반적으로 XPS 프린터 드라이버(XPSDrv)를 대상으로 하는 XPS 문서를 EMF 와 비교하여 사용하는 경우 스풀 파일 크기가 줄어듭니다. 그러나 다음과 같은 예외가 있습니다.  
  
- 매우 복잡하거나 다중 계층이거나 비효율적으로 작성된 벡터 그래픽은 동일한 그래픽의 비트맵 버전보다 클 수 있습니다.  
  
- 화면 표시를 위해 XPS 파일은 디바이스 글꼴과 컴퓨터 기반 글꼴을 포함하는 반면 GDI 스풀 파일은 디바이스 글꼴을 포함하지 않습니다. 그러나 두 종류의 글꼴은 모두 하위 집합으로 지정되며(아래 참조), 프린터 드라이버가 파일을 프린터로 전송하기 전에 디바이스 글꼴을 제거할 수 있습니다.  
  
 스풀 크기 감소는 다음과 같은 여러 메커니즘을 통해 수행됩니다.  
  
- **글꼴 하위 집합**. 실제 문서내에 사용된 문자만 XPS 파일에 저장됩니다.  
  
- **고급 그래픽 지원**. 투명도 및 그라데이션 프리미티브에 대한 기본 지원은 XPS 문서에서 콘텐츠의 래스터화를 방지합니다.  
  
- **공용 리소스 식별**. 여러 번 사용되는 리소스(예: 회사 로고를 나타내는 이미지)는 공유 리소스로 처리되며 한 번만 로드됩니다.  
  
- **ZIP 압축**. 모든 XPS 문서는 ZIP 압축을 사용합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [방법 주제](printing-how-to-topics.md)
- [WPF의 문서](documents-in-wpf.md)
- [XPS 문서](/windows/desktop/printdocs/documents)
- [문서 Serialization 및 스토리지](document-serialization-and-storage.md)
- [마이크로소프트 XPS 문서 변환기 (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
