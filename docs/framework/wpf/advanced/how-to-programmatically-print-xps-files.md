---
title: '방법: 프로그래밍 방식으로 XPS 파일 인쇄'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- printing XPS files programmatically [WPF]
- XPS files [WPF], printing programmatically
ms.assetid: 0b1c0a3f-b19e-43d6-bcc9-eb3ec4e555ad
ms.openlocfilehash: cc86a7e7c6a816af37c3d063825ed62583afa78a
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966994"
---
# <a name="how-to-programmatically-print-xps-files"></a>방법: 프로그래밍 방식으로 XPS 파일 인쇄

<xref:System.Printing.PrintQueue.AddJob%2A> 메서드의 오버 로드 하나를 사용 하 여 <xref:System.Windows.Controls.PrintDialog>을 열지 않고도 XPS (XML Paper Specification) 파일을 인쇄할 수 있습니다. 또는 원칙적으로 모든 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)].

많은 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A?displayProperty=nameWithType> 및 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A?displayProperty=nameWithType> 방법을 사용 하 여 XPS 파일을 인쇄할 수도 있습니다. 자세한 내용은 [XPS 문서 인쇄](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90))를 참조 하세요.

XPS를 인쇄 하는 또 다른 방법은 <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A?displayProperty=nameWithType> 또는 <xref:System.Windows.Controls.PrintDialog.PrintVisual%2A?displayProperty=nameWithType> 방법을 사용 하는 것입니다. [인쇄 호출 대화 상자](how-to-invoke-a-print-dialog.md)를 참조하세요.

## <a name="example"></a>예제

3 매개 변수 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> 메서드를 사용 하는 주요 단계는 다음과 같습니다. 아래 예제에서 자세히 설명합니다.

1. 프린터가 XPSDrv 프린터인지 확인합니다. XPSDrv에 대 한 자세한 내용은 [인쇄 개요](printing-overview.md) 를 참조 하세요.

2. 프린터가 XPSDrv 프린터가 아닌 경우 스레드 아파트를 단일 스레드로 설정합니다.

3. 인쇄 서버 및 인쇄 대기열 개체를 인스턴스화합니다.

4. 작업 이름, 인쇄할 파일 및 프린터가 XPSDrv 프린터 인지 여부를 나타내는 <xref:System.Boolean> 플래그를 지정 하 여 메서드를 호출 합니다.

아래 예제에서는 모든 XPS 파일을 디렉터리에 배치 하는 방법을 보여 줍니다. 응용 프로그램에서 사용자에 게 디렉터리를 지정 하 라는 메시지를 표시 하지만 3 개의 매개 변수 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> 메서드에는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]필요 하지 않습니다. 이 파일은 전달할 수 있는 XPS 파일 이름 및 경로가 있는 모든 코드 경로에서 사용할 수 있습니다.

<xref:System.Printing.PrintQueue.AddJob%2A>의 3 개 매개 변수 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> 오버 로드는 <xref:System.Boolean> 매개 변수가 `false`될 때마다 단일 스레드 아파트에서 실행 되어야 합니다 .이는 XPSDrv가 아닌 프린터를 사용할 때 여야 합니다. 그러나 .NET의 기본 아파트 상태는 다중 스레드입니다. 이 예제에서 XPSDrv가 아닌 프린터를 가정하므로 이 기본값을 뒤집어야 합니다.

두 가지 방법으로 기본값을 변경할 수 있습니다. 한 가지 방법은 응용 프로그램의 `Main` 메서드 (일반적으로 "`static void Main(string[] args)`")의 첫 번째 줄 바로 위에 <xref:System.STAThreadAttribute> (즉, "`[System.STAThreadAttribute()]`")를 추가 하는 것입니다. 그러나 대부분의 응용 프로그램에서는 `Main` 메서드에 다중 스레드 아파트 상태가 필요 하므로 두 번째 방법이 있습니다. 즉, 아파트 상태가 <xref:System.Threading.Thread.SetApartmentState%2A>를 사용 하 여 <xref:System.Threading.ApartmentState.STA>로 설정 된 별도의 스레드에서 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>에 대 한 호출을 추가 합니다. 아래 예제에서는 두 번째 방법을 사용합니다.

