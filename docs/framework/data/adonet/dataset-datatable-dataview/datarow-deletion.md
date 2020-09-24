---
title: DataRow 삭제
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 2092d7319a398bbdeaef764d677818f78ddf9de9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153354"
---
# <a name="datarow-deletion"></a><span data-ttu-id="70592-102">DataRow 삭제</span><span class="sxs-lookup"><span data-stu-id="70592-102">DataRow Deletion</span></span>

<span data-ttu-id="70592-103">개체에서 개체를 삭제 하는 데 사용할 수 있는 두 가지 방법은 <xref:System.Data.DataRow> <xref:System.Data.DataTable> 개체의 **Remove** 메서드와 <xref:System.Data.DataRowCollection> <xref:System.Data.DataRow.Delete%2A> **DataRow** 개체의 메서드를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70592-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="70592-104"><xref:System.Data.DataRowCollection.Remove%2A>메서드가 **DataRowCollection**에서 **DataRow** 를 삭제 하는 반면 메서드는 <xref:System.Data.DataRow.Delete%2A> 행을 삭제 하도록 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="70592-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="70592-105">실제 제거는 응용 프로그램이 **AcceptChanges** 메서드를 호출할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="70592-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="70592-106"><xref:System.Data.DataRow.Delete%2A>를 사용하면 행을 실제로 삭제하기 전에 삭제 표시된 행을 프로그래밍 방식으로 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70592-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="70592-107">삭제 표시된 행의 <xref:System.Data.DataRow.RowState%2A> 속성은 <xref:System.Data.DataRow.Delete%2A>로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="70592-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="70592-108"><xref:System.Data.DataRow.Delete%2A> 개체를 반복하는 동안에는 foreach 루프에서 <xref:System.Data.DataRowCollection.Remove%2A> 또는 <xref:System.Data.DataRowCollection>가 호출되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="70592-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="70592-109"><xref:System.Data.DataRow.Delete%2A> 또는 <xref:System.Data.DataRowCollection.Remove%2A>는 컬렉션의 상태를 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70592-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="70592-110"><xref:System.Data.DataSet> **DataAdapter** 및 관계형 데이터 원본과 함께 또는 **DataTable** 을 사용 하는 경우 **DataRow** 의 **Delete** 메서드를 사용 하 여 행을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="70592-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="70592-111">**Delete** 메서드는 **데이터 집합이** 나 **DataTable** 에서 행을 **삭제** 된 것으로 표시 하지만 제거 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70592-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="70592-112">대신 **DataAdapter** 가 **Deleted**로 표시 된 행을 발견 하면 해당 **DeleteCommand** 메서드를 실행 하 여 데이터 소스에서 행을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="70592-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="70592-113">그런 다음 **AcceptChanges** 메서드를 사용 하 여 행을 영구적으로 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70592-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="70592-114">**제거** 를 사용 하 여 행을 삭제 하면 해당 행은 테이블에서 완전히 제거 되지만 **DataAdapter** 는 데이터 원본에서 행을 삭제 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70592-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="70592-115">**DataRowCollection** 의 **Remove** 메서드는 다음 예제와 같이 **DataRow** 를 인수로 사용 하 고 컬렉션에서 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="70592-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="70592-116">반면, 다음 예제에서는 **DataRow** 에 대해 **Delete** 메서드를 호출 하 여 **RowState** 를 **deleted**로 변경 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="70592-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="70592-117">행이 삭제 되도록 표시 되 고 **datatable** 개체의 **AcceptChanges** 메서드를 호출 하면 **datatable**에서 해당 행이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70592-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="70592-118">반면 **RejectChanges**를 호출 하면 행의 **RowState** 가 **삭제**된 것으로 표시 되기 전의 상태로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="70592-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="70592-119">**DataRow** 의 **RowState** 이 **추가**되 면 테이블에 추가 된 것을 의미 하 고 **삭제**된 것으로 표시 되 면 테이블에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70592-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70592-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="70592-120">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="70592-121">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="70592-121">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="70592-122">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="70592-122">ADO.NET Overview</span></span>](../ado-net-overview.md)
