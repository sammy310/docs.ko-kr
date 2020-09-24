---
title: '방법: 클래스 멤버로 열 표현'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ab28021-4d15-4d9c-bf2e-6ccc0daa7d1a
ms.openlocfilehash: e73b017b5a500a8c48b3fe22557f6c6619f3b227
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166354"
---
# <a name="how-to-represent-columns-as-class-members"></a>방법: 클래스 멤버로 열 표현

특성을 사용 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute> 하 여 필드 또는 속성을 데이터베이스 열과 연결 합니다.  
  
### <a name="to-map-a-field-or-property-to-a-database-column"></a>필드 또는 속성을 데이터베이스 열에 매핑하려면  
  
- <xref:System.Data.Linq.Mapping.ColumnAttribute> 특성을 속성 또는 필드 선언에 추가합니다.  
  
## <a name="example"></a>예제  

 다음 코드에서는 `CustomerID` 클래스의 `Customer` 필드를 `CustomerID` 데이터베이스 테이블의 `Customers` 열에 매핑합니다.  
  
 [!code-csharp[DLinqCustomize#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#2)]
 [!code-vb[DLinqCustomize#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#2)]  
  
 이름을 유추할 수 있는 경우에는 <xref:System.Data.Linq.Mapping.DataAttribute.Name%2A> 속성을 지정할 필요가 없습니다. 이름을 지정하지 않으면 이름은 속성 또는 필드의 이름과 동일한 것으로 간주됩니다.  
  
## <a name="see-also"></a>참고 항목

- [LINQ to SQL 개체 모델](the-linq-to-sql-object-model.md)
- [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](how-to-customize-entity-classes-by-using-the-code-editor.md)
