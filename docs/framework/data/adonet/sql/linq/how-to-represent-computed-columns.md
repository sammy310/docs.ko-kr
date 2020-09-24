---
title: '방법: 계산 열 표현'
ms.date: 03/30/2017
ms.assetid: 4025f1fd-9dfa-46c0-b04f-34e8bc7957a2
ms.openlocfilehash: d952a6c22cd96bbc89aeebfa4b13e9727a363c73
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166328"
---
# <a name="how-to-represent-computed-columns"></a>방법: 계산 열 표현

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 특성의 속성을 사용 <xref:System.Data.Linq.Mapping.ColumnAttribute> 하 여 해당 내용이 계산 결과인 열을 나타낼 수 있습니다.  
  
 코드 예는 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A>를 참조하세요.  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서는 기본 키로 계산된 열을 지원하지 않습니다.  
  
### <a name="to-represent-a-computed-column"></a>계산된 열을 나타내려면  
  
1. <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.  
  
2. 수식의 문자열 표현을 <xref:System.Data.Linq.Mapping.ColumnAttribute.Expression%2A> 속성에 할당합니다.  
  
## <a name="see-also"></a>참고 항목

- [LINQ to SQL 개체 모델](the-linq-to-sql-object-model.md)
- [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](how-to-customize-entity-classes-by-using-the-code-editor.md)
