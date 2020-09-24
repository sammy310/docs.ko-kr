---
title: 관계 유추
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: ee691eee95c34afdb6374cdd7448d4b44ece3055
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177568"
---
# <a name="inferring-relationships"></a>관계 유추

테이블로 유추되는 요소에 역시 테이블로 유추되는 자식 요소가 있으면 두 테이블 사이에 <xref:System.Data.DataRelation>이 만들어집니다. **ParentTableName_Id** 이름이 인 새 열이 부모 요소에 대해 만들어진 테이블과 자식 요소에 대해 만들어진 테이블 모두에 추가 됩니다. 이 id 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다. 열은 부모 테이블의 자동 증분 기본 키가 되며 두 테이블 간의 **DataRelation** 에 사용 됩니다. 추가 된 id 열의 데이터 형식은 System.string 이며 다른 모든 유추 된 열의 데이터 형식 ( **system.string**)과는 **다릅니다.** <xref:System.Data.ForeignKeyConstraint> **DeleteRule**  =  부모 테이블과 자식 테이블 모두에서 새 열을 사용 하 여 DeleteRule**Cascade** 가 만들어집니다.  
  
 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 유추 프로세스에서는 **Element1** 및 **ChildElement1**라는 두 개의 테이블을 생성 합니다.  
  
 **Element1** 테이블에는 두 개의 열 **Element1_Id** 와 **childelement2 라는**가 있습니다. **Element1_Id** 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다. **Childelement2 라는** 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다. **Element1_Id** 열은 **Element1** 테이블의 기본 키로 설정 됩니다.  
  
 **ChildElement1** 테이블에는 **attr1**, **attr2** 및 **Element1_Id**라는 세 개의 열이 있습니다. **Attr1** 및 **attr2** 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다. **Element1_Id** 열의 **ColumnMapping** 속성은 **mappingtype.attribute**로 설정 됩니다.  
  
 **DataRelation** 및 **ForeignKeyConstraint** 는 두 테이블의 **Element1_Id** 열을 사용 하 여 생성 됩니다.  
  
 **데이터 집합:** DocumentElement  
  
 **테이블:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **테이블:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1_ChildElement1  
  
 **Parenttable:** Element1  
  
 **Parentcolumn:** Element1_Id  
  
 **Childtable:** ChildElement1  
  
 **Childcolumn:** Element1_Id  
  
 **중첩:** True  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **열:** Element1_Id  
  
 **Parenttable:** Element1  
  
 **Childtable:** ChildElement1  
  
 **DeleteRule:** 캐스케이딩  
  
 **AcceptRejectRule:** 없음을  
  
## <a name="see-also"></a>참고 항목

- [XML에서 데이터 세트 관계형 구조 유추](inferring-dataset-relational-structure-from-xml.md)
- [XML에서 데이터 세트 로드](loading-a-dataset-from-xml.md)
- [XML에서 데이터 세트 스키마 정보 로드](loading-dataset-schema-information-from-xml.md)
- [DataRelation 중첩](nesting-datarelations.md)
- [데이터 세트에서 XML 사용](using-xml-in-a-dataset.md)
- [DataSets, DataTables 및 DataViews](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
