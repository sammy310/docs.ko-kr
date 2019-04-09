---
title: DataRow 및 DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 14e210c36ee2ab8ddba7451ac7b346ad72288d94
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096357"
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="209ff-102">DataRow 및 DataRowView</span><span class="sxs-lookup"><span data-stu-id="209ff-102">DataRows and DataRowViews</span></span>
<span data-ttu-id="209ff-103"><xref:System.Data.DataView>는 <xref:System.Data.DataRowView> 개체의 열거할 수 있는 컬렉션을 노출시킵니다.</span><span class="sxs-lookup"><span data-stu-id="209ff-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="209ff-104">합니다 **DataRowView** 개체 이름 또는 기본 테이블의 열 서 수 참조에 따라 인덱싱된 개체 배열로 값을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="209ff-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="209ff-105">액세스할 수 있습니다는 <xref:System.Data.DataRow> 의해 노출 되는 **DataRowView** 를 사용 하 여를 <xref:System.Data.DataRowView.Row%2A> 의 속성을 **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="209ff-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="209ff-106">사용 하 여 값을 볼 때를 **DataRowView**, <xref:System.Data.DataView.RowStateFilter%2A> 의 속성을 **DataView** 기본 행 버전을 결정 **DataRow** 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="209ff-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="209ff-107">사용 하 여 다른 행 버전에 액세스 하는 방법에 대 한 정보에 대 한는 **DataRow**를 참조 하세요 [행 상태 및 행 버전](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="209ff-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="209ff-108">다음 코드 예제에서는 테이블의 현재 값과 원래 값을 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="209ff-108">The following code example displays all the current and original values in a table.</span></span>  
  
```vb  
Dim catView As DataView = New DataView(catDS.Tables("Categories"))  
Console.WriteLine("Current Values:")  
WriteView(catView)  
Console.WriteLine("Original Values:")  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal  
WriteView(catView)      
  
Public Shared Sub WriteView(thisDataView As DataView)  
  Dim rowView As DataRowView  
  Dim i As Integer  
  
  For Each rowView In thisDataView  
    For i = 0 To thisDataView.Table.Columns.Count - 1  
      Console.Write(rowView(i) & vbTab)  
    Next  
    Console.WriteLine()  
  Next  
End Sub  
```  
  
```csharp  
DataView catView = new DataView(catDS.Tables["Categories"]);  
Console.WriteLine("Current Values:");  
WriteView(catView);  
Console.WriteLine("Original Values:");  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal;  
WriteView(catView);  
  
public static void WriteView(DataView thisDataView)  
{  
  foreach (DataRowView rowView in thisDataView)  
  {  
    for (int i = 0; i < thisDataView.Table.Columns.Count; i++)  
      Console.Write(rowView[i] + "\t");  
    Console.WriteLine();  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="209ff-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="209ff-109">See also</span></span>

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="209ff-110">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="209ff-110">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="209ff-111">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="209ff-111">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
