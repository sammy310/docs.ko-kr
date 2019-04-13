---
title: '방법: 정보 쿼리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: aedf89f1e570b34d31050fabb91842cefe351488
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162844"
---
# <a name="how-to-query-for-information"></a>방법: 정보 쿼리
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 쿼리는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 쿼리와 동일한 구문을 사용합니다. 유일한 차이점은에서 참조 된 개체가 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리 데이터베이스의 요소에 매핑됩니다. 자세한 내용은 [LINQ 쿼리 소개(C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 작성 한 쿼리를 해당 SQL 쿼리로 변환 하 고 처리를 위해 서버에 보냅니다.  
  
 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 쿼리의 일부 기능을 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램에서 사용할 때 특히 주의해야 합니다. 자세한 내용은 [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)합니다.  
  
## <a name="example"></a>예제  
 다음 쿼리에서는 London의 고객 목록을 요구합니다. 이 예제에서 `Customers`는 Northwind 샘플 데이터베이스의 테이블입니다.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>참고자료

- [개체 모델 만들기](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
- [샘플 데이터베이스 다운로드](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [데이터베이스 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
