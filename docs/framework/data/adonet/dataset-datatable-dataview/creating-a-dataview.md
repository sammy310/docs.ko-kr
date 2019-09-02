---
title: DataView 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 391c071f19149e9690c9121b1094aef5bfa605cd
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203830"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="387be-102">DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="387be-102">Creating a DataView</span></span>
<span data-ttu-id="387be-103"><xref:System.Data.DataView>를 만드는 방법은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="387be-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="387be-104">**DataView** 생성자를 사용 하거나의 <xref:System.Data.DataTable.DefaultView%2A> <xref:System.Data.DataTable>속성에 대 한 참조를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="387be-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="387be-105">**DataView** 생성자는 비어 있거나, **datatable** 을 단일 인수로 사용 하거나, 필터 조건, 정렬 조건 및 행 상태 필터와 함께 **datatable** 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="387be-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="387be-106">**DataView**에 사용할 수 있는 추가 인수에 대 한 자세한 내용은 [데이터 정렬 및 필터링](sorting-and-filtering-data.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="387be-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="387be-107">Dataview가 만들어질 때와 **Sort**, **RowFilter**또는 **Rowstatefilter** 속성이 모두 수정 될 때 **dataview** 에 대 한 인덱스가 작성 되기 때문에 초기에 **DataView**를 만들 때 순서 또는 필터링 조건을 생성자 인수로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="387be-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="387be-108">정렬 또는 필터 조건을 지정 하지 않고 **dataview** 를 만든 후 나중에 **sort**, **RowFilter**또는 **rowstatefilter** 속성을 설정 하면 인덱스는 나중에 두 번 이상 빌드됩니다. 정렬 또는 필터 속성을 수정할 때 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="387be-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="387be-109">인수를 사용 하지 않는 생성자를 사용 하 여 **dataview** 를 만드는 경우에는 **테이블** 속성을 설정할 때까지 **dataview** 를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="387be-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="387be-110">다음 코드 예제에서는 **dataview** 생성자를 사용 하 여 **dataview** 를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="387be-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="387be-111">**RowFilter**, **Sort** 열 및 **DataViewRowState** 는 **DataTable**과 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="387be-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="387be-112">다음 코드 예제에서는 테이블의 **DefaultView** 속성을 사용 하 여 **DataTable** 의 기본 **DataView** 에 대 한 참조를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="387be-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="387be-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="387be-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="387be-114">DataView</span><span class="sxs-lookup"><span data-stu-id="387be-114">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="387be-115">데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="387be-115">Sorting and Filtering Data</span></span>](sorting-and-filtering-data.md)
- [<span data-ttu-id="387be-116">DataTable</span><span class="sxs-lookup"><span data-stu-id="387be-116">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="387be-117">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="387be-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
