---
title: DataRelation 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 9cefc97e571f315a6a644e0a058d4283168ecb9f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199364"
---
# <a name="adding-datarelations"></a><span data-ttu-id="ae558-102">DataRelation 추가</span><span class="sxs-lookup"><span data-stu-id="ae558-102">Adding DataRelations</span></span>
<span data-ttu-id="ae558-103">여러 <xref:System.Data.DataSet> 개체가 포함된 <xref:System.Data.DataTable>에서는 <xref:System.Data.DataRelation> 개체를 사용하여 하나의 테이블을 다른 테이블에 연관시키거나, 테이블 사이를 탐색하거나, 연관된 테이블의 자식 또는 부모 행을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae558-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="ae558-104">만드는 데 필요한 인수를 **DataRelation** 에 대 한 이름과 합니다 **DataRelation** 생성 되 고 하나 이상의 배열 <xref:System.Data.DataColumn> 부모 및 자식으로 작동 하는 열에 대 한 참조 관계의 열입니다.</span><span class="sxs-lookup"><span data-stu-id="ae558-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="ae558-105">만든 후에 **DataRelation**, 테이블 사이 탐색 하 고 값을 검색 하려면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae558-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="ae558-106">추가 **DataRelation** 에 <xref:System.Data.DataSet> 기본적으로 추가 <xref:System.Data.UniqueConstraint> 부모 테이블에 및 <xref:System.Data.ForeignKeyConstraint> 자식 테이블에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae558-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="ae558-107">이러한 기본 제약 조건에 대 한 자세한 내용은 참조 하세요. [DataTable 제약 조건](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ae558-107">For more information about these default constraints, see [DataTable Constraints](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="ae558-108">다음 코드 예제는 **DataRelation** 2를 사용 하 여 <xref:System.Data.DataTable> 개체를 <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="ae558-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ae558-109">각 <xref:System.Data.DataTable> 라는 열이 포함 되어 **CustID**, 둘 사이의 링크로 작동 하는 <xref:System.Data.DataTable> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ae558-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="ae558-110">이 예제에서는 단일 추가 **DataRelation** 에 **관계** 의 컬렉션을 <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="ae558-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="ae558-111">예제에서 첫 번째 인수의 이름을 지정 합니다 **DataRelation** 만들어지는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae558-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="ae558-112">부모를 설정 하는 두 번째 인수 **DataColumn** 세 번째 인수 설정 자식 **DataColumn**합니다.</span><span class="sxs-lookup"><span data-stu-id="ae558-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
```vb  
customerOrders.Relations.Add("CustOrders", _  
  customerOrders.Tables("Customers").Columns("CustID"), _  
  customerOrders.Tables("Orders").Columns("CustID"))  
```  
  
```csharp  
customerOrders.Relations.Add("CustOrders",  
  customerOrders.Tables["Customers"].Columns["CustID"],  
  customerOrders.Tables["Orders"].Columns["CustID"]);  
```  
  
 <span data-ttu-id="ae558-113">**DataRelation** 역시를 **중첩** 속성을로 설정 하면 **true**을 부모 테이블의 관련된 행 내에서 중첩 된 자식 테이블에서 행을 사용 하면 사용 하 여 XML 요소로 작성할 경우 <xref:System.Data.DataSet.WriteXml%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae558-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="ae558-114">자세한 내용은 [데이터 세트에서 XML 사용](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae558-114">For more information, see [Using XML in a DataSet](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae558-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae558-115">See also</span></span>

- [<span data-ttu-id="ae558-116">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="ae558-116">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="ae558-117">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="ae558-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
