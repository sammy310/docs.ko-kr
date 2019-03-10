---
title: '연습: 백그라운드에서 작업 실행'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- background tasks
- forms [Windows Forms], multithreading
- forms [Windows Forms], background operations
- background threads
- BackgroundWorker class [Windows Forms], examples
- threading [Windows Forms], background operations
- background operations
ms.assetid: 1b9a4e0a-f134-48ff-a1be-c461446a31ba
ms.openlocfilehash: 0ba4ca2589a61a9331308a816da6ddb5276adbc9
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57703662"
---
# <a name="walkthrough-running-an-operation-in-the-background"></a>연습: 백그라운드에서 작업 실행
완료하는 데 오랜 시간이 걸리는 작업이 있으며 사용자 인터페이스에서 지연이 발생되지 않게 하려는 경우 <xref:System.ComponentModel.BackgroundWorker> 클래스를 사용하여 다른 스레드에서 작업을 실행할 수 있습니다.  
  
 이 예제에서 사용 되는 코드의 전체 목록은 참조 하세요. [방법: 백그라운드에서 작업 실행](how-to-run-an-operation-in-the-background.md)을 참조하세요.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](/visualstudio/ide/personalizing-the-visual-studio-ide)을 참조하세요.  
  
### <a name="to-run-an-operation-in-the-background"></a>백그라운드에서 작업을 실행 하려면  
  
1.  Windows Forms 디자이너에서 활성 폼을 사용 하 여 두를 끌어 <xref:System.Windows.Forms.Button> 에서 제어를 **도구 상자** 폼을 설정 합니다 `Name` 및 <xref:System.Windows.Forms.Control.Text%2A> 다음 표에 따라 단추의 속성을 합니다.  
  
    |단추|이름|텍스트|  
    |------------|----------|----------|  
    |`button1`|`startBtn`|**시작**|  
    |`button2`|`cancelBtn`|**취소**|  
  
2.  열기를 **도구 상자**를 클릭 합니다 **구성 요소** 탭 한 다음 끌어는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 폼.  
  
     합니다 `backgroundWorker1` 구성 요소에 표시 되는 **구성 요소 트레이에**합니다.  
  
3.  **속성** 창에서 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`로 설정합니다.  
  
4.  에 **속성** 창을 **이벤트** 단추를 두 번 클릭 하는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기를 만들려면 이벤트.  
  
5.  에 시간이 많이 걸리는 코드를 삽입 합니다 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기입니다.  
  
6.  작업에 필요한 모든 매개 변수를 추출 합니다 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 의 속성을 <xref:System.ComponentModel.DoWorkEventArgs> 매개 변수입니다.  
  
7.  에 계산의 결과 할당 합니다 <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> 의 속성을 <xref:System.ComponentModel.DoWorkEventArgs>.  
  
     이 수는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기입니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#2)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#2)]  
  
8.  작업의 결과 검색 하는 코드를 삽입 합니다 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기입니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#3)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#3)]  
  
9. `TimeConsumingOperation` 메서드를 구현합니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#4)]  
  
10. Windows Forms 디자이너에서 두 번 클릭 `startButton` 만들려면는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기입니다.  
  
11. 호출 된 <xref:System.ComponentModel.BackgroundWorker.RunWorkerAsync%2A> 에서 메서드를 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트 처리기 `startButton`합니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#5)]  
  
12. Windows Forms 디자이너에서 두 번 클릭 `cancelButton` 만들려면는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기입니다.  
  
13. 호출 된 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 에서 메서드를 <xref:System.Windows.Forms.Control.Click> 에 대 한 이벤트 처리기 `cancelButton`합니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#6](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#6)]  
  
14. 파일의 맨 위에 있는 System.ComponentModel 및 System.Threading 네임 스페이스를 가져옵니다.  
  
     [!code-csharp[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/CS/Form1.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker.Example#7](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker.Example/VB/Form1.vb#7)]  
  
15. 솔루션을 빌드하려면 f6 키를 디버거 외부에서 응용 프로그램을 실행 하려면 ctrl+f5를 누릅니다.  
  
> [!NOTE]
>  F5 키를 눌러 디버거에서 응용 프로그램을 실행 하는 예외에서 발생 된 `TimeConsumingOperation` 메서드를 포착 하 디버거에 의해 표시 합니다. 디버거, 외부 응용 프로그램을 실행 하는 경우는 <xref:System.ComponentModel.BackgroundWorker> 예외를 처리 하 고 캐시에 <xref:System.ComponentModel.AsyncCompletedEventArgs.Error%2A> 의 속성은 <xref:System.ComponentModel.RunWorkerCompletedEventArgs>합니다.  
  
1.  클릭 합니다 **시작** 비동기 작업을 실행 하려면 단추를 클릭 합니다 **취소** 비동기 작업 실행을 중지 하려면 단추.  
  
     각 작업의 결과가 <xref:System.Windows.Forms.MessageBox>에 표시됩니다.  
  
## <a name="next-steps"></a>다음 단계  
  
-   비동기 작업이 진행 됨에 따라 진행률을 보고 하는 폼을 구현 합니다. 자세한 내용은 [방법: 백그라운드 작업을 사용 하는 폼 구현](how-to-implement-a-form-that-uses-a-background-operation.md)합니다.  
  
-   구성 요소에 대 한 비동기 패턴을 지 원하는 클래스를 구현 합니다. 자세한 내용은 [이벤트 기반 비동기 패턴 구현](../../../standard/asynchronous-programming-patterns/implementing-the-event-based-asynchronous-pattern.md)합니다.  
  
## <a name="see-also"></a>참고자료
- <xref:System.ComponentModel.BackgroundWorker>
- <xref:System.ComponentModel.DoWorkEventArgs>
- [방법: 백그라운드 작업을 사용하는 양식 구현](how-to-implement-a-form-that-uses-a-background-operation.md)
- [방법: 백그라운드에서 작업 실행](how-to-run-an-operation-in-the-background.md)
- [BackgroundWorker 구성 요소](backgroundworker-component.md)
