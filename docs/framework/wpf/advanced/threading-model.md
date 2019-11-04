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
ms.openlocfilehash: ef25123ed53ecf3e03e4f4c969bed2ef570591ad
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459036"
---
# <a name="threading-model"></a>스레딩 모델
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]는 개발자가 스레딩의 어려움을 해결하도록 디자인되어 있습니다. 결과적으로 대부분의 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 개발자는 둘 이상의 스레드를 사용 하는 인터페이스를 작성할 필요가 없습니다. 다중 스레드 프로그램은 복잡하고 디버그하기 어려우므로 단일 스레드 솔루션이 있을 경우 피해야 합니다.  
  
 그러나 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] framework는 잘 설계 되지 않은 모든 문제에 대해 단일 스레드 솔루션을 제공할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]은 닫히지 않지만 여러 스레드가 응답성 또는 응용 프로그램 성능을 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 향상 시키는 경우는 여전히 있습니다. 일부 배경 자료를 설명한 후 이 문서에서는 이러한 상황 중 일부를 살펴보고 몇몇 하위 수준 세부 정보에 대한 설명으로 마무리 짓습니다.  

> [!NOTE]
> 이 항목에서는 비동기 호출에 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 메서드를 사용 하 여 스레딩을 설명 합니다. <xref:System.Action> 또는 <xref:System.Func%601>를 매개 변수로 사용 하는 <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> 메서드를 호출 하 여 비동기 호출을 수행할 수도 있습니다.  <xref:System.Windows.Threading.Dispatcher.InvokeAsync%2A> 메서드는 <xref:System.Windows.Threading.DispatcherOperation.Task%2A> 속성이 있는 <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>를 반환 합니다. <xref:System.Windows.Threading.DispatcherOperation> 또는 연결 된 <xref:System.Threading.Tasks.Task>`await` 키워드를 사용할 수 있습니다. <xref:System.Windows.Threading.DispatcherOperation> 또는 <xref:System.Windows.Threading.DispatcherOperation%601>에서 반환 된 <xref:System.Threading.Tasks.Task>를 동기적으로 대기 해야 하는 경우 <xref:System.Windows.Threading.TaskExtensions.DispatcherOperationWait%2A> 확장 메서드를 호출 합니다.  <xref:System.Threading.Tasks.Task.Wait%2A?displayProperty=nameWithType>를 호출 하면 교착 상태가 발생 합니다. <xref:System.Threading.Tasks.Task>를 사용 하 여 비동기 작업을 수행 하는 방법에 대 한 자세한 내용은 작업 병렬 처리를 참조 하세요.  <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 메서드는 <xref:System.Action> 또는 <xref:System.Func%601>를 매개 변수로 사용 하는 오버 로드도 포함 합니다.  <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 메서드를 사용 하 여 대리자, <xref:System.Action> 또는 <xref:System.Func%601>를 전달 하 여 동기 호출을 수행할 수 있습니다.  
  
