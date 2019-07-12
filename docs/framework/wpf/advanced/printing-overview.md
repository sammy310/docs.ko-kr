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
ms.openlocfilehash: acfc252708bf8be7abacb1adc2968122501315a0
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67860207"
---
# <a name="printing-overview"></a>인쇄 개요
Microsoft.NET Framework를 사용 하 여 Windows Presentation Foundation (WPF)를 사용 하 여 응용 프로그램 개발자는 새로운 풍부한 인쇄 및 인쇄 시스템 관리 Api. [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)]에서는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 응용 프로그램을 만드는 개발자와 비관리 코드를 사용하는 개발자도 이러한 인쇄 시스템 향상 기능을 일부 사용할 수 있습니다. 이 새로운 기능의 핵심은 새 [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] 파일 형식과 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 인쇄 경로입니다.  
  
 이 항목에는 다음과 같은 섹션이 포함되어 있습니다.  
  
<a name="introduction_to_XPS"></a>   
## <a name="about-xps"></a>XPS 정보  
 XPS는 전자 문서 형식, 스풀 파일 형식 및 페이지 설명 언어입니다. [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)], [!INCLUDE[TLA#tla_opc](../../../../includes/tlasharptla-opc-md.md)] 및 기타 산업 표준을 사용하여 플랫폼 간 문서를 만드는 공개 문서 형식입니다. XPS는 디지털 문서, 공유, 인쇄, 보고, 만들어지고 보관 프로세스를 간소화 합니다. 참조 추가 대 한 내용은 XPS [XPS 문서](/windows/desktop/printdocs/documents)합니다.  
  
 인쇄 XPS 기반 콘텐츠를 사용 하 여에 대 한 몇 가지 기법 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 에서 보여 [프로그래밍 방식으로 XPS 파일 인쇄](how-to-programmatically-print-xps-files.md)합니다. 이 항목에 포함된 내용을 검토하는 동안 이러한 예제를 참조하는 것이 유용할 수도 있습니다. (비관리 코드 개발자에 대 한 설명서를 참조 해야 합니다 [MXDC_ESCAPE 함수](/windows/desktop/printdocs/mxdc-escape)합니다. Windows Forms 개발자의 API를 사용 해야 합니다 <xref:System.Drawing.Printing> 전체를 지원 하지 않는 네임 스페이스 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 하이브리드 GDI-XPS 인쇄 경로 지원 하지 않지만 인쇄 경로입니다. 아래의 **인쇄 경로 아키텍처**를 참조하세요.  
  
<a name="XPS_print_path_intro"></a>   
## <a name="xps-print-path"></a>XPS 인쇄 경로  
 사양 XPS (XML Paper) 인쇄 경로 새로운 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Windows 응용 프로그램에서 인쇄를 처리 하는 방법을 다시 정의 하는 기능입니다. 때문에 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 문서 표시 언어 (예: RTF), 인쇄 스풀러 형식 (예: WMF) 및 페이지 설명 언어 (예: PCL 또는 포스트 스크립트) 바꾸면; 새로운 인쇄 경로 게시 응용 프로그램에서에서 XPS 형식으로 유지 관리 합니다 인쇄 드라이버 또는 장치에서 최종 처리 합니다.  
  
 XPS 인쇄 경로 XPS 인쇄 드라이버 모델 (XPSDrv)와 같은 개발자를 위한 몇 가지 이점을 제공 하는 기반 [!INCLUDE[TLA#tla_wys](../../../../includes/tlasharptla-wys-md.md)] 인쇄, 향상 된 색 지원 및 인쇄 성능 향상. (에 XPSDrv에 대 한 자세한 참조를 [Windows 드라이버 키트 설명서](/windows-hardware/drivers/).)  
  
 XPS 문서에 대 한 인쇄 스풀러 작업 이전 버전의 Windows와 같이 기본적으로 동일합니다. 그러나 기존 하는 것 외에도 XPS 인쇄 경로 지원 하도록 향상 되었습니다에 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 인쇄 경로입니다. 기본적으로 새로운 인쇄 경로 XPS 스풀 파일을 사용합니다. 이전 버전용으로 작성 된 사용자 모드 프린터 드라이버를 하는 동안 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] XPS 프린터 드라이버 (XPSDrv)는 XPS 인쇄 경로 사용 하는 데 필요한, 계속 작동 합니다.  
  
 XPS 인쇄 경로 중요 이점과 포함:  
  
- [!INCLUDE[TLA2#tla_wys](../../../../includes/tla2sharptla-wys-md.md)] 인쇄 지원  
  
- 32bpc(채널당 비트), CMYK, 명명된 색, n-잉크 및 투명도와 그라데이션 기본 지원을 포함하는 고급 색 프로필에 대한 기본 지원입니다.  
  
- 두.NET Framework에 대 한 인쇄 성능 향상 및 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 기반 응용 프로그램입니다.  
  
- 업계 표준 XPS 형식입니다.  
  
 기본 인쇄 시나리오에서는 간단 하 고 직관적인 API 사용자 인터페이스, 구성 및 작업 제출 위한 단일 진입점을 사용 하 여 제공 됩니다. 고급 시나리오에서는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 사용자 지정(또는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 없음), 동기 또는 비동기 인쇄 및 일괄 처리 인쇄 기능을 위한 추가 지원이 추가됩니다. 두 옵션 모두 완전 신뢰 또는 부분 신뢰 모드로 인쇄 지원을 제공합니다.  
  
 XPS는 확장성을 염두에서에 두고 설계 되었습니다. 확장성 프레임 워크를 사용 하 여 기능과 모듈 방식으로 xps 추가할 수 있습니다. 확장성 기능은 다음과 같습니다.  
  
- 인쇄 스키마. 공용 스키마는 정기적으로 업데이트되며 디바이스 기능을 빠르게 확장할 수 있게 해줍니다. 아래의 **PrintTicket 및 PrintCapabilities**를 참조하세요.  
  
- 확장 가능한 필터 파이프라인. XPS 프린터 드라이버 (XPSDrv) 필터 파이프라인은 직접 및 확장 가능한 XPS 문서 인쇄를 사용 하도록 설계 되었습니다. 자세한 내용은 [XPSDrv 프린터 드라이버](/windows-hardware/drivers/print/xpsdrv-printer-drivers)합니다. 
  
### <a name="print-path-architecture"></a>인쇄 경로 아키텍처  
 반면 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 및.NET Framework 응용 프로그램 지원, XPS [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 사용 하 여 Windows Forms 응용 프로그램을 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] XPS XPS를 만들기 위해 변환 XPS 프린터 드라이버 (XPSDrv)에 대 한 콘텐츠 형식입니다. XPS 인쇄 경로 사용 하 여 필요 하지 않으며 계속 사용할 수 있습니다, 이러한 응용 프로그램 [!INCLUDE[TLA#tla_emf](../../../../includes/tlasharptla-emf-md.md)] 기반 인쇄 합니다. 그러나 대부분의 XPS 기능과 향상 된 기능은 XPS 인쇄 경로 대상으로 하는 응용 프로그램에 사용할 수만 있습니다.  
  
 XPSDrv 기반 프린터를 사용할 수 있도록 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Windows Forms 응용 프로그램에서 XPS 프린터 드라이버 (XPSDrv)으로 변환 하도록 지원 하 고 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] xps 형식을 지정 합니다. XPSDrv 모델에 xp 변환기를 제공 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 형식이 되도록 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 응용 프로그램에서 인쇄할 수 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 문서. 에 대 한 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램을 변환 하는 xps [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 형식으로 자동으로 수행 됩니다 합니다 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> 및 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 의 메서드는 <xref:System.Windows.Xps.XpsDocumentWriter> 쓰기 작업의 대상 인쇄 대기열에 XPSDrv 드라이버가 없는 때마다 클래스입니다. (Windows Forms 응용 프로그램에서 인쇄할 수 없는 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 문서입니다.)  
  
 다음 그림에서는 인쇄 하위 시스템을 보여 주며 제공한 일부 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)], 소프트웨어 및 하드웨어 공급 업체에서 정의 하는 부분:  
  
 ![스크린샷은은 XPS 인쇄 시스템 보여 줍니다.](./media/printing-overview/xml-paper-specification-print-system.png)  
  
### <a name="basic-xps-printing"></a>기본 XPS 인쇄  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 기본 및 고급 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]를 둘 다 정의합니다. 광범위 한 인쇄 사용자 지정 또는 전체 XPS 기능에 대 한 액세스 필요 하지 않은 응용 프로그램 설정, 기본 인쇄 지원은 사용할 수 있습니다. 기본 인쇄 지원은 최소한의 구성이 필요하며 익숙한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 제공하는 인쇄 대화 상자 컨트롤을 통해 노출됩니다. 많은 XPS 기능은 경우 정책이이 간소화 된 인쇄 모델을 사용 하 여 사용할 수 있습니다.  
  
#### <a name="printdialog"></a>PrintDialog  
 합니다 <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> 컨트롤에 대 한 단일 진입점을 제공 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 구성 및 XPS 작업을 제출 합니다. 컨트롤을 인스턴스화하고 사용하는 방법에 대한 자세한 내용은 [인쇄 대화 상자 호출](how-to-invoke-a-print-dialog.md)을 참조하세요.  
  
### <a name="advanced-xps-printing"></a>고급 XPS 인쇄  
 XPS 기능의 전체 집합에 액세스 하려면 고급 인쇄 API는 사용 해야 합니다. 여러 관련 API는 아래에 자세히 설명 되어 있습니다. XPS 인쇄 경로 Api의 전체 목록은 참조 하세요. 합니다 <xref:System.Windows.Xps> 고 <xref:System.Printing> 네임 스페이스 참조 합니다.  
  
#### <a name="printticket-and-printcapabilities"></a>PrintTicket 및 PrintCapabilities  
 합니다 <xref:System.Printing.PrintTicket> 고 <xref:System.Printing.PrintCapabilities> 클래스 고급 XPS 기능의 기반이 됩니다. 두 유형의 개체는 모두 데이터 정렬, 양면 인쇄, 스테이플링 등과 같은 인쇄 지향 기능의 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 형식 구조체입니다. 이러한 구조체는 인쇄 스키마에서 정의됩니다. <xref:System.Printing.PrintTicket>은 인쇄 작업을 처리하는 방법을 프린터에 지시합니다. <xref:System.Printing.PrintCapabilities> 클래스는 프린터 기능을 정의합니다. 프린터 기능 쿼리를 통해 프린터에서 지원하는 기능을 완전히 활용하는 <xref:System.Printing.PrintTicket>을 만들 수 있습니다. 마찬가지로, 지원되지 않는 기능을 방지할 수 있습니다.  
  
 다음 예제에서는 코드를 사용하여 프린터의 <xref:System.Printing.PrintCapabilities>를 쿼리하고 <xref:System.Printing.PrintTicket>을 만드는 방법을 보여 줍니다.  
  
 [!code-cpp[xpscreate#PrinterCapabilities](~/samples/snippets/cpp/VS_Snippets_Wpf/XpsCreate/CPP/XpsCreate.cpp#printercapabilities)]
 [!code-csharp[xpscreate#PrinterCapabilities](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsCreate/CSharp/XpsCreate.cs#printercapabilities)]
 [!code-vb[xpscreate#PrinterCapabilities](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsCreate/visualbasic/xpscreate.vb#printercapabilities)]  
  
#### <a name="printserver-and-printqueue"></a>PrintServer 및 PrintQueue  
 <xref:System.Printing.PrintServer> 클래스는 네트워크 인쇄 서버를 나타내고 <xref:System.Printing.PrintQueue> 클래스는 프린터 및 프린터와 연결된 출력 작업 큐를 나타냅니다. 함께 이러한 Api 서버의 인쇄 작업의 고급 관리를 허용 합니다. <xref:System.Printing.PrintServer> 또는 해당 파생 클래스 중 하나는 <xref:System.Printing.PrintQueue>를 관리하는 데 사용됩니다. <xref:System.Printing.PrintQueue.AddJob%2A> 메서드는 새 인쇄 작업을 대기열에 삽입하는 데 사용됩니다.  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Printing.LocalPrintServer>를 만들고 기본 <xref:System.Printing.PrintQueue>에 액세스하는 방법을 보여 줍니다.  
  
 [!code-csharp[xpsprint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[xpsprint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
#### <a name="xpsdocumentwriter"></a>XpsDocumentWriter  
 <xref:System.Windows.Xps.XpsDocumentWriter>, 많은 합니다 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> 및 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 메서드를 XPS 문서를 쓰는 데 사용 되는 <xref:System.Printing.PrintQueue>합니다. 예를 들어 합니다 <xref:System.Windows.Xps.XpsDocumentWriter.Write%28System.Windows.Documents.FixedPage%2CSystem.Printing.PrintTicket%29> 메서드는 XPS 문서 출력 데 및 <xref:System.Printing.PrintTicket> 동기적으로 합니다. 합니다 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%28System.Windows.Documents.FixedDocument%2CSystem.Printing.PrintTicket%29> 메서드 출력 XPS 문서를 사용 하 고 <xref:System.Printing.PrintTicket> 비동기적으로 합니다.  
  
 다음 예제에서는 코드를 사용하여 <xref:System.Windows.Xps.XpsDocumentWriter>를 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[XpsPrint#PrintQueueSnip](~/samples/snippets/csharp/VS_Snippets_Wpf/XpsPrint/CSharp/XpsPrintHelper.cs#printqueuesnip)]
 [!code-vb[XpsPrint#PrintQueueSnip](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XpsPrint/visualbasic/xpsprinthelper.vb#printqueuesnip)]  
  
 <xref:System.Printing.PrintQueue.AddJob%2A> 메서드는 다양한 인쇄 방법도 제공합니다. [프로그래밍 방식으로 XPS 파일 인쇄](how-to-programmatically-print-xps-files.md)를 참조하세요. 참조하세요.  
  
<a name="GDI_Print_Path_intro"></a>   
## <a name="gdi-print-path"></a>GDI 인쇄 경로  
 하는 동안 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램은 XPS 인쇄 경로 고유 하 게 지원 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 되며 Windows Forms 응용 프로그램 일부 XPS 기능의 활용할 수도 수 있습니다. XPS 프린터 드라이버 (XPSDrv)으로 변환할 수 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 기반 XPS 형식으로 출력 합니다. 고급 시나리오에서는 콘텐츠의 사용자 지정 변환이 사용 하 여 지원 되는 [Microsoft XPS 문서 변환기 (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)합니다. 마찬가지로 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 응용 프로그램에 출력할 수 있습니다를 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 중 하나를 호출 하 여 인쇄 경로 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> 또는 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 의 메서드는 <xref:System.Windows.Xps.XpsDocumentWriter> 클래스 고 비 XpsDrv 프린터를 대상으로 지정 인쇄 대기열입니다.  

XPS 기능, 지원 또는 현재 필요 하지 않은 응용 프로그램에 대 한 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 인쇄 경로 그대로 유지 됩니다.  
  
- 대 한 추가 참조 자료에 대 한 합니다 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 인쇄 경로 및 다양 한 XPS 변환 옵션을 참조 하십시오 [Microsoft XPS 문서 변환기 (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-) 하 고 [XPSDrv 프린터 드라이버](/windows-hardware/drivers/print/xpsdrv-printer-drivers)합니다.  
  
<a name="XPS_Driver_Model_intro"></a>   
## <a name="xpsdrv-driver-model"></a>XPSDrv 드라이버 모델  
 XPS 인쇄 경로 xps 인쇄 하는 경우 기본 인쇄 스풀 형식으로 XPS를 사용 하 여 스풀러 효율성을 향상 시킵니다-프린터 또는 드라이버를 사용 하도록 설정 합니다. 간소화된 스풀링 프로세스에서는 문서가 스풀링되기 전에 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] 데이터 파일과 같은 중간 스풀 파일을 생성할 필요가 없습니다. 작은 스풀 파일 크기를 통해 XPS 인쇄 경로 네트워크 트래픽이 감소 하 고 인쇄 성능을 향상 시킬 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)]는 응용 프로그램 출력을 렌더링 서비스에 대한 일련의 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 호출로 나타내는 닫힌 형식입니다. 와 달리 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)], XPS 스풀 형식은 XPS 기반 프린터 드라이버 (XPSDrv)에 출력할 때 해석 없이 실제 문서를 나타냅니다. 드라이버가 형식의 데이터에 대해 직접 작동할 수 있습니다. 이 기능은 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] 파일과 [!INCLUDE[TLA2#tla_gdi](../../../../includes/tla2sharptla-gdi-md.md)] 기반 인쇄 드라이버를 사용할 때 필요한 데이터 및 색 공간 변환을 제거합니다.  
  
 그러나 비교할 XPS 프린터 드라이버 (XPSDrv)를 대상으로 하는 XPS 문서를 사용 하는 경우 스풀 파일 크기가 감소 일반적으로 해당 [!INCLUDE[TLA2#tla_emf](../../../../includes/tla2sharptla-emf-md.md)] 있습니다 가지 예외:  
  
- 매우 복잡하거나 다중 계층이거나 비효율적으로 작성된 벡터 그래픽은 동일한 그래픽의 비트맵 버전보다 클 수 있습니다.  
  
- 화면 표시를 위해 XPS 파일은 디바이스 글꼴과 컴퓨터 기반 글꼴을 포함하는 반면 GDI 스풀 파일은 디바이스 글꼴을 포함하지 않습니다. 그러나 두 종류의 글꼴은 모두 하위 집합으로 지정되며(아래 참조), 프린터 드라이버가 파일을 프린터로 전송하기 전에 디바이스 글꼴을 제거할 수 있습니다.  
  
 스풀 크기 감소는 다음과 같은 여러 메커니즘을 통해 수행됩니다.  
  
- **글꼴 하위 집합**. 실제 문서 내에서 사용 되는 문자만 XPS 파일에 저장 됩니다.  
  
- **고급 그래픽 지원**. 투명도 및 그라데이션 기본 형식에 대한 기본 지원을 통해 [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] 문서에서 콘텐츠의 래스터화를 방지합니다.  
  
- **공용 리소스 식별**. 여러 번 사용되는 리소스(예: 회사 로고를 나타내는 이미지)는 공유 리소스로 처리되며 한 번만 로드됩니다.  
  
- **ZIP 압축**. 모든 XPS 문서는 ZIP 압축을 사용 합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Controls.PrintDialog>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.PrintQueue>
- [방법 항목](printing-how-to-topics.md)
- [WPF의 문서](documents-in-wpf.md)
- [XPS 문서](/windows/desktop/printdocs/documents)
- [문서 serialization 및 저장소](document-serialization-and-storage.md)
- [Microsoft XPS 문서 변환기 (MXDC)](/windows/desktop/printdocs/microsoft-xps-document-converter--mxdc-)
