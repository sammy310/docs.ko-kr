---
title: 스레딩 모델
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text on buttons [WPF], updating
- message processing [WPF], nested
- blocking operations [WPF]
- Common Language Runtime (CLR), locking mechanism
- locking mechanism of Common Language Runtime (CLR)
- threading model [WPF]
- Word [WPF], spelling checking
- button text [WPF], updating
- spelling checking in Word [WPF]
- asynchronous behavior [WPF], exposing
- nested message processing [WPF]
- reentrancy [WPF]
ms.assetid: 02d8fd00-8d7c-4604-874c-58e40786770b
ms.openlocfilehash: 0bcb0e7369345aaae39d99a005a07304aaad7043
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200352"
---
# <a name="threading-model"></a>스레딩 모델
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 개발자가 스레딩의 어려움을 해결에서 저장 하도록 설계 되었습니다. 결과적으로 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개발자가 둘 이상의 스레드를 사용 하는 인터페이스를 작성할 필요가 없습니다. 다중 스레드 프로그램은 복잡하고 디버그하기 어려우므로 단일 스레드 솔루션이 있을 경우 피해야 합니다.  
  
 그러나 아무리 얼마나 잘 구성 되었는지, 아니요 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] framework 적이 모든 종류의 문제에 대 한 단일 스레드 솔루션을 제공 하는 일을 할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 가 근접 하는 여러 스레드가 개선 하는 상황도 있습니다 하지만 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 응답성 이나 응용 프로그램 성능. 일부 배경 자료를 설명한 후 이 문서에서는 이러한 상황 중 일부를 살펴보고 몇몇 하위 수준 세부 정보에 대한 설명으로 마무리 짓습니다.  

