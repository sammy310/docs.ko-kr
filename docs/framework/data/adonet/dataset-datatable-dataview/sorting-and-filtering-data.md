---
title: 데이터 정렬 및 필터링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fdd9c753-39df-48cd-9822-2781afe76200
ms.openlocfilehash: 89e2fdf656fb06ee545ba936f033646ad86182d4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183379"
---
# <a name="sorting-and-filtering-data"></a><span data-ttu-id="06c01-102">데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="06c01-102">Sorting and Filtering Data</span></span>

<span data-ttu-id="06c01-103"><xref:System.Data.DataView>를 사용하면 다음과 같은 여러 가지 방법으로 <xref:System.Data.DataTable>의 데이터를 정렬 및 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-103">The <xref:System.Data.DataView> provides several ways of sorting and filtering data in a <xref:System.Data.DataTable>:</span></span>  
  
- <span data-ttu-id="06c01-104"><xref:System.Data.DataView.Sort%2A> 속성을 사용하여 하나 또는 여러 열의 정렬 순서를 지정하고, ASC(오름차순) 및 DESC(내림차순) 매개 변수를 포함시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-104">You can use the <xref:System.Data.DataView.Sort%2A> property to specify single or multiple column sort orders and include ASC (ascending) and DESC (descending) parameters.</span></span>  
  
- <span data-ttu-id="06c01-105"><xref:System.Data.DataView.ApplyDefaultSort%2A> 속성을 사용하여 테이블의 기본 키 열을 기준으로 오름차순의 정렬 순서를 자동으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-105">You can use the <xref:System.Data.DataView.ApplyDefaultSort%2A> property to automatically create a sort order, in ascending order, based on the primary key column or columns of the table.</span></span> <span data-ttu-id="06c01-106"><xref:System.Data.DataView.ApplyDefaultSort%2A>**Sort** 속성이 null 참조 또는 빈 문자열인 경우와 테이블에 기본 키가 정의 되어 있는 경우에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-106"><xref:System.Data.DataView.ApplyDefaultSort%2A> only applies when the **Sort** property is a null reference or an empty string, and when the table has a primary key defined.</span></span>  
  