<a name="threading_overview"></a>   
## <a name="overview-and-the-dispatcher"></a>개요 및 디스패처  
 일반적으로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 두 개의 스레드로 시작 합니다. 하나는 렌더링을 처리 하 고 다른 하나는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 관리 하기 위한 것입니다. 렌더링 스레드는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 입력을 받고, 이벤트를 처리 하 고, 화면을 그리고 응용 프로그램 코드를 실행 하는 동안 백그라운드에서 숨겨진 상태로 효율적으로 실행 됩니다. 대부분의 응용 프로그램은 단일 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드를 사용 하지만 일부 경우에는 여러 가지를 사용 하는 것이 가장 좋습니다. 나중에 예제를 통해 이를 설명하겠습니다.  
  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드는 <xref:System.Windows.Threading.Dispatcher>라는 개체 내에서 작업 항목을 큐에 대기 시킵니다. <xref:System.Windows.Threading.Dispatcher>는 우선 순위에 따라 작업 항목을 선택하고 각 작업 항목을 완료할 때까지 실행합니다.  모든 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에는 <xref:System.Windows.Threading.Dispatcher>가 하나 이상 있어야 하 고 각 <xref:System.Windows.Threading.Dispatcher>는 정확히 하나의 스레드에서 작업 항목을 실행할 수 있습니다.  
  
 응답성이 뛰어난 사용자에 게 친숙 한 응용 프로그램을 작성 하는 트릭은 작업 항목을 작게 유지 하 여 <xref:System.Windows.Threading.Dispatcher> 처리량을 최대화 하는 것입니다. 이러한 방식으로 항목이 처리를 대기 하는 <xref:System.Windows.Threading.Dispatcher> 큐에 남아 있지 않습니다. 입력과 응답 간의 인식할 수 있는 지연으로 인해 사용자가 불편해질 수 있습니다.  
  
 응용 프로그램에서 큰 작업을 처리 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 하는 방법은 무엇입니까? 코드에 큰 계산을 포함하거나 몇몇 원격 서버에서 데이터베이스를 쿼리해야 하면 어떻게 될까요? 일반적으로는 개별 스레드에서 큰 작업을 처리 하는 것이 좋습니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드는 <xref:System.Windows.Threading.Dispatcher> 큐의 항목을 사용 하지 않고 그대로 둡니다. 큰 작업이 완료 되 면 표시를 위해 결과를 다시 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에 보고할 수 있습니다.  
  
 지금 까지는 Windows를 사용 하 여 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 만든 스레드에서만 액세스할 수 있습니다. 즉, 일부 장기 실행 작업을 처리하는 백그라운드 스레드는 작업이 완료될 때 입력란을 업데이트할 수 없습니다. Windows는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 구성 요소의 무결성을 보장 하기 위해이를 수행 합니다. 목록 상자의 콘텐츠가 그리는 동안 백그라운드 스레드를 통해 업데이트되면 목록 상자가 이상하게 표시될 수 있습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 이 조정을 적용하는 기본 제공 상호 배제 메커니즘이 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 대부분 클래스는 <xref:System.Windows.Threading.DispatcherObject>에서 파생 됩니다. 생성 시 <xref:System.Windows.Threading.DispatcherObject>는 현재 실행 중인 스레드에 연결 된 <xref:System.Windows.Threading.Dispatcher>에 대 한 참조를 저장 합니다. 실제로 <xref:System.Windows.Threading.DispatcherObject>는이를 만드는 스레드와 연결 됩니다. 프로그램을 실행 하는 동안 <xref:System.Windows.Threading.DispatcherObject>는 해당 공용 <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 메서드를 호출할 수 있습니다. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 현재 스레드와 연결 된 <xref:System.Windows.Threading.Dispatcher>를 검사 하 고 생성 중에 저장 된 <xref:System.Windows.Threading.Dispatcher> 참조와 비교 합니다. 일치 하지 않는 경우 <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A> 예외를 throw 합니다. <xref:System.Windows.Threading.DispatcherObject.VerifyAccess%2A>은 <xref:System.Windows.Threading.DispatcherObject>에 속하는 모든 메서드의 시작 부분에서 호출 됩니다.  
  
 한 스레드만 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 수정할 수 있는 경우 백그라운드 스레드는 사용자와 상호 작용 하는 방법 백그라운드 스레드는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에 게 작업을 대신 수행 하도록 요청할 수 있습니다. 이렇게 하려면 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드의 <xref:System.Windows.Threading.Dispatcher> 작업 항목을 등록 합니다. <xref:System.Windows.Threading.Dispatcher> 클래스는 <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 및 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>작업 항목을 등록 하는 두 가지 메서드를 제공 합니다. 메서드는 둘 다 대리자 실행을 예약합니다. <xref:System.Windows.Threading.Dispatcher.Invoke%2A>는 동기 호출입니다. 즉, [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 실제로 대리자 실행을 완료할 때까지 반환 되지 않습니다. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>는 비동기 이며 즉시 반환 됩니다.  
  
 <xref:System.Windows.Threading.Dispatcher>은 우선 순위에 따라 큐의 요소를 정렬 합니다. <xref:System.Windows.Threading.Dispatcher> 큐에 요소를 추가할 때 지정할 수 있는 10 개의 수준이 있습니다. 이러한 우선 순위는 <xref:System.Windows.Threading.DispatcherPriority> 열거에서 유지 관리 됩니다. <xref:System.Windows.Threading.DispatcherPriority> 수준에 대 한 자세한 내용은 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)] 설명서에서 찾을 수 있습니다.  
  
