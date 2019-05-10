---
title: 데이터 집합 콘텐츠 복사
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb846617-2b1a-44ff-bd7f-5835f5ea37fa
ms.openlocfilehash: 29afeb84498f2b1d000940ddc28545602a44d408
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626148"
---
# <a name="copying-dataset-contents"></a>데이터 집합 콘텐츠 복사
복사본을 만들 수 있습니다는 <xref:System.Data.DataSet> 원래 데이터는 영향을 주지 않고 데이터로 작업 하거나 사용할 수 있도록 데이터의 하위 집합으로는 **데이터 집합**합니다. 복사 하는 경우는 **데이터 집합**를 할 수 있습니다.  
  
- 정확한 복사본을 만듭니다는 **데이터 집합**, 스키마, 데이터, 행 상태 정보 및 행 버전을 포함 합니다.  
  
- 만들기는 **데이터 집합** 기존 스키마를 포함 하는 **데이터 집합**, 하지만 수정 된 행만 합니다. 수정 된 모든 행을 반환 하거나 특정을 지정할 수 있습니다 **DataRowState**합니다. 행 상태에 대 한 자세한 내용은 참조 하세요. [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.  
  
- 스키마 나 관계형 구조만 복사 합니다 **데이터 집합** 없이 모든 행을 복사 합니다. <xref:System.Data.DataTable>를 사용하여 행을 기존 <xref:System.Data.DataTable.ImportRow%2A>로 가져올 수 있습니다.  
  
 정확한 복사본을 만들 합니다 **데이터 집합** 스키마와 데이터 모두를 포함 하는, 사용 하 여는 <xref:System.Data.DataSet.Copy%2A> 메서드를 **데이터 집합**. 다음 코드 예제에는의 정확한 복사본을 만드는 방법을 보여 줍니다 합니다 **데이터 집합**합니다.  
  
```vb  
Dim copyDataSet As DataSet = customerDataSet.Copy()  
```  
  
```csharp  
DataSet copyDataSet = customerDataSet.Copy();  
```  
  
 복사본을 만드는 **데이터 집합** 스키마 및 나타내는 데이터만 포함 하는 **Added**, **Modified**, 또는 **Deleted** 행을 사용 하 여는 <xref:System.Data.DataSet.GetChanges%2A> 메서드를 **데이터 집합**합니다. 사용할 수도 있습니다 **GetChanges** 전달 하 여 지정한 행 상태의 행만 반환 하는 **DataRowState** 호출 하는 경우 값 **GetChanges**합니다. 다음 코드 예제에서는 전달 하는 방법을 보여 줍니다.는 **DataRowState** 를 호출할 때 **GetChanges**합니다.  
  
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
  
 복사본을 만드는 **데이터 집합** 만 포함 하는 스키마를 사용 합니다 <xref:System.Data.DataSet.Clone%2A> 메서드를 **데이터 집합**. 복제에 기존 행을 추가할 수도 있습니다 **데이터 집합** 를 사용 하 여 합니다 **ImportRow** 메서드를 **DataTable**합니다. **ImportRow** 지정된 된 테이블에 데이터, 행 상태 및 행 버전 정보를 추가 합니다. 열 값은 열 이름이 일치하고 데이터 형식이 호환되는 위치에만 추가됩니다.  
  
 다음 코드 예제에서는의 복제본을 만듭니다는 **데이터 집합** 추가한 다음 원래에서 행 **데이터 집합** 에 **고객** 테이블에 **데이터 집합**  고객에 대 한 복제 위치를 **CountryRegion** 열에 값이 "Germany"입니다.  
  
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
  
## <a name="see-also"></a>참고자료

- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [DataSet, DataTable 및 DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터](https://go.microsoft.com/fwlink/?LinkId=217917)
