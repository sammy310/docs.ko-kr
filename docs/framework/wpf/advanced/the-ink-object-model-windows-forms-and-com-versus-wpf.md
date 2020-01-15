---
title: '잉크 개체 모델: Windows Forms/COM 및 WPF'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- enabling ink [WPF]
- InkCanvas control [WPF]
- ink object model [WPF]
- tablet pen [WPF], events [WPF]
- ink [WPF], enabling
- events [WPF], tablet pen
ms.assetid: 577835be-b145-4226-8570-1d309e9b3901
ms.openlocfilehash: 2c0d155d320bab2f0114280e962c8f2f0b559681
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636421"
---
# <a name="the-ink-object-model-windows-forms-and-com-versus-wpf"></a>잉크 개체 모델: Windows Forms/COM 및 WPF

기본적으로 디지털 잉크를 지 원하는 세 가지 플랫폼은 Tablet PC Windows Forms 플랫폼, Tablet PC COM 플랫폼 및 Windows Presentation Foundation (WPF) 플랫폼입니다.  Windows Forms 및 COM 플랫폼은 유사한 개체 모델을 공유 하지만 WPF 플랫폼의 개체 모델은 상당히 다릅니다.  이 항목에서는 한 개체 모델을 사용 하는 개발자가 다른 개체를 더 잘 이해할 수 있도록 상위 수준에서 차이점에 대해 설명 합니다.  
  
## <a name="enabling-ink-in-an-application"></a>응용 프로그램에서 잉크 사용  
 세 플랫폼 모두 개체와 컨트롤을 제공 하 여 응용 프로그램에서 태블릿 펜의 입력을 받을 수 있도록 합니다.  Windows Forms [및 COM](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) 플랫폼은 [microsoft.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) [InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) [,.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90))m m a. m m a.  [Microsoft](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) . a m a. m a. m a [.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90))  Microsoft.Ink.InkOverlay [및 사용자](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) 지정 컨트롤을 잉크 [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) 를 사용 하기 위해 기존 창에 연결할 수 있습니다.  
  
 WPF 플랫폼에는 <xref:System.Windows.Controls.InkCanvas> 컨트롤이 포함 되어 있습니다.  응용 프로그램에 <xref:System.Windows.Controls.InkCanvas>을 추가 하 고 즉시 잉크 수집을 시작할 수 있습니다. 사용자는 <xref:System.Windows.Controls.InkCanvas>를 사용 하 여 잉크를 복사 하 고, 선택 하 고, 크기를 조정할 수 있습니다.  <xref:System.Windows.Controls.InkCanvas>에 다른 컨트롤을 추가할 수 있으며, 사용자는 해당 컨트롤을 필기할 수도 있습니다.  <xref:System.Windows.Controls.InkPresenter>를 추가 하 고 해당 스타일러스 요소를 수집 하 여 잉크 사용 사용자 지정 컨트롤을 만들 수 있습니다.  
  
 다음 표에서는 응용 프로그램에서 잉크를 사용 하도록 설정 하는 방법에 대해 자세히 설명 합니다.  
  
|이 작업을 수행 하는 중...|WPF 플랫폼에서 ...|Windows Forms/COM 플랫폼에서 ...|  
|-----------------|--------------------------|------------------------------------------|  
|응용 프로그램에 잉크 사용 컨트롤 추가|[잉크 시작을](getting-started-with-ink.md)참조 하세요.|[자동 클레임 양식 샘플](/windows/desktop/tablet/auto-claims-form-sample) 을 참조 하세요.|  
|사용자 지정 컨트롤에서 잉크 사용|[잉크 입력 컨트롤 만들기](creating-an-ink-input-control.md)를 참조 하세요.|[잉크 클립보드 샘플](/windows/desktop/tablet/ink-clipboard-sample)을 참조 하세요.|  
  