<a name="samples"></a>   
## <a name="threads-in-action-the-samples"></a>사용 중인 스레드: 샘플  
  
<a name="prime_number"></a>   
### <a name="a-single-threaded-application-with-a-long-running-calculation"></a>장기 실행 계산이 포함된 단일 스레드 애플리케이션  
 대부분의 Gui (그래픽 사용자 인터페이스)는 사용자 상호 작용에 대 한 응답으로 생성 되는 이벤트를 기다리는 동안 유휴 시간의 상당 부분을 차지 합니다. 신중한 프로그래밍을 통해 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]의 응답성에 영향을 주지 않고이 유휴 시간을 constructively 사용할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스레딩 모델에서는 입력이 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에서 발생 하는 작업을 중단 하는 것을 허용 하지 않습니다. 즉, 만료 되기 전에 보류 중인 입력 이벤트를 처리 하기 위해 주기적으로 <xref:System.Windows.Threading.Dispatcher>로 돌아가야 합니다.  
  
 다음 예제를 참조하세요.  
  
 ![소수 스레딩을 보여 주는 스크린샷](./media/threading-model/threading-prime-numbers.png)  
  
 이 간단한 애플리케이션은 3부터 위쪽으로 계산하여 소수를 검색합니다. 사용자가 **시작** 단추를 클릭 하면 검색이 시작 됩니다. 프로그램이 소수를 찾으면 검색 결과로 사용자 인터페이스를 업데이트합니다. 이때 사용자가 검색을 중지할 수 있습니다.  
  
 간단한 방법이지만 소수 검색이 영원히 계속될 수 있는 문제가 있습니다.  단추의 click 이벤트 처리기 내에서 전체 검색을 처리 하는 경우 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에서 다른 이벤트를 처리할 수 있는 기회가 제공 되지 않습니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 입력에 응답 하거나 메시지를 처리할 수 없습니다. 다시 표시되지 않으며 단추 클릭에 응답하지 않습니다.  
  
 소수 검색을 별도의 스레드에서 수행할 수 있지만 이 경우 동기화 문제를 처리해야 합니다. 단일 스레드 방법을 통해 발견된 가장 큰 소수를 나열하는 레이블을 직접 업데이트할 수 있습니다.  
  
 계산 작업을 관리 하기 쉬운 청크로 분할 하는 경우 주기적으로 <xref:System.Windows.Threading.Dispatcher>로 돌아가서 이벤트를 처리할 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 제공 하 여 입력을 다시 그리고 처리할 기회를 제공할 수 있습니다.  
  
 계산 및 이벤트 처리 간에 처리 시간을 분할 하는 가장 좋은 방법은 <xref:System.Windows.Threading.Dispatcher>계산을 관리 하는 것입니다. <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A> 메서드를 사용 하 여 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 이벤트를 그리는 동일한 큐에서 프라임 번호 검사를 예약할 수 있습니다. 예제에서는 단일 소수 검사를 한 번만 예약합니다. 소수 검사가 완료된 후 즉시 다음 검사를 예약합니다. 이 검사는 보류 중인 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 이벤트가 처리 된 후에만 진행 됩니다.  
  
 ![디스패처 큐를 보여 주는 스크린샷](./media/threading-model/threading-dispatcher-queue.png)  
  
 Microsoft Word는이 메커니즘을 사용 하 여 맞춤법 검사를 수행 합니다. 맞춤법 검사는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드의 유휴 시간을 사용 하 여 백그라운드에서 수행 됩니다. 코드를 살펴보겠습니다.  
  
 다음 예제에서는 사용자 인터페이스를 만드는 XAML을 보여 줍니다.  
  
 [!code-xaml[ThreadingPrimeNumbers#ThreadingPrimeNumberXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml#threadingprimenumberxaml)]  
  
 다음 예제에서는 코드 숨김을 보여 줍니다.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumbercodebehind)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumbercodebehind)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button>에 대 한 이벤트 처리기를 보여 줍니다.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberstartorstop)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberStartOrStop](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberstartorstop)]  
  
 이 처리기는 <xref:System.Windows.Controls.Button>텍스트를 업데이트 하는 것 외에도 <xref:System.Windows.Threading.Dispatcher> 큐에 대리자를 추가 하 여 첫 번째 소수 검사를 예약 합니다. 이 이벤트 처리기가 작업을 완료 한 후에는 <xref:System.Windows.Threading.Dispatcher>이이 대리자를 선택 하 여 실행 합니다.  
  
 앞에서 설명한 것 처럼 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>은 실행을 위해 대리자를 예약 하는 데 사용 되는 <xref:System.Windows.Threading.Dispatcher> 멤버입니다. 이 경우 <xref:System.Windows.Threading.DispatcherPriority.SystemIdle> 우선 순위를 선택 합니다. <xref:System.Windows.Threading.Dispatcher>는 처리할 중요 한 이벤트가 없는 경우에만이 대리자를 실행 합니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 응답성이 숫자 검사보다 더 중요합니다. 또한 숫자 검사 루틴을 표현하는 새 대리자를 전달합니다.  
  
 [!code-csharp[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingPrimeNumbers/CSharp/Window1.xaml.cs#threadingprimenumberchecknextnumber)]
 [!code-vb[ThreadingPrimeNumbers#ThreadingPrimeNumberCheckNextNumber](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingPrimeNumbers/visualbasic/mainwindow.xaml.vb#threadingprimenumberchecknextnumber)]  
  
 이 메서드는 다음 홀수가 소수인지 확인합니다. 소수 인 경우 메서드는 검색을 반영 하기 위해 `bigPrime`<xref:System.Windows.Controls.TextBlock>를 직접 업데이트 합니다. 구성 요소를 만드는 데 사용된 같은 스레드에서 계산이 수행되므로 이 작업을 수행할 수 있습니다. 계산을 위해 별도의 스레드를 사용 하도록 선택 했으므로 보다 복잡 한 동기화 메커니즘을 사용 하 고 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에서 업데이트를 실행 해야 합니다. 이 상황은 다음에 살펴보겠습니다.  
  
 이 샘플에 대 한 전체 소스 코드는 [장기 실행 계산이 포함 된 단일 스레드 응용 프로그램 샘플](https://go.microsoft.com/fwlink/?LinkID=160038) 을 참조 하세요.  
  
<a name="weather_sim"></a>   
### <a name="handling-a-blocking-operation-with-a-background-thread"></a>백그라운드 스레드를 사용하여 차단 작업 처리  
 그래픽 애플리케이션에서 차단 작업을 처리하는 것은 어려울 수 있습니다. 애플리케이션이 고정된 것처럼 보이므로 이벤트 처리기에서 차단 메서드를 호출하려고 하지 않습니다. 개별 스레드를 사용 하 여 이러한 작업을 처리할 수 있지만, 작업을 완료 하면 작업자 스레드에서 GUI를 직접 수정할 수 없기 때문에 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드와 동기화 해야 합니다. <xref:System.Windows.Threading.Dispatcher.Invoke%2A> 또는 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>를 사용 하 여 대리자를 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드의 <xref:System.Windows.Threading.Dispatcher>에 삽입할 수 있습니다. 결국 이러한 대리자는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 수정할 수 있는 권한을 사용 하 여 실행 됩니다.  
  
 이 예제에서는 날씨 예보를 검색하는 원격 프로시저 호출을 모방합니다. 별도의 작업자 스레드를 사용 하 여이 호출을 실행 하 고 완료 되 면 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드의 <xref:System.Windows.Threading.Dispatcher> 업데이트 메서드를 예약 합니다.  
  
 ![날씨 UI를 보여 주는 스크린샷](./media/threading-model/threading-weather-ui.png)  
  
 [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweathercodebehind)]
 [!code-vb[ThreadingWeatherForecast#ThreadingWeatherCodeBehind](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweathercodebehind)]  
  
 다음은 주의할 몇 가지 세부 정보입니다.  
  
- 단추 처리기 만들기  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherbuttonhandler)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherButtonHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherbuttonhandler)]  
  
 단추가 클릭되면 시계 그림을 표시하고 애니메이션 효과를 주기 시작합니다. 단추를 사용하지 않습니다. 새 스레드에서 `FetchWeatherFromServer` 메서드를 호출한 다음을 반환 하 여 날씨 예측을 수집 하기 위해 대기 하는 동안 <xref:System.Windows.Threading.Dispatcher> 이벤트를 처리할 수 있도록 합니다.  
  
- 날씨 페치  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherfetchweather)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherFetchWeather](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherfetchweather)]  
  
 예제를 간단하게 유지하기 위해 이 예제에는 실제로 네트워킹 코드가 없습니다. 대신에 4초 동안 새 스레드를 절전 모드로 전환하여 네트워크 액세스 지연을 시뮬레이트합니다. 이번에는 원래 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 계속 실행 중 이며 이벤트에 응답 합니다. 이 상황을 표시하기 위해 애니메이션을 계속 실행하고 [최소화] 및 [최대화] 단추도 계속 작동합니다.  
  
 지연이 완료 되 고 일기 예보를 임의로 선택 하면 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에 다시 보고 하는 시간입니다. 이렇게 하려면 해당 스레드의 <xref:System.Windows.Threading.Dispatcher>를 사용 하 여 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에서 `UpdateUserInterface` 호출을 예약 합니다. 날씨를 설명하는 문자열을 예약된 메서드 호출에 전달합니다.  
  
