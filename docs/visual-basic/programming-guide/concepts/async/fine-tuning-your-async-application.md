---
title: Async (Visual Basic) 응용 프로그램 미세 조정
ms.date: 07/20/2015
ms.assetid: 4c3e7997-a95f-4fbe-a6ac-60ba042d30b9
ms.openlocfilehash: 88b26aea0740bb4a5c5e9d87790746a708bf45a1
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58838018"
---
# <a name="fine-tuning-your-async-application-visual-basic"></a>Async (Visual Basic) 응용 프로그램 미세 조정
<xref:System.Threading.Tasks.Task> 형식이 제공하는 메서드 및 속성을 사용하여 async 애플리케이션에 정확성 및 유연성을 추가할 수 있습니다. 이 섹션의 항목에서는 <xref:System.Threading.CancellationToken>을 사용하는 예제와 <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Task.WhenAny%2A?displayProperty=nameWithType>과 같은 중요한 `Task` 메서드를 보여 줍니다.  
  
 `WhenAny` 및 `WhenAll`를 사용하면 더 쉽게 여러 작업을 시작하고 단일 작업을 모니터링하여 완료할 때까지 기다릴 수 있습니다.  
  
-   `WhenAny`는 컬렉션의 임의 작업이 완료되면 완료되는 작업을 반환합니다.  
  
     사용 하는 예제에 대 한 `WhenAny`를 참조 하세요 [취소 작업 남은 비동기 작업 하나가 완료 되 면 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)하 고 [여러 비동기 작업을 시작 하 고 프로세스에 완료 될 때마다 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md).  
  
-   `WhenAll`은 컬렉션의 모든 작업이 완료되면 완료되는 작업을 반환합니다.  
  
     자세한 내용과 `WhenAll`을 사용하는 예제는 [방법: Task.WhenAll (Visual Basic)을 사용 하 여 비동기 연습 확장](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)합니다.  
  
 이 섹션에 포함된 예제는 다음과 같습니다.  
  
-   [비동기 작업 또는 작업 (Visual Basic)의 목록을 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)합니다.  
  
-   [(Visual Basic) 시간의 기간 이후 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)  
  
-   [하나가 (Visual Basic) 완료 되 면 남은 비동기 작업 취소](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)  
  
-   [여러 비동기 작업을 시작 하 고 (Visual Basic)를 완료 될 때마다 처리](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)  
  
> [!NOTE]
>  예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.  
  
 다음 그림과 같이 프로젝트는 프로세스를 시작하는 단추와 프로세스를 취소하는 단추가 포함된 UI를 만듭니다. 단추 이름은 `startButton` 및 `cancelButton`입니다.  
  
 ![취소 단추가 있는 WPF 창](./media/fine-tuning-your-async-application/cancellation-and-start-button.png "시작 및 중지 단추가 있는 대화 상자")  
  
 [Async 샘플: 애플리케이션 미세 조정](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)에서 전체 WPF(Windows Presentation Foundation) 프로젝트를 다운로드하여 완료할 수 있습니다.  
  
## <a name="see-also"></a>참고자료

- [Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)
