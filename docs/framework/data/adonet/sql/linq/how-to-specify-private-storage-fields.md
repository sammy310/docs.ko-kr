---
title: '방법: 전용 스토리지 필드 지정'
ms.date: 03/30/2017
ms.assetid: 5a40e816-cc6e-43a0-b32a-9caaa0ab6912
ms.openlocfilehash: e0928b2f2e817c8cc936f7aa1190229842a121a3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195438"
---
# <a name="how-to-specify-private-storage-fields"></a>방법: 전용 스토리지 필드 지정
사용 하 여는 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 속성에는 <xref:System.Data.Linq.Mapping.DataAttribute> 특성을 기본 저장소 필드의 이름을 지정 합니다.  
  
 코드 예는 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A>를 참조하세요.  
  
### <a name="to-specify-the-name-of-an-underlying-storage-field"></a>기본 저장소 필드의 이름을 지정하려면  
  
1.  <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 특성에 <xref:System.Data.Linq.Mapping.ColumnAttribute> 속성을 추가합니다.  
  
2.  필드의 이름을 <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A> 속성의 값으로 지정합니다.  
  
## <a name="see-also"></a>참고자료

- [LINQ to SQL 개체 모델](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [방법: 코드 편집기를 사용하여 엔터티 클래스 사용자 지정](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