> [!NOTE]
>  이 항목에서는 사용 하 여 스레딩을 설명 된 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 메서드 비동기 호출에 대 한 합니다. 또한 호출 하 여 비동기 호출을 만들 수는 <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> 메서드를 사용 하는 <xref:System.Action> 또는 <xref:System.Func%601> 매개 변수로 합니다.  <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> 메서드가 반환 되는 <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>, 있는 <xref:System.Windows.Threading.DispatcherOperation.Task%2A> 속성입니다. 사용할 수는 `await` 키워드 중 하나를 사용 합니다 <xref:System.Windows.Threading.DispatcherOperation> 또는 연결 된 <xref:System.Threading.Tasks.Task>합니다. 동기적으로 대기 해야 하는 경우는 <xref:System.Threading.Tasks.Task> 에서 반환 하는 <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>를 호출 합니다 <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> 확장 메서드.  호출 <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType> 교착 상태가 발생 합니다. 사용에 대 한 자세한 내용은 <xref:System.Threading.Tasks.Task> 비동기 작업을 수행 하려면 작업 병렬 처리를 참조 하세요.  합니다 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 메서드 역시 오버 로드는 <xref:System.Action> 또는 <xref:System.Func%601> 매개 변수로 합니다.  사용할 수는 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 대리자를 전달 하 여 호출 하는 메서드를 동기 <xref:System.Action> 또는 <xref:System.Func%601>합니다.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>개요 및 디스패처  
 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 2 개의 스레드가 있는 응용 프로그램 시작: 렌더링 처리 및 관리 하기 위한 다른 하나는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. 렌더링 스레드는 효과적으로 하는 동안 백그라운드에서 실행 된 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드 입력을 받고, 이벤트를 처리, 화면에 그리는 및 응용 프로그램 코드를 실행 합니다. 대부분의 응용 프로그램 사용 하 여 단일 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 이지만 일부 상황에서 몇 가지를 사용 하 여 스레드입니다. 나중에 예제를 통해 이를 설명하겠습니다.  
  
 합니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 라는 개체 내부의 항목을 작업 하는 스레드가 대기를 <xref:System.Windows.Threading.Dispatcher>입니다. <xref:System.Windows.Threading.Dispatcher>는 우선 순위에 따라 작업 항목을 선택하고 각 작업 항목을 완료할 때까지 실행합니다.  모든 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에 하나 이상의 권한이 있어야 <xref:System.Windows.Threading.Dispatcher>, 및 각 <xref:System.Windows.Threading.Dispatcher> 정확히 하나의 스레드에서 작업 항목을 실행할 수 있습니다.  
  
 친숙 하 게 응답 응용 프로그램 빌드를 최대화 하는 것을 <xref:System.Windows.Threading.Dispatcher> 처리량을 작업 항목을 작게 유지 합니다. 이 방법에서는 항목이 얻지 못하게에 부실는 <xref:System.Windows.Threading.Dispatcher> 큐 처리를 위해 대기 합니다. 입력과 응답 간의 인식할 수 있는 지연으로 인해 사용자가 불편해질 수 있습니다.  
  
 다음 방법을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램이 큰 작업을 처리 해야 할까요? 코드에 큰 계산을 포함하거나 몇몇 원격 서버에서 데이터베이스를 쿼리해야 하면 어떻게 될까요? 별도 스레드에서 두면 큰 작업을 처리할 대답은 일반적으로 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가의 항목에는 <xref:System.Windows.Threading.Dispatcher> 큐입니다. 큰 작업이 완료 되 면 해당 결과 보고할 수 있어 다시는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드를 표시 합니다.  
  
 지금까지 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 허용 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 만든 스레드에서 액세스할 수 있습니다. 즉, 일부 장기 실행 작업을 처리하는 백그라운드 스레드는 작업이 완료될 때 입력란을 업데이트할 수 없습니다. [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 무결성을 보장 하려면이 작업을 수행 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 구성 요소입니다. 목록 상자의 콘텐츠가 그리는 동안 백그라운드 스레드를 통해 업데이트되면 목록 상자가 이상하게 표시될 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이 조정을 적용 하는 기본 제공 상호 배제 메커니즘을 있습니다. 대부분의 클래스 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서 파생 <xref:System.Windows.Threading.DispatcherObject>합니다. 생성 시를 <xref:System.Windows.Threading.DispatcherObject> 에 대 한 참조를 저장 합니다 <xref:System.Windows.Threading.Dispatcher> 현재 실행 중인 스레드에 연결 합니다. 실제로 <xref:System.Windows.Threading.DispatcherObject> 만든 스레드를 사용 하 여 연결 합니다. 프로그램 실행 중에 <xref:System.Windows.Threading.DispatcherObject> 해당 공용을 호출할 수 <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 메서드. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 검사는 <xref:System.Windows.Threading.Dispatcher> 현재 스레드와 연결 된와 비교는 <xref:System.Windows.Threading.Dispatcher> 생성 중에 저장 된 참조입니다. 일치 하지 않으면 <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 예외를 throw 합니다. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 에 속한 모든 메서드의 시작 부분에서 호출 될 것을 <xref:System.Windows.Threading.DispatcherObject>입니다.  
  
 경우에 하나의 스레드를 수정할 수는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 사용자를 사용 하 여 백그라운드 스레드 상호 작용? 백그라운드 스레드를 요청할 수 있습니다는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드를 대신 하 여 작업을 수행 합니다. 와 작업 항목을 등록 하 여 수행 합니다 <xref:System.Windows.Threading.Dispatcher> 의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. <xref:System.Windows.Threading.Dispatcher> 클래스는 작업 항목을 등록 하는 두 가지 방법을 제공 합니다. <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 및 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>합니다. 메서드는 둘 다 대리자 실행을 예약합니다. <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 동기 호출 – 즉, 될 때까지 반환 하지 않기를 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 실제로 대리자 실행을 완료 합니다. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 비동기를 즉시 반환 합니다.  
  
 <xref:System.Windows.Threading.Dispatcher> 우선 순위별로 큐에 있는 요소를 정렬 합니다. 에 요소를 추가 하는 경우 지정 될 수 있는 10 개의 수준이 있습니다를 <xref:System.Windows.Threading.Dispatcher> 큐입니다. 이러한 우선 순위에서 유지 관리는 <xref:System.Windows.Threading.DispatcherPriority> 열거형입니다. 에 대 한 자세한 정보 <xref:System.Windows.Threading.DispatcherPriority> 수준에서 찾을 수 있습니다는 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] 설명서.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>실행 중인 스레드: 샘플  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>장기 실행 계산이 포함된 단일 스레드 애플리케이션  
 대부분의 [!INCLUDE[TLA#tla_gui#plural](../../../../includes/tlasharptla-guisharpplural-md.md)] 사용자 상호 작용에 대 한 응답으로 생성 된 이벤트를 기다리는 동안 유휴 시간 중 많은 부분을 소비 합니다. 신중 하 게 프로그래밍이 유휴 시간 없이 사용할 수 있습니다을 생산적으로의 응답성에 영향을 주지는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]합니다. 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스레딩 모델에서 발생 하는 작업을 중단에 대 한 입력을 허용 하지 않습니다는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 즉, 반환 해야 합니다 <xref:System.Windows.Threading.Dispatcher> 입력된 이벤트 쓸모가 없어지기 전에 보류 중인 프로세스를 주기적으로 합니다.  
  
 다음 예제를 참조하세요.  
  
 ![소수의 스레딩 보여 주는 스크린샷.](./media/threading-model/threading-prime-numbers.png)  
  
 이 간단한 애플리케이션은 3부터 위쪽으로 계산하여 소수를 검색합니다. 클릭할 때 합니다 **시작** 단추 검색이 시작 됩니다. 프로그램이 소수를 찾으면 검색 결과로 사용자 인터페이스를 업데이트합니다. 이때 사용자가 검색을 중지할 수 있습니다.  
  
 간단한 방법이지만 소수 검색이 영원히 계속될 수 있는 문제가 있습니다.  제공 되지 않습니다 단추의 click 이벤트 처리기 내에서 전체 검색을 처리 한 경우는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 다른 이벤트를 처리 하는 스레드입니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 입력 또는 프로세스에 응답할 수는 메시지입니다. 다시 표시되지 않으며 단추 클릭에 응답하지 않습니다.  
  
 소수 검색을 별도의 스레드에서 수행할 수 있지만 이 경우 동기화 문제를 처리해야 합니다. 단일 스레드 방법을 통해 발견된 가장 큰 소수를 나열하는 레이블을 직접 업데이트할 수 있습니다.  
  
 작업을 관리 하기 쉬운 청크로 계산의 경우, 주기적으로를 반환할 수 있습니다는 <xref:System.Windows.Threading.Dispatcher> 및 이벤트를 처리 합니다. 제공할 수 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다시 표시 되 고 입력을 처리할 수 있습니다.  
  
 계산과 이벤트 처리 간에 처리 시간을 분할 하는 가장 좋은 방법은 계산을 관리 하는 것은 <xref:System.Windows.Threading.Dispatcher>합니다. 사용 하 여 합니다 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 메서드를에서 소수 검사를 예약할 수 있습니다 동일한 큐 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 이벤트에서 가져온 것입니다. 예제에서는 단일 소수 검사를 한 번만 예약합니다. 소수 검사가 완료된 후 즉시 다음 검사를 예약합니다. 보류 중인 설정한 후에 진행 되는이 확인 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 이벤트가 처리 된 합니다.  
  
 ![디스패처 큐를 보여 주는 스크린샷.](./media/threading-model/threading-dispatcher-queue.png)  
  
 [!INCLUDE[TLA#tla_word](../../../../includes/tlasharptla-word-md.md)] 이 메커니즘을 사용 하 여 맞춤법 검사를 수행 합니다. 유휴 시간을 사용 하 여 백그라운드에서 이루어집니다 맞춤법 검사는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 코드를 살펴보겠습니다.  
  
 다음 예제에서는 사용자 인터페이스를 만드는 XAML을 보여 줍니다.  
  
 [!code-xaml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 다음 예제에서는 코드 숨김을 보여 줍니다.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 다음 예제에서는 이벤트의 이벤트 처리기는 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 텍스트를 업데이트 하는 것 외에도 합니다 <xref:System.Windows.Controls.Button>,이 처리기는 대리자를 추가 하 여 첫 번째 소수 검사를 예약 하는 일을 담당 합니다 <xref:System.Windows.Threading.Dispatcher> 큐입니다. 이 이벤트 처리기가 해당 작업을 완료 한 후 따라는 <xref:System.Windows.Threading.Dispatcher> 이 대리자 실행을 선택 합니다.  
  
 앞에서 설명한 것 처럼 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 되는 <xref:System.Windows.Threading.Dispatcher> 대리자 실행을 예약 하는 데 사용 되는 멤버입니다. 선택이 경우에 <xref:System.Windows.Threading.DispatcherPriority.SystemIdle> 우선 순위입니다. <xref:System.Windows.Threading.Dispatcher> 처리 하는 데 중요 한 이벤트가 없을 경우에이 대리자를 실행 합니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 응답성이 숫자 검사 보다 더 중요 합니다. 또한 숫자 검사 루틴을 표현하는 새 대리자를 전달합니다.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 이 메서드는 다음 홀수가 소수인지 확인합니다. 메서드를 직접 업데이트 소수인 경우는 `bigPrime`<xref:System.Windows.Controls.TextBlock> 해당 검색을 반영 하도록 합니다. 구성 요소를 만드는 데 사용된 같은 스레드에서 계산이 수행되므로 이 작업을 수행할 수 있습니다. 계산에 대 한 별도 스레드를 사용 하도록 선택한 경우를 할 것 더 복잡 한 동기화 메커니즘을 사용 하 고 업데이트를 실행 합니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 이 상황은 다음에 살펴보겠습니다.  
  
 이 샘플에 대 한 전체 소스 코드에 대 한 참조를 [장기 실행 계산 샘플을 사용 하 여 단일 스레드 응용 프로그램](https://go.microsoft.com/fwlink/?LinkID=160038)  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>백그라운드 스레드를 사용하여 차단 작업 처리  
 그래픽 애플리케이션에서 차단 작업을 처리하는 것은 어려울 수 있습니다. 애플리케이션이 고정된 것처럼 보이므로 이벤트 처리기에서 차단 메서드를 호출하려고 하지 않습니다. 이러한 작업을 처리 하는 별도 스레드에서 사용할 수 있지만를 동기화 해야 작업을 완료 했습니다 합니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 직접 수정할 수 없습니다. 스레드를 [!INCLUDE[TLA2#tla_gui](../../../../includes/tla2sharptla-gui-md.md)] 작업자 스레드에서 합니다. 사용할 수 있습니다 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 또는 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 대리자에 삽입 하는 <xref:System.Windows.Threading.Dispatcher> 의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 결국 이러한 대리자는 수정할 수 있는 권한이 있는 실행 됩니다 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소입니다.  
  
 이 예제에서는 날씨 예보를 검색하는 원격 프로시저 호출을 모방합니다. 별도 작업자 스레드가이 호출을 실행 하는를 사용 하 여 및에서 업데이트 메서드를 예약 합니다 <xref:System.Windows.Threading.Dispatcher> 의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 완료 되 면 스레드입니다.  
  
 ![날씨 UI를 보여 주는 스크린샷.](./media/threading-model/threading-weather-ui.png)  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 다음은 주의할 몇 가지 세부 정보입니다.  
  
-   단추 처리기 만들기  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 단추가 클릭되면 시계 그림을 표시하고 애니메이션 효과를 주기 시작합니다. 단추를 사용하지 않습니다. 호출을 `FetchWeatherFromServer` 메서드는 새 스레드를 사용 하 고에서 반환 되는 경우 허용를 <xref:System.Windows.Threading.Dispatcher> 잠시 기다리면 일기 예보를 수집할 이벤트를 처리 하 합니다.  
  
-   날씨 페치  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 예제를 간단하게 유지하기 위해 이 예제에는 실제로 네트워킹 코드가 없습니다. 대신에 4초 동안 새 스레드를 절전 모드로 전환하여 네트워크 액세스 지연을 시뮬레이트합니다. 이 시간 동안 원래 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 여전히 실행 하 고 이벤트에 응답 합니다. 이 상황을 표시하기 위해 애니메이션을 계속 실행하고 [최소화] 및 [최대화] 단추도 계속 작동합니다.  
  
 지연이 끝나고 일기 예보 임의로 선택, 경우에 시간에 보고 하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 에 대 한 호출을 예약 하 여이 작업을 수행 `UpdateUserInterface` 에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 해당 스레드를 사용 하 여 스레드 <xref:System.Windows.Threading.Dispatcher>합니다. 날씨를 설명하는 문자열을 예약된 메서드 호출에 전달합니다.  
  
-   업데이트는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 경우는 <xref:System.Windows.Threading.Dispatcher> 에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 시간에 대 한 예약 된 호출을 실행 합니다 `UpdateUserInterface`합니다. 이 메서드는 시계 애니메이션을 중지하고 날씨를 설명할 이미지를 선택합니다. 이 이미지를 표시하고 "예보 페치" 단추를 복원합니다.  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>여러 Windows, 여러 스레드  
 일부 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 여러 개의 최상위 창이 필요 합니다. 한 스레드에서 완벽 하 게 적합 /<xref:System.Windows.Threading.Dispatcher> 더 나은 작업을 수행 하는 여러 windows 하지만 경우에 따라 여러 스레드를 관리 하는 조합 합니다. 특히 창 중 하나가 스레드를 독점할 가능성이 있는 경우 여러 스레드를 사용하는 것이 좋습니다.  
  
 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 탐색기가이 방식으로 작동 합니다. 새로운 각 탐색기 창은 원래 프로세스에 속하지만 독립 스레드의 제어를 기반으로 만들어집니다.  
  
 사용 하 여를 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Frame> 컨트롤을 웹 페이지를 표시할 수 있습니다. 간단한 쉽게 만들 수 있습니다 [!INCLUDE[TLA2#tla_ie](../../../../includes/tla2sharptla-ie-md.md)] 대체 합니다. 새 탐색기 창을 여는 중요한 기능으로 시작합니다. 사용자가 “새 창” 단추를 클릭하면 창 복사본을 별도의 스레드에서 시작합니다. 이렇게 하면 창 중 하나에 있는 장기 실행 또는 차단 작업으로 인해 모든 다른 창이 잠기지 않습니다.  
  
 실제로 웹 브라우저 모델에는 복잡한 자체 스레딩 모델이 있습니다. 대부분의 독자에게 친숙해야 하므로 이를 선택했습니다.  
  
 다음 예제에서는 코드를 보여 줍니다.  
  
 [!code-xaml[ThreadingMultipleBrowsers#ThreadingMultiBrowserXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml#threadingmultibrowserxaml)]  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsercodebehind)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsercodebehind)]  
  
 이 코드의 다음 스레딩 세그먼트는 이 컨텍스트에서 가장 흥미로운 부분입니다.  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowsernewwindow)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserNewWindow](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowsernewwindow)]  
  
 이 메서드는 “새 창” 단추가 클릭될 때 호출됩니다. 이 메서드는 새 스레드를 만들고 비동기적으로 시작합니다.  
  
 [!code-csharp[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingMultipleBrowsers/CSharp/Window1.xaml.cs#threadingmultibrowserthreadstart)]
 [!code-vb[ThreadingMultipleBrowsers#ThreadingMultiBrowserThreadStart](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingMultipleBrowsers/VisualBasic/Window1.xaml.vb#threadingmultibrowserthreadstart)]  
  
 이 메서드는 새 스레드의 시작점입니다. 이 스레드의 제어를 기반으로 새 창을 만듭니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 에서는 자동으로 새 <xref:System.Windows.Threading.Dispatcher> 새 스레드를 관리 합니다. 창을 작동 하기 위해 수행 해야 하는 시작 된 <xref:System.Windows.Threading.Dispatcher>합니다.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>기술 세부 정보 및 주의 사항  
  
### <a name="writing-components-using-threading"></a>스레딩을 사용하여 구성 요소 작성  
 구성 요소를 클라이언트에 비동기 동작을 노출할 수 있습니다 하는 방법에 대 한는 패턴을 설명 하는 Microsoft.NET Framework Developer's Guide (참조 [이벤트 기반 비동기 패턴 개요](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)). 예를 들어 패키지 한다고 가정해 보겠습니다는 `FetchWeatherFromServer` 재사용 가능 하 고 그래픽이 아닌 구성 요소에는 메서드. 다음 표준 Microsoft.NET Framework 패턴을 다음과 같이 표시 됩니다.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync` 사용 합니다 백그라운드 스레드 만들기와 같은 앞에서 설명한 기술 중 하나는 작업을 비동기적으로 수행 호출 스레드를 차단 하지 않습니다.  
  
 이 패턴의 가장 중요 한 부분 중 하나를 호출 합니다 *MethodName* `Completed` 메서드를 호출한 스레드와 동일한 스레드에서 *MethodName* `Async` 로 시작 하는 방법. 사용 하 여 수행할 수 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 를 저장 하 여 비교적 쉽게 <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>-다음 고 그래픽이 아닌 구성 요소 에서만에 사용 될 수 있지만 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 없는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 또는 [!INCLUDE[TLA#tla_aspnet](../../../../includes/tlasharptla-aspnet-md.md)] 프로그램입니다.  
  
 합니다 <xref:System.Windows.Threading.DispatcherSynchronizationContext> 클래스에는이 요구 사항을 해결-의 단순화 된 버전으로 생각해 <xref:System.Windows.Threading.Dispatcher> 상호 작동 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 프레임 워크에도 합니다.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>중첩 펌핑  
 완전히 잠글 수 없는 경우에 따라는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 살펴보겠습니다 합니다 <xref:System.Windows.MessageBox.Show%2A> 메서드는 <xref:System.Windows.MessageBox> 클래스입니다. <xref:System.Windows.MessageBox.Show%2A> 확인 단추를 클릭할 때까지 반환 하지 않습니다. 하지만 상호 작용하기 위해 메시지 루프를 포함해야 하는 창을 만듭니다. 사용자가 [확인]을 클릭할 때까지 기다리고 있는 동안 원래 애플리케이션 창은 사용자 입력에 반응하지 않습니다. 하지만 이 창은 그리기 메시지를 계속 처리합니다. 원래 창은 숨겨졌다 표시될 때 자동으로 재배치됩니다.  
  
 ![확인 단추가 있는 MessageBox를 보여 주는 스크린샷](./media/threading-model/threading-message-loop.png)  
  
 일부 스레드는 메시지 상자 창을 처리해야 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 메시지 상자 창에 대 한 새 스레드를 만들 수 있지만이 스레드는 원래 창에서 사용할 수 없는 요소를 그릴 수 없습니다 (이전 설명은 상호 배제 해야 함). 대신 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 중첩된 메시지 처리 시스템을 사용 합니다. <xref:System.Windows.Threading.Dispatcher> 라는 특수 메서드를 포함 하는 클래스 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>를 저장 하는 응용 프로그램의 현재 실행 지점을 다음 새 메시지 루프를 시작 합니다. 원래 후 실행을 다시 시작할 중첩된 메시지 루프가 완료 되 면 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> 호출 합니다.  
  
 이 경우 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> 에 대 한 호출 시 프로그램 컨텍스트를 유지 관리 <xref:System.Windows.MessageBox>.<xref:System.Windows.MessageBox.Show%2A>, 백그라운드 창을 다시 표시 되 고 메시지 상자 창에 대 한 입력을 처리 하는 새 메시지 루프를 시작 합니다. 사용자가 확인을 클릭 하 고 팝업 창을 지우면 중첩된 루프가 존재 시간과 호출 후 컨트롤을 다시 시작 <xref:System.Windows.MessageBox.Show%2A>합니다.  
  
### <a name="stale-routed-events"></a>부실 라우트된 이벤트  
 라우트된 이벤트 시스템 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트가 발생할 때 전체 트리에 알립니다.  
  
 [!code-xaml[InputOvw#ThreadingArticleStaticRoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 타원을 마우스 왼쪽된 단추를 누르면 `handler2` 실행 됩니다. 후 `handler2` 완료 되 면 이벤트에 전달 됩니다 합니다 <xref:System.Windows.Controls.Canvas> 개체를 사용 하 여 `handler1` 처리 합니다. 경우에 이런 `handler2` 는 명시적으로 표시 이벤트 개체를 처리 합니다.  
  
 가능성이 있는 `handler2` 이 이벤트를 처리 하는 시간이 많이 걸립니다. `handler2` 사용할 수 있습니다 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> 시간 동안 반환 하지 않는 중첩된 메시지 루프를 시작 합니다. 경우 `handler2` 이벤트 메시지 루프가이 되었을 때 처리 된 것으로 완료 하는 표시 하지 않으면, 이벤트는 매우 오래 된 경우에 트리에서 위로 전달 됩니다.  
  
### <a name="reentrancy-and-locking"></a>재입력 및 잠금  
 잠금 메커니즘은는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 처럼 동작 하지 않습니다 예상한 것; 스레드 잠금을 요청할 때 작업을 완전히 중단할를 예상할 수 있습니다. 실제로 스레드는 우선 순위가 높은 메시지를 계속 수신하고 처리합니다. 이를 통해 교착 상태를 방지하고 인터페이스가 최소한으로 응답할 수 있지만 미묘한 버그가 발생할 수 있습니다.  대부분의 경우 드문 경우 이지만이 대 한 사용자에 게 알 필요가 없습니다 (일반적으로 관련 된 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창 메시지 또는 COM STA 구성 요소)이 사실을 알 가치가 있습니다.  
  
 개발자 작업 가정 하기 때문에 대부분의 인터페이스 스레드 안전을 고려 빌드되지 않는는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 둘 이상의 스레드에서 액세스 되지 않습니다. 예기치 않은 시간에 단일 스레드 환경 변화를 만들 수는이 경우에서에 영향 시켜는 <xref:System.Windows.Threading.DispatcherObject> 상호 배제 메커니즘을 해결 해야 합니다. 다음 의사 코드를 살펴보겠습니다.  
  
 ![해당 표시 스레딩 재입력 다이어그램입니다. ](./media/threading-model/threading-reentrancy.png "ThreadingReentrancy")  
  
 대부분의 시간에는 이것이 되지만 시간 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이러한 예상치 않은 재진입 문제가 발생할 실제로 수 있습니다. 따라서 특정 키 시간 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 호출 <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>를 사용 하도록 해당 스레드에 대 한 잠금 명령을 변경 하는 합니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 대신 일반적인 재입력 없는 잠금을 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 잠금.  
  
 이유는 않은 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 팀이이 동작을 선택? 이 팀은 COM STA 개체 및 종료 스레드를 사용해야 했습니다. 개체가 가비지 수집 하는 경우 해당 `Finalize` 메서드 전용된 종료자 스레드에서 실행 되는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 문제가 여기 고 COM STA 개체는 생성 된에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드 삭제 될 수는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드입니다. 합니다 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 의 같은 작업을 수행을 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> (이 경우 Win32의를 사용 하 여 `SendMessage`). 경우에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 사용 중이면 종료자 스레드가 중단 되 고 COM STA 개체를 삭제할 수 없으므로 심각한 메모리 누수가 발생 합니다. 하므로 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 팀을 내린 방식으로 작동 하는 잠금 수 있도록 수행 합니다.  
  
 에 대 한 작업 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 다시 everywhere 재입력을 차단 하지는 메모리 누수를 초래 하지 않고 예기치 않은 재입력을 방지 하는 것입니다.  
  
## <a name="see-also"></a>참고자료

- [장기 실행 계산 샘플을 사용 하 여 단일 스레드 응용 프로그램](https://go.microsoft.com/fwlink/?LinkID=160038)
