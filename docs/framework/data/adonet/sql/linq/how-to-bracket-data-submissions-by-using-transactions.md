---
title: '방법: 트랜잭션을 사용하여 대괄호로 묶은 데이터 전송'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
ms.openlocfilehash: 4d3efedbf15be55fa7a9ab235f881f1c97758953
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161362"
---
# <a name="how-to-bracket-data-submissions-by-using-transactions"></a>방법: 트랜잭션을 사용하여 대괄호로 묶은 데이터 전송

<xref:System.Transactions.TransactionScope>를 사용하여 데이터베이스에 대한 전송을 표시합니다. 자세한 내용은 [트랜잭션 지원](transaction-support.md)을 참조 하세요.  
  
## <a name="example"></a>예제  

 다음 코드에서는 데이터베이스 전송을 <xref:System.Transactions.TransactionScope>로 묶습니다.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>참고 항목

- [샘플 데이터베이스 다운로드](downloading-sample-databases.md)
- [데이터 변경 및 변경 내용 전송](making-and-submitting-data-changes.md)
- [트랜잭션 지원](transaction-support.md)
