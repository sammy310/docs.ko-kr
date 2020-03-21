---
title: DataTable에 데이터 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: 02d7f94259cc56513be404c5539ca7015d5f3533
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151535"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="1f553-102">DataTable에 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="1f553-102">Adding Data to a DataTable</span></span>
<span data-ttu-id="1f553-103"><xref:System.Data.DataTable>을 만들고 열 및 제약 조건을 사용하여 해당 테이블의 구조를 정의한 후에는 새 데이터 행을 테이블에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-103">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="1f553-104">새 행을 추가하려면 새 변수의 형식을 <xref:System.Data.DataRow>로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-104">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="1f553-105">메서드를 호출할 때 새 **DataRow** 개체가 <xref:System.Data.DataTable.NewRow%2A> 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-105">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="1f553-106">그런 다음 **DataTable은** <xref:System.Data.DataColumnCollection>에 의해 정의된 대로 테이블의 구조를 기반으로 **DataRow** 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-106">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="1f553-107">다음 예제에서는 **NewRow** 메서드를 호출 하 여 새 행을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-107">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="1f553-108">그러면 다음 예제와 같이 인덱스나 열 이름을 사용하여 새로 추가된 행을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-108">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="1f553-109">데이터가 새 행에 삽입된 후 **Add** 메서드를 사용하여 다음 <xref:System.Data.DataRowCollection>코드에 표시된 에 행을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-109">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="1f553-110">다음 예제와 **Add** 같이 <xref:System.Object>로 입력된 값 배열을 전달하여 Add 메서드를 호출하여 새 행을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-110">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="1f553-111">**Object로**입력된 값 배열을 **Add** 메서드에 전달하면 테이블 내부에 새 행이 생성되고 해당 열 값이 개체 배열의 값으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-111">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="1f553-112">배열 값은 테이블에 나타나는 순서에 따라 해당 열과 순서대로 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-112">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="1f553-113">다음 예제는 새로 만든 **Customers** 테이블에 10개의 행을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="1f553-113">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
```vb  
Dim workRow As DataRow  
Dim i As Integer  
  
For i = 0 To 9  
  workRow = workTable.NewRow()  
  workRow(0) = i  
  workRow(1) = "CustName" & I.ToString()  
  workTable.Rows.Add(workRow)  
Next  
```  
  
```csharp  
DataRow workRow;  
  
for (int i = 0; i <= 9; i++)
{  
  workRow = workTable.NewRow();  
  workRow[0] = i;  
  workRow[1] = "CustName" + i.ToString();  
  workTable.Rows.Add(workRow);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="1f553-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1f553-114">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="1f553-115">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="1f553-115">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="1f553-116">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="1f553-116">ADO.NET Overview</span></span>](../ado-net-overview.md)
