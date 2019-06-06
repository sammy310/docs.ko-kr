---
title: 시작
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
ms.openlocfilehash: 6f9592ecebdaaac7cdec60ce12e99b910275d553
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490059"
---
# <a name="getting-started"></a>시작
사용 하 여 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 사용할 수는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 메모리 내 컬렉션을 액세스 하는 것 처럼 데이터베이스를 SQL에 액세스 하는 기술입니다.  
  
 예를 들어 다음 코드에서 `nw` 개체는 `Northwind` 데이터베이스를 나타내기 위해 만든 것으로 `Customers` 테이블을 대상으로 열은 `Customers`에서 `London`가 필터링되고 `CompanyName`에 대한 문자열은 검색용으로 선택됩니다.  
  
 루프가 실행되면 `CompanyName` 값의 컬렉션이 검색됩니다.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="next-steps"></a>다음 단계  
 삽입 및 업데이트를 비롯 한 몇 가지 추가 예제를 참조 하세요 [어떤 있습니다 수 수행 된 LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md)합니다.  
  
 그런 다음 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]을 사용하는 실제 경험을 가지는 연습과 자습서를 시도해 보세요. 참조 [연습으로 학습](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)합니다.  
  
 마지막으로 직접 시작 하는 방법에 알아봅니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 프로젝트를 읽으면 [LINQ to SQL 사용을 위한 일반 단계](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)
- [LINQ 소개 (C#)](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [LINQ 소개(Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/introduction-to-linq.md)
- [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
