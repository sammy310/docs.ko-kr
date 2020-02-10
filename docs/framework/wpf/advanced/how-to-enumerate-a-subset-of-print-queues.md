---
title: '방법: 인쇄 큐의 하위 집합 열거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- enumerating [WPF], subset of print queues
- print queues [WPF], enumerating subset of
ms.assetid: cc4a1b5b-d46f-4c5e-bc26-22c226e4bee0
ms.openlocfilehash: aae41931f012f6d34fc057fdd6ee9fc9baab6e7b
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094542"
---
# <a name="how-to-enumerate-a-subset-of-print-queues"></a><span data-ttu-id="6a308-102">방법: 인쇄 큐의 하위 집합 열거</span><span class="sxs-lookup"><span data-stu-id="6a308-102">How to: Enumerate a Subset of Print Queues</span></span>
<span data-ttu-id="6a308-103">회사 전체 프린터 집합을 관리 하는 IT (정보 기술) 전문가가 직면 하는 일반적인 상황은 특정 특성을 가진 프린터 목록을 생성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-103">A common situation faced by information technology (IT) professionals managing a company-wide set of printers is to generate a list of printers having certain characteristics.</span></span> <span data-ttu-id="6a308-104">이 기능은 <xref:System.Printing.PrintServer> 개체의 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 메서드와 <xref:System.Printing.EnumeratedPrintQueueTypes> 열거에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-104">This functionality is provided by the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method of a <xref:System.Printing.PrintServer> object and the <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6a308-105">예제</span><span class="sxs-lookup"><span data-stu-id="6a308-105">Example</span></span>  
 <span data-ttu-id="6a308-106">아래 예제에서 코드는 나열 하려는 인쇄 큐의 특성을 지정 하는 플래그의 배열을 만드는 것부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-106">In the example below, the code begins by creating an array of flags that specify the characteristics of the print queues we want to list.</span></span> <span data-ttu-id="6a308-107">이 예에서는 인쇄 서버에 로컬로 설치 되 고 공유 되는 인쇄 대기열을 찾고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-107">In this example, we are looking for print queues that are installed locally on the print server and are shared.</span></span> <span data-ttu-id="6a308-108"><xref:System.Printing.EnumeratedPrintQueueTypes> 열거형은 다른 여러 가지 가능성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-108">The <xref:System.Printing.EnumeratedPrintQueueTypes> enumeration provides many other possibilities.</span></span>  
  
 <span data-ttu-id="6a308-109">그런 다음 코드는 <xref:System.Printing.PrintServer>에서 파생 된 클래스인 <xref:System.Printing.LocalPrintServer> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-109">The code then creates a <xref:System.Printing.LocalPrintServer> object, a class derived from <xref:System.Printing.PrintServer>.</span></span> <span data-ttu-id="6a308-110">로컬 인쇄 서버는 응용 프로그램이 실행 되 고 있는 컴퓨터입니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-110">The local print server is the computer on which the application is running.</span></span>  
  
 <span data-ttu-id="6a308-111">마지막으로 중요 한 단계는 배열을 <xref:System.Printing.PrintServer.GetPrintQueues%2A> 메서드에 전달 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-111">The last significant step is to pass the array to the <xref:System.Printing.PrintServer.GetPrintQueues%2A> method.</span></span>  
  
 <span data-ttu-id="6a308-112">마지막으로 결과가 사용자에게 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-112">Finally, the results are presented to the user.</span></span>  
  
 [!code-cpp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/cpp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CPP/Program.cpp#listsubsetofprintqueues)]
 [!code-csharp[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/csharp/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/CSharp/Program.cs#listsubsetofprintqueues)]
 [!code-vb[EnumerateSubsetOfPrintQueues#ListSubsetOfPrintQueues](~/samples/snippets/visualbasic/VS_Snippets_Wpf/EnumerateSubsetOfPrintQueues/visualbasic/program.vb#listsubsetofprintqueues)]  
  
 <span data-ttu-id="6a308-113">각 인쇄 큐를 단계별로 안내 하는 `foreach` 루프를 통해이 예제를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-113">You could extend this example by having the `foreach` loop that steps through each print queue do further screening.</span></span> <span data-ttu-id="6a308-114">예를 들어 루프가 각 인쇄 큐의 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 메서드를 호출 하 고 양면 인쇄를 위해 반환 된 값을 테스트 하도록 하 여 양면 인쇄를 지원 하지 않는 프린터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a308-114">For example, you could screen out printers that do not support two-sided printing by having the loop call each print queue's <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method and test the returned value for the presence of duplexing.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a308-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6a308-115">See also</span></span>

- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="6a308-116">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="6a308-116">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="6a308-117">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="6a308-117">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="6a308-118">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="6a308-118">Microsoft XPS Document Writer</span></span>](/windows/win32/printdocs/microsoft-xps-document-writer)
