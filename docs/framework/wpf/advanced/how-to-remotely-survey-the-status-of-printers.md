---
title: '방법: 원격으로 프린터 상태 조사'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- surveying printer status remotely [WPF]
- printer status [WPF], surveying remotely
- remotely surveying printer status [WPF]
- status [WPF], printers [WPF], surveying remotely
ms.assetid: d6324759-8292-4c23-9584-9c708887dc94
ms.openlocfilehash: 859ccb703c6c54c66d6ea7b433c67d156627e25b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187031"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a>방법: 원격으로 프린터 상태 조사
중간 규모 및 대규모 기업에는 언제든지 종이 걸림이나 용지 부족 또는 다른 문제 상황으로 인해 여러 프린터가 작동하지 않을 수 있습니다. Microsoft .NET Framework의 API에 노출된 풍부한 프린터 속성 집합은 프린터 상태를 신속하게 조사할 수 있는 수단을 제공합니다.  
  
## <a name="example"></a>예제  
 이러한 종류의 유틸리티를 만드는 주요 단계는 다음과 같습니다.  
  
1. 모든 인쇄 서버 목록을 가져옵니다.  
  
2. 서버를 반복하여 해당 인쇄 큐를 쿼리합니다.  
  
3. 서버 루프의 각 단계 내에서 모든 서버 큐를 반복하고 큐가 현재 작동하지 않는다는 것을 나타내는 각 속성을 읽습니다.  
  
 아래의 코드는 일련의 코드 조각입니다. 편의를 위해 이 예제에서는 인쇄 서버의 CRLF로 구분된 목록이 있다고 가정합니다. 변수는 `fileOfPrintServers` 이 <xref:System.IO.StreamReader> 파일의 개체입니다. 각 서버 이름은 자체 줄에 있기 <xref:System.IO.StreamReader.ReadLine%2A> 때문에 호출은 다음 서버의 <xref:System.IO.StreamReader>이름을 얻고 다음 줄의 시작 부분으로 커서를 이동합니다.  
  
 외부 루프 내에서 코드는 <xref:System.Printing.PrintServer> 최신 인쇄 서버에 대한 개체를 만들고 응용 프로그램이 서버에 대한 관리 권한을 갖도록 지정합니다.  
  
> [!NOTE]
> 서버가 많은 경우 필요한 속성만 초기화하는 <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> 생성자만 사용하여 성능을 향상시킬 수 있습니다.  
  
 그런 다음 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 이 예제에서는 서버의 모든 큐에 대한 컬렉션을 만들고 이를 반복하기 시작합니다. 이 내부 루프에는 프린터의 상태를 검사하는 두 가지 방법에 해당하는 분기 구조가 포함되어 있습니다.  
  
- 형식의 <xref:System.Printing.PrintQueue.QueueStatus%2A> <xref:System.Printing.PrintQueueStatus>속성의 플래그를 읽을 수 있습니다.  
  
- 의 각 관련 속성을 <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>읽을 <xref:System.Printing.PrintQueue.IsPaperJammed%2A>수 있습니다.  
  
 이 예제에서는 두 메서드를 보여 주므로 사용자가 이전에 사용할 메서드에 대한 메시지가 표시되고 <xref:System.Printing.PrintQueue.QueueStatus%2A> 속성의 플래그를 사용하려는 경우 "y"로 응답했습니다. 두 가지 방법에 대한 자세한 내용은 아래를 참조하세요.  
  
 마지막으로 결과가 사용자에게 표시됩니다.  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <xref:System.Printing.PrintQueue.QueueStatus%2A> 속성의 플래그를 사용하여 프린터 상태를 확인하려면 각 관련 플래그를 확인하여 설정된지 확인합니다. 일련의 비트 플래그에 하나의 비트가 설정되었는지 확인하는 표준 방법은 일련의 플래그가 있는 논리적 AND 연산을 하나의 피연산자로 수행하고 플래그 자체를 다른 피연산자로 수행하는 것입니다. 플래그 자체가 하나의 비트만 설정하므로 논리적 AND의 결과는 비트가 설정되는 것과 거의 동일합니다. 여부를 확인하려면 플래그 자체와 논리적 AND의 결과를 비교합니다. 자세한 내용은& <xref:System.Printing.PrintQueueStatus> [연산자(C# 참조)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-) <xref:System.FlagsAttribute>및 을 참조하십시오.  
  
 비트가 설정된 각 특성의 경우 코드는 사용자에게 표시될 최종 보고서에 메시지를 추가합니다. 코드의 끝에 호출되는 **ReportAvailabilityAtThisTime** 메서드는 아래 설명되어 있습니다.  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 각 속성을 사용하여 프린터 상태를 확인하려면 단순히 각 속성을 읽고 속성이 `true`인지 여부를 사용자에게 표시할 수 있는 최종 보고서에 메시지를 추가합니다. 코드의 끝에 호출되는 **ReportAvailabilityAtThisTime** 메서드는 아래 설명되어 있습니다.  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 **ReportAvailabilityAtThisTime** 메서드는 현재 시간에 큐를 사용 가능한지 확인해야 할 경우에 생성됩니다.  
  
 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 메서드는 및 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 속성이 같으면 아무 일도 하지 않습니다. 이 경우 프린터를 항상 사용할 수 있기 때문입니다. 서로 다른 경우 메서드는 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 개체가 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 아닌 <xref:System.Int32> <xref:System.DateTime> 자정 이후의 분(분)을 나타내기 때문에 자정을 지나 총 분으로 변환해야 하는 현재 시간을 가져옵니다. 마지막으로 메서드는 현재 시간이 시작과 "끝" 시간 사이인지를 확인합니다.  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Printing.PrintQueue.StartTimeOfDay%2A>
- <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A>
- <xref:System.DateTime>
- <xref:System.Printing.PrintQueueStatus>
- <xref:System.FlagsAttribute>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- [& 연산자(C# 참조)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [WPF의 문서](documents-in-wpf.md)
- [인쇄 개요](printing-overview.md)
