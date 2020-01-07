---
title: '방법: 정보 쿼리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 3380b486da33a5dc083ed51f6705e666978df197
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634653"
---
# <a name="how-to-query-for-information"></a>방법: 정보 쿼리
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리는 LINQ의 쿼리와 동일한 구문을 사용 합니다. 유일한 차이점은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리에서 참조 되는 개체가 데이터베이스의 요소에 매핑되는 것입니다. 자세한 내용은 [LINQ 쿼리 소개(C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 작성한 쿼리를 해당 SQL 쿼리로 변환하고 SQL Server에 전달하여 처리합니다.  
  
 LINQ 쿼리의 일부 기능은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 응용 프로그램에서 특별히 주의 해야 할 수 있습니다. 자세한 내용은 [쿼리 개념](query-concepts.md)을 참조 하세요.  
  
## <a name="example"></a>예  
 다음 쿼리에서는 London의 고객 목록을 요구합니다. 이 예제에서 `Customers`는 Northwind 샘플 데이터베이스의 테이블입니다.  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>참조

- [개체 모델 만들기](creating-the-object-model.md)
- [샘플 데이터베이스 다운로드](downloading-sample-databases.md)
- [데이터베이스 쿼리](querying-the-database.md)
