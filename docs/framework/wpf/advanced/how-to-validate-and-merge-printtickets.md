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
ms.openlocfilehash: be8b299c99515394bc676cfd7a715cb82ac4d58c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59301154"
---
# <a name="how-to-validate-and-merge-printtickets"></a><span data-ttu-id="957e0-102">방법: PrintTicket 유효성 검사 및 병합</span><span class="sxs-lookup"><span data-stu-id="957e0-102">How to: Validate and Merge PrintTickets</span></span>
<span data-ttu-id="957e0-103">합니다 [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) 융통성 있고 확장 가능한 포함 <xref:System.Printing.PrintCapabilities> 및 <xref:System.Printing.PrintTicket> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-103">The [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) includes the flexible and extensible <xref:System.Printing.PrintCapabilities> and <xref:System.Printing.PrintTicket> elements.</span></span> <span data-ttu-id="957e0-104">이전 인쇄 장치 기능을 항목별로 정리 하 고 후자 지정이 장치 문서, 개별 문서 또는 개별 페이지의 특정 시퀀스에 대해 해당 기능을 어떻게 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-104">The former itemizes the capabilities of a print device and the latter specifies how the device should use those capabilities with respect to a particular sequence of documents, individual document, or individual page.</span></span>  
  
 <span data-ttu-id="957e0-105">인쇄를 지 원하는 응용 프로그램에 대 한 작업의 일반적인 순서는 다음과 같은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-105">A typical sequence of tasks for an application that supports printing would be as follows.</span></span>  
  
1. <span data-ttu-id="957e0-106">프린터의 기능을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-106">Determine a printer's capabilities.</span></span>  
  
2. <span data-ttu-id="957e0-107">구성 된 <xref:System.Printing.PrintTicket> 해당 기능을 사용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-107">Configure a <xref:System.Printing.PrintTicket> to use those capabilities.</span></span>  
  
3. <span data-ttu-id="957e0-108">유효성 검사는 <xref:System.Printing.PrintTicket>합니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-108">Validate the <xref:System.Printing.PrintTicket>.</span></span>  
  
 <span data-ttu-id="957e0-109">이 문서에서는이 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-109">This article shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="957e0-110">예제</span><span class="sxs-lookup"><span data-stu-id="957e0-110">Example</span></span>  
 <span data-ttu-id="957e0-111">아래의 간단한 예제에서는 관심이 프린터 이루어지는 지원할 수 있는지 여부, 양면 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-111">In the simple example below, we are interested only in whether a printer can support duplexing — two-sided printing.</span></span> <span data-ttu-id="957e0-112">주요 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-112">The major steps are as follows.</span></span>  
  
1. <span data-ttu-id="957e0-113">가져오기는 <xref:System.Printing.PrintCapabilities> 개체는 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="957e0-113">Get a <xref:System.Printing.PrintCapabilities> object with the <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> method.</span></span>  
  
2. <span data-ttu-id="957e0-114">원하는 기능의 존재 여부를 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-114">Test for the presence of the capability you want.</span></span> <span data-ttu-id="957e0-115">아래 예제에서는 테스트를 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 의 속성을 <xref:System.Printing.PrintCapabilities> 시트의 옆으로 "페이지 넘기기"를 사용 하 여 용지의 양면 인쇄 기능이 있는지에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-115">In the example below, we test the <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> property of the <xref:System.Printing.PrintCapabilities> object for the presence of the capability of printing on both sides of a sheet of paper with the "page turning" along the long side of the sheet.</span></span> <span data-ttu-id="957e0-116">이후 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 은 컬렉션 사용 합니다 `Contains` 메서드의 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span><span class="sxs-lookup"><span data-stu-id="957e0-116">Since <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> is a collection, we use the `Contains` method of <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="957e0-117">이 단계가 꼭 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-117">This step is not strictly necessary.</span></span> <span data-ttu-id="957e0-118">합니다 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 아래에서 사용 하는 방법에 각 요청을 확인 합니다는 <xref:System.Printing.PrintTicket> 프린터의 기능에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-118">The <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method used below will check each request in the <xref:System.Printing.PrintTicket> against the capabilities of the printer.</span></span> <span data-ttu-id="957e0-119">프린터에서 요청한 기능을 사용할 수 없습니다, 프린터 드라이버에서 다른 요청을 대체 합니다는 <xref:System.Printing.PrintTicket> 메서드에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-119">If the requested capability is not supported by printer, the printer driver will substitute an alternative request in the <xref:System.Printing.PrintTicket> returned by the method.</span></span>  
  
