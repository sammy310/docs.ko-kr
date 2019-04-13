---
title: 관계 유추
ms.date: 03/30/2017
ms.assetid: 8fa86a9d-6545-4a9d-b1f5-58d9742179c7
ms.openlocfilehash: f8a9aba493dfe82466608ea60932ddfec5ef64f1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127883"
---
# <a name="inferring-relationships"></a>관계 유추
테이블로 유추되는 요소에 역시 테이블로 유추되는 자식 요소가 있으면 두 테이블 사이에 <xref:System.Data.DataRelation>이 만들어집니다. 새 열 이름 가진 **ParentTableName_Id** 부모 요소에 대해 만들어진 테이블과 자식 요소에 대해 생성 된 테이블에 추가 됩니다. 합니다 **ColumnMapping** id 열 속성에 설정할 **MappingType.Hidden**합니다. 열은 부모 테이블에 대 한 자동 증분 기본 키 되며 사용할지 합니다 **DataRelation** 두 테이블 간에 합니다. 추가 id 열의 데이터 형식은 **System.Int32**에 데이터 형식의 다른 모든 유추 된 열과 달리 **System.String**합니다. A <xref:System.Data.ForeignKeyConstraint> 사용 하 여 **DeleteRule** = **Cascade** 부모 테이블과 자식 테이블에 새 열을 사용 하 여도 생성 됩니다.  
  
 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1>  
    <ChildElement1 attr1="value1" attr2="value2"/>  
    <ChildElement2>Text2</ChildElement2>  
  </Element1>  
</DocumentElement>  
```  
  
 유추 과정에서 두 테이블을 생성 합니다. **Element1** 하 고 **ChildElement1**합니다.  
  
 합니다 **Element1** 테이블 두 개의 열이 포함 됩니다. **Element1_Id** 하 고 **ChildElement2**합니다. 합니다 **ColumnMapping** 의 속성을 **Element1_Id** 열으로 설정 됩니다 **MappingType.Hidden**합니다. 합니다 **ColumnMapping** 의 속성을 **ChildElement2** 열으로 설정 됩니다 **MappingType.Element**합니다. **Element1_Id** 의 기본 키로 설정할 열을 **Element1** 테이블.  
  
 **ChildElement1** 테이블 3 개 열이 포함 됩니다. **attr1**, **attr2** 및 **Element1_Id**합니다. **ColumnMapping** 에 대 한 속성을 **attr1** 및 **attr2** 열에 설정할 **MappingType.Attribute**합니다. 합니다 **ColumnMapping** 의 속성을 **Element1_Id** 열으로 설정 됩니다 **MappingType.Hidden**합니다.  
  
 A **DataRelation** 및 **ForeignKeyConstraint** 사용 하 여 만들어집니다 합니다 **Element1_Id** 두 테이블의 열입니다.  
  
 **DataSet:** DocumentElement  
  
 **테이블:** Element1  
  
|Element1_Id|ChildElement2|  
|------------------|-------------------|  
|0|Text2|  
  
 **테이블:** ChildElement1  
  
|attr1|attr2|Element1_Id|  
|-----------|-----------|------------------|  
|value1|value2|0|  
  
 **DataRelation:** Element1_ChildElement1  
  
 **ParentTable:** Element1  
  
 **ParentColumn:** Element1_Id  
  
 **ChildTable:** ChildElement1  
  
 **ChildColumn:** Element1_Id  
  
 **중첩 되어 있습니다.** True  
  
 **ForeignKeyConstraint:** Element1_ChildElement1  
  
 **열:** Element1_Id  
  
 **ParentTable:** Element1  
  
 **ChildTable:** ChildElement1  
  
 **DeleteRule:** Cascade  
  
 **AcceptRejectRule:** 없음  
  
## <a name="see-also"></a>참고자료

- [XML에서 데이터 집합 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [XML에서 데이터 집합 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [DataRelation 중첩](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations.md)
- [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
