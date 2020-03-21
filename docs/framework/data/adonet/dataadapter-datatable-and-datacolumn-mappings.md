---
title: DataAdapter DataTable 및 DataColumn 매핑
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d023260a-a66a-4c39-b8f4-090cd130e730
ms.openlocfilehash: 6380dd0512bd7834f50b87f90f445cb01b7a8b95
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151561"
---
# <a name="dataadapter-datatable-and-datacolumn-mappings"></a>DataAdapter DataTable 및 DataColumn 매핑
**DataAdapter는** TableMappings 속성에 <xref:System.Data.Common.DataTableMapping> 0 개 이상의 개체 컬렉션을 **포함합니다.** **DataTableMapping은** 데이터 원본에 대해 쿼리에서 반환된 데이터와 을 <xref:System.Data.DataTable>위한 마스터 매핑을 제공합니다. **DataTableMapping** 이름은 **DataTable** 이름 대신 **데이터 어댑터**의 **채우기** 메서드에 전달할 수 있습니다. 다음 예제에서는 **작성자** 테이블에 대 한 **작성자 매핑이라는** **데이터 테이블 매핑을** 만듭니다.  
  
```vb  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors")  
```  
  
```csharp  
workAdapter.TableMappings.Add("AuthorsMapping", "Authors");  
```  
  
 **DataTableMapping을** 사용하면 데이터베이스의 열 이름과 다른 **DataTable에서** 열 이름을 사용할 수 있습니다. **DataAdapter는** 테이블이 업데이트될 때 열을 일치시키기 위해 매핑을 사용합니다.  
  
 **DataAdapter의** **채우기** 또는 **업데이트** 메서드를 호출할 때 **TableName** 또는 **DataTableMapping** 이름을 지정하지 않으면 **DataAdapter는** "테이블"이라는 **DataTableMapping을** 찾습니다. 해당 **DataTable매핑이** 없는 경우 **DataTable의** **테이블 이름은** "테이블"입니다. "테이블"의 이름으로 **DataTableMapping을** 만들어 기본 **DataTableMapping을** 지정할 수 있습니다.  
  
 다음 코드 예제에서는 <xref:System.Data.Common> 네임스페이스에서 **DataTableMapping을** 만들고 "테이블"이라는 이름을 지정하여 지정된 **DataAdapter의** 기본 매핑으로 만듭니다. 그런 다음 예제에서는 쿼리 결과(Northwind 데이터베이스의 **고객** 테이블)의 첫 번째 테이블에서 열을 **Northwind** <xref:System.Data.DataSet> **의 Northwind Customers** 테이블의 사용자 친화적인 이름 집합에 매핑합니다. 매핑되지 않는 열의 경우 데이터 소스의 열 이름이 사용됩니다.  
  
```vb  
Dim mapping As DataTableMapping = _  
  adapter.TableMappings.Add("Table", "NorthwindCustomers")  
mapping.ColumnMappings.Add("CompanyName", "Company")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode")  
  
adapter.Fill(custDS)  
```  
  
```csharp  
DataTableMapping mapping =
  adapter.TableMappings.Add("Table", "NorthwindCustomers");  
mapping.ColumnMappings.Add("CompanyName", "Company");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIPCode");  
  
adapter.Fill(custDS);  
```  
  
 고급 상황에서는 동일한 **DataAdapter가** 서로 다른 매핑으로 다른 테이블로 로드하도록 결정할 수 있습니다. 이렇게 하려면 **DataTableMapping** 개체를 추가하기만 하면 됩니다.  
  
 **채우기** 메서드가 **DataSet** 및 **DataTableMapping** 이름의 인스턴스를 전달하면 해당 이름의 매핑이 있는 경우 해당 메서드가 사용됩니다. 그렇지 않으면 해당 이름의 **DataTable이** 사용됩니다.  
  
 다음 예제에서는 **고객의** 이름과 **BizTalkSchema의**DataTable 이름으로 **DataTable매핑을** 만듭니다. **DataTable** 그런 다음 SELECT 문에서 반환된 행을 **BizTalkSchema** **DataTable에**매핑합니다.  
  
