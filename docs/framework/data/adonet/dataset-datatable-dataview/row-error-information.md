---
title: 행 오류 정보
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
ms.openlocfilehash: 89889c5543e6518046bb59b59646ecba715f5e03
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59152726"
---
# <a name="row-error-information"></a><span data-ttu-id="77361-102">행 오류 정보</span><span class="sxs-lookup"><span data-stu-id="77361-102">Row Error Information</span></span>
<span data-ttu-id="77361-103"><xref:System.Data.DataTable>에서 값을 편집하면서 행 오류에 응답하지 않으려면 나중에 사용할 수 있도록 오류 정보를 행에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="77361-103">To avoid having to respond to row errors while editing values in a <xref:System.Data.DataTable>, you can add the error information to the row for later use.</span></span> <span data-ttu-id="77361-104"><xref:System.Data.DataRow> 개체는 이를 위해 행마다 <xref:System.Data.DataRow.RowError%2A> 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="77361-104">The <xref:System.Data.DataRow> object provides a <xref:System.Data.DataRow.RowError%2A> property on each row for this purpose.</span></span> <span data-ttu-id="77361-105">데이터를 추가할를 **RowError** 의 속성을 **DataRow** 설정를 <xref:System.Data.DataRow.HasErrors%2A> 속성을 **DataRow** 를 **true**.</span><span class="sxs-lookup"><span data-stu-id="77361-105">Adding data to the **RowError** property of a **DataRow** sets the <xref:System.Data.DataRow.HasErrors%2A> property of the **DataRow** to **true**.</span></span> <span data-ttu-id="77361-106">경우는 **DataRow** 의 일부인를 **DataTable**, 및 **DataRow.HasErrors** 됩니다 **true**, **DataTable.HasErrors** 속성도 **true**합니다.</span><span class="sxs-lookup"><span data-stu-id="77361-106">If the **DataRow** is part of a **DataTable**, and **DataRow.HasErrors** is **true**, the **DataTable.HasErrors** property is also **true**.</span></span> <span data-ttu-id="77361-107">에 적용 됩니다는 **데이터 집합** 는 합니다 **DataTable** 속한 합니다.</span><span class="sxs-lookup"><span data-stu-id="77361-107">This applies as well to the **DataSet** to which the **DataTable** belongs.</span></span> <span data-ttu-id="77361-108">오류를 테스트 하는 경우를 확인할 수 있습니다 합니다 **HasErrors** 속성을 오류 정보는 모든 행에 추가 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="77361-108">When testing for errors, you can check the **HasErrors** property to determine if error information has been added to any rows.</span></span> <span data-ttu-id="77361-109">경우 **HasErrors** 는 **true**를 사용할 수는 <xref:System.Data.DataTable.GetErrors%2A> 메서드의 **DataTable** 반환 하 고 다음 예제에서와 같이 오류가 있는 행만을 검사할 합니다.</span><span class="sxs-lookup"><span data-stu-id="77361-109">If **HasErrors** is **true**, you can use the <xref:System.Data.DataTable.GetErrors%2A> method of the **DataTable** to return and examine only the rows with errors, as shown in the following example.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable("Customers")  
workTable.Columns.Add("CustID", Type.GetType("System.Int32"))  
workTable.Columns.Add("Total", Type.GetType("System.Double"))  
  
AddHandler workTable.RowChanged, New DataRowChangeEventHandler(AddressOf OnRowChanged)  
  
Dim i  As Int32  
  
For i  = 0 To 10  
  workTable.Rows.Add(New Object() {i , i *100})  
Next  
  
If workTable.HasErrors Then  
  Console.WriteLine("Errors in Table " & workTable.TableName)  
  
  Dim myRow As DataRow  
  
  For Each myRow In workTable.GetErrors()  
    Console.WriteLine("CustID = " & myRow("CustID").ToString())  
    Console.WriteLine(" Error = " & myRow.RowError & vbCrLf)  
  Next  
End If  
  
Private Shared Sub OnRowChanged( _  
    sender As Object, args As DataRowChangeEventArgs)  
  ' Check for zero values.  
  If CDbl(args.Row("Total")) = 0 Then args.Row.RowError = _  
      "Total cannot be 0."  
End Sub  
```  
  
```csharp  
DataTable  workTable = new DataTable("Customers");  
workTable.Columns.Add("CustID", typeof(Int32));  
workTable.Columns.Add("Total", typeof(Double));  
  
workTable.RowChanged += new DataRowChangeEventHandler(OnRowChanged);  
  
for (int i = 0; i < 10; i++)  
  workTable.Rows.Add(new Object[] {i, i*100});  
  
if (workTable.HasErrors)  
{  
  Console.WriteLine("Errors in Table " + workTable.TableName);  
  
  foreach (DataRow myRow in workTable.GetErrors())  
  {  
    Console.WriteLine("CustID = " + myRow["CustID"]);  
    Console.WriteLine(" Error = " + myRow.RowError + "\n");  
  }  
}  
  
protected static void OnRowChanged(  
    Object sender, DataRowChangeEventArgs args)  
{  
  // Check for zero values.  
  if (args.Row["Total"].Equals(0D))  
    args.Row.RowError = "Total cannot be 0.";  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="77361-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="77361-110">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="77361-111">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="77361-111">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="77361-112">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="77361-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
