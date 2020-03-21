---
title: 행 찾기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5da300e2-74c0-4d13-9202-fc20ed8212d8
ms.openlocfilehash: cfd4587f0dde7687ecf88bf6b31c44b90a2287ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151145"
---
# <a name="finding-rows"></a>행 찾기
<xref:System.Data.DataView.Find%2A>의 <xref:System.Data.DataView.FindRows%2A> 및 <xref:System.Data.DataView> 메서드를 사용하여 행의 정렬 키 값에 따라 행을 검색할 수 있습니다. **찾기** 및 **FindRows** 메서드에서 검색 값의 대/소문자 구분은 <xref:System.Data.DataTable>기본 의 **CaseSensitive** 속성에 의해 결정됩니다. 검색 값이 기존 정렬 키 값 전체와 일치해야 결과를 반환할 수 있습니다.  
  
 **Find** 메서드는 검색 조건과 일치하는 인덱스를 <xref:System.Data.DataRowView> 사용하여 정수를 반환합니다. 두 행이상이 검색 조건과 일치하는 경우 첫 번째 일치하는 **DataRowView의** 인덱스만 반환됩니다. 일치하는 항목이 없는 경우 **찾기는** -1을 반환합니다.  
  
 여러 행과 일치하는 검색 결과를 반환하려면 **FindRows** 메서드를 사용합니다. **FindRows는** **DataView**에서 일치하는 모든 행을 참조하는 **DataRowView** 배열을 반환한다는 점을 제외하면 **Find** 메서드와 마찬가지로 작동합니다. 일치하는 항목이 없는 경우 **DataRowView** 배열이 비어 있습니다.  
  
 **찾기** 또는 **FindRows** 메서드를 사용하려면 **ApplyDefaultSort를** **true로** 설정하거나 **Sort** 속성을 사용하여 정렬 순서를 지정해야 합니다. 정렬 순서를 지정하지 않으면 예외가 throw됩니다.  
  
 **Find** 및 **FindRows** 메서드는 길이가 정렬 순서의 열 수와 일치하는 입력으로 값 배열을 사용합니다. 하나의 열에 대해 정렬하는 경우에는 하나의 값을 전달할 수 있습니다. 정렬 순서에 여러 열이 포함된 경우에는 개체 배열을 전달합니다. 여러 열의 정렬의 경우 개체 배열의 값은 **DataView**의 **Sort** 속성에 지정된 열의 순서와 일치해야 합니다.  
  
 다음 코드 예제에서는 단일 열 정렬 순서를 사용하여 **DataView에** 대해 호출되는 **Find** 메서드를 보여 주습니다.  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName", DataViewRowState.CurrentRows)  
  
Dim rowIndex As Integer = custView.Find("The Cracker Box")  
  
If rowIndex = -1 Then  
  Console.WriteLine("No match found.")  
Else  
  Console.WriteLine("{0}, {1}", _  
    custView(rowIndex)("CustomerID").ToString(), _  
    custView(rowIndex)("CompanyName").ToString())  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",
  "CompanyName", DataViewRowState.CurrentRows);  
  
int rowIndex = custView.Find("The Cracker Box");  
  
if (rowIndex == -1)  
  Console.WriteLine("No match found.");  
else  
  Console.WriteLine("{0}, {1}",  
    custView[rowIndex]["CustomerID"].ToString(),  
    custView[rowIndex]["CompanyName"].ToString());  
```  
  
 **Sort** 속성이 여러 열을 지정하는 경우 다음 코드 예제와 같이 **Sort** 속성에서 지정한 순서대로 각 열에 대한 검색 값이 있는 개체 배열을 전달해야 합니다.  
  
```vb  
Dim custView As DataView = _  
  New DataView(custDS.Tables("Customers"), "", _  
  "CompanyName, ContactName", _  
  DataViewRowState.CurrentRows)  
  
Dim foundRows() As DataRowView = _  
  custView.FindRows(New object() {"The Cracker Box", "Liu Wong"})  
  
If foundRows.Length = 0 Then  
  Console.WriteLine("No match found.")  
Else  
  Dim myDRV As DataRowView  
  For Each myDRV In foundRows  
    Console.WriteLine("{0}, {1}", _  
      myDRV("CompanyName").ToString(), myDRV("ContactName").ToString())  
  Next  
End If  
```  
  
```csharp  
DataView custView = new DataView(custDS.Tables["Customers"], "",  
  "CompanyName, ContactName",  
  DataViewRowState.CurrentRows);  
  
DataRowView[] foundRows =
  custView.FindRows(new object[] {"The Cracker Box", "Liu Wong"});  
  
if (foundRows.Length == 0)  
  Console.WriteLine("No match found.");  
else  
  foreach (DataRowView myDRV in foundRows)  
    Console.WriteLine("{0}, {1}", myDRV["CompanyName"].ToString(),
      myDRV["ContactName"].ToString());  
```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [DataView](dataviews.md)
- [ADO.NET 개요](../ado-net-overview.md)