```vb  
Dim mapping As ITableMapping = _  
  adapter.TableMappings.Add("Customers", "BizTalkSchema")  
mapping.ColumnMappings.Add("CustomerID", "ClientID")  
mapping.ColumnMappings.Add("CompanyName", "ClientName")  
mapping.ColumnMappings.Add("ContactName", "Contact")  
mapping.ColumnMappings.Add("PostalCode", "ZIP")  
  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
ITableMapping mapping =
  adapter.TableMappings.Add("Customers", "BizTalkSchema");  
mapping.ColumnMappings.Add("CustomerID", "ClientID");  
mapping.ColumnMappings.Add("CompanyName", "ClientName");  
mapping.ColumnMappings.Add("ContactName", "Contact");  
mapping.ColumnMappings.Add("PostalCode", "ZIP");  
  
adapter.Fill(custDS, "Customers");  
```  
  
> [!NOTE]
> 열 매핑에 소스 열 이름을 제공하지 않거나 테이블 매핑에 소스 테이블 이름을 제공하지 않으면 기본 이름이 자동으로 생성됩니다. 열 매핑에 대해 소스 열이 제공되지 않으면 열 매핑에 **SourceColumn1로**시작하는 **SourceColumn** *N의* 증분 기본 이름이 제공됩니다. 테이블 매핑에 소스 테이블 이름이 제공되지 않으면 테이블 매핑에 SourceTable 1로 시작하는 **SourceTable** *N의*증분 기본 이름이 제공됩니다. **SourceTable1**  
  
> [!NOTE]
> 열 매핑에 대 한 **SourceColumn** *N의* 명명 규칙을 방지 하는 것이 좋습니다., 또는 **SourceTable** *N* 테이블 매핑에 대 한, **DataTableMappingCollection에서**열 매핑 **컬렉션** 또는 테이블 매핑 이름에 있는 기존 기본 열 매핑 이름과 충돌할 수 있습니다 때문에. 이미 있는 이름을 제공하면 예외가 throw됩니다.  
  
## <a name="handling-multiple-result-sets"></a>여러 개의 결과 집합 처리  
 **SelectCommand가** 여러 테이블을 반환하는 경우 **채우기는** 지정된 테이블 이름으로 시작하여 TableName *N*형식에서 계속하여 **TableName1로** **TableName** 시작하여 **DataSet의**테이블에 대한 증분 값으로 테이블 이름을 자동으로 생성합니다. 테이블 매핑을 사용하여 자동으로 생성된 테이블 이름을 **DataSet**의 테이블에 지정한 이름으로 매핑할 수 있습니다. 예를 들어 두 테이블인 **고객** 및 **주문을**반환하는 **SelectCommand의** 경우 다음 호출을 **[채우기]**  
  
```vb  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.Fill(customersDataSet, "Customers");  
```  

 두 테이블은 **DataSet**: **고객** 및 **고객1에서**만들어집니다. 테이블 매핑을 사용하여 두 번째 테이블이 **Customers1**대신 **Orders라는** 이름을 지정할 수 있습니다. 이렇게 하려면 다음 예제와 같이 **Customers1의** 원본 테이블을 **DataSet** 테이블 **주문에**매핑합니다.  
  
```vb  
adapter.TableMappings.Add("Customers1", "Orders")  
adapter.Fill(customersDataSet, "Customers")  
```  

```csharp  
adapter.TableMappings.Add("Customers1", "Orders");  
adapter.Fill(customersDataSet, "Customers");  
```
  
## <a name="see-also"></a>참고 항목

- [DataAdapter 및 DataReader](dataadapters-and-datareaders.md)
- [ADO.NET에서 데이터 검색 및 수정](retrieving-and-modifying-data.md)
- [ADO.NET 개요](ado-net-overview.md)
