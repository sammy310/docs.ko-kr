---
title: DataTable에 데이터 추가
description: DataTable을 만들고 열과 제약 조건을 사용 하 여 해당 구조를 정의한 후에는이 예제 코드를 참조 하 여 ADO.NET의 테이블에 새 데이터 행을 추가 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d6aa8474-7bde-48f7-949d-20dc38a1625b
ms.openlocfilehash: aac2d90cc57a4af823c42f8c7eb2adcd43c63caf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164820"
---
# <a name="adding-data-to-a-datatable"></a><span data-ttu-id="fe0df-103">DataTable에 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="fe0df-103">Adding Data to a DataTable</span></span>

<span data-ttu-id="fe0df-104"><xref:System.Data.DataTable>을 만들고 열 및 제약 조건을 사용하여 해당 테이블의 구조를 정의한 후에는 새 데이터 행을 테이블에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0df-104">After you create a <xref:System.Data.DataTable> and define its structure using columns and constraints, you can add new rows of data to the table.</span></span> <span data-ttu-id="fe0df-105">새 행을 추가하려면 새 변수의 형식을 <xref:System.Data.DataRow>로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0df-105">To add a new row, declare a new variable as type <xref:System.Data.DataRow>.</span></span> <span data-ttu-id="fe0df-106">메서드를 호출 하면 새 **DataRow** 개체가 반환 됩니다 <xref:System.Data.DataTable.NewRow%2A> .</span><span class="sxs-lookup"><span data-stu-id="fe0df-106">A new **DataRow** object is returned when you call the <xref:System.Data.DataTable.NewRow%2A> method.</span></span> <span data-ttu-id="fe0df-107">그런 다음 **DataTable** 은에 정의 된 대로 테이블의 구조를 기반으로 **DataRow** 개체를 만듭니다 <xref:System.Data.DataColumnCollection> .</span><span class="sxs-lookup"><span data-stu-id="fe0df-107">The **DataTable** then creates the **DataRow** object based on the structure of the table, as defined by the <xref:System.Data.DataColumnCollection>.</span></span>  
  
 <span data-ttu-id="fe0df-108">다음 예제에서는 **NewRow** 메서드를 호출 하 여 새 행을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fe0df-108">The following example demonstrates how to create a new row by calling the **NewRow** method.</span></span>  
  
```vb  
Dim workRow As DataRow = workTable.NewRow()  
```  
  
```csharp  
DataRow workRow = workTable.NewRow();  
```  
  
 <span data-ttu-id="fe0df-109">그러면 다음 예제와 같이 인덱스나 열 이름을 사용하여 새로 추가된 행을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe0df-109">You then can manipulate the newly added row using an index or the column name, as shown in the following example.</span></span>  
  
```vb  
workRow("CustLName") = "Smith"  
workRow(1) = "Smith"  
```  
  
```csharp  
workRow["CustLName"] = "Smith";  
workRow[1] = "Smith";  
```  
  
 <span data-ttu-id="fe0df-110">새 행에 데이터를 삽입 한 후에는 **Add** <xref:System.Data.DataRowCollection> 다음 코드에 나와 있는 것 처럼 add 메서드를 사용 하 여에 행을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0df-110">After data is inserted into the new row, the **Add** method is used to add the row to the <xref:System.Data.DataRowCollection>, shown in the following code.</span></span>  
  
```vb  
workTable.Rows.Add(workRow)  
```  
  
```csharp  
workTable.Rows.Add(workRow);  
```  
  
 <span data-ttu-id="fe0df-111">다음 예제와 같이 **Add** 메서드를 호출 하 여로 형식화 된 값의 배열을 전달 하 여 새 행을 추가할 수도 있습니다 <xref:System.Object> .</span><span class="sxs-lookup"><span data-stu-id="fe0df-111">You can also call the **Add** method to add a new row by passing in an array of values, typed as <xref:System.Object>, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Add(new Object() {1, "Smith"})  
```  
  
```csharp  
workTable.Rows.Add(new Object[] {1, "Smith"});  
```  
  
 <span data-ttu-id="fe0df-112">**Object**로 형식화 된 값 배열을 **Add** 메서드에 전달 하면 테이블 안에 새 행이 생성 되 고 해당 열 값이 개체 배열의 값으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fe0df-112">Passing an array of values, typed as **Object**, to the **Add** method creates a new row inside the table and sets its column values to the values in the object array.</span></span> <span data-ttu-id="fe0df-113">배열 값은 테이블에 나타나는 순서에 따라 해당 열과 순서대로 대응합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0df-113">Note that values in the array are matched sequentially to the columns, based on the order in which they appear in the table.</span></span>  
  
 <span data-ttu-id="fe0df-114">다음 예에서는 새로 만든 **Customers** 테이블에 10 개의 행을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe0df-114">The following example adds 10 rows to the newly created **Customers** table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fe0df-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe0df-115">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="fe0df-116">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="fe0df-116">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="fe0df-117">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="fe0df-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