따라서 예제는 먼저 <xref:System.Threading.Thread> 개체를 인스턴스화하고 **Printxps** 메서드를 <xref:System.Threading.ThreadStart> 매개 변수로 전달 합니다. **Printxps** 메서드는이 예제 뒷부분에 정의 되어 있습니다. 그런 다음 스레드는 단일 스레드 아파트로 설정 됩니다. `Main` 메서드의 나머지 코드는 새 스레드를 시작합니다.

예제의 핵심은 `static`**BatchXPSPrinter.PrintXPS** 메서드에 있습니다. 인쇄 서버 및 큐를 만든 후 메서드는 사용자에 게 XPS 파일이 포함 된 디렉터리를 묻는 메시지를 표시 합니다. 디렉터리가 있는지 확인 한 후에 \*.xps 파일이 있는지 확인 한 후 메서드는 이러한 각 파일을 인쇄 큐에 추가 합니다. 이 예제에서는 프린터가 XPSDrv가 아닌 것으로 가정 하므로 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29> 메서드의 마지막 매개 변수에 `false`를 전달 합니다. 따라서 메서드는 파일의 XPS 태그를 프린터의 페이지 설명 언어로 변환 하려고 시도 하기 전에 유효성을 검사 합니다. 유효성 검사에 실패하면 예외가 throw됩니다. 예제 코드는 예외를 catch 하 고 사용자에 게 알리고 다음 XPS 파일 처리로 이동 합니다.

[!code-csharp[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/csharp/VS_Snippets_Wpf/BatchPrintXPSFiles/CSharp/Program.cs#batchprintxpsfiles)]
[!code-vb[BatchPrintXPSFiles#BatchPrintXPSFiles](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BatchPrintXPSFiles/visualbasic/program.vb#batchprintxpsfiles)]

XPSDrv 프린터를 사용하는 경우 마지막 매개 변수를 `true`로 설정할 수 있습니다. 이 경우 XPS는 프린터의 페이지 설명 언어 이기 때문에 메서드는 파일의 유효성을 검사 하거나 다른 페이지 설명 언어로 변환 하지 않고 파일을 프린터로 보냅니다. 디자인 타임에 응용 프로그램이 XPSDrv 프린터를 사용 하는지 여부를 잘 모르는 경우 응용 프로그램을 수정 하 여 <xref:System.Printing.PrintQueue.IsXpsDevice%2A> 속성을 읽고 검색 된 항목에 따라 분기할 수 있습니다.

Windows Vista 및 Microsoft .NET Framework 출시 후 즉시 사용할 수 있는 XPSDrv 프린터가 거의 없으므로 xpsdrv가 아닌 프린터를 XPSDrv 프린터로 위장 해야 할 수도 있습니다. 이렇게 하려면 애플리케이션을 실행하는 컴퓨터의 다음 레지스트리 키에 있는 파일의 목록에 Pipelineconfig.xml을 추가합니다.

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Environments\Windows NT x86\Drivers\Version-3\\ *\<PseudoXPSPrinter>* \DependentFiles

여기서 *\<PseudoXPSPrinter>* 는 인쇄 대기열입니다. 그런 다음 컴퓨터를 다시 부팅해야 합니다.

이 위장을 통해 예외를 발생 시 키 지 않고 <xref:System.Printing.PrintQueue.AddJob%28System.String%2CSystem.String%2CSystem.Boolean%29>의 최종 매개 변수로 `true`를 전달할 수 있지만, *\<pseudoxpsprinter> >* 는 XPSDrv 프린터가 아니기 때문에 가비지만 인쇄 됩니다.

> [!NOTE]
> 간단히 하기 위해 위의 예제에서는 파일이 XPS 임을 테스트 하는 \*.xps 확장명이 있는지를 사용 합니다. 그러나 XPS 파일에는이 확장이 필요 하지 않습니다. [Isxps (Isxps 규칙 도구)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100)) 는 파일에서 XPS 유효성을 검사 하는 한 가지 방법입니다.

## <a name="see-also"></a>참조

- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.AddJob%2A>
- <xref:System.Threading.ApartmentState>
- <xref:System.STAThreadAttribute>
- [XPS 문서](/windows/desktop/printdocs/documents)
- [XPS 문서 인쇄](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms771525(v=vs.90))
- [관리 되는 스레딩 및 관리 되지 않는 스레딩](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/5s8ee185(v=vs.100))
- [isXPS.exe(isXPS 규칙 도구)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aa348104(v=vs.100))
- [WPF의 문서](documents-in-wpf.md)
- [인쇄 개요](printing-overview.md)
