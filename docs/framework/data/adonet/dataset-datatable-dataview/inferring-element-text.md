---
title: 요소 텍스트 유추
ms.date: 03/30/2017
ms.assetid: 789799e5-716f-459f-a168-76c5cf22178b
ms.openlocfilehash: 6ffe8f2fbf01fbe8dfa9d78f3dfb9e39b6e80b16
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224964"
---
# <a name="inferring-element-text"></a>요소 텍스트 유추
요소 텍스트를 포함 하 고 테이블로 유추 될 (특성이 있는 요소) 또는 반복 되는 요소와 같은 이름 가진 새 열을 자식 요소가 없는 경우 **TableName_Text** 요소의 유추 테이블에 추가 됩니다. 이 요소에 포함된 텍스트는 테이블의 행에 추가되어 새 열에 저장됩니다. 합니다 **ColumnMapping** 새 열의 속성에 설정할 **MappingType.SimpleContent**합니다.  
  
 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<DocumentElement>  
  <Element1 attr1="value1">Text1</Element1>  
</DocumentElement>  
```  
  
 유추 과정 이라는 테이블이 생성 됩니다 **Element1** 두 개의 열을 사용 하 여: **attr1** 하 고 **Element1_Text**합니다. 합니다 **ColumnMapping** 의 속성을 **attr1** 열으로 설정 됩니다 **MappingType.Attribute**합니다. 합니다 **ColumnMapping** 의 속성을 **Element1_Text** 열으로 설정 됩니다 **MappingType.SimpleContent**합니다.  
  
 **DataSet:** DocumentElement  
  
 **테이블:** Element1  
  
|attr1|Element1_Text|  
|-----------|--------------------|  
|value1|Text1|  
  
 요소에 텍스트뿐만 아니라 텍스트가 포함된 자식 요소도 있는 경우에는 해당 요소에 포함된 텍스트를 저장할 열이 테이블에 추가되지 않습니다. 따라서 이 요소에 포함된 텍스트는 무시되지만 자식 요소에 있는 텍스트는 해당 테이블의 행에 저장됩니다. 예를 들어, 다음과 같은 XML을 가정해 봅시다.  
  
```xml  
<Element1>  
  Text1  
  <ChildElement1>Text2</ChildElement1>  
  Text3  
</Element1>  
```  
  
 유추 과정 이라는 테이블이 생성 됩니다 **Element1** 라는 열이 하나인 **ChildElement1**합니다. 에 대 한 텍스트를 **ChildElement1** 요소는 테이블의 행에 포함 됩니다. 다른 텍스트는 무시됩니다. 합니다 **ColumnMapping** 의 속성을 **ChildElement1** 열으로 설정 됩니다 **MappingType.Element**합니다.  
  
 **DataSet:** DocumentElement  
  
 **테이블:** Element1  
  
|ChildElement1|  
|-------------------|  
|Text2|  
  
## <a name="see-also"></a>참고자료

- [XML에서 데이터 집합 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [XML에서 데이터 집합 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
