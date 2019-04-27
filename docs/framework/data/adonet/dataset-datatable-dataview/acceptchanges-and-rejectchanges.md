---
title: AcceptChanges 및 RejectChanges
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e2d1a6fe-31f9-4b83-9728-06c406a3394e
ms.openlocfilehash: bbcc666b99c2bade479e5ee51750b043c820845d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879907"
---
# <a name="acceptchanges-and-rejectchanges"></a><span data-ttu-id="a1c52-102">AcceptChanges 및 RejectChanges</span><span class="sxs-lookup"><span data-stu-id="a1c52-102">AcceptChanges and RejectChanges</span></span>
<span data-ttu-id="a1c52-103">데이터에 대 한 변경 내용의 정확성을 확인 한 후는 <xref:System.Data.DataTable>를 사용 하 여 변경 내용을 적용할 수 있습니다 합니다 <xref:System.Data.DataRow.AcceptChanges%2A> 메서드의 <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, 또는 <xref:System.Data.DataSet>로 설정 됩니다는 **현재** 행 값을 **원래** 값을 설정 합니다 합니다 **RowState** 속성을 **Unchanged**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c52-103">After verifying the accuracy of changes made to data in a <xref:System.Data.DataTable>, you can accept the changes using the <xref:System.Data.DataRow.AcceptChanges%2A> method of the <xref:System.Data.DataRow>, <xref:System.Data.DataTable>, or <xref:System.Data.DataSet>, which will set the **Current** row values to be the **Original** values and will set the **RowState** property to **Unchanged**.</span></span> <span data-ttu-id="a1c52-104">수락 하거나 거부 하는 변경 내용을 모두 지웁니다 **RowError** 정보와 집합 합니다 **HasErrors** 속성을 **false**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c52-104">Accepting or rejecting changes clears out any **RowError** information and sets the **HasErrors** property to **false**.</span></span> <span data-ttu-id="a1c52-105">또한, 변경 사항을 승인하거나 거부하면 데이터 소스에서 데이터를 업데이트하는 데도 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1c52-105">Accepting or rejecting changes can also affect updating data in the data source.</span></span> <span data-ttu-id="a1c52-106">자세한 내용은 [Dataadapter 사용 하 여 데이터 원본 업데이트](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c52-106">For more information, see [Updating Data Sources with DataAdapters](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).</span></span>  
  
 <span data-ttu-id="a1c52-107">외래 키 제약 조건이 있는 경우는 **DataTable**, 변경 내용을 승인 또는 거부를 사용 하 여 **AcceptChanges** 하 고 **RejectChanges** 합니다 의자식행으로전파됩니다 **DataRow** 에 따라 합니다 **ForeignKeyConstraint.AcceptRejectRule**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c52-107">If foreign key constraints exist on the **DataTable**, changes accepted or rejected using **AcceptChanges** and **RejectChanges** are propagated to child rows of the **DataRow** according to the **ForeignKeyConstraint.AcceptRejectRule**.</span></span> <span data-ttu-id="a1c52-108">자세한 내용은 [DataTable 제약 조건](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c52-108">For more information, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="a1c52-109">다음 예제에서는 오류가 발생한 행을 검사하여 가능한 경우 오류를 해결하고 오류를 해결할 수 없는 경우에는 해당 행을 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c52-109">The following example checks for rows with errors, resolves the errors where applicable, and rejects the rows where the error cannot be resolved.</span></span> <span data-ttu-id="a1c52-110">해결 된 경우 오류를 참고 합니다 **RowError** 값이 빈 문자열을 다시 설정 발생 합니다 **HasErrors** 속성을 설정할 **false**.</span><span class="sxs-lookup"><span data-stu-id="a1c52-110">Note that, for resolved errors, the **RowError** value is reset to an empty string, causing the **HasErrors** property to be set to **false**.</span></span> <span data-ttu-id="a1c52-111">오류가 발생 한 모든 행 해결 되거나 거부 된 경우 **AcceptChanges** 전체에 대 한 모든 변경 내용을 적용 하기 위해 호출 됩니다 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="a1c52-111">When all the rows with errors have been resolved or rejected, **AcceptChanges** is called to accept all changes for the entire **DataTable**.</span></span>  
  
```vb  
If workTable.HasErrors Then  
  Dim errRow As DataRow  
  
  For Each errRow in workTable.GetErrors()  
  
    If errRow.RowError = "Total cannot exceed 1000." Then  
      errRow("Total") = 1000  
      errRow.RowError = ""    ' Clear the error.  
    Else  
      errRow.RejectChanges()  
    End If  
  Next  
End If  
  
workTable.AcceptChanges()  
```  
  
```csharp  
if (workTable.HasErrors)  
{  
  
  foreach (DataRow errRow in workTable.GetErrors())  
  {  
    if (errRow.RowError == "Total cannot exceed 1000.")  
    {  
      errRow["Total"] = 1000;  
      errRow.RowError = "";    // Clear the error.  
    }  
    else  
      errRow.RejectChanges();  
  }  
}  
  
workTable.AcceptChanges();  
```  
  
## <a name="see-also"></a><span data-ttu-id="a1c52-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="a1c52-112">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataSet>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="a1c52-113">DataTable에서 데이터 조작</span><span class="sxs-lookup"><span data-stu-id="a1c52-113">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="a1c52-114">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="a1c52-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
