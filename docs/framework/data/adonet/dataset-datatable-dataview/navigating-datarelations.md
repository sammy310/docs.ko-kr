---
title: DataRelation 탐색
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: 73523297454be37716acedad13498954ef9a89a0
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040343"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="b78e7-102">DataRelation 탐색</span><span class="sxs-lookup"><span data-stu-id="b78e7-102">Navigating DataRelations</span></span>
<span data-ttu-id="b78e7-103"><xref:System.Data.DataRelation>의 기본 기능 중 하나는 <xref:System.Data.DataTable> 내에서 <xref:System.Data.DataSet>를 하나씩 탐색할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-103">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="b78e7-104">이렇게 하면 관련 **datatable**에서 단일 **DataRow** 가 지정 된 경우 하나의 **DataTable** 에서 관련 된 모든 <xref:System.Data.DataRow> 개체를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-104">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="b78e7-105">예를 들어 고객 테이블과 주문 테이블 간에 **DataRelation** 을 설정한 후에는 **GetChildRows**를 사용 하 여 특정 고객 행의 모든 주문 행을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-105">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="b78e7-106">다음 코드 예에서는 **Customers** 테이블과 **데이터 집합** 의 **orders** 테이블 사이에 **DataRelation** 을 만들고 각 고객에 대 한 모든 주문을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-106">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="b78e7-107">다음 예제에서는 이전 예제를 기반으로 네 개의 테이블을 모두 연관시키고 각각의 관계를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-107">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="b78e7-108">이전 예에서와 같이 **CustomerID** 는 **Customers** 테이블을 **Orders** 테이블에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-108">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="b78e7-109">**Customers** 테이블의 각 고객에 대해 **orders** 테이블의 모든 자식 행이 결정 되어 특정 고객에 게 포함 된 주문 수와 해당 **OrderID** 값이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-109">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="b78e7-110">또한 확장 된 예제에서는 **OrderDetails** 및 **Products** 테이블의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-110">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="b78e7-111">**Orders** 테이블은 **OrderID** 를 사용 하 여 각 고객 주문, 주문 된 제품 및 수량을 확인 하는 **OrderDetails** 테이블과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-111">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="b78e7-112">**OrderDetails** 테이블에는 주문 된 제품의 **productid** 만 포함 되어 있으므로 **OrderDetails** 은 **ProductName**을 반환 하기 위해 **productid** 를 사용 하는 **제품과** 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-112">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="b78e7-113">이 관계에서 **Products** 테이블은 부모이 고 **Order Details** 테이블은 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-113">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="b78e7-114">결과적으로 **OrderDetails** 테이블을 반복 하는 경우 **GetParentRow** 를 호출 하 여 관련 된 **ProductName** 값을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-114">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="b78e7-115">**Customers** 및 **Orders** 테이블에 대해 **DataRelation** 을 만들 때 **createConstraints** 플래그에 대해 값이 지정 되지 않습니다 (기본값은 **true**임).</span><span class="sxs-lookup"><span data-stu-id="b78e7-115">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="b78e7-116">여기서는 **Orders** 테이블의 모든 행에 부모 **Customers** 테이블에 있는 **CustomerID** 값이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-116">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="b78e7-117">**Customers** 테이블에 존재 하지 않는 **CustomerID** 가 **Orders** 테이블에 있는 경우 <xref:System.Data.ForeignKeyConstraint> 하면 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-117">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="b78e7-118">자식 열에 부모 열에 포함 되지 않은 값이 포함 되어 있을 경우 **DataRelation**을 추가할 때 **createConstraints** 플래그를 **false** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-118">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="b78e7-119">이 예에서는 **Orders** 테이블과 **OrderDetails** 테이블 간의 **DataRelation** 에 대해 **createConstraints** 플래그가 **false** 로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-119">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="b78e7-120">이를 통해 응용 프로그램은 **OrderDetails** 테이블의 모든 레코드를 반환할 수 있으며 런타임 예외를 생성 하지 않고 **Orders** 테이블의 레코드 하위 집합만 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-120">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="b78e7-121">확장된 예제는 다음과 같은 형식의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-121">The expanded sample generates output in the following format.</span></span>  
  
```output  
Customer ID: NORTS  
  Order ID: 10517  
        Order Date: 4/24/1997 12:00:00 AM  
           Product: Filo Mix  
          Quantity: 6  
           Product: Raclette Courdavault  
          Quantity: 4  
           Product: Outback Lager  
          Quantity: 6  
  Order ID: 11057  
        Order Date: 4/29/1998 12:00:00 AM  
           Product: Outback Lager  
          Quantity: 3  
```  
  
 <span data-ttu-id="b78e7-122">다음 코드 예는 **OrderDetails** 및 **Products** 테이블의 값이 반환 되 고 반환 되는 **Orders** 테이블에 있는 레코드의 하위 집합만 포함 된 확장 된 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="b78e7-122">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b78e7-123">참조</span><span class="sxs-lookup"><span data-stu-id="b78e7-123">See also</span></span>

- [<span data-ttu-id="b78e7-124">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="b78e7-124">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b78e7-125">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="b78e7-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
