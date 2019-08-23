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
ms.openlocfilehash: 0a7756684d5a133fa9cb014f109d14e413223ea9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69945222"
---
# <a name="how-to-remotely-survey-the-status-of-printers"></a><span data-ttu-id="56e92-102">방법: 원격으로 프린터 상태 조사</span><span class="sxs-lookup"><span data-stu-id="56e92-102">How to: Remotely Survey the Status of Printers</span></span>
<span data-ttu-id="56e92-103">중간 규모 및 대규모 기업에는 언제든지 종이 걸림이나 용지 부족 또는 다른 문제 상황으로 인해 여러 프린터가 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-103">At any given time at medium and large companies there may be multiple printers that are not working due to a paper jam or being out of paper or some other problematic situation.</span></span> <span data-ttu-id="56e92-104">Microsoft .NET Framework의 Api에 표시 되는 다양 한 프린터 속성은 프린터 상태를 신속 하 게 조사 하는 수단을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-104">The rich set of printer properties exposed in the APIs of Microsoft .NET Framework provide a means for performing a rapid survey of the states of printers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56e92-105">예제</span><span class="sxs-lookup"><span data-stu-id="56e92-105">Example</span></span>  
 <span data-ttu-id="56e92-106">이러한 종류의 유틸리티를 만드는 주요 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-106">The major steps for creating this kind of utility are as follows.</span></span>  
  
1. <span data-ttu-id="56e92-107">모든 인쇄 서버 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-107">Obtain a list of all print servers.</span></span>  
  
2. <span data-ttu-id="56e92-108">서버를 반복하여 해당 인쇄 큐를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-108">Loop through the servers to query their print queues.</span></span>  
  
3. <span data-ttu-id="56e92-109">서버 루프의 각 단계 내에서 모든 서버 큐를 반복하고 큐가 현재 작동하지 않는다는 것을 나타내는 각 속성을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-109">Within each pass of the server loop, loop through all the server's queues and read each property that might indicate that the queue is not currently working.</span></span>  
  
 <span data-ttu-id="56e92-110">아래의 코드는 일련의 코드 조각입니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-110">The code below is a series of snippets.</span></span> <span data-ttu-id="56e92-111">편의를 위해 이 예제에서는 인쇄 서버의 CRLF로 구분된 목록이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-111">For simplicity, this example assumes that there is a CRLF-delimited list of print servers.</span></span> <span data-ttu-id="56e92-112">`fileOfPrintServers` 변수<xref:System.IO.StreamReader> 는이 파일에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-112">The variable `fileOfPrintServers` is a <xref:System.IO.StreamReader> object for this file.</span></span> <span data-ttu-id="56e92-113">각 서버 이름이 별도의 줄에 있으므로의 <xref:System.IO.StreamReader.ReadLine%2A> 호출은 다음 서버의 이름을 가져오고의 커서를 다음 줄의 시작 부분으로 <xref:System.IO.StreamReader>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-113">Since each server name is on its own line, any call of <xref:System.IO.StreamReader.ReadLine%2A> gets the name of the next server and moves the <xref:System.IO.StreamReader>'s cursor to the beginning of the next line.</span></span>  
  
 <span data-ttu-id="56e92-114">외부 루프 내에서 코드는 최신 인쇄 서버 <xref:System.Printing.PrintServer> 에 대 한 개체를 만들고 응용 프로그램이 서버에 대 한 관리 권한을 갖도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-114">Within the outer loop, the code creates a <xref:System.Printing.PrintServer> object for the latest print server and specifies that the application is to have administrative rights to the server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56e92-115">서버 수가 많은 경우 필요한 속성만 초기화 하는 <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> 생성자를 사용 하 여 성능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-115">If there are a lot of servers, you can improve performance by using the <xref:System.Printing.PrintServer.%23ctor%28System.String%2CSystem.String%5B%5D%2CSystem.Printing.PrintSystemDesiredAccess%29> constructors that only initialize the properties you are going to need.</span></span>  
  
 <span data-ttu-id="56e92-116">그런 다음이 예제 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 에서는를 사용 하 여 모든 서버 큐의 컬렉션을 만들고이를 반복 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-116">The example then uses <xref:System.Printing.PrintServer.GetPrintQueues%2A> to create a collection of all of the server's queues and begins to loop through them.</span></span> <span data-ttu-id="56e92-117">이 내부 루프에는 프린터의 상태를 검사하는 두 가지 방법에 해당하는 분기 구조가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-117">This inner loop contains a branching structure corresponding to the two ways of checking a printer's status:</span></span>  
  
