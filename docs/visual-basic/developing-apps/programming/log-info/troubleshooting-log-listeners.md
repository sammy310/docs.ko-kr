---
title: '문제 해결: 로그 수신기'
ms.date: 07/20/2015
helpviewer_keywords:
- event logs, troubleshooting
- troubleshooting Visual Basic, event logs
- troubleshooting event logs
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
ms.openlocfilehash: dd139935dae7fe4d1334b861e6590df29bab7202
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346863"
---
# <a name="troubleshooting-log-listeners-visual-basic"></a><span data-ttu-id="55b66-102">문제 해결: 로그 수신기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55b66-102">Troubleshooting: Log Listeners (Visual Basic)</span></span>

<span data-ttu-id="55b66-103">`My.Application.Log` 및 `My.Log` 개체를 사용하여 애플리케이션에서 발생하는 이벤트에 대한 정보를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55b66-103">You can use the `My.Application.Log` and `My.Log` objects to log information about events that occur in your application.</span></span>  
  
 <span data-ttu-id="55b66-104">해당 메시지를 수신하는 로그 수신기를 확인하려면 [연습: My.Application.Log가 정보를 기록하는 위치 확인](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55b66-104">To determine which log listeners receive those messages, see [Walkthrough: Determining Where My.Application.Log Writes Information](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).</span></span>  
  
 <span data-ttu-id="55b66-105">`Log` 개체는 로그 필터링을 사용하여 기록하는 정보의 양을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55b66-105">The `Log` object can use log filtering to limit the amount of information that it logs.</span></span> <span data-ttu-id="55b66-106">필터가 잘못 구성된 경우 로그에 잘못된 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55b66-106">If the filters are misconfigured, the logs might contain the wrong information.</span></span> <span data-ttu-id="55b66-107">필터링에 대한 자세한 내용은 [연습: My.Application.Log 출력 필터링](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55b66-107">For more information about filtering, see [Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).</span></span>  
  
 <span data-ttu-id="55b66-108">그러나 로그가 잘못 구성된 경우 현재 구성에 대한 자세한 정보가 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55b66-108">However, if a log is configured incorrectly, you may need more information about its current configuration.</span></span> <span data-ttu-id="55b66-109">이 정보는 로그의 고급 `TraceSource` 속성을 통해 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55b66-109">You can get to this information through the log's advanced `TraceSource` property.</span></span>  
  
### <a name="to-determine-the-log-listeners-for-the-log-object-in-code"></a><span data-ttu-id="55b66-110">코드에서 Log 개체에 대한 로그 수신기를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="55b66-110">To determine the log listeners for the Log object in code</span></span>  
  
1. <span data-ttu-id="55b66-111">코드 파일의 시작 부분에 있는 <xref:System.Diagnostics> 네임스페이스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="55b66-111">Import the <xref:System.Diagnostics> namespace at the beginning of the code file.</span></span> <span data-ttu-id="55b66-112">자세한 내용은 [Imports 문(.NET 네임스페이스 및 형식)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55b66-112">For more information, see [Imports Statement (.NET Namespace and Type)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#13)]  
  
2. <span data-ttu-id="55b66-113">각 로그 수신기에 대한 정보로 구성된 문자열을 반환하는 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55b66-113">Create a function that returns a string consisting of information for each of the log's listeners.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#14)]  
  
3. <span data-ttu-id="55b66-114">로그의 추적 수신기 컬렉션을 `GetListeners` 함수에 전달하고 반환 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="55b66-114">Pass the collection of the log's trace listeners to the `GetListeners` function, and display the return value.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#19)]  
  
     <span data-ttu-id="55b66-115">자세한 내용은 <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55b66-115">For more information, see <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55b66-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55b66-116">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="55b66-117">애플리케이션 로그 작업</span><span class="sxs-lookup"><span data-stu-id="55b66-117">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="55b66-118">연습: My.Application.Log가 정보를 기록하는 위치 확인</span><span class="sxs-lookup"><span data-stu-id="55b66-118">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
