---
title: 데이터 세트 콘텐츠 복사
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: de13e07eb5c19b8beffa724fec4a128c418a4fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151366"
---
# <a name="copying-dataset-contents"></a>데이터 세트 콘텐츠 복사
원본 데이터에 영향을 주지 <xref:System.Data.DataSet> 않고 데이터로 작업하거나 **DataSet에서**데이터의 하위 집합으로 작업할 수 있도록 a의 복사본을 만들 수 있습니다. **데이터 집합을**복사할 때 다음을 수행할 수 있습니다.  
  
- 스키마, 데이터, 행 상태 정보 및 행 버전을 포함하여 **DataSet의**정확한 복사본을 만듭니다.  
  
- 기존 **DataSet의** 스키마를 포함하지만 수정된 행만 포함하는 **DataSet을**만듭니다. 수정된 모든 행을 반환하거나 특정 **DataRowState**를 지정할 수 있습니다. 행 상태에 대한 자세한 내용은 [행 상태 및 행 버전을](row-states-and-row-versions.md)참조하십시오.  
  
- 행을 복사하지 않고 **DataSet의** 스키마 또는 관계형 구조만 복사합니다. <xref:System.Data.DataTable>를 사용하여 행을 기존 <xref:System.Data.DataTable.ImportRow%2A>로 가져올 수 있습니다.  
  
 스키마와 데이터를 모두 포함하는 **DataSet의** 정확한 복사본을 만들려면 <xref:System.Data.DataSet.Copy%2A> **DataSet**의 메서드를 사용합니다. 다음 코드 예제에서는 **DataSet**의 정확한 복사본을 만드는 방법을 보여 주며 있습니다.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 스키마를 포함하는 **DataSet의** 복사본을 만들고 **추가됨,** **수정됨**또는 **삭제된** 행을 나타내는 데이터만 만들려면 <xref:System.Data.DataSet.GetChanges%2A> **DataSet**의 메서드를 사용합니다. GetChanges를 사용하여 **GetChanges** 를 호출할 때 **DataRowState** 값을 전달하여 지정된 행 상태의 행만 반환할 수도 **있습니다.** 다음 코드 예제에서는 **GetChanges**를 호출할 때 **DataRowState를** 전달하는 방법을 보여 주며 있습니다.  
  
```vb  
' Copy all changes.  
Dim changeDataSet As DataSet = customerDataSet.GetChanges()  
' Copy only new rows.  
Dim addedDataSetAs DataSet = _  
    customerDataSet.GetChanges(DataRowState.Added)  
```  
  
```csharp  
// Copy all changes.  
DataSet changeDataSet = customerDataSet.GetChanges();  
// Copy only new rows.  
DataSet addedDataSet= customerDataSet.GetChanges(DataRowState.Added);  
```  
  
 스키마만 포함하는 **DataSet의** 복사본을 만들려면 <xref:System.Data.DataSet.Clone%2A> **DataSet**의 메서드를 사용합니다. DataTable 의 **ImportRow** 메서드를 사용하여 복제된 **DataSet에** 기존 행을 추가할 수도 **있습니다.** **ImportRow** 는 지정된 테이블에 데이터, 행 상태 및 행 버전 정보를 추가합니다. 열 값은 열 이름이 일치하고 데이터 형식이 호환되는 위치에만 추가됩니다.  
  
 다음 코드 예제에서는 **DataSet의** 복제본을 만들고 원래 **DataSet의** 행을 **DataSet** 복제의 **고객** 테이블에 추가하여 **CountryRegion** 열에 "독일" 값이 있는 고객을 위한 것입니다.  
  
```vb  
Dim customerDataSet As New DataSet  
        customerDataSet.Tables.Add(New DataTable("Customers"))  
        customerDataSet.Tables("Customers").Columns.Add("Name", GetType(String))  
        customerDataSet.Tables("Customers").Columns.Add("CountryRegion", GetType(String))  
        customerDataSet.Tables("Customers").Rows.Add("Juan", "Spain")  
        customerDataSet.Tables("Customers").Rows.Add("Johann", "Germany")  
        customerDataSet.Tables("Customers").Rows.Add("John", "UK")  
  
Dim germanyCustomers As DataSet = customerDataSet.Clone()  
  
Dim copyRows() As DataRow = _  
  customerDataSet.Tables("Customers").Select("CountryRegion = 'Germany'")  
  
Dim customerTable As DataTable = germanyCustomers.Tables("Customers")  
Dim copyRow As DataRow  
  
For Each copyRow In copyRows  
  customerTable.ImportRow(copyRow)  
Next  
```  
  
```csharp  
DataSet customerDataSet = new DataSet();  
customerDataSet.Tables.Add(new DataTable("Customers"));  
customerDataSet.Tables["Customers"].Columns.Add("Name", typeof(string));  
customerDataSet.Tables["Customers"].Columns.Add("CountryRegion", typeof(string));  
customerDataSet.Tables["Customers"].Rows.Add("Juan", "Spain");  
customerDataSet.Tables["Customers"].Rows.Add("Johann", "Germany");  
customerDataSet.Tables["Customers"].Rows.Add("John", "UK");  
  
DataSet germanyCustomers = customerDataSet.Clone();  
  
DataRow[] copyRows =
  customerDataSet.Tables["Customers"].Select("CountryRegion = 'Germany'");  
  
DataTable customerTable = germanyCustomers.Tables["Customers"];  
  
foreach (DataRow copyRow in copyRows)  
  customerTable.ImportRow(copyRow);  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [DataSets, DataTables 및 DataViews](index.md)
- [ADO.NET 개요](../ado-net-overview.md)
