---
title: DataRow 및 DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 14e7e1ccb051410c351e49afee9f2d6809264833
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151301"
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="5732b-102">DataRow 및 DataRowView</span><span class="sxs-lookup"><span data-stu-id="5732b-102">DataRows and DataRowViews</span></span>
<span data-ttu-id="5732b-103"><xref:System.Data.DataView>는 <xref:System.Data.DataRowView> 개체의 열거할 수 있는 컬렉션을 노출시킵니다.</span><span class="sxs-lookup"><span data-stu-id="5732b-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="5732b-104">**DataRowView** 개체는 값을 기본 테이블의 열의 이름 또는 서수 참조로 인덱싱되는 개체 배열로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="5732b-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="5732b-105">DataRowView <xref:System.Data.DataRow> 의 <xref:System.Data.DataRowView.Row%2A> 속성을 사용하여 **DataRowView에** 의해 노출되는 액세스 에 액세스할 수 있습니다. **DataRowView**</span><span class="sxs-lookup"><span data-stu-id="5732b-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="5732b-106">**DataRowView를**사용하여 값을 볼 때 <xref:System.Data.DataView.RowStateFilter%2A> **DataView의** 속성은 노출된 기본 **DataRow의** 행 버전을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="5732b-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="5732b-107">**DataRow를**사용하여 다른 행 버전에 액세스하는 것에 대한 자세한 내용은 [행 상태 및 행 버전을](row-states-and-row-versions.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5732b-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="5732b-108">다음 코드 예제에서는 테이블의 현재 값과 원래 값을 모두 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5732b-108">The following code example displays all the current and original values in a table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5732b-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5732b-109">See also</span></span>

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="5732b-110">DataView</span><span class="sxs-lookup"><span data-stu-id="5732b-110">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="5732b-111">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="5732b-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
