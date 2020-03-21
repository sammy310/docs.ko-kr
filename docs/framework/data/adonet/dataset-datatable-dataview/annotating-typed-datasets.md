---
title: 형식화된 데이터 세트에 주석 지정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 757a87f92d8dc6049de1844fed892d95dc57c990
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151522"
---
# <a name="annotating-typed-datasets"></a>형식화된 데이터 세트에 주석 지정
주석을 사용하면 원본으로 사용하는 스키마를 수정하지 않고 형식화된 <xref:System.Data.DataSet>의 요소 이름을 수정할 수 있습니다. 기본 스키마의 요소 이름을 수정하면 형식이 지정된 **DataSet이** 데이터 원본에 존재하지 않는 개체를 참조하고 데이터 원본에 있는 개체에 대한 참조가 손실됩니다.  
  
 주석을 사용하면 형식이 설정된 **DataSet의** 개체 이름을 보다 의미 있는 이름으로 사용자 지정하여 코드를 더 읽기 쉽고 입력한 **DataSet을** 클라이언트가 더 쉽게 사용할 수 있도록 하는 동시에 기본 스키마를 그대로 둘 수 있습니다. 예를 **들어, Northwind** 데이터베이스의 **Customers** 테이블에 대 한 다음 스키마 요소 고객 **Row의** <xref:System.Data.DataRowCollection> **DataRow** 개체 이름 및 명명 된 **고객**.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 **고객의** **DataRowCollection** 이름은 클라이언트 코드에서 의미가 있지만 **CustomersRow의** **DataRow** 이름은 단일 개체이므로 오해의 소지가 있습니다. 또한 일반적인 시나리오에서는 **개체가 행** 식별자 없이 참조되고 대신 단순히 **Customer** 개체라고 합니다. 해결 방법은 스키마에 추가하고 **DataRow** 및 **DataRowCollection** 개체의 새 이름을 식별하는 것입니다. 다음 코드는 이전 스키마에 주석을 단 것입니다.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 **Customer의** **typedName** 값을 지정하면 **Customer**의 **DataRow** 개체 이름이 생성됩니다. **고객의** **형식된Plural값을** 지정하는 것은 **고객의** **DataRowCollection** 이름을 유지합니다.  
  
 다음 표에서는 사용할 수 있는 주석을 보여 줍니다.  
  
|주석|Description|  
|----------------|-----------------|  
|**typedName**|개체 이름입니다.|  
|**typedPlural**|개체 컬렉션의 이름입니다.|  
|**typedParent**|부모 관계에서 참조될 때의 개체 이름입니다.|  
|**typedChildren**|자식 관계에서 개체를 반환하기 위한 메서드의 이름입니다.|  
|**null값**|기본 값이 **DBNull인**경우 값입니다. **nullValue** 주석은 다음 표를 참조하십시오. 기본값은 **_throw**.|  
  
 다음 표에서는 **nullValue** 어구에 대해 지정할 수 있는 값을 보여 주며 있습니다.  
  
|nullValue 값|Description|  
|---------------------|-----------------|  
|*대체 값*|반환될 값을 지정합니다. 반환되는 값은 요소의 형식과 일치해야 합니다. 예를 들어, `nullValue="0"`을 사용하여 null 정수 필드에 0을 반환합니다.|  
|**_throw**|예외를 throw합니다. 이것이 기본값입니다.|  
|**_null**|기본 형식이 발견되면 null 참조를 반환하거나 예외를 throw합니다.|  
|**_empty**|문자열의 경우 **String.Empty를**반환합니다. 기본 형식이 발견되면 예외를 throw합니다.|  
  
 다음 표에서는 형식이 설정된 **DataSet의** 개체에 대한 기본값과 사용 가능한 주석이 표시됩니다.  
  
|개체/메서드/이벤트|기본값|주석|  
|---------------------------|-------------|----------------|  
|**Datatable**|TableNameDataTable|typedPlural|  
|**데이터 테이블** 방법|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**Datarow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**속성**|PropertyName|typedName|  
|**어린이** 접근자|GetChildTableNameRows|typedChildren|  
|**상위 주** 접근자|TableNameRow|typedParent|  
|**데이터 집합** 이벤트|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 형식이 입력된 **DataSet** 주석을 사용하려면 XML 스키마 정의 언어(XSD) 스키마에 다음 **xmlns** 참조를 포함해야 합니다. 데이터베이스 테이블에서 xsd를 만들려면 <xref:System.Data.DataSet.WriteXmlSchema%2A> [Visual Studio의 데이터 집합을](/visualstudio/data-tools/dataset-tools-in-visual-studio)보거나 작업합니다.  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 다음은 포함 된 **주문** 테이블과 관계와 **노스 윈드** 데이터베이스의 **Customers** 테이블을 노출 하는 샘플 추가 스키마입니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""
      xmlns:xs="http://www.w3.org/2001/XMLSchema"
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone" codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order" codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"                  codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter" codegen:nullValue="1980-01-01T00:00:00"
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 다음 코드 예제에서는 샘플 스키마에서 만든 강력한 형식의 **DataSet을** 사용합니다. 하나는 <xref:System.Data.SqlClient.SqlDataAdapter> **Customers** 테이블을 채우고 다른 <xref:System.Data.SqlClient.SqlDataAdapter> 테이블을 사용하여 **Orders** 테이블을 채웁니다. 강력하게 입력된 **데이터 집합은** **데이터 관계**를 정의합니다.  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =
    customers.Customers.NewCustomer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [형식화된 데이터 세트](typed-datasets.md)
- [DataSets, DataTables 및 DataViews](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
