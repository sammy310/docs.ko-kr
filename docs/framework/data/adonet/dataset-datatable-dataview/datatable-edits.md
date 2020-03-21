---
title: DataTable 편집
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 9e8c4204b51121b147fc7614066d9b849a687574
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151262"
---
# <a name="datatable-edits"></a><span data-ttu-id="d8542-102">DataTable 편집</span><span class="sxs-lookup"><span data-stu-id="d8542-102">DataTable Edits</span></span>
<span data-ttu-id="d8542-103"><xref:System.Data.DataRow>에서 열 값을 변경하는 경우, 변경된 값은 현재 상태의 행에 바로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="d8542-104">그런 <xref:System.Data.DataRowState> 다음 **은 수정됨**으로 설정되고 변경 <xref:System.Data.DataRow.AcceptChanges%2A> 내용은 <xref:System.Data.DataRow.RejectChanges%2A> **DataRow**의 또는 메서드를 사용하여 수락되거나 거부됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="d8542-105">**DataRow는** 또한 편집하는 동안 행의 상태를 일시 중단하는 데 사용할 수 있는 세 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="d8542-106">이러한 메서드에는 <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> 및 <xref:System.Data.DataRow.CancelEdit%2A>이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="d8542-107">**DataRow에서** 열 값을 직접 수정하면 **DataRow는** **현재**, **기본값**및 **원래** 행 버전을 사용하여 열 값을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="d8542-108">이러한 행 버전 외에도 **BeginEdit**, **EndEdit**및 **CancelEdit** 메서드는 네 번째 행 버전인 **제안된**버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="d8542-109">행 버전에 대한 자세한 내용은 [행 상태 및 행 버전을](row-states-and-row-versions.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d8542-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="d8542-110">**제안된** 행 버전은 **BeginEdit를** 호출하여 시작되고 **EndEdit** 또는 **CancelEdit를** 사용하거나 **AcceptChanges** 또는 **RejectChanges**를 호출하여 끝나는 편집 작업 중에 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="d8542-111">편집 작업 중에 **DataTable의** **ColumnChanged** 이벤트에서 **제안값을** 평가하여 개별 열에 유효성 검사 논리를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="d8542-112">**ColumnChanged** 이벤트에는 변경되는 열과 **제안값에**대한 참조를 유지하는 **DataColumnChangeEventArgs가** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="d8542-113">사용자는 제안된 값을 검사한 후 이 값을 수정하거나 편집을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="d8542-114">편집이 끝나면 행이 **제안된** 상태 밖으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="d8542-115">**EndEdit를**호출하여 편집을 확인하거나 **CancelEdit**를 호출하여 편집을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="d8542-116">**EndEdit는** 편집 내용을 확인하지만 **DataSet은** **AcceptChanges가** 호출될 때까지 변경 내용을 실제로 수락하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="d8542-117">또한 **EndEdit** 또는 **CancelEdit으로**편집을 종료하기 전에 **AcceptChanges를** 호출하면 편집이 종료되고 현재 행 **및** **원래** 행 버전 모두에 대해 **제안된** 행 값이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="d8542-118">동일한 방식으로 **RejectChanges를** 호출하면 편집이 종료되고 **현재** 및 **제안된** 행 버전이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="d8542-119">편집이 이미 종료되어 있기 때문에 **AcceptChanges** 또는 **RejectChanges를** 호출 한 후 **EndEdit** 또는 **CancelEdit를** 호출하면 아무런 효과가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="d8542-120">다음 예제에서는 **EndEdit** 및 **CancelEdit를**사용하여 **BeginEdit를** 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="d8542-121">또한 이 예제에서는 **ColumnChanged** 이벤트에서 **제안된 값을** 확인하고 편집을 취소할지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="d8542-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d8542-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d8542-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="d8542-123">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="d8542-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="d8542-124">DataTable 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="d8542-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="d8542-125">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="d8542-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
