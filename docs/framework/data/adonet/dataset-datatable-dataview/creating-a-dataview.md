---
title: DataView 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 05122f7c980c4b7dfdb27eec73464a4f0556ba99
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096682"
---
# <a name="creating-a-dataview"></a><span data-ttu-id="0c2ec-102">DataView 만들기</span><span class="sxs-lookup"><span data-stu-id="0c2ec-102">Creating a DataView</span></span>
<span data-ttu-id="0c2ec-103"><xref:System.Data.DataView>를 만드는 방법은 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-103">There are two ways to create a <xref:System.Data.DataView>.</span></span> <span data-ttu-id="0c2ec-104">사용할 수는 **DataView** 생성자에 대 한 참조를 만들 수 있습니다는 <xref:System.Data.DataTable.DefaultView%2A> 의 속성은 <xref:System.Data.DataTable>합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-104">You can use the **DataView** constructor, or you can create a reference to the <xref:System.Data.DataTable.DefaultView%2A> property of the <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="0c2ec-105">합니다 **DataView** 생성자 비워 둘 수 있습니다, 또는 중 하나를 수행 하는 **DataTable** 단일 인수로 또는 **DataTable** 필터 조건, 정렬 조건 및 행과 함께 상태 필터입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-105">The **DataView** constructor can be empty, or it can take either a **DataTable** as a single argument, or a **DataTable** along with filter criteria, sort criteria, and a row state filter.</span></span> <span data-ttu-id="0c2ec-106">에 사용할 수 있는 추가 인수에 대 한 자세한 합니다 **DataView**를 참조 하세요 [정렬 및 필터링 데이터](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-106">For more information about the additional arguments available for use with the **DataView**, see [Sorting and Filtering Data](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).</span></span>  
  
 <span data-ttu-id="0c2ec-107">때문에 대 한 인덱스를 **DataView** 때 작성 되는 **DataView** 만들어지면 있으면 및를 **정렬**, **RowFilter**, 또는  **RowStateFilter** 속성이 수정, 모든 초기 정렬 순서를 제공 하거나 만들 때 생성자 인수로 필터링 기준을 하 여 최적의 성능을 얻습니다 합니다 **DataView**합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-107">Because the index for a **DataView** is built both when the **DataView** is created, and when any of the **Sort**, **RowFilter**, or **RowStateFilter** properties are modified, you achieve best performance by supplying any initial sort order or filtering criteria as constructor arguments when you create the **DataView**.</span></span> <span data-ttu-id="0c2ec-108">만들기는 **DataView** 정렬 또는 필터 조건을 지정 하 고 다음 설정 하지 않고 합니다 **정렬**를 **RowFilter**, 또는 **RowStateFilter** 속성에는 나중에 인덱스를 두 번 이상 빌드해야 하면: 면 때 합니다 **DataView** 만들어지면 및 다시 정렬 또는 필터 속성은입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-108">Creating a **DataView** without specifying sort or filter criteria and then setting the **Sort**, **RowFilter**, or **RowStateFilter** properties later causes the index to be built at least twice: once when the **DataView** is created, and again when any of the sort or filter properties are modified.</span></span>  
  
 <span data-ttu-id="0c2ec-109">만든 경우는 **DataView** 인수를 사용 하지 않는 생성자를 사용 하 여, 됩니다 사용할 수는 **DataView** 설정 해야 합니다 **테이블** 속성 .</span><span class="sxs-lookup"><span data-stu-id="0c2ec-109">Note that if you create a **DataView** using the constructor that does not take any arguments, you will not be able to use the **DataView** until you have set the **Table** property.</span></span>  
  
 <span data-ttu-id="0c2ec-110">다음 코드 예제에는 만드는 방법을 보여 줍니다는 **DataView** 사용 하는 **DataView** 생성자입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-110">The following code example demonstrates how to create a **DataView** using the **DataView** constructor.</span></span> <span data-ttu-id="0c2ec-111">A **RowFilter**, **정렬** 열 및 **DataViewRowState** 와 함께 제공 되는 **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-111">A **RowFilter**, **Sort** column, and **DataViewRowState** are supplied along with the **DataTable**.</span></span>  
  
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
  
 <span data-ttu-id="0c2ec-112">다음 코드 예제에는 기본값에 대 한 참조를 가져오는 방법을 보여 줍니다 **DataView** 의 **DataTable** 사용 하는 **DefaultView** 테이블의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2ec-112">The following code example demonstrates how to obtain a reference to the default **DataView** of a **DataTable** using the **DefaultView** property of the table.</span></span>  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c2ec-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="0c2ec-113">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [<span data-ttu-id="0c2ec-114">DataView</span><span class="sxs-lookup"><span data-stu-id="0c2ec-114">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [<span data-ttu-id="0c2ec-115">데이터 정렬 및 필터링</span><span class="sxs-lookup"><span data-stu-id="0c2ec-115">Sorting and Filtering Data</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)
- [<span data-ttu-id="0c2ec-116">DataTable</span><span class="sxs-lookup"><span data-stu-id="0c2ec-116">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="0c2ec-117">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="0c2ec-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
