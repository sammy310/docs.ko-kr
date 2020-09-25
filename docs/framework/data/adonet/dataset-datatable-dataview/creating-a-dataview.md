---
title: DataView 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 539e9763c8aa4affdb6f3bd219a99dbca50cee01
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202345"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="15c42-102">DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="15c42-102">Creating a DataView</span></span>

<span data-ttu-id="15c42-103"><xref:System.Data.DataView>를 만드는 방법은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="15c42-104">**DataView** 생성자를 사용 하거나의 속성에 대 한 참조를 만들 수 있습니다 <xref:System.Data.DataTable.DefaultView%2A> <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="15c42-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="15c42-105">**DataView** 생성자는 비어 있거나, **datatable** 을 단일 인수로 사용 하거나, 필터 조건, 정렬 조건 및 행 상태 필터와 함께 **datatable** 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="15c42-106">**DataView**에 사용할 수 있는 추가 인수에 대 한 자세한 내용은 [데이터 정렬 및 필터링](sorting-and-filtering-data.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15c42-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="15c42-107">Dataview **가 만들어질** 때 그리고 **Sort**, **RowFilter**또는 **Rowstatefilter** 속성이 모두 수정 될 때 **dataview** 의 인덱스가 빌드되기 때문에 **dataview**를 만들 때 초기 정렬 순서나 필터링 조건을 생성자 인수로 제공 하 여 최상의 성능을 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="15c42-108">정렬 또는 필터 조건을 지정 하지 않고 **dataview** 를 만든 후 나중에 **sort**, **RowFilter**또는 **rowstatefilter** 속성을 설정 하면 인덱스를 두 번 이상 작성 합니다. 즉, **dataview** 를 만들 때 한 번, 정렬 또는 필터 속성이 수정 될 때 다시 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="15c42-109">인수를 사용 하지 않는 생성자를 사용 하 여 **dataview** 를 만드는 경우에는 **테이블** 속성을 설정할 때까지 **dataview** 를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="15c42-110">다음 코드 예제에서는 **dataview** 생성자를 사용 하 여 **dataview** 를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="15c42-111">**RowFilter**, **Sort** 열 및 **DataViewRowState** 는 **DataTable**과 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="15c42-112">다음 코드 예제에서는 테이블의 **DefaultView** 속성을 사용 하 여 **DataTable** 의 기본 **DataView** 에 대 한 참조를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15c42-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="15c42-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15c42-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="15c42-114">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="15c42-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="15c42-115">데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="15c42-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="15c42-116">DataTables</span><span class="sxs-lookup"><span data-stu-id="15c42-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="15c42-117">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="15c42-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
