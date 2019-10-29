---
title: '방법: PrintTicket 유효성 검사 및 병합'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- merging PrintTickets [WPF]
- PrintTicket [WPF], merging
- validation of PrintTickets [WPF]
- PrintTicket [WPF], validation
ms.assetid: 4fe2d501-d0b0-4fef-86af-6ffe6c162532
ms.openlocfilehash: 15e328729886e0f1efc3b47705fcb4ce13013137
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035581"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="07def-102">방법: PrintTicket 유효성 검사 및 병합</span><span class="sxs-lookup"><span data-stu-id="07def-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="07def-103">Microsoft Windows [인쇄 스키마](https://go.microsoft.com/fwlink/?LinkId=186397) 에는 유연 하 고 확장 가능한 <xref:System.Printing.PrintCapabilities> 및 <xref:System.Printing.PrintTicket> 요소가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07def-103">The Microsoft Windows [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="07def-104">이전에는 인쇄 장치의 기능을 항목별로 요약, 후자는 특정 문서 시퀀스, 개별 문서 또는 개별 페이지와 관련 하 여 장치에서 이러한 기능을 사용 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="07def-105">인쇄를 지 원하는 응용 프로그램에 대 한 일반적인 작업 시퀀스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="07def-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="07def-106">프린터 기능을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="07def-107">이러한 기능을 사용 하도록 <xref:System.Printing.PrintTicket>를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="07def-108"><xref:System.Printing.PrintTicket>의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="07def-109">이 문서에서는이 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="07def-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07def-110">예제</span><span class="sxs-lookup"><span data-stu-id="07def-110">Example</span></span>  
 <span data-ttu-id="07def-111">아래 간단한 예제에서는 프린터가 양면 인쇄 (양면 인쇄)를 지원 하는지 여부에 대해서만 관심이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07def-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="07def-112">주요 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="07def-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="07def-113"><xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 메서드를 사용 하 여 <xref:System.Printing.PrintCapabilities> 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="07def-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="07def-114">원하는 기능이 있는지 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="07def-115">아래 예제에서는 <xref:System.Printing.PrintCapabilities> 개체의 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 속성을 테스트 하 여 용지의 위쪽에 "페이지 넘기기"를 포함 하는 용지의 양쪽 면에서 인쇄 기능이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="07def-116"><xref:System.Printing.PrintCapabilities.DuplexingCapability%2A>는 컬렉션 이므로 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>의 `Contains` 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="07def-117">이 단계는 반드시 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="07def-117">This step is not strictly necessary.</span></span> <span data-ttu-id="07def-118">아래에 사용 되는 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 방법은 <xref:System.Printing.PrintTicket>의 각 요청을 프린터의 기능에 대해 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="07def-119">프린터에서 요청 된 기능을 지원 하지 않는 경우 프린터 드라이버는 메서드에서 반환 된 <xref:System.Printing.PrintTicket>의 대체 요청을 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="07def-120">프린터에서 양면을 지 원하는 경우 샘플 코드는 이중을 요청 하는 <xref:System.Printing.PrintTicket>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="07def-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="07def-121">그러나 응용 프로그램은 <xref:System.Printing.PrintTicket> 요소에서 사용할 수 있는 모든 프린터 설정을 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="07def-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="07def-122">프로그래머와 프로그램 시간 모두에 불필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="07def-123">대신, 코드는 이중 요청만 설정 하 고이 <xref:System.Printing.PrintTicket> 완전히 구성 되 고 유효성이 검사 된 기존 <xref:System.Printing.PrintTicket>와 병합 합니다 .이 경우에는 사용자의 기본 <xref:System.Printing.PrintTicket>입니다.</span><span class="sxs-lookup"><span data-stu-id="07def-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="07def-124">따라서이 샘플에서는 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 메서드를 호출 하 여 사용자의 기본 <xref:System.Printing.PrintTicket>를 사용 하 여 새 <xref:System.Printing.PrintTicket> 최소를 병합 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="07def-125">그러면 새 <xref:System.Printing.PrintTicket>를 해당 속성 중 하나로 포함 하는 <xref:System.Printing.ValidationResult> 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="07def-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="07def-126">그런 다음이 샘플에서는 새 <xref:System.Printing.PrintTicket>에서 양면을 요청 하는지 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="07def-127">이 경우 샘플은 사용자에 대 한 새로운 기본 인쇄 티켓을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="07def-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="07def-128">위의 2 단계가 중단 되었고 프린터가 긴 쪽의 이중 양면을 지원 하지 않는 경우 테스트 결과 `false`발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="07def-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="07def-129">위의 메모를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="07def-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="07def-130">마지막으로 중요 한 단계는 <xref:System.Printing.PrintQueue.Commit%2A> 메서드를 사용 하 여 <xref:System.Printing.PrintQueue>의 <xref:System.Printing.PrintQueue.UserPrintTicket%2A> 속성에 대 한 변경 내용을 커밋하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="07def-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="07def-131">이 예제를 빠르게 테스트할 수 있도록 그 나머지는 아래에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07def-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="07def-132">프로젝트 및 네임 스페이스를 만든 다음이 문서의 코드 조각을 모두 네임 스페이스 블록에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="07def-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="07def-133">참조</span><span class="sxs-lookup"><span data-stu-id="07def-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="07def-134">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="07def-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="07def-135">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="07def-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="07def-136">인쇄 스키마</span><span class="sxs-lookup"><span data-stu-id="07def-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)