## <a name="ink-data"></a>잉크 데이터  
 Windows Forms 및 COM 플랫폼에서, [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) [, microsoft](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)). .comom. .comom. [Microsoft.Ink.InkEdit](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552265(v=vs.90)).coma [는 각각](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) [microsoft 잉크나](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) 개체를 노출 합니다. [Microsoft](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) 잉크나 a 개체는 하나 이상의 [microsoft 잉크나](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) 개체에 대 한 데이터를 포함 하며 이러한 스트로크를 관리 하 고 조작 하는 공용 메서드 및 속성을 노출 합니다.  [Microsoft 잉크나](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) a 개체는 포함 된 스트로크의 수명을 관리 합니다. [Microsoft 잉크나](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) a 개체는 자신이 소유한 스트로크를 만들고 삭제 합니다.  각 [microsoft. m a. 스트로크](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) 는 부모 [microsoft.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) a m a. a m a. m a.  
  
 WPF 플랫폼에서 <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType> 클래스는 자체 수명을 소유 하 고 관리 합니다. <xref:System.Windows.Ink.Stroke> 개체 그룹은 <xref:System.Windows.Ink.StrokeCollection>에서 함께 수집할 수 있습니다 .이는 잉크의 적중 테스트, 지우기, 변환 및 직렬화와 같은 일반적인 잉크 데이터 관리 작업을 위한 메서드를 제공 합니다. <xref:System.Windows.Ink.Stroke>은 언제 든 지 0 개 이상의 <xref:System.Windows.Ink.StrokeCollection> 개체에 속할 수 있습니다.  [Microsoft 잉크나](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) 개체를 포함 하는 대신 <xref:System.Windows.Controls.InkCanvas> 및 <xref:System.Windows.Controls.InkPresenter>에 <xref:System.Windows.Ink.StrokeCollection?displayProperty=nameWithType>포함 됩니다.  
  
 다음 그림 쌍은 잉크 데이터 개체 모델을 비교 합니다.  Windows Forms 및 COM 플랫폼에서 [microsoft](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583670(v=vs.90)) 잉크나 개체는 [microsoft](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552692(v=vs.90)) 잉크나 개체의 수명을 제한 하 고 스타일러스 패킷은 개별 스트로크에 속합니다.  다음 그림에 표시 된 것 처럼 둘 이상의 스트로크가 동일한 [DrawingAttributes](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583636(v=vs.90)) 개체를 참조할 수 있습니다.  
  
 ![COM&#47;Winforms에 대 한 잉크 개체 모델의 다이어그램입니다.](./media/ink-inkownsstrokes.png "Ink_InkOwnsStrokes")  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 각 <xref:System.Windows.Ink.Stroke?displayProperty=nameWithType>는 특정 항목에 대 한 참조가 있는 경우 존재 하는 공용 언어 런타임 개체입니다.  각 <xref:System.Windows.Ink.Stroke>는 <xref:System.Windows.Input.StylusPointCollection> 및 <xref:System.Windows.Ink.DrawingAttributes?displayProperty=nameWithType> 개체 (공용 언어 런타임 개체 이기도)를 참조 합니다.  
  
 ![WPF에 대 한 잉크 개체 모델의 다이어그램입니다.](./media/ink-wpfinkobjectmodel.png "Ink_WPFInkObjectModel")  
  
 다음 표에서는 WPF 플랫폼과 Windows Forms 및 COM 플랫폼에서 몇 가지 일반적인 작업을 수행 하는 방법을 비교 합니다.  
  
|태스크|Windows Presentation Foundation|Windows Forms 및 COM|  
|----------|-------------------------------------|---------------------------|  
|잉크 저장|<xref:System.Windows.Ink.StrokeCollection.Save%2A>|[Microsoft.Ink.Ink.Save](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571335(v=vs.90))|  
|잉크 로드|<xref:System.Windows.Ink.StrokeCollection.%23ctor%2A> 생성자를 사용 하 여 <xref:System.Windows.Ink.StrokeCollection>를 만듭니다.|[Microsoft.Ink.Ink.Load](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms569609(v=vs.90))|  
|적중 테스트|<xref:System.Windows.Ink.StrokeCollection.HitTest%2A>|[Microsoft.Ink.Ink.HitTest](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571330(v=vs.90))|  
|잉크 복사|<xref:System.Windows.Controls.InkCanvas.CopySelection%2A>|[Microsoft.Ink.Ink.ClipboardCopy](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571316(v=vs.90))|  
|잉크 붙여넣기|<xref:System.Windows.Controls.InkCanvas.Paste%2A>|[Microsoft.Ink.Ink.ClipboardPaste](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms571318(v=vs.90))|  
|스트로크 컬렉션의 사용자 지정 속성 액세스|<xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A> (속성은 내부적으로 저장 되 고 <xref:System.Windows.Ink.StrokeCollection.AddPropertyData%2A>, <xref:System.Windows.Ink.StrokeCollection.RemovePropertyData%2A>및 <xref:System.Windows.Ink.StrokeCollection.ContainsPropertyData%2A>를 통해 액세스 됨)|[Microsoft 잉크나 속성을](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms582214(v=vs.90)) 사용 합니다.|  
  
### <a name="sharing-ink-between-platforms"></a>플랫폼 간 잉크 공유  
 플랫폼에는 잉크 데이터에 대 한 다양 한 개체 모델이 있지만 플랫폼 간에 데이터를 공유 하는 것이 매우 쉽습니다. 다음 예제에서는 Windows Forms 응용 프로그램에서 잉크를 저장 하 고 Windows Presentation Foundation 응용 프로그램에 잉크를 로드 합니다.  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#SaveWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewinforms)]
[!code-vb[WinFormWPFInk#SaveWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewinforms)]  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#LoadWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwpf)]
[!code-vb[WinFormWPFInk#LoadWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwpf)]  
  
 다음 예제에서는 Windows Presentation Foundation 응용 프로그램에서 잉크를 저장 하 고 Windows Forms 응용 프로그램에 잉크를 로드 합니다.  
  
 [!code-csharp[WinFormWPFInk#UsingWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwpf)]
 [!code-vb[WinFormWPFInk#UsingWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwpf)]  
[!code-csharp[WinFormWPFInk#SaveWPF](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#savewpf)]
[!code-vb[WinFormWPFInk#SaveWPF](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#savewpf)]  
  
 [!code-csharp[WinFormWPFInk#UsingWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#usingwinforms)]
 [!code-vb[WinFormWPFInk#UsingWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#usingwinforms)]  
[!code-csharp[WinFormWPFInk#LoadWinforms](~/samples/snippets/csharp/VS_Snippets_Wpf/WinformWPFInk/CSharp/Program.cs#loadwinforms)]
[!code-vb[WinFormWPFInk#LoadWinforms](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WinformWPFInk/VisualBasic/Module1.vb#loadwinforms)]
## <a name="events-from-the-tablet-pen"></a>태블릿 펜의 이벤트  

 사용자가 펜 [데이터를 입력](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90))하면 WINDOWS FORMS 및 COM 플랫폼의 [InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))및 [microsoft](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583740(v=vs.90)) 에 대 한 이벤트를 수신 합니다. InkCollector [또는 컨트롤](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms552322(v=vs.90)) 에 연결 되어 있으며 [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) , 태블릿 입력 데이터에 의해 발생 한 이벤트를 구독할 수 있는 경우. 이러한 이벤트가 발생 하는 스레드는 이벤트가 펜으로 발생 하는지, 마우스를 사용 하 여 발생 하는지 아니면 프로그래밍 방식으로 발생 하는지에 따라 달라 집니다. 이러한 이벤트와 관련 된 스레딩에 대 한 자세한 내용은 [이벤트를 발생 시킬 수 있는](/windows/desktop/tablet/threads-on-which-an-event-can-fire) [일반 스레딩 고려 사항](/windows/desktop/tablet/general-threading-considerations) 및 스레드를 참조 하세요.  
  
 Windows Presentation Foundation 플랫폼에서 <xref:System.Windows.UIElement> 클래스는 펜 입력에 대 한 이벤트를 포함 합니다. 즉, 모든 컨트롤이 스타일러스 이벤트의 전체 집합을 노출 합니다.  스타일러스 이벤트는 터널링/버블링 이벤트 쌍을 가지 며 응용 프로그램 스레드에서 항상 발생 합니다.  자세한 내용은 [라우트된 이벤트 개요](routed-events-overview.md)합니다.  
  
 다음 다이어그램에서는 스타일러스 이벤트를 발생 시키는 클래스의 개체 모델을 비교 하 여 보여 줍니다. Windows Presentation Foundation 개체 모델은 터널링 이벤트의 상응 항목이 아닌 버블링 이벤트만 표시 합니다.  
  
 ![WPF vs Winforms의 스타일러스 이벤트 다이어그램](./media/ink-stylusevents.png "Ink_StylusEvents")  
  
## <a name="pen-data"></a>펜 데이터  
 세 플랫폼은 모두 태블릿 펜에서 제공 되는 데이터를 가로채 조작할 수 있는 방법을 제공 합니다.  Windows Forms 및 COM 플랫폼에서이는 [StylusInput](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90))을 만들고, 창 또는 컨트롤을 연결 하 고, StylusInput를 구현 하는 클래스를 만드는 것입니다 .이를 위해 [StylusInput.](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575194(v=vs.90)) IStylusSyncPlugin 또는 [Microsoft.StylusInput.IStylusSyncPlugin](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms575201(v=vs.90)) 그런 다음 사용자 지정 플러그 인이 [StylusInput](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90))의 플러그 인 컬렉션에 추가 됩니다. 이 개체 모델에 대 한 자세한 내용은 [StylusInput api의 아키텍처](/windows/desktop/tablet/architecture-of-the-stylusinput-apis)를 참조 하세요.  
  
 WPF 플랫폼에서 <xref:System.Windows.UIElement> 클래스는 [StylusInput](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms585724(v=vs.90))에 대 한 디자인과 비슷한 플러그 인 컬렉션을 노출 합니다.  펜 데이터를 가로채려 면 <xref:System.Windows.Input.StylusPlugIns.StylusPlugIn>에서 상속 하는 클래스를 만들고이 개체를 <xref:System.Windows.UIElement>의 <xref:System.Windows.UIElement.StylusPlugIns%2A> 컬렉션에 추가 합니다. 이 상호 작용에 대 한 자세한 내용은 [스타일러스에서 입력 가로채기](intercepting-input-from-the-stylus.md)를 참조 하세요.  
  
 모든 플랫폼에서 스레드 풀은 스타일러스 이벤트를 통해 잉크 데이터를 받아서 응용 프로그램 스레드로 보냅니다.  COM 및 Windows 플랫폼의 스레딩에 대 한 자세한 내용은 [StylusInput api에 대 한 스레딩 고려 사항](/windows/desktop/tablet/threading-considerations-for-the-stylusinput-apis)을 참조 하세요.  Windows 프레젠테이션 소프트웨어의 스레딩에 대 한 자세한 내용은 [잉크 스레딩 모델](the-ink-threading-model.md)을 참조 하세요.  
  
 다음 그림에서는 펜 스레드 풀에서 펜 데이터를 수신 하는 클래스의 개체 모델을 비교 합니다.  
  
 ![StylusPlugin 모델 WPF vs Winforms의 다이어그램입니다.](./media/ink-stylusplugins.png "Ink_StylusPlugins")
