---
title: DataTable에 열 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e85c4a0e-4f3f-458c-b58b-0ddbc06bf974
ms.openlocfilehash: 2e7008f6693d7d76520a7ff6ae9172e28e4990c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207008"
---
# <a name="adding-columns-to-a-datatable"></a>DataTable에 열 추가
A <xref:System.Data.DataTable> 의 컬렉션을 포함 <xref:System.Data.DataColumn> 개체에서 참조 하는 **열** 테이블의 속성입니다. 이 열 컬렉션과 모든 제약 조건을 함께 사용하여 테이블의 스키마나 구조를 정의합니다.  
  
 만든 **DataColumn** 를 사용 하 여 테이블 내에서 개체를 **DataColumn** 생성자 또는 호출 하 여는 **추가** 메서드를 **열**는 테이블의 속성을 <xref:System.Data.DataColumnCollection>입니다. **추가** 메서드에서 선택적 **ColumnName**를 **DataType**, 및 **식** 인수 새 만들고  **DataColumn** 컬렉션의 구성원으로 합니다. 또한 기존 수락 **DataColumn** 개체 및 컬렉션에 추가 하 고 추가에 대 한 참조를 반환 **DataColumn** 요청 하는 경우. 때문에 **DataTable** 개체를 모든 데이터 원본에 특정 형식의 데이터를 지정 하는 경우.NET Framework 형식이 사용 됩니다는 **DataColumn**합니다.  
  
 다음 예제에서는 네 개의 열을 추가 하는 **DataTable**합니다.  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
  
Dim workCol As DataColumn = workTable.Columns.Add( _  
    "CustID", Type.GetType("System.Int32"))  
workCol.AllowDBNull = false  
workCol.Unique = true  
  
workTable.Columns.Add("CustLName", Type.GetType("System.String"))  
workTable.Columns.Add("CustFName", Type.GetType("System.String"))  
workTable.Columns.Add("Purchases", Type.GetType("System.Double"))  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
  
DataColumn workCol = workTable.Columns.Add("CustID", typeof(Int32));  
workCol.AllowDBNull = false;  
workCol.Unique = true;  
  
workTable.Columns.Add("CustLName", typeof(String));  
workTable.Columns.Add("CustFName", typeof(String));  
workTable.Columns.Add("Purchases", typeof(Double));  
```  
  
 예에서 알 수 있듯이 대 한 속성을 **CustID** 열은 허용 하지 않도록 설정 됩니다 **DBNull** 값 및 고유 하 게 값을 제한 하 합니다. 그러나 정의 하는 경우는 **CustID** 테이블의 기본 키 열으로 열을 **AllowDBNull** 속성 자동으로 설정 됩니다 **false** 및 합니다 **Unique** 속성 자동으로 설정 됩니다 **true**합니다. 자세한 내용은 [기본 키 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/defining-primary-keys.md)합니다.  
  
> [!CAUTION]
>  열은 열에 증분 기본 이름인 지정 된 열에 대 한 열 이름을 제공 하지 않으면,*N* "Column1"부터 추가 될 때에 **DataColumnCollection**합니다. 명명 규칙을 방지 하는 것이 좋습니다 "열*N*"에 있는 기존의 기본 열 이름과 충돌이 발생할 수 있습니다를 제공 하는 경우 열 이름을 제공 하는 이름 때문에 **DataColumnCollection**합니다. 이미 있는 이름을 입력하면 예외가 throw됩니다.  
  
 <xref:System.Xml.Linq.XElement>를 <xref:System.Data.DataColumn.DataType%2A>에서 <xref:System.Data.DataColumn>의 <xref:System.Data.DataTable>로 사용하는 경우 데이터를 읽을 때 XML serialization이 작동하지 않습니다. 예를 들어 <xref:System.Xml.XmlDocument> 메서드를 사용하여 `DataTable.WriteXml`를 작성하는 경우 XML에 대한 serialization 수행 시 <xref:System.Xml.Linq.XElement>에 추가 부모 노드가 있습니다. 이 문제를 해결하려면 <xref:System.Data.SqlTypes.SqlXml> 대신 <xref:System.Xml.Linq.XElement> 형식을 사용합니다. `ReadXml` 및 `WriteXml`이 <xref:System.Data.SqlTypes.SqlXml>와 올바르게 작동합니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Data.DataColumn>
- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataTable>
- [DataTable 스키마 정의](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