3. <span data-ttu-id="957e0-120">샘플 코드는 만들고 프린터에서 양면 인쇄를 지 원하는 경우는 <xref:System.Printing.PrintTicket> 이루어지는 요청입니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-120">If the printer supports duplexing, the sample code creates a <xref:System.Printing.PrintTicket> that asks for duplexing.</span></span> <span data-ttu-id="957e0-121">하지만 응용 프로그램 설정에서 사용할 수 있는 가능한 모든 프린터를 지정 하지 않습니다는 <xref:System.Printing.PrintTicket> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-121">But the application does not specify every possible printer setting available in the <xref:System.Printing.PrintTicket> element.</span></span> <span data-ttu-id="957e0-122">프로그래머와 프로그램 시간을 낭비 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-122">That would be wasteful of both programmer and program time.</span></span> <span data-ttu-id="957e0-123">코드를이 이루어지는 요청만 설정 하 고 다음이 병합 하는 대신 <xref:System.Printing.PrintTicket> 기존에 완벽 하 게 구성 하 고 유효성을 검사 <xref:System.Printing.PrintTicket>,이 경우 사용자의 기본 <xref:System.Printing.PrintTicket>입니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-123">Instead, the code sets only the duplexing request and then merges this <xref:System.Printing.PrintTicket> with an existing, fully configured and validated, <xref:System.Printing.PrintTicket>, in this case, the user's default <xref:System.Printing.PrintTicket>.</span></span>  
  
4. <span data-ttu-id="957e0-124">그에 따라 샘플을 호출 합니다 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 새로 병합 하는 방법 minimal <xref:System.Printing.PrintTicket> 사용자의 기본을 사용 하 여 <xref:System.Printing.PrintTicket>입니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-124">Accordingly, the sample calls the <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> method to merge the new, minimal, <xref:System.Printing.PrintTicket> with the user's default <xref:System.Printing.PrintTicket>.</span></span> <span data-ttu-id="957e0-125">반환 합니다.는 <xref:System.Printing.ValidationResult> 포함 하는 <xref:System.Printing.PrintTicket> 으로 해당 속성 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-125">This returns a <xref:System.Printing.ValidationResult> that includes the new <xref:System.Printing.PrintTicket> as one of its properties.</span></span>  
  
5. <span data-ttu-id="957e0-126">이 샘플에는 항목을 다음 테스트 새 <xref:System.Printing.PrintTicket> 양면 인쇄를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-126">The sample then tests that the new <xref:System.Printing.PrintTicket> requests duplexing.</span></span> <span data-ttu-id="957e0-127">이 경우 샘플을 사용 하 고 사용자에 대 한 새 기본 인쇄 티켓입니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-127">If it does, then the sample makes it the new default print ticket for the user.</span></span> <span data-ttu-id="957e0-128">위의 2 단계 생략 했습니다 및 프린터를 옆으로 이루어지는 지원 하지 않을 경우 테스트 결과는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-128">If step 2 above had been left out and the printer did not support duplexing along the long side, then the test would have resulted in `false`.</span></span> <span data-ttu-id="957e0-129">(위 참고 사항 참조).</span><span class="sxs-lookup"><span data-stu-id="957e0-129">(See the note above.)</span></span>  
  
6. <span data-ttu-id="957e0-130">마지막 중요 한 단계 하 여 변경 내용을 커밋하는 것 합니다 <xref:System.Printing.PrintQueue.UserPrintTicket%2A> 의 속성을 <xref:System.Printing.PrintQueue> 사용 하 여를 <xref:System.Printing.PrintQueue.Commit%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="957e0-130">The last significant step is to commit the change to the <xref:System.Printing.PrintQueue.UserPrintTicket%2A> property of the <xref:System.Printing.PrintQueue> with the <xref:System.Printing.PrintQueue.Commit%2A> method.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 <span data-ttu-id="957e0-131">이 예제에서는 신속 하 게 테스트할 수 있습니다, 있도록의 나머지 부분에서는 아래 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-131">So that you can quickly test this example, the remainder of it is presented below.</span></span> <span data-ttu-id="957e0-132">프로젝트 및 네임 스페이스를 만들고 두 코드 조각 네임 스페이스 블록에이 문서에 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="957e0-132">Create a project and a namespace and then paste both the code snippets in this article into the namespace block.</span></span>  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a><span data-ttu-id="957e0-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="957e0-133">See also</span></span>

- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [<span data-ttu-id="957e0-134">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="957e0-134">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="957e0-135">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="957e0-135">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="957e0-136">인쇄 스키마</span><span class="sxs-lookup"><span data-stu-id="957e0-136">Print Schema</span></span>](https://go.microsoft.com/fwlink/?LinkId=186397)
