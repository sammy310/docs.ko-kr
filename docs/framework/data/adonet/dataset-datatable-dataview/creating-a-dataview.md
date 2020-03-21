---
title: DataView 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151340"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="e8bf1-102">DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="e8bf1-102">Creating a DataView</span></span>
<span data-ttu-id="e8bf1-103"><xref:System.Data.DataView>를 만드는 방법은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="e8bf1-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="e8bf1-104">**DataView** 생성기를 사용하거나 <xref:System.Data.DataTable.DefaultView%2A> <xref:System.Data.DataTable>의 속성에 대한 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8bf1-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="e8bf1-105">**DataView** 생성자는 비어 있거나 **DataTable을** 단일 인수로 사용할 수 있거나 필터 조건, 정렬 조건 및 행 상태 필터와 함께 **DataTable을** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8bf1-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="e8bf1-106">**DataView에서**사용할 수 있는 추가 인수에 대한 자세한 내용은 [데이터 정렬 및 필터링](sorting-and-filtering-data.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8bf1-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="e8bf1-107">**DataView에** 대 한 인덱스는 **DataView를** 만들 때 와 **정렬**, **RowFilter**또는 **RowStateFilter** 속성 중 하나만 수정 될 때 모두 빌드되므로 **DataView를**만들 때 초기 정렬 순서 또는 필터링 조건을 생성자 인수로 제공하여 최상의 성능을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8bf1-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="e8bf1-108">정렬 또는 필터 조건을 지정하지 않고 **DataView를** 만든 다음 **Sort**, **RowFilter**또는 **RowStateFilter** 속성을 설정하지 않고 나중에 **DataView를** 만들 때 한 번, 정렬 또는 필터 속성이 수정될 때 인덱스를 두 번 이상 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="e8bf1-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="e8bf1-109">인수를 사용하지 않는 생성기를 사용하여 **DataView를** 만드는 경우 **Table** 속성을 설정하기 전까지는 **DataView를** 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e8bf1-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="e8bf1-110">다음 코드 예제에서는 **DataView** 생성기를 사용하여 **DataView를** 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8bf1-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="e8bf1-111">**행 필터,** **정렬** 열 및 **DataViewRowState는** **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="e8bf1-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],
    "Country = 'USA'",
    "ContactName",
    DataViewRowState.CurrentRows);  
```  
  
 <span data-ttu-id="e8bf1-112">다음 코드 예제에서는 테이블의 **DefaultView** 속성을 사용하여 **DataTable의** 기본 **DataView에** 대한 참조를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8bf1-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8bf1-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8bf1-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="e8bf1-114">DataView</span><span class="sxs-lookup"><span data-stu-id="e8bf1-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="e8bf1-115">데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="e8bf1-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="e8bf1-116">DataTable</span><span class="sxs-lookup"><span data-stu-id="e8bf1-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="e8bf1-117">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="e8bf1-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