- <span data-ttu-id="56e92-118"><xref:System.Printing.PrintQueue.QueueStatus%2A> 형식의<xref:System.Printing.PrintQueueStatus>속성에 대 한 플래그를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-118">You can read the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property which is of type <xref:System.Printing.PrintQueueStatus>.</span></span>  
  
- <span data-ttu-id="56e92-119"><xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, 및<xref:System.Printing.PrintQueue.IsPaperJammed%2A>와 같은 각각의 관련 속성을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-119">You can read each relevant property such as <xref:System.Printing.PrintQueue.IsOutOfPaper%2A>, and <xref:System.Printing.PrintQueue.IsPaperJammed%2A>.</span></span>  
  
 <span data-ttu-id="56e92-120">이 예제에서는 두 메서드를 모두 보여 줍니다. 따라서 사용자는 이전에 사용할 메서드를 묻는 메시지를 표시 하 고 <xref:System.Printing.PrintQueue.QueueStatus%2A> 속성의 플래그를 사용 하려는 경우 "y"로 응답 했습니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-120">This example demonstrates both methods, so the user was previously prompted as to which method to use and responded with "y" if he or she wanted to use the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property.</span></span> <span data-ttu-id="56e92-121">두 가지 방법에 대한 자세한 내용은 아래를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56e92-121">See below for the details of the two methods.</span></span>  
  
 <span data-ttu-id="56e92-122">마지막으로 결과가 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-122">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#surveyqueues)]
 [!code-csharp[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#surveyqueues)]
 [!code-vb[PrinterStatusSurvey#SurveyQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#surveyqueues)]  
  
 <span data-ttu-id="56e92-123"><xref:System.Printing.PrintQueue.QueueStatus%2A> 속성의 플래그를 사용 하 여 프린터 상태를 확인 하려면 각 관련 플래그를 확인 하 여 설정 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-123">To check printer status using the flags of the <xref:System.Printing.PrintQueue.QueueStatus%2A> property, you check each relevant flag to see if it is set.</span></span> <span data-ttu-id="56e92-124">일련의 비트 플래그에 하나의 비트가 설정되었는지 확인하는 표준 방법은 일련의 플래그가 있는 논리적 AND 연산을 하나의 피연산자로 수행하고 플래그 자체를 다른 피연산자로 수행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-124">The standard way to see if one bit is set in a set of bit flags is to perform a logical AND operation with the set of flags as one operand and the flag itself as the other.</span></span> <span data-ttu-id="56e92-125">플래그 자체가 하나의 비트만 설정하므로 논리적 AND의 결과는 비트가 설정되는 것과 거의 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-125">Since the flag itself has only one bit set, the result of the logical AND is that, at most, that same bit is set.</span></span> <span data-ttu-id="56e92-126">여부를 확인하려면 플래그 자체와 논리적 AND의 결과를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-126">To find out whether it is or not, just compare the result of the logical AND with the flag itself.</span></span> <span data-ttu-id="56e92-127">자세한 내용은 <xref:System.Printing.PrintQueueStatus> [& 연산자 (C# 참조)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)및 <xref:System.FlagsAttribute>을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="56e92-127">For more information, see <xref:System.Printing.PrintQueueStatus>, the [& Operator (C# Reference)](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-), and <xref:System.FlagsAttribute>.</span></span>  
  
 <span data-ttu-id="56e92-128">비트가 설정된 각 특성의 경우 코드는 사용자에게 표시될 최종 보고서에 메시지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-128">For each attribute whose bit is set, the code adds a notice to the final report that will be presented to the user.</span></span> <span data-ttu-id="56e92-129">코드의 끝에 호출되는 **ReportAvailabilityAtThisTime** 메서드는 아래 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-129">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueattributes)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueattributes)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueAttributes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueattributes)]  
  
 <span data-ttu-id="56e92-130">각 속성을 사용하여 프린터 상태를 확인하려면 단순히 각 속성을 읽고 속성이 `true`인지 여부를 사용자에게 표시할 수 있는 최종 보고서에 메시지를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-130">To check printer status using each property, you simply read each property and add a note to the final report that will be presented to the user if the property is `true`.</span></span> <span data-ttu-id="56e92-131">코드의 끝에 호출되는 **ReportAvailabilityAtThisTime** 메서드는 아래 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-131">(The **ReportAvailabilityAtThisTime** method that is called at the end of the code is discussed below.)</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#spottroubleusingqueueproperties)]
 [!code-csharp[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#spottroubleusingqueueproperties)]
 [!code-vb[PrinterStatusSurvey#SpotTroubleUsingQueueProperties](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#spottroubleusingqueueproperties)]  
  
 <span data-ttu-id="56e92-132">**ReportAvailabilityAtThisTime** 메서드는 현재 시간에 큐를 사용 가능한지 확인해야 할 경우에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-132">The **ReportAvailabilityAtThisTime** method was created in case you need to determine if the queue is available at the current time of day.</span></span>  
  
 <span data-ttu-id="56e92-133"><xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 및<xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 속성이 같으면 메서드는 아무 작업도 수행 하지 않습니다 .이 경우 항상 프린터를 사용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-133">The method will do nothing if the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are equal; because in that case the printer is available at all times.</span></span> <span data-ttu-id="56e92-134">서로 다른 <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> 경우 메서드는 및 <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> 속성이 <xref:System.Int32>의 시간 (분)을 <xref:System.DateTime> 나타내는 s 자정 이후의 총 시간 (분)으로 변환 되어야 하는 현재 시간을 가져옵니다. 개체가.</span><span class="sxs-lookup"><span data-stu-id="56e92-134">If they are different, the method gets the current time which then has to be converted into total minutes past midnight because the <xref:System.Printing.PrintQueue.StartTimeOfDay%2A> and <xref:System.Printing.PrintQueue.UntilTimeOfDay%2A> properties are <xref:System.Int32>s representing minutes-after-midnight, not <xref:System.DateTime> objects.</span></span> <span data-ttu-id="56e92-135">마지막으로 메서드는 현재 시간이 시작과 "끝" 시간 사이인지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="56e92-135">Finally, the method checks to see if the current time is between the start and "until" times.</span></span>  
  
 [!code-cpp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/cpp/VS_Snippets_Wpf/PrinterStatusSurvey/CPP/Program.cpp#usingstartanduntiltimes)]
 [!code-csharp[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/csharp/VS_Snippets_Wpf/PrinterStatusSurvey/CSharp/Program.cs#usingstartanduntiltimes)]
 [!code-vb[PrinterStatusSurvey#UsingStartAndUntilTimes](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrinterStatusSurvey/visualbasic/program.vb#usingstartanduntiltimes)]  
  
## <a name="see-also"></a><span data-ttu-id="56e92-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="56e92-136">See also</span></span>

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
- [<span data-ttu-id="56e92-137">& 연산자 (C# 참조)</span><span class="sxs-lookup"><span data-stu-id="56e92-137">& Operator (C# Reference)</span></span>](../../../csharp/language-reference/operators/bitwise-and-shift-operators.md#logical-and-operator-)
- [<span data-ttu-id="56e92-138">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="56e92-138">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="56e92-139">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="56e92-139">Printing Overview</span></span>](printing-overview.md)
