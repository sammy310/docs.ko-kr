---
title: DataTable 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eecf9d78-60e3-4fdc-8de0-e56c13a89414
ms.openlocfilehash: 272976d3c581d3e8a5860ba5cf3f9695ca370d8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034413"
---
# <a name="creating-a-datatable"></a>DataTable 만들기
<xref:System.Data.DataTable>은 메모리 내 관계형 데이터가 포함된 하나의 테이블을 나타내며, 독립적으로 만들어 사용하거나 다른 .NET Framework 개체에 의해 사용될 수도 있습니다. 이 경우에는 주로 <xref:System.Data.DataSet>의 멤버로 사용됩니다.  
  
 만들 수 있습니다는 **DataTable** 개체를 사용 하 여 **DataTable** 생성자입니다. 에 추가할 수 있습니다는 **데이터 집합** 사용 하 여를 **추가** 에 추가 하는 방법의 **DataTable** 개체의 **테이블** 컬렉션.  
  
 만들 수도 있습니다 **DataTable** 내에서 개체를 **데이터 집합** 사용 하 여는 **채우기** 또는 **FillSchema** 의 메서드는  **DataAdapter** 개체는 미리 정의 되거나 유추 된 XML 스키마를 사용 하 여 또는 합니다 **ReadXml**, **ReadXmlSchema**, 또는 **InferXmlSchema** 메서드를 **데이터 집합**합니다. 추가한 후를 **DataTable** 의 구성원으로는 **테이블** 하나의 컬렉션 **DataSet**, 기타 테이블의컬렉션에추가할수없습니다**데이터 집합**합니다.  
  
 처음 만들 때는 **DataTable**, 스키마 (구조) 없습니다. 테이블의 스키마를 정의 하려면 만들기 및 추가 해야 합니다 <xref:System.Data.DataColumn> 개체를 **열** 테이블의 컬렉션입니다. 또한 테이블에 대 한 기본 키 열 정의 및 만들기 추가 하는 **제약 조건** 개체를 **제약 조건** 테이블의 컬렉션입니다. 에 대 한 스키마를 정의한 후는 **DataTable**를 추가 하 여 테이블에 데이터 행을 추가할 수 있습니다 **DataRow** 개체를 합니다 **행** 테이블의 컬렉션입니다.  
  
 에 대 한 값을 제공 하지 않아도 됩니다 합니다 <xref:System.Data.DataTable.TableName%2A> 만들 때 속성을 **DataTable**; 다른 시간에 속성을 지정 하거나 비워 둘 수 있습니다. 그러나 없는 테이블을 추가 하는 하면를 **TableName** 값을 **데이터 집합**, 테이블은 증분 기본 이름인 Table 주어 집니다*N*"Table" table0부터.  
  
> [!NOTE]
>  사용 하지 않는 것이 좋습니다는 "테이블*N*" 제공 하는 경우 명명 규칙을 **TableName** 값을 제공한 이름에 있는 기존의 기본 테이블 이름과 충돌이 발생할 수 있습니다는 **데이터 집합** . 이미 있는 이름을 입력하면 예외가 throw됩니다.  
  
 다음 예제에서는 인스턴스를 **DataTable** 개체 및 이름을 지정한 "고객"을 선택 합니다.  
  
```vb  
Dim workTable as DataTable = New DataTable("Customers")  
```  
  
```csharp  
DataTable workTable = new DataTable("Customers");  
```  
  
 다음 예제에서는 인스턴스를 만듭니다는 **DataTable** 추가 하 여 합니다 **테이블** 의 컬렉션을 **데이터 집합**합니다.  
  
```vb  
Dim customers As DataSet = New DataSet  
Dim customersTable As DataTable = _  
   customers.Tables.Add("CustomersTable")  
```  
  
```csharp  
DataSet customers = new DataSet();  
DataTable customersTable = customers.Tables.Add("CustomersTable");  
```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Data.DataTable>
- <xref:System.Data.DataTableCollection>
- [DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [DataAdapter에서 데이터 집합 채우기](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [XML에서 데이터 세트 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-a-dataset-from-xml.md)
- [XML에서 데이터 세트 스키마 정보 로드](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/loading-dataset-schema-information-from-xml.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
