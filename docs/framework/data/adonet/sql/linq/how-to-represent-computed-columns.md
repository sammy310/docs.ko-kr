---
title: '방법: 계산 열 표현'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: 01c3442448285893ebb476ed11889e073065d4d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69943539"
---
# <a name="how-to-represent-computed-columns"></a>방법: 계산 열 표현
특성의 속성을 사용 하 여 해당 내용이 계산 결과인 열을 나타낼 수 있습니다. <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute>  
  
 코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>를 참조하세요.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 기본 키로 계산된 열을 지원하지 않습니다.  
  
### <a name="to-represent-a-computed-column"></a>계산된 열을 나타내려면  
  
1. <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.  
  
2. 수식의 문자열 표현을 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 속성에 할당합니다.  
  
## <a name="see-also"></a>참고자료

- [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [방법: 코드 편집기를 사용 하 여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
