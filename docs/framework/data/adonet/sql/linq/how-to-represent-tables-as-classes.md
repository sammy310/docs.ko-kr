---
title: '방법: 클래스로 테이블 표현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 84dda12b-88a2-4cd2-92b3-8db87b28d14c
ms.openlocfilehash: 49e7d6768d8739bba94c9e8d38bcc582c8bd6e4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902904"
---
# <a name="how-to-represent-tables-as-classes"></a>방법: 클래스로 테이블 표현
사용 된 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.TableAttribute> 클래스를 데이터베이스 테이블과 연결 된 엔터티 클래스로 지정 하는 특성입니다.  
  
### <a name="to-map-a-class-to-a-database-table"></a>데이터베이스 테이블에 클래스를 매핑하려면  
  
-   <xref:System.Data.Linq.Mapping.TableAttribute> 특성을 클래스 선언에 추가합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `Customer` 클래스를 `Customers` 데이터베이스 테이블과 연결된 엔터티 클래스로 설정합니다.  
  
 [!code-csharp[DLinqCustomize#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#1)]
 [!code-vb[DLinqCustomize#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#1)]  
  
 이름을 유추할 수 있는 경우에는 <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> 속성을 지정할 필요가 없습니다. 이름을 지정하지 않으면 이름은 속성 또는 필드의 이름과 동일한 것으로 간주됩니다.  
  
## <a name="see-also"></a>참고자료

- [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [방법: 코드 편집기를 사용 하 여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
