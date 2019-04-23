---
title: DataRelation 탐색
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5e673f4-9b44-45ae-aaea-c504d1cc5d3e
ms.openlocfilehash: f4dfccad23bf5d15f5cbd0a33e76a136417e13ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59204161"
---
# <a name="navigating-datarelations"></a><span data-ttu-id="c35d7-102">DataRelation 탐색</span><span class="sxs-lookup"><span data-stu-id="c35d7-102">Navigating DataRelations</span></span>
<span data-ttu-id="c35d7-103"><xref:System.Data.DataRelation>의 기본 기능 중 하나는 <xref:System.Data.DataTable> 내에서 <xref:System.Data.DataSet>를 하나씩 탐색할 수 있도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-103">One of the primary functions of a <xref:System.Data.DataRelation> is to allow navigation from one <xref:System.Data.DataTable> to another within a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c35d7-104">이 모두를 검색할 수 있습니다 관련 <xref:System.Data.DataRow> 개체를 **DataTable** 단일 주어 지 면 **DataRow** 연관 **DataTable**합니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-104">This allows you to retrieve all the related <xref:System.Data.DataRow> objects in one **DataTable** when given a single **DataRow** from a related **DataTable**.</span></span> <span data-ttu-id="c35d7-105">예를 들어, 설정한 후에 **DataRelation** 고객 테이블 사이의 orders 테이블을 사용 하 여 특정 고객 행에 대 한 모든 주문 행을 검색할 수 있습니다 **GetChildRows**.</span><span class="sxs-lookup"><span data-stu-id="c35d7-105">For example, after establishing a **DataRelation** between a table of customers and a table of orders, you can retrieve all the order rows for a particular customer row using **GetChildRows**.</span></span>  
  
 <span data-ttu-id="c35d7-106">다음 코드 예제에서는 **DataRelation** 간에 **고객** 테이블 및 **주문** 목차를 **데이터 집합** 반환 각 고객에 대 한 모든 주문</span><span class="sxs-lookup"><span data-stu-id="c35d7-106">The following code example creates a **DataRelation** between the **Customers** table and the **Orders** table of a **DataSet** and returns all the orders for each customer.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableRelation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableRelation/VB/source.vb#1)]  
  
 <span data-ttu-id="c35d7-107">다음 예제에서는 이전 예제를 기반으로 네 개의 테이블을 모두 연관시키고 각각의 관계를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-107">The next example builds on the preceding example, relating four tables together and navigating those relationships.</span></span> <span data-ttu-id="c35d7-108">이전 예에서 같이 **CustomerID** 관련를 **고객** 테이블의 **주문** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-108">As in the previous example, **CustomerID** relates the **Customers** table to the **Orders** table.</span></span> <span data-ttu-id="c35d7-109">각 고객에 대 한 합니다 **고객** 테이블의 모든 자식 행의 **주문** 특정 고객 주문의 수를 반환 하기 위해 테이블 결정 됩니다 및 해당 **OrderID** 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-109">For each customer in the **Customers** table, all the child rows in the **Orders** table are determined, in order to return the number of orders a particular customer has and their **OrderID** values.</span></span>  
  
 <span data-ttu-id="c35d7-110">확장 된 예제는 또한에서 값을 반환 합니다 **OrderDetails** 하 고 **제품** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-110">The expanded example also returns the values from the **OrderDetails** and **Products** tables.</span></span> <span data-ttu-id="c35d7-111">**주문을** 테이블이 관련 되어 합니다 **OrderDetails** 사용 하 여 테이블 **OrderID** 각각에 대해 주문 된 고객 주문, 어떤 제품 및 수량을 확인 하려면.</span><span class="sxs-lookup"><span data-stu-id="c35d7-111">The **Orders** table is related to the **OrderDetails** table using **OrderID** to determine, for each customer order, what products and quantities were ordered.</span></span> <span data-ttu-id="c35d7-112">때문에 합니다 **OrderDetails** 만 표에 합니다 **ProductID** 는 주문 된 제품의 **OrderDetails** 관련이 **제품** 사용 하 여 **ProductID** 반환 하기 위해 합니다 **ProductName**합니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-112">Because the **OrderDetails** table only contains the **ProductID** of an ordered product, **OrderDetails** is related to **Products** using **ProductID** in order to return the **ProductName**.</span></span> <span data-ttu-id="c35d7-113">이 관계는 **제품** 테이블은 부모 및 **Order Details** 테이블은 자식입니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-113">In this relation, the **Products** table is the parent and the **Order Details** table is the child.</span></span> <span data-ttu-id="c35d7-114">결과적으로 반복할 때 합니다 **OrderDetails** 테이블 **GetParentRow** 관련 된 검색을 위해 호출 **ProductName** 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-114">As a result, when iterating through the **OrderDetails** table, **GetParentRow** is called to retrieve the related **ProductName** value.</span></span>  
  
 <span data-ttu-id="c35d7-115">때 합니다 **DataRelation** 만들어집니다는 **고객** 및 **주문** 테이블에 대 한 지정 된 값을 **createConstraints**플래그 (기본값은 **true**).</span><span class="sxs-lookup"><span data-stu-id="c35d7-115">Notice that when the **DataRelation** is created for the **Customers** and **Orders** tables, no value is specified for the **createConstraints** flag (the default is **true**).</span></span> <span data-ttu-id="c35d7-116">이 가정의 행을 **주문** 테이블을 **CustomerID** 부모에 존재 하는 값 **고객** 테이블.</span><span class="sxs-lookup"><span data-stu-id="c35d7-116">This assumes that all the rows in the **Orders** table have a **CustomerID** value that exists in the parent **Customers** table.</span></span> <span data-ttu-id="c35d7-117">경우는 **CustomerID** 있는 **주문** 테이블에 존재 하지 않는 **고객** 테이블을 <xref:System.Data.ForeignKeyConstraint> 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-117">If a **CustomerID** exists in the **Orders** table that does not exist in the **Customers** table, a <xref:System.Data.ForeignKeyConstraint> causes an exception to be thrown.</span></span>  
  
 <span data-ttu-id="c35d7-118">자식 열에는 부모 열 없는 값을 포함할 수를 설정 합니다 **createConstraints** 플래그를 **false** 추가 하는 경우는 **DataRelation**합니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-118">When the child column might contain values that the parent column does not contain, set the **createConstraints** flag to **false** when adding the **DataRelation**.</span></span> <span data-ttu-id="c35d7-119">예에서는 **createConstraints** 플래그가로 설정 됩니다 **false** 에 대 한를 **DataRelation** 간에 **주문** 테이블과 합니다  **OrderDetails** 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-119">In the example, the **createConstraints** flag is set to **false** for the **DataRelation** between the **Orders** table and the **OrderDetails** table.</span></span> <span data-ttu-id="c35d7-120">이 통해 응용 프로그램에서 모든 레코드를 반환 하는 **OrderDetails** 테이블과 레코드의 하위 집합만 합니다 **주문** 런타임 예외를 생성 하지 않고 테이블.</span><span class="sxs-lookup"><span data-stu-id="c35d7-120">This enables the application to return all the records from the **OrderDetails** table and only a subset of records from the **Orders** table without generating a run-time exception.</span></span> <span data-ttu-id="c35d7-121">확장된 예제는 다음과 같은 형식의 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-121">The expanded sample generates output in the following format.</span></span>  
  
```  
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
  
 <span data-ttu-id="c35d7-122">다음 코드 예제는 확장 된 샘플은 위치 값을 **OrderDetails** 및 **제품** 테이블에서 레코드의 하위 집합만 반환 됩니다는 **주문**반환 되는 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="c35d7-122">The following code example is an expanded sample where the values from the **OrderDetails** and **Products** tables are returned, with only a subset of the records in the **Orders** table being returned.</span></span>  
  
 [!code-csharp[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/CS/source.cs#1)]
 [!code-vb[DataWorks Data.DataTableNavigation#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.DataTableNavigation/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c35d7-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="c35d7-123">See also</span></span>

- [<span data-ttu-id="c35d7-124">DataSet, DataTable 및 DataView</span><span class="sxs-lookup"><span data-stu-id="c35d7-124">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="c35d7-125">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="c35d7-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
