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
ms.openlocfilehash: 2be08f5d3c2cd82e50569a105e3fa15f12ad352c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355170"
---
# <a name="how-to-validate-and-merge-printtickets"></a>방법: PrintTicket 유효성 검사 및 병합
합니다 [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)] [Print Schema](https://go.microsoft.com/fwlink/?LinkId=186397) 융통성 있고 확장 가능한 포함 <xref:System.Printing.PrintCapabilities> 및 <xref:System.Printing.PrintTicket> 요소입니다. 이전 인쇄 장치 기능을 항목별로 정리 하 고 후자 지정이 장치 문서, 개별 문서 또는 개별 페이지의 특정 시퀀스에 대해 해당 기능을 어떻게 사용 해야 합니다.  
  
 인쇄를 지 원하는 응용 프로그램에 대 한 작업의 일반적인 순서는 다음과 같은 것입니다.  
  
1.  프린터의 기능을 확인 합니다.  
  
2.  구성 된 <xref:System.Printing.PrintTicket> 해당 기능을 사용 하도록 합니다.  
  
3.  유효성 검사는 <xref:System.Printing.PrintTicket>합니다.  
  
 이 문서에서는이 작업을 수행 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 아래의 간단한 예제에서는 관심이 프린터 이루어지는 지원할 수 있는지 여부, 양면 인쇄 합니다. 주요 단계는 다음과 같습니다.  
  
1.  가져오기는 <xref:System.Printing.PrintCapabilities> 개체는 <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A> 메서드.  
  
2.  원하는 기능의 존재 여부를 테스트 합니다. 아래 예제에서는 테스트를 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 의 속성을 <xref:System.Printing.PrintCapabilities> 시트의 옆으로 "페이지 넘기기"를 사용 하 여 용지의 양면 인쇄 기능이 있는지에 대 한 개체입니다. 이후 <xref:System.Printing.PrintCapabilities.DuplexingCapability%2A> 은 컬렉션 사용 합니다 `Contains` 메서드의 <xref:System.Collections.ObjectModel.ReadOnlyCollection%601>.  
  
    > [!NOTE]
    >  이 단계가 꼭 필요 하지 않습니다. 합니다 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 아래에서 사용 하는 방법에 각 요청을 확인 합니다는 <xref:System.Printing.PrintTicket> 프린터의 기능에 대 한 합니다. 프린터에서 요청한 기능을 사용할 수 없습니다, 프린터 드라이버에서 다른 요청을 대체 합니다는 <xref:System.Printing.PrintTicket> 메서드에서 반환 합니다.  
  
3.  샘플 코드는 만들고 프린터에서 양면 인쇄를 지 원하는 경우는 <xref:System.Printing.PrintTicket> 이루어지는 요청입니다. 하지만 응용 프로그램 설정에서 사용할 수 있는 가능한 모든 프린터를 지정 하지 않습니다는 <xref:System.Printing.PrintTicket> 요소입니다. 프로그래머와 프로그램 시간을 낭비 될 것입니다. 코드를이 이루어지는 요청만 설정 하 고 다음이 병합 하는 대신 <xref:System.Printing.PrintTicket> 기존에 완벽 하 게 구성 하 고 유효성을 검사 <xref:System.Printing.PrintTicket>,이 경우 사용자의 기본 <xref:System.Printing.PrintTicket>입니다.  
  
4.  그에 따라 샘플을 호출 합니다 <xref:System.Printing.PrintQueue.MergeAndValidatePrintTicket%2A> 새로 병합 하는 방법 minimal <xref:System.Printing.PrintTicket> 사용자의 기본을 사용 하 여 <xref:System.Printing.PrintTicket>입니다. 반환 합니다.는 <xref:System.Printing.ValidationResult> 포함 하는 <xref:System.Printing.PrintTicket> 으로 해당 속성 중 하나입니다.  
  
5.  이 샘플에는 항목을 다음 테스트 새 <xref:System.Printing.PrintTicket> 양면 인쇄를 요청 합니다. 이 경우 샘플을 사용 하 고 사용자에 대 한 새 기본 인쇄 티켓입니다. 위의 2 단계 생략 했습니다 및 프린터를 옆으로 이루어지는 지원 하지 않을 경우 테스트 결과는 `false`합니다. (위 참고 사항 참조).  
  
6.  마지막 중요 한 단계 하 여 변경 내용을 커밋하는 것 합니다 <xref:System.Printing.PrintQueue.UserPrintTicket%2A> 의 속성을 <xref:System.Printing.PrintQueue> 사용 하 여를 <xref:System.Printing.PrintQueue.Commit%2A> 메서드.  
  
 [!code-csharp[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#usingmergeandvalidate)]
 [!code-vb[PrintTicketManagment#UsingMergeAndValidate](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#usingmergeandvalidate)]  
  
 이 예제에서는 신속 하 게 테스트할 수 있습니다, 있도록의 나머지 부분에서는 아래 표시 됩니다. 프로젝트 및 네임 스페이스를 만들고 두 코드 조각 네임 스페이스 블록에이 문서에 붙여 넣습니다.  
  
 [!code-csharp[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintTicketManagment/CSharp/printticket.cs#uiformergeandvalidateptutility)]
 [!code-vb[PrintTicketManagment#UIForMergeAndValidatePTUtility](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintTicketManagment/visualbasic/printticket.vb#uiformergeandvalidateptutility)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Printing.PrintCapabilities>
- <xref:System.Printing.PrintTicket>
- <xref:System.Printing.PrintServer.GetPrintQueues%2A>
- <xref:System.Printing.PrintServer>
- <xref:System.Printing.EnumeratedPrintQueueTypes>
- <xref:System.Printing.PrintQueue>
- <xref:System.Printing.PrintQueue.GetPrintCapabilities%2A>
- [WPF의 문서](documents-in-wpf.md)
- [인쇄 개요](printing-overview.md)
- [인쇄 스키마](https://go.microsoft.com/fwlink/?LinkId=186397)
