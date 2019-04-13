---
title: DataTable 제약 조건
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 254f486fa19d8af30759d9a9fd6642a1a40e82a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165180"
---
# <a name="datatable-constraints"></a>DataTable 제약 조건
제약 조건을 사용하여 <xref:System.Data.DataTable>의 데이터를 제한함으로써 데이터 무결성을 유지할 수 있습니다. 제약 조건은 자동 규칙이기 때문에 행 값이 조금이라도 변경되면 열 또는 관련 열에 적용되어 작업 과정을 결정합니다. 제약 조건이 적용 됩니다 때 합니다 `System.Data.DataSet.EnforceConstraints` 의 속성을 <xref:System.Data.DataSet> 는 **true**. `EnforceConstraints` 속성을 설정하는 방법을 보여 주는 코드 예제는 <xref:System.Data.DataSet.EnforceConstraints%2A> 참조 항목을 참조하세요.  
  
 ADO.NET에는 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint>의 두 가지 제약 조건이 있습니다. 기본적으로 두 제약 조건이 만들어지면 자동으로 추가 하 여 두 개 이상의 테이블 간에 관계를 만들 때를 <xref:System.Data.DataRelation> 에 **데이터 집합**합니다. 그러나 지정 하 여이 동작을 비활성화할 수 있습니다 **createConstraints** = **false** 관계를 만들 때.  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  
 A **ForeignKeyConstraint** 업데이트 및 삭제 관련된 테이블에 전파 하는 방법에 대 한 규칙을 적용 합니다. 예를 들어 한 테이블의 행에 있는 값이 업데이트 되거나 삭제 및 동일한 값도 또는에서 사용 될 하나 이상의 관련 테이블을 **ForeignKeyConstraint** 관련된 테이블에서 수행할 작업을 결정 합니다.  
  
 합니다 <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> 및 <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> 의 속성을 **ForeignKeyConstraint** 사용자를 삭제 하거나 관련된 테이블의 행을 업데이트 하려고 할 때 수행할 동작을 정의 합니다. 다음 표에서 다양 한 설정에 사용할 수 있는 **DeleteRule** 및 **UpdateRule** 의 속성을 **ForeignKeyConstraint**합니다.  
  
|규칙 설정|설명|  
|------------------|-----------------|  
|**Cascade**|관련 행을 삭제하거나 업데이트합니다.|  
|**SetNull**|관련된 행에서 값을 설정 **DBNull**합니다.|  
|**SetDefault**|관련 행의 값을 기본값으로 설정합니다.|  
|**없음**|관련 행에 대해 아무 동작도 수행하지 않습니다. 이 값이 기본값입니다.|  
  
 A **ForeignKeyConstraint** 제한할 수 있습니다, 전파 하는 것은 물론 관련 열을 변경 합니다. 속성에 대 한 설정에 따라를 **ForeignKeyConstraint** 열의 경우를 **EnforceConstraints** 의 속성을 **데이터 집합** 는 **true**, 부모 행에서 특정 작업을 수행 하면 예외가 발생 됩니다. 예를 들어 경우는 **DeleteRule** 의 속성을 **ForeignKeyConstraint** 는 **없음**, 모든 자식 행이 있는 경우 부모 행을 삭제할 수 없습니다.  
  
 foreign key 제약 조건을 사용 하 여 열 배열 간 또는 단일 열을 만들 수 있습니다 합니다 **ForeignKeyConstraint** 생성자입니다. 결과 전달 **ForeignKeyConstraint** 개체를 **추가** 테이블의 메서드 **제약 조건** 속성을 **ConstraintCollection**. 몇 가지 오버 로드에 생성자 인수를 전달할 수도 있습니다는 **추가** 메서드를 **ConstraintCollection** 만들려는 **ForeignKeyConstraint**합니다.  
  
 만들 때를 **ForeignKeyConstraint**, 전달할 수 있습니다 합니다 **DeleteRule** 및 **UpdateRule** 인수 하거나 생성자에 값으로 속성으로 설정할 수는 다음 예제에서는 (여기서는 **DeleteRule** 값으로 설정 됩니다 **None**).  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None    
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],   
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;    
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a>AcceptRejectRule  
 사용 하 여 행의 변경 내용에 허용 될 수는 **AcceptChanges** 메서드 또는 취소를 사용 하는 **RejectChanges** 메서드를 **데이터 집합**, **DataTable**, 또는 **DataRow**합니다. 경우는 **데이터 집합** 포함 **ForeignKeyConstraints**호출, 합니다 **AcceptChanges** 또는 **RejectChanges** 메서드에 적용 합니다  **AcceptRejectRule**합니다. 합니다 **AcceptRejectRule** 의 속성을 **ForeignKeyConstraint** 자식 요소에서 수행 될 작업을 결정 경우 행 **AcceptChanges** 또는  **RejectChanges** 부모 행에서 호출 됩니다.  
  
 다음 표에서 사용 가능한 설정 합니다 **AcceptRejectRule**합니다.  
  
|규칙 설정|설명|  
|------------------|-----------------|  
|**Cascade**|자식 행의 변경을 승인하거나 거부합니다.|  
|**없음**|자식 행에 대해 아무 동작도 수행하지 않습니다. 이 값이 기본값입니다.|  
  
### <a name="example"></a>예제  
 다음 예제에서는<xref:System.Data.ForeignKeyConstraint>를 만들고 <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>을 비롯한 해당 속성을 몇 가지 설정한 다음 <xref:System.Data.ConstraintCollection> 개체의 <xref:System.Data.DataTable>에 추가합니다.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  
 합니다 **UniqueConstraint** 단일 열 또는 열 배열에 할당할 수 있는 개체를 **DataTable**, 지정 된 열 또는 열의 모든 데이터가 행별로 고유한 인지 확인 합니다. 열 또는 열 배열의 unique 제약 조건을 사용 하 여 만들 수 있습니다 합니다 **UniqueConstraint** 생성자입니다. 결과 전달 **UniqueConstraint** 개체를 **추가** 테이블의 메서드 **제약 조건** 속성을 **ConstraintCollection**. 몇 가지 오버 로드에 생성자 인수를 전달할 수도 있습니다는 **추가** 메서드를 **ConstraintCollection** 만들려는 **UniqueConstraint**합니다. 만들 때를 **UniqueConstraint** 열 또는 열을 지정할 수도 있습니다 하나 이상의 열이 기본 키인지 여부를 합니다.  
  
 설정 하 여 열에 대해 unique 제약 조건을 만들 수도 있습니다는 **Unique** 열의 속성 **true**합니다. 또는 설정 합니다 **Unique** 단일 열의 속성 **false** 존재할 수 있는 모든 unique 제약 조건을 제거 합니다. 하나 이상의 열을 테이블의 기본 키로 정의하면 지정한 열에 대한 UNIQUE 제약 조건이 자동으로 만들어집니다. 열을 제거 하는 경우는 **PrimaryKey** 의 속성을 **DataTable**의 **UniqueConstraint** 제거 됩니다.  
  
 다음 예제에서는 **UniqueConstraint** 의 두 개의 열에는 **DataTable**합니다.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]   
    {custTable.Columns["CustomerID"],   
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [DataSets, DataTables 및 DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
