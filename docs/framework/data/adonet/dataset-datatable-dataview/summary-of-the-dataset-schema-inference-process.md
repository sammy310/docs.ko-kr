---
title: 데이터 집합 스키마 유추 프로세스 요약
ms.date: 03/30/2017
ms.assetid: fd0891c8-d068-4e30-a76f-7c375f078bf7
ms.openlocfilehash: 272e5762b7afd9f3ab24cbdec5f31bb120364815
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116066"
---
# <a name="summary-of-the-dataset-schema-inference-process"></a>데이터 집합 스키마 유추 프로세스 요약
유추 과정에서는 우선 XML 문서에서 테이블로 유추될 요소를 결정합니다. 그런 다음 남아 있는 XML에서 해당 테이블의 열을 결정합니다. 중첩된 테이블인 경우에는 유추 과정에서 중첩된 <xref:System.Data.DataRelation> 및 <xref:System.Data.ForeignKeyConstraint> 개체를 생성합니다.  
  
 다음은 유추 규칙에 대해 간략히 요약한 것입니다.  
  
-   특성이 있는 요소는 테이블로 유추됩니다.  
  
-   자식 요소가 있는 요소는 테이블로 유추됩니다.  
  
-   반복되는 요소는 하나의 테이블로 유추됩니다.  
  
-   문서 요소에 열로 유추되는 특성이나 자식 요소가 없으면 문서 요소 또는 루트 요소는 <xref:System.Data.DataSet>으로 유추됩니다. 그렇지 않으면 문서 요소는 테이블로 유추됩니다.  
  
-   특성은 열로 유추됩니다.  
  
-   특성이나 자식 요소가 없거나 반복되지 않는 요소는 열로 유추됩니다.  
  
-   유추 되는 다른 요소 안에 중첩 된 테이블로 유추 되는 요소에 대 한 테이블로, 중첩 된 **DataRelation** 두 테이블 사이 만들어집니다. 라는 새 기본 키 열 **TableName_Id** 두 테이블에 추가 되 고 사용 합니다 **DataRelation**합니다. A **ForeignKeyConstraint** 사용 하 여 두 테이블 간에 만들어집니다 합니다 **TableName_Id** 열입니다.  
  
-   라는 새 열 테이블로 유추 되 고 텍스트를 포함 하지만 자식 요소가 없는 요소에 대 한 **TableName_Text** 텍스트의 각 요소에 만들어집니다. 테이블로 유추되는 요소에 텍스트와 자식 요소가 모두 있으면 해당 텍스트는 무시됩니다.  
  
## <a name="see-also"></a>참고자료

- [XML에서 데이터 집합 관계형 구조 유추](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/inferring-dataset-relational-structure-from-xml.md)
- [XML에서 데이터 집합 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [XML에서 데이터 집합 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [데이터 집합에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)
- [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
