---
title: DataRelation 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 9cefc97e571f315a6a644e0a058d4283168ecb9f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034525"
---
# <a name="adding-datarelations"></a>DataRelation 추가
여러 <xref:System.Data.DataSet> 개체가 포함된 <xref:System.Data.DataTable>에서는 <xref:System.Data.DataRelation> 개체를 사용하여 하나의 테이블을 다른 테이블에 연관시키거나, 테이블 사이를 탐색하거나, 연관된 테이블의 자식 또는 부모 행을 반환할 수 있습니다.  
  
 만드는 데 필요한 인수를 **DataRelation** 에 대 한 이름과 합니다 **DataRelation** 생성 되 고 하나 이상의 배열 <xref:System.Data.DataColumn> 부모 및 자식으로 작동 하는 열에 대 한 참조 관계의 열입니다. 만든 후에 **DataRelation**, 테이블 사이 탐색 하 고 값을 검색 하려면 사용할 수 있습니다.  
  
 추가 **DataRelation** 에 <xref:System.Data.DataSet> 기본적으로 추가 <xref:System.Data.UniqueConstraint> 부모 테이블에 및 <xref:System.Data.ForeignKeyConstraint> 자식 테이블에 있습니다. 이러한 기본 제약 조건에 대 한 자세한 내용은 참조 하세요. [DataTable 제약 조건](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)합니다.  
  
 다음 코드 예제는 **DataRelation** 2를 사용 하 여 <xref:System.Data.DataTable> 개체를 <xref:System.Data.DataSet>. 각 <xref:System.Data.DataTable> 라는 열이 포함 되어 **CustID**, 둘 사이의 링크로 작동 하는 <xref:System.Data.DataTable> 개체입니다. 이 예제에서는 단일 추가 **DataRelation** 에 **관계** 의 컬렉션을 <xref:System.Data.DataSet>. 예제에서 첫 번째 인수의 이름을 지정 합니다 **DataRelation** 만들어지는 합니다. 부모를 설정 하는 두 번째 인수 **DataColumn** 세 번째 인수 설정 자식 **DataColumn**합니다.  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 **DataRelation** 역시를 **중첩** 속성을로 설정 하면 **true**을 부모 테이블의 관련된 행 내에서 중첩 된 자식 테이블에서 행을 사용 하면 사용 하 여 XML 요소로 작성할 경우 <xref:System.Data.DataSet.WriteXml%2A> 합니다. 자세한 내용은 [데이터 세트에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)을 참조하세요.  
  
## <a name="see-also"></a>참고자료

- [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
