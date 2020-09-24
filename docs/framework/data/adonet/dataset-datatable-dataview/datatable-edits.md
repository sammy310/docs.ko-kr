---
title: DataTable 편집
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 4fdb19e7fa014bf4a7c924b1fbae53fa44de6e3c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153263"
---
# <a name="datatable-edits"></a><span data-ttu-id="2e2c1-102">DataTable 편집</span><span class="sxs-lookup"><span data-stu-id="2e2c1-102">DataTable Edits</span></span>

<span data-ttu-id="2e2c1-103"><xref:System.Data.DataRow>에서 열 값을 변경하는 경우, 변경된 값은 현재 상태의 행에 바로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="2e2c1-104"><xref:System.Data.DataRowState>그런 다음가 **Modified**로 설정 되 고, <xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A> **DataRow**의 또는 메서드를 사용 하 여 변경 내용이 허용 되거나 거부 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="2e2c1-105">또한 **DataRow** 는 편집 하는 동안 행의 상태를 일시 중단 하는 데 사용할 수 있는 세 가지 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="2e2c1-106">이러한 메서드에는 <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> 및 <xref:System.Data.DataRow.CancelEdit%2A>이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="2e2c1-107">**Datarow** 의 열 값을 직접 수정 하는 경우 **datarow** 는 **현재**, **기본**및 **원래** 행 버전을 사용 하 여 열 값을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="2e2c1-108">이러한 행 버전 외에도 **BeginEdit**, **EndEdit**및 **CancelEdit** 메서드는 네 번째 행 버전 ( **제안 됨**)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="2e2c1-109">행 버전에 대 한 자세한 내용은 [행 상태 및 행 버전](row-states-and-row-versions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="2e2c1-110">**제안** 된 행 버전은 **BeginEdit** 를 호출 하 여 시작 하 고 **EndEdit** 또는 **CancelEdit를** 사용 하거나 **AcceptChanges** 또는 **RejectChanges**를 호출 하 여 종료 되는 편집 작업 중에 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="2e2c1-111">편집 작업을 수행 하는 동안 **DataTable**의 **Columnchanged** 이벤트에서 **ProposedValue** 를 평가 하 여 개별 열에 유효성 검사 논리를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="2e2c1-112">**Columnchanged** 이벤트는를 변경 하는 열과 **ProposedValue**에 대 한 참조를 유지 하는 **DataColumnChangeEventArgs** 을 보유 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="2e2c1-113">사용자는 제안된 값을 검사한 후 이 값을 수정하거나 편집을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="2e2c1-114">편집이 종료 되 면 행이 **제안** 된 상태에서 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="2e2c1-115">**EndEdit**를 호출 하 여 편집을 확인 하거나 **CancelEdit**를 호출 하 여 편집을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="2e2c1-116">**EndEdit** 에서 편집을 확인 하는 동안에는 **AcceptChanges** 가 호출 될 때까지 **데이터 집합이** 실제로 변경 내용을 수락 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="2e2c1-117">**EndEdit** 또는 **CancelEdit**를 사용 하 여 편집을 종료 하기 전에 **AcceptChanges** 를 호출 하는 경우에는 편집이 종료 되 고 **현재** 행과 **원래** 행 버전 모두에 대해 **제안** 된 행 값이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="2e2c1-118">동일한 방식으로 **RejectChanges** 를 호출 하면 편집이 종료 되 고 **현재** 및 **제안** 된 행 버전이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="2e2c1-119">**AcceptChanges** 또는 **RejectChanges** 를 호출한 후에는 **EndEdit** 또는 **CancelEdit** 를 호출 해도 편집이 이미 종료 되었으므로 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="2e2c1-120">다음 예제에서는 **EndEdit** 및 **CancelEdit**와 함께 **BeginEdit** 를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="2e2c1-121">또한이 예제에서는 **Columnchanged** 이벤트에서 **ProposedValue** 를 확인 하 고 편집을 취소할지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e2c1-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2e2c1-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e2c1-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="2e2c1-123">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="2e2c1-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="2e2c1-124">DataTable 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="2e2c1-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="2e2c1-125">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="2e2c1-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
