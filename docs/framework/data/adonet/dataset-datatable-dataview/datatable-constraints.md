---
title: DataTable 제약 조건
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 4b7972c281786a4e36d0e9c1e455776a293423ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151288"
---
# <a name="datatable-constraints"></a>DataTable 제약 조건
제약 조건을 사용하여 <xref:System.Data.DataTable>의 데이터를 제한함으로써 데이터 무결성을 유지할 수 있습니다. 제약 조건은 자동 규칙이기 때문에 행 값이 조금이라도 변경되면 열 또는 관련 열에 적용되어 작업 과정을 결정합니다. 구속조건은 의 `System.Data.DataSet.EnforceConstraints` <xref:System.Data.DataSet> 속성이 **true일**때 적용됩니다. `EnforceConstraints` 속성을 설정하는 방법을 보여 주는 코드 예제는 <xref:System.Data.DataSet.EnforceConstraints%2A> 참조 항목을 참조하세요.  
  
 ADO.NET에는 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint>의 두 가지 제약 조건이 있습니다. 기본적으로 두 제약 조건은 <xref:System.Data.DataRelation> **DataSet**에 a를 추가하여 두 개 이상의 테이블 간의 관계를 만들 때 자동으로 만들어집니다. 그러나 관계를 만들**때** false **만들기를** = 지정하여 이 동작을 비활성화할 수 있습니다.  
  
## <a name="foreignkeyconstraint"></a>ForeignKeyConstraint  
 **ForeignKeyConstraint는** 관련 테이블에 대한 업데이트 및 삭제가 전파되는 방법에 대한 규칙을 적용합니다. 예를 들어 한 테이블의 행에 있는 값이 업데이트되거나 삭제되고 동일한 값이 하나 이상의 관련 테이블에서도 사용되는 경우 **ForeignKeyConstraint는** 관련 테이블에서 발생하는 일을 결정합니다.  
  
 <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> **ForeignKeyConstraint의** 및 <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> 속성은 사용자가 관련 테이블에서 행을 삭제하거나 업데이트하려고 할 때 수행되는 작업을 정의합니다. 다음 표는 **ForeignKeyConstraint의** **DeleteRule** 및 **UpdateRule** 속성에 사용할 수 있는 다른 설정에 대해 설명합니다.  
  
|규칙 설정|Description|  
|------------------|-----------------|  
|**캐스케이드**|관련 행을 삭제하거나 업데이트합니다.|  
|**SetNull**|관련 행의 값을 **DBNull로**설정합니다.|  
|**SetDefault**|관련 행의 값을 기본값으로 설정합니다.|  
|**없음**|관련 행에 대해 아무 동작도 수행하지 않습니다. 이것이 기본값입니다.|  
  
 **ForeignKeyConstraint는** 관련 열에 대한 변경 내용을 제한하고 전파할 수 있습니다. 열의 **ForeignKeyConstraint에** 대해 설정된 속성에 따라 **DataSet의** **EnforceConstraints** 속성이 **true인**경우 부모 행에서 특정 작업을 수행하면 예외가 발생합니다. 예를 들어 **ForeignKeyConstraint의** **DeleteRule** 속성이 **없음인**경우 하위 행이 있는 경우 부모 행을 삭제할 수 없습니다.  
  
 **ForeignKeyConstraint** 생성자사용으로 단일 열 간에 또는 열 배열 사이에 외래 키 제약 조건을 만들 수 있습니다. 결과 **ForeignKeyConstraint** 개체를 테이블의 **제약 조건** 속성의 **메서드 추가** **메서드에**전달합니다. 생성자 인수를 **제약 조건** 의 **Add** 메서드의 여러 오버로드에 전달하여 **ForeignKeyConstraint을**만들 수도 있습니다.  
  
 **ForeignKeyConstraint를**만들 때 **DeleteRule** 및 **UpdateRule** 값을 생성자에게 인수로 전달하거나 다음 예제와 같이 속성으로 설정할 수 있습니다(DeleteRule 값이 **없음으로**설정된 경우). **DeleteRule**  
  
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
 행에 대한 변경 사항은 **AcceptChanges** 메서드를 사용하여 수락하거나 **DataSet,** **DataTable**또는 **DataRow**의 **RejectChanges** 메서드를 사용하여 취소할 수 있습니다. 데이터 **집합에** **외래키제약이**포함된 경우 **AcceptChanges** 또는 **RejectChanges** 메서드를 호출하면 **AcceptRejectRule**을 적용합니다. **ForeignKeyConstraint의** **AcceptRejectRule** 속성은 부모 행에서 **AcceptChanges** 또는 **RejectChanges가** 호출될 때 자식 행에서 수행될 작업을 결정합니다.  
  
 다음 표에는 **AcceptRejectRule**에 사용할 수 있는 설정이 나열되어 있습니다.  
  
|규칙 설정|Description|  
|------------------|-----------------|  
|**캐스케이드**|자식 행의 변경을 승인하거나 거부합니다.|  
|**없음**|자식 행에 대해 아무 동작도 수행하지 않습니다. 이것이 기본값입니다.|  
  
### <a name="example"></a>예제  
 다음 예제에서는<xref:System.Data.ForeignKeyConstraint>를 만들고 <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>을 비롯한 해당 속성을 몇 가지 설정한 다음 <xref:System.Data.ConstraintCollection> 개체의 <xref:System.Data.DataTable>에 추가합니다.  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a>UniqueConstraint  
 단일 열또는 **DataTable의**열 배열에 할당할 수 있는 **UniqueConstraint** 개체는 지정된 열 또는 열의 모든 데이터가 행당 고유하도록 합니다. **UniqueConstraint** 생성자 사용을 사용하여 열 또는 열 배열에 대해 고유한 제약 조건을 만들 수 있습니다. 결과 **고유 제약 조건** 개체를 테이블의 제약 **조건** 속성의 **메서드 추가** **메서드에**전달합니다. 생성자 인수를 **ConstraintCollection의** **Add** 메서드의 여러 오버로드에 전달하여 **고유 제약 조건을**만들 수도 있습니다. 열 또는 열에 대한 **고유 제약 조건을** 만들 때 열 또는 열이 기본 키인지 여부를 선택적으로 지정할 수 있습니다.  
  
 열의 **고유** 속성을 **true로**설정하여 열에 대한 고유한 제약 조건을 만들 수도 있습니다. 또는 단일 열의 **고유** 속성을 **false로** 설정하면 존재할 수 있는 고유한 제약 조건이 제거됩니다. 하나 이상의 열을 테이블의 기본 키로 정의하면 지정한 열에 대한 UNIQUE 제약 조건이 자동으로 만들어집니다. **DataTable의** **PrimaryKey** 속성에서 열을 제거하면 **고유 제약 조건이** 제거됩니다.  
  
 다음 예제는 **DataTable**의 두 열에 대해 **고유 제약 조건을** 만듭니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [DataTable 스키마 정의](datatable-schema-definition.md)
- [DataSets, DataTables 및 DataViews](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