- [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 업데이트  
  
     [!code-csharp[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/csharp/VS_Snippets_Wpf/ThreadingWeatherForecast/CSharp/Window1.xaml.cs#threadingweatherupdateui)]
     [!code-vb[ThreadingWeatherForecast#ThreadingWeatherUpdateUI](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ThreadingWeatherForecast/visualbasic/window1.xaml.vb#threadingweatherupdateui)]  
  
 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드의 <xref:System.Windows.Threading.Dispatcher>에 시간이 있으면 예약 된 호출을 실행 하 여 `UpdateUserInterface`합니다. 이 메서드는 시계 애니메이션을 중지하고 날씨를 설명할 이미지를 선택합니다. 이 이미지를 표시하고 "예보 페치" 단추를 복원합니다.  
  
<a name="multi_browser"></a>   
### <a name="multiple-windows-multiple-threads"></a>여러 Windows, 여러 스레드  
 일부 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에는 여러 개의 최상위 창이 필요 합니다. 한 스레드/<xref:System.Windows.Threading.Dispatcher> 조합에서 여러 windows를 관리 하는 것은 완벽 하 게 사용할 수 있지만, 경우에 따라 여러 스레드에서 더 나은 작업을 수행할 수 있습니다. 특히 창 중 하나가 스레드를 독점할 가능성이 있는 경우 여러 스레드를 사용하는 것이 좋습니다.  
  
 Windows 탐색기는 이런 방식으로 작동 합니다. 새로운 각 탐색기 창은 원래 프로세스에 속하지만 독립 스레드의 제어를 기반으로 만들어집니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Frame> 컨트롤을 사용 하 여 웹 페이지를 표시할 수 있습니다. 간단한 Internet Explorer 대체를 쉽게 만들 수 있습니다. 새 탐색기 창을 여는 중요한 기능으로 시작합니다. 사용자가 “새 창” 단추를 클릭하면 창 복사본을 별도의 스레드에서 시작합니다. 이렇게 하면 창 중 하나에 있는 장기 실행 또는 차단 작업으로 인해 모든 다른 창이 잠기지 않습니다.  
  
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
  
 이 메서드는 새 스레드의 시작점입니다. 이 스레드의 제어를 기반으로 새 창을 만듭니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 새 <xref:System.Windows.Threading.Dispatcher>를 자동으로 만들어 새 스레드를 관리 합니다. Windows 기능을 사용 하려면 <xref:System.Windows.Threading.Dispatcher>를 시작 해야 합니다.  
  
<a name="stumbling_points"></a>   
## <a name="technical-details-and-stumbling-points"></a>기술 세부 정보 및 주의 사항  
  
### <a name="writing-components-using-threading"></a>스레딩을 사용하여 구성 요소 작성  
 Microsoft .NET Framework 개발자 가이드에서는 구성 요소가 비동기 동작을 클라이언트에 노출 하는 방법에 대 한 패턴을 설명 합니다 ( [이벤트 기반 비동기 패턴 개요](../../../standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)참조). 예를 들어 `FetchWeatherFromServer` 메서드를 재사용 가능한 그래픽이 아닌 구성 요소로 패키징하 려 한다고 가정 합니다. 표준 Microsoft .NET Framework 패턴을 따라 다음과 같이 표시 됩니다.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent1)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent1)]  
  
 `GetWeatherAsync`는 백그라운드 스레드 만들기와 같이 앞에서 설명한 기술 중 하나를 사용하여 호출 스레드를 잠그지 않고 비동기적으로 작업을 수행합니다.  
  
 이 패턴의 가장 중요 한 부분 중 하나는 *methodname*`Async` 메서드를 호출한 동일한 스레드에서 *methodname*`Completed` 메서드를 호출 하 여 시작 하는 것입니다. <xref:System.Windows.Threading.Dispatcher.CurrentDispatcher%2A>을 저장 하 여 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 매우 쉽게 사용할 수 있지만, 그래픽이 아닌 구성 요소는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 또는 ASP.NET 프로그램이 아닌 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램 에서만 사용할 수 있습니다.  
  
 <xref:System.Windows.Threading.DispatcherSynchronizationContext> 클래스는이 요구 사항을 해결 합니다. 즉, 다른 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 프레임 워크와 함께 작동 하는 <xref:System.Windows.Threading.Dispatcher> 단순화 된 버전으로 간주 합니다.  
  
 [!code-csharp[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/csharp/VS_Snippets_Wpf/CommandingOverviewSnippets/CSharp/Window1.xaml.cs#threadingarticleweathercomponent2)]
 [!code-vb[CommandingOverviewSnippets#ThreadingArticleWeatherComponent2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CommandingOverviewSnippets/visualbasic/window1.xaml.vb#threadingarticleweathercomponent2)]  
  
### <a name="nested-pumping"></a>중첩 펌핑  
 경우에 따라 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드를 완전히 잠그는 것은 불가능 합니다. <xref:System.Windows.MessageBox> 클래스의 <xref:System.Windows.MessageBox.Show%2A> 메서드를 살펴보겠습니다. <xref:System.Windows.MessageBox.Show%2A>은 사용자가 확인 단추를 클릭할 때까지 반환 되지 않습니다. 하지만 상호 작용하기 위해 메시지 루프를 포함해야 하는 창을 만듭니다. 사용자가 [확인]을 클릭할 때까지 기다리고 있는 동안 원래 애플리케이션 창은 사용자 입력에 반응하지 않습니다. 하지만 이 창은 그리기 메시지를 계속 처리합니다. 원래 창은 숨겨졌다 표시될 때 자동으로 재배치됩니다.  
  
 ![확인 단추를 사용 하 여 MessageBox를 표시 하는 스크린샷](./media/threading-model/threading-message-loop.png)  
  
 일부 스레드는 메시지 상자 창을 처리해야 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 메시지 상자 창인 경우에만 새 스레드를 만들 수 있지만 이 스레드는 원래 창에서 사용되지 않는 요소를 그릴 수 없습니다(상호 배제에 대한 이전 설명 참조). 대신 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 중첩 된 메시지 처리 시스템을 사용 합니다. <xref:System.Windows.Threading.Dispatcher> 클래스에는 응용 프로그램의 현재 실행 지점을 저장 하 고 새 메시지 루프를 시작 하는 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>라는 특수 메서드가 포함 되어 있습니다. 중첩 된 메시지 루프가 완료 되 면 원래 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A> 호출한 후에 실행이 다시 시작 됩니다.  
  
 이 경우 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>는 <xref:System.Windows.MessageBox>에 대 한 호출에서 프로그램 컨텍스트를 유지 관리 합니다.<xref:System.Windows.MessageBox.Show%2A>새 메시지 루프를 시작 하 여 백그라운드 창을 다시 그리고 메시지 상자 창에 대 한 입력을 처리 합니다. 사용자가 확인을 클릭 하 여 팝업 창을 지우면 중첩 루프가 종료 되 고 <xref:System.Windows.MessageBox.Show%2A>호출 후에 제어가 다시 시작 됩니다.  
  
### <a name="stale-routed-events"></a>부실 라우트된 이벤트  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 라우트된 이벤트 시스템은 이벤트가 발생할 때 전체 트리를 알립니다.  
  
 [!code-xaml[InputOvw#ThreadingArticleStaticRoutedEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/InputOvw/CSharp/Page1.xaml#threadingarticlestaticroutedevent)]  
  
 마우스 왼쪽 단추를 타원 위에서 누르면 `handler2`이 실행 됩니다. `handler2` 완료 되 면 이벤트는 `handler1`를 사용 하 여 처리 하는 <xref:System.Windows.Controls.Canvas> 개체에 전달 됩니다. 이는 `handler2`에서 이벤트 개체를 처리 된 것으로 명시적으로 표시 하지 않는 경우에만 발생 합니다.  
  
 `handler2`이 이벤트를 처리 하는 데 상당한 시간이 걸릴 수 있습니다. `handler2`에서 <xref:System.Windows.Threading.Dispatcher.PushFrame%2A>를 사용 하 여 시간에 대해 반환 되지 않는 중첩 된 메시지 루프를 시작할 수 있습니다. 이 메시지 루프가 완료 될 때 `handler2` 이벤트를 처리 된 것으로 표시 하지 않으면 이벤트는 매우 오래 된 경우에도 트리 위로 전달 됩니다.  
  
### <a name="reentrancy-and-locking"></a>재입력 및 잠금  
 CLR (공용 언어 런타임)의 잠금 메커니즘은 짐작할 수 있는 것과 동일 하 게 동작 하지 않습니다. 잠금을 요청할 때 스레드가 작업을 완전히 중단 하는 것으로 예측할 수 있습니다. 실제로 스레드는 우선 순위가 높은 메시지를 계속 수신하고 처리합니다. 이를 통해 교착 상태를 방지하고 인터페이스가 최소한으로 응답할 수 있지만 미묘한 버그가 발생할 수 있습니다.  대부분의 경우에 대 한 정보를 알 필요가 없지만 드물게 발생 하는 경우 (일반적으로 [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] 창 메시지 또는 COM STA 구성 요소와 관련 됨)에는이 작업을 수행 하는 것이 좋습니다.  
  
 개발자는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 둘 이상의 스레드에서 액세스할 수 없다고 가정 하 여 대부분의 인터페이스는 스레드 보안을 염두에 두어야 합니다. 이 경우 단일 스레드는 예기치 않은 시간에 환경 변경을 수행 하 여 <xref:System.Windows.Threading.DispatcherObject> 상호 제외 메커니즘이 해결 될 것으로 예상 하는 효과를 발생 시킬 수 있습니다. 다음 의사 코드를 살펴보겠습니다.  
  
 ![스레딩 재진입을 보여 주는 다이어그램입니다.](./media/threading-model/threading-reentrancy.png "ThreadingReentrancy")  
  
 가장 중요 한 것은 아니지만 예기치 않은 재입력으로 인해 문제가 발생 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 시간이 있습니다. 따라서 특정 키 시간에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]은 <xref:System.Windows.Threading.Dispatcher.DisableProcessing%2A>호출 하 여 일반적인 CLR 잠금 대신 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 재진입 해제 잠금을 사용 하도록 해당 스레드에 대 한 잠금 명령을 변경 합니다.  
  
 따라서 CLR 팀에서이 동작을 선택 하는 이유는 무엇 인가요? 이 팀은 COM STA 개체 및 종료 스레드를 사용해야 했습니다. 개체가 가비지 수집 될 때 해당 `Finalize` 메서드는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 아니라 전용 종료자 스레드에서 실행 됩니다. [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에서 만든 COM STA 개체는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드에서만 삭제할 수 있기 때문에 문제가 발생 합니다. CLR은 <xref:System.Windows.Threading.Dispatcher.BeginInvoke%2A>와 동일 하 게 수행 합니다 (이 경우 Win32's `SendMessage`사용). 그러나 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 스레드가 사용 중인 경우 종료자 스레드가 중단 되 고 COM STA 개체를 삭제할 수 없으므로 심각한 메모리 누수가 발생 합니다. 따라서 CLR 팀은 잠금이 작동 하는 방식에 대 한 어려운 호출을 수행 했습니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에 대 한 작업은 메모리 누수를 재 도입 하지 않고 예기치 않은 재진입을 방지 하는 것입니다 .이 경우에는 모든 위치에서 재진입을 차단 하지 않습니다.  
  
## <a name="see-also"></a>참조

- [장기 실행 계산이 포함된 단일 스레드 애플리케이션 샘플](https://go.microsoft.com/fwlink/?LinkID=160038)
