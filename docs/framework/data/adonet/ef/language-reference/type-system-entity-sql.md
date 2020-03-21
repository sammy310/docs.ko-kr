---
title: 형식 시스템(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 818a505b-a196-41dd-aaac-2ccd5f7a2f1a
ms.openlocfilehash: b8b721aff5b7886fdb897ecaa3dcc163ec94ae79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149833"
---
# <a name="type-system-entity-sql"></a>형식 시스템(Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]다음과 같은 여러 가지 유형을 지원합니다.  
  
- 기본(단순) 형식 - `Int32` 및 `String.`  
  
- 명목 형식 - 스키마에서 정의됨. <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.ComplexType> 및 <xref:System.Data.Metadata.Edm.RelationshipType>  
  
- 익명 형식 - 스키마에서 명시적으로 정의되지 않음. <xref:System.Data.Metadata.Edm.CollectionType>, <xref:System.Data.Metadata.Edm.RowType> 및 <xref:System.Data.Metadata.Edm.RefType>  
  
 이 섹션에서는 스키마에 명시적으로 정의되지 않았지만 Entity SQL에서 지원하는 익명 형식에 대해 설명합니다. 기본 및 공칭 형식에 대한 자세한 내용은 [CSDL(개념식 모델 유형)을](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)참조하십시오.  
  
## <a name="rows"></a>행  
 행의 구조는 행이 구성된 형식화된 멤버 및 명명된 멤버의 시퀀스에 따라 달라집니다. 행 형식은 ID를 갖지 않으며 상속받을 수 없습니다. 멤버가 각각 동일한 경우 같은 행 형식의 인스턴스는 서로 동일합니다. 행은 구조가 동일한 것을 제외한 어떠한 동작도 갖지 않으며 공용 언어 런타임에 해당하는 항목이 없습니다. 쿼리를 실행하면 행 또는 행 컬렉션이 포함된 구조가 생성될 수 있습니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리와 호스트 언어 간의 API 바인딩은 결과를 생성하는 쿼리에서 행이 구현되는 방법을 정의합니다. 행 인스턴스를 생성하는 방법에 대한 자세한 내용은 [유형 생성](constructing-types-entity-sql.md)을 참조하십시오.  
  
## <a name="collections"></a>컬렉션  
 컬렉션 형식은 다른 개체의 0개 이상 인스턴스를 나타냅니다. 컬렉션을 생성하는 방법에 대한 자세한 내용은 [생성 형식을](constructing-types-entity-sql.md)참조하십시오.  
  
## <a name="references"></a>참조  
 참조는 특정 엔터티 집합 내의 특정 엔터티를 가리키는 논리 포인터입니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 참조를 통한 생성, 해체 및 탐색에 사용되는 다음 연산자를 지원합니다.  
  
- [Ref](ref-entity-sql.md)  
  
- [CREATEREF](createref-entity-sql.md)  
  
- [키](key-entity-sql.md)  
  
- [DEREF](deref-entity-sql.md)  
  
 멤버 액세스(dot) 연산자(`.`)를 사용하여 참조를 탐색할 수 있습니다. 다음 조각에서는 r(참조) 속성을 탐색하여 Id 속성(Order)을 추출합니다.  
  
```sql  
select o2.r.Id
from (select ref(o) as r from LOB.Orders as o) as o2
```  
  
 참조 값이 null이거나 참조 대상이 존재하지 않는 경우 결과는 null입니다.  
  
## <a name="see-also"></a>참고 항목

- [Entity SQL 개요](entity-sql-overview.md)
- [엔터티 SQL 참조](entity-sql-reference.md)
- [CAST](cast-entity-sql.md)
- [CSDL, SSDL 및 MSL 사양](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)
