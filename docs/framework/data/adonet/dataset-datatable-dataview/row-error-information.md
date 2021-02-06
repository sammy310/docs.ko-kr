---
description: '자세히 알아보기: 행 오류 정보'
title: 행 오류 정보
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8b1f9070-d032-48c7-b030-bd8fbb2ca59a
ms.openlocfilehash: d3eb8b20893ad47720ebb03ad4ab61940f014bd3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651693"
---
# <a name="row-error-information"></a><span data-ttu-id="d2a86-103">행 오류 정보</span><span class="sxs-lookup"><span data-stu-id="d2a86-103">Row Error Information</span></span>

<span data-ttu-id="d2a86-104"><xref:System.Data.DataTable>에서 값을 편집하면서 행 오류에 응답하지 않으려면 나중에 사용할 수 있도록 오류 정보를 행에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a86-104">To avoid having to respond to row errors while editing values in a <xref:System.Data.DataTable>, you can add the error information to the row for later use.</span></span> <span data-ttu-id="d2a86-105"><xref:System.Data.DataRow> 개체는 이를 위해 행마다 <xref:System.Data.DataRow.RowError%2A> 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a86-105">The <xref:System.Data.DataRow> object provides a <xref:System.Data.DataRow.RowError%2A> property on each row for this purpose.</span></span> <span data-ttu-id="d2a86-106">**Datarow** 의 **RowError** 속성에 데이터를 추가 하면 <xref:System.Data.DataRow.HasErrors%2A> **datarow** 의 속성이 **true** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a86-106">Adding data to the **RowError** property of a **DataRow** sets the <xref:System.Data.DataRow.HasErrors%2A> property of the **DataRow** to **true**.</span></span> <span data-ttu-id="d2a86-107">**Datarow** 가 **datatable** 의 일부이 고, **datarow. Haserrors** 가 **true** 이면 **datatable. haserrors** 속성도 **true** 입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a86-107">If the **DataRow** is part of a **DataTable**, and **DataRow.HasErrors** is **true**, the **DataTable.HasErrors** property is also **true**.</span></span> <span data-ttu-id="d2a86-108">이는 **DataTable** 이 속한 **데이터 집합** 에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a86-108">This applies as well to the **DataSet** to which the **DataTable** belongs.</span></span> <span data-ttu-id="d2a86-109">오류를 테스트할 때 **haserrors** 속성을 확인 하 여 오류 정보가 행에 추가 되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a86-109">When testing for errors, you can check the **HasErrors** property to determine if error information has been added to any rows.</span></span> <span data-ttu-id="d2a86-110">**Haserrors** 가 **true** 인 경우 <xref:System.Data.DataTable.GetErrors%2A> 다음 예제와 같이 **DataTable** 의 메서드를 사용 하 여 오류가 있는 행만 반환 하 고 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a86-110">If **HasErrors** is **true**, you can use the <xref:System.Data.DataTable.GetErrors%2A> method of the **DataTable** to return and examine only the rows with errors, as shown in the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d2a86-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2a86-111">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="d2a86-112">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="d2a86-112">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="d2a86-113">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="d2a86-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
