---
title: 형식화된 데이터 세트 쿼리
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
ms.assetid: ad712fa1-2baf-462a-b163-574cce6d376a
ms.openlocfilehash: d956fd5f07c108146d20623bcf811266380c132c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61651742"
---
# <a name="query-typed-datasets"></a><span data-ttu-id="6b557-102">형식화 된 데이터 집합 쿼리</span><span class="sxs-lookup"><span data-stu-id="6b557-102">Query typed DataSets</span></span>

<span data-ttu-id="6b557-103">하는 경우의 스키마를 <xref:System.Data.DataSet> 응용 프로그램 디자인 타임에 알려진는 형식화 된를 사용 하는 것이 좋습니다 <xref:System.Data.DataSet> LINQ to DataSet 사용 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="6b557-103">If the schema of the <xref:System.Data.DataSet> is known at application design time, we recommend that you use a typed <xref:System.Data.DataSet> when using LINQ to DataSet.</span></span> <span data-ttu-id="6b557-104">형식화된 <xref:System.Data.DataSet>은 <xref:System.Data.DataSet>에서 파생된 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-104">A typed <xref:System.Data.DataSet> is a class that derives from a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6b557-105">따라서 <xref:System.Data.DataSet>의 모든 메서드, 이벤트 및 속성이 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-105">As such, it inherits all the methods, events, and properties of a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6b557-106">또한 형식화된 <xref:System.Data.DataSet>에서는 강력한 형식의 메서드, 이벤트 및 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-106">Additionally, a typed <xref:System.Data.DataSet> provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="6b557-107">즉, 컬렉션 기반의 메서드 대신 이름을 사용하여 테이블과 열에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-107">This means that you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="6b557-108">이렇게 하면 간단하고 이해하기 쉬운 쿼리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-108">This makes queries simpler and more readable.</span></span> <span data-ttu-id="6b557-109">자세한 내용은 [형식화 된 데이터 집합](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-109">For more information, see [Typed DataSets](../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md).</span></span>

<span data-ttu-id="6b557-110">LINQ to DataSet 형식화 된 쿼리도 지원 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-110">LINQ to DataSet also supports querying over a typed <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6b557-111">형식화된 <xref:System.Data.DataSet>을 사용하면 열 데이터에 액세스하기 위해 제네릭 <xref:System.Data.DataRowExtensions.Field%2A> 메서드 또는 <xref:System.Data.DataRowExtensions.SetField%2A> 메서드를 사용하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-111">With a typed <xref:System.Data.DataSet>, you do not have to use the generic <xref:System.Data.DataRowExtensions.Field%2A> method or <xref:System.Data.DataRowExtensions.SetField%2A> method to access column data.</span></span> <span data-ttu-id="6b557-112"><xref:System.Data.DataSet>에 형식 정보가 있기 때문에 컴파일 타임에 속성 이름을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-112">Property names are available at compile time because the type information is included in the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="6b557-113">LINQ to DataSet 런타임에 코드 대신 컴파일될 때 형식 불일치 오류가 발생 있도록를 올바른 형식으로 열 값에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-113">LINQ to DataSet provides access to column values as the correct type, so that type mismatch errors are caught when the code is compiled instead of at run time.</span></span>

<span data-ttu-id="6b557-114">형식화 된 쿼리를 시작 하기 전에 <xref:System.Data.DataSet>를 사용 하 여 클래스를 생성 해야 합니다 **데이터 집합 디자이너** Visual Studio에서.</span><span class="sxs-lookup"><span data-stu-id="6b557-114">Before you can begin querying a typed <xref:System.Data.DataSet>, you must generate the class by using the **DataSet Designer** in Visual Studio.</span></span> <span data-ttu-id="6b557-115">자세한 내용은 [만들기 및 데이터 집합 구성](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-115">For more information, see [Create and configure DataSets](/visualstudio/data-tools/create-and-configure-datasets-in-visual-studio).</span></span>

## <a name="example"></a><span data-ttu-id="6b557-116">예제</span><span class="sxs-lookup"><span data-stu-id="6b557-116">Example</span></span>

<span data-ttu-id="6b557-117">다음 예제에서는 형식화된 <xref:System.Data.DataSet>에 대한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b557-117">The following example shows a query over a typed <xref:System.Data.DataSet>:</span></span>

```csharp
var query = from o in orders
            where o.OnlineOrderFlag == true
            select new { o.SalesOrderID,
                         o.OrderDate,
                         o.SalesOrderNumber };

foreach(var order in query)
{
    Console.WriteLine("{0}\t{1:d}\t{2}",
      order.SalesOrderID,
      order.OrderDate,
      order.SalesOrderNumber);
}
```

```vb
Dim orders = ds.Tables("SalesOrderHeader")

Dim query = _
       From o In orders _
       Where o.OnlineOrderFlag = True _
       Select New {SalesOrderID := o.SalesOrderID, _
                   OrderDate := o.OrderDate, _
                   SalesOrderNumber := o.SalesOrderNumber}

For Each Dim onlineOrder In query
 Console.WriteLine("{0}\t{1:d}\t{2}", _
 onlineOrder.SalesOrderID, _
 onlineOrder.OrderDate, _
 onlineOrder.SalesOrderNumber)
Next
```

## <a name="see-also"></a><span data-ttu-id="6b557-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="6b557-118">See also</span></span>

- [<span data-ttu-id="6b557-119">데이터 집합 쿼리</span><span class="sxs-lookup"><span data-stu-id="6b557-119">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="6b557-120">크로스 테이블 쿼리</span><span class="sxs-lookup"><span data-stu-id="6b557-120">Cross-Table Queries</span></span>](../../../../docs/framework/data/adonet/cross-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="6b557-121">단일 테이블 쿼리</span><span class="sxs-lookup"><span data-stu-id="6b557-121">Single-Table Queries</span></span>](../../../../docs/framework/data/adonet/single-table-queries-linq-to-dataset.md)