- <span data-ttu-id="06c01-107"><xref:System.Data.DataView.RowFilter%2A> 속성을 사용하여 해당 열 값을 기준으로 행의 하위 집합을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-107">You can use the <xref:System.Data.DataView.RowFilter%2A> property to specify subsets of rows based on their column values.</span></span> <span data-ttu-id="06c01-108">**RowFilter** 속성의 유효한 식에 대 한 자세한 내용은 <xref:System.Data.DataColumn.Expression%2A> 클래스의 속성에 대 한 참조 정보를 참조 하세요 <xref:System.Data.DataColumn> .</span><span class="sxs-lookup"><span data-stu-id="06c01-108">For details about valid expressions for the **RowFilter** property, see the reference information for the <xref:System.Data.DataColumn.Expression%2A> property of the <xref:System.Data.DataColumn> class.</span></span>  
  
     <span data-ttu-id="06c01-109">데이터의 하위 집합에 대 한 동적 뷰를 제공 하는 것과는 반대로 데이터에 대 한 특정 쿼리 결과를 반환 하려면 <xref:System.Data.DataView.Find%2A> <xref:System.Data.DataView.FindRows%2A> **RowFilter** 속성을 설정 하는 대신 **DataView** 의 또는 메서드를 사용 하 여 최상의 성능을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-109">If you want to return the results of a particular query on the data, as opposed to providing a dynamic view of a subset of the data, use the <xref:System.Data.DataView.Find%2A> or <xref:System.Data.DataView.FindRows%2A> methods of the **DataView** to achieve best performance rather than setting the **RowFilter** property.</span></span> <span data-ttu-id="06c01-110">**RowFilter** 속성을 설정 하면 데이터의 인덱스가 다시 빌드되고, 응용 프로그램에 오버 헤드가 추가 되 고 성능이 저하 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-110">Setting the **RowFilter** property rebuilds the index for the data, adding overhead to your application and decreasing performance.</span></span> <span data-ttu-id="06c01-111">**RowFilter** 속성은 바인딩된 컨트롤이 필터링 된 결과를 표시 하는 데이터 바인딩된 응용 프로그램에서 사용 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-111">The **RowFilter** property is best used in a data-bound application where a bound control displays filtered results.</span></span> <span data-ttu-id="06c01-112">**Find** 및 **findrows** 메서드는 인덱스를 다시 작성할 필요 없이 현재 인덱스를 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-112">The **Find** and **FindRows** methods leverage the current index without requiring the index to be rebuilt.</span></span> <span data-ttu-id="06c01-113">**Find** 및 **findrows** 메서드에 대 한 자세한 내용은 [행 찾기](finding-rows.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="06c01-113">For more information about the **Find** and **FindRows** methods, see [Finding Rows](finding-rows.md).</span></span>  
  
- <span data-ttu-id="06c01-114"><xref:System.Data.DataView.RowStateFilter%2A> 속성을 사용하면 표시할 행 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-114">You can use the <xref:System.Data.DataView.RowStateFilter%2A> property to specify which row versions to view.</span></span> <span data-ttu-id="06c01-115">**DataView** 는 기본 행의 **RowState** 에 따라 노출할 행 버전을 암시적으로 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-115">The **DataView** implicitly manages which row version to expose depending upon the **RowState** of the underlying row.</span></span> <span data-ttu-id="06c01-116">예를 들어 **Rowstatefilter** 가 **DataViewRowState**로 설정 된 경우 **현재** 행 버전이 없으므로 **DataView** 는 **삭제** 된 모든 행의 **원래** 행 버전을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-116">For example, if the **RowStateFilter** is set to **DataViewRowState.Deleted**, the **DataView** exposes the **Original** row version of all **Deleted** rows because there is no **Current** row version.</span></span> <span data-ttu-id="06c01-117">**DataRowView**의 **RowVersion** 속성을 사용 하 여 표시 되는 행의 행 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-117">You can determine which row version of a row is being exposed by using the **RowVersion** property of the **DataRowView**.</span></span>  
  
     <span data-ttu-id="06c01-118">다음 표에서는 **DataViewRowState**에 대 한 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-118">The following table shows the options for **DataViewRowState**.</span></span>  
  
    |<span data-ttu-id="06c01-119">DataViewRowState 옵션</span><span class="sxs-lookup"><span data-stu-id="06c01-119">DataViewRowState options</span></span>|<span data-ttu-id="06c01-120">설명</span><span class="sxs-lookup"><span data-stu-id="06c01-120">Description</span></span>|  
    |------------------------------|-----------------|  
    |<span data-ttu-id="06c01-121">**CurrentRows**</span><span class="sxs-lookup"><span data-stu-id="06c01-121">**CurrentRows**</span></span>|<span data-ttu-id="06c01-122">**변경 되지 않고** **추가**되거나 **수정** 된 모든 행의 **현재** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-122">The **Current** row version of all **Unchanged**, **Added**, and **Modified** rows.</span></span> <span data-ttu-id="06c01-123">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-123">This is the default.</span></span>|  
    |<span data-ttu-id="06c01-124">**추가됨**</span><span class="sxs-lookup"><span data-stu-id="06c01-124">**Added**</span></span>|<span data-ttu-id="06c01-125">**추가** 된 모든 행의 **현재** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-125">The **Current** row version of all **Added** rows.</span></span>|  
    |<span data-ttu-id="06c01-126">**삭제됨**</span><span class="sxs-lookup"><span data-stu-id="06c01-126">**Deleted**</span></span>|<span data-ttu-id="06c01-127">**삭제** 된 모든 행의 **원래** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-127">The **Original** row version of all **Deleted** rows.</span></span>|  
    |<span data-ttu-id="06c01-128">**ModifiedCurrent**</span><span class="sxs-lookup"><span data-stu-id="06c01-128">**ModifiedCurrent**</span></span>|<span data-ttu-id="06c01-129">**수정** 된 모든 행의 **현재** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-129">The **Current** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="06c01-130">**ModifiedOriginal**</span><span class="sxs-lookup"><span data-stu-id="06c01-130">**ModifiedOriginal**</span></span>|<span data-ttu-id="06c01-131">**수정** 된 모든 행의 **원래** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-131">The **Original** row version of all **Modified** rows.</span></span>|  
    |<span data-ttu-id="06c01-132">**없음**</span><span class="sxs-lookup"><span data-stu-id="06c01-132">**None**</span></span>|<span data-ttu-id="06c01-133">행이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-133">No rows.</span></span>|  
    |<span data-ttu-id="06c01-134">**OriginalRows**</span><span class="sxs-lookup"><span data-stu-id="06c01-134">**OriginalRows**</span></span>|<span data-ttu-id="06c01-135">**변경 되지 않은**모든 행, **수정**된 행 및 **삭제** 된 행의 **원래** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-135">The **Original** row version of all **Unchanged**, **Modified**, and **Deleted** rows.</span></span>|  
    |<span data-ttu-id="06c01-136">**변경 안 됨**</span><span class="sxs-lookup"><span data-stu-id="06c01-136">**Unchanged**</span></span>|<span data-ttu-id="06c01-137">**변경 되지 않은** 모든 행의 **현재** 행 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-137">The **Current** row version of all **Unchanged** rows.</span></span>|  
  
 <span data-ttu-id="06c01-138">행 상태 및 행 버전에 대 한 자세한 내용은 [행 상태 및 행 버전](row-states-and-row-versions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06c01-138">For more information about row states and row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="06c01-139">다음 코드 예제에서는 재고 수량이 재주문 수준보다 적거나 같은 모든 제품을 표시하는 뷰를 만듭니다. 이 때 먼저 공급자 ID로 정렬한 다음 제품 이름으로 정렬하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="06c01-139">The following code example creates a view that shows all the products where the number of units in stock is less than or equal to the reorder level, sorted first by supplier ID and then by product name.</span></span>  
  
```vb  
Dim prodView As DataView = New DataView(prodDS.Tables("Products"), _  
   "UnitsInStock <= ReorderLevel", _  
   "SupplierID, ProductName", _  
   DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView prodView = new DataView(prodDS.Tables["Products"],  
   "UnitsInStock <= ReorderLevel",  
   "SupplierID, ProductName",  
   DataViewRowState.CurrentRows);  
```  
  
## <a name="see-also"></a><span data-ttu-id="06c01-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06c01-140">See also</span></span>

- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataColumn.Expression%2A?displayProperty=nameWithType>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="06c01-141">데이터 보기</span><span class="sxs-lookup"><span data-stu-id="06c01-141">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="06c01-142">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="06c01-142">ADO.NET Overview</span></span>](../ado-net-overview.md)
