---
title: DataRelation 추가
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a4a564fb-c1c4-4135-b6c2-b030e51195e4
ms.openlocfilehash: 5fe2bd45e0abada1f9ec7071e3863da853479b51
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202385"
---
# <a name="adding-datarelations"></a><span data-ttu-id="173cf-102">DataRelation 추가</span><span class="sxs-lookup"><span data-stu-id="173cf-102">Adding DataRelations</span></span>

<span data-ttu-id="173cf-103">여러 <xref:System.Data.DataSet> 개체가 포함된 <xref:System.Data.DataTable>에서는 <xref:System.Data.DataRelation> 개체를 사용하여 하나의 테이블을 다른 테이블에 연관시키거나, 테이블 사이를 탐색하거나, 연관된 테이블의 자식 또는 부모 행을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="173cf-103">In a <xref:System.Data.DataSet> with multiple <xref:System.Data.DataTable> objects, you can use <xref:System.Data.DataRelation> objects to relate one table to another, to navigate through the tables, and to return child or parent rows from a related table.</span></span>  
  
 <span data-ttu-id="173cf-104">**Datarelation** 을 만드는 데 필요한 인수는 만들어지는 **datarelation** 의 이름과 <xref:System.Data.DataColumn> 관계의 부모 및 자식 열로 사용 되는 열에 대 한 하나 이상의 참조의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="173cf-104">The arguments required to create a **DataRelation** are a name for the **DataRelation** being created, and an array of one or more <xref:System.Data.DataColumn> references to the columns that serve as the parent and child columns in the relationship.</span></span> <span data-ttu-id="173cf-105">**DataRelation**을 만든 후에는이를 사용 하 여 테이블 간에 이동 하 고 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="173cf-105">After you have created a **DataRelation**, you can use it to navigate between tables and to retrieve values.</span></span>  
  
 <span data-ttu-id="173cf-106">**DataRelation** 을에 추가 하면 <xref:System.Data.DataSet> 기본적으로 <xref:System.Data.UniqueConstraint> 부모 테이블 및에 대 한가 <xref:System.Data.ForeignKeyConstraint> 자식 테이블에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="173cf-106">Adding a **DataRelation** to a <xref:System.Data.DataSet> adds, by default, a <xref:System.Data.UniqueConstraint> to the parent table and a <xref:System.Data.ForeignKeyConstraint> to the child table.</span></span> <span data-ttu-id="173cf-107">이러한 기본 제약 조건에 대 한 자세한 내용은 [DataTable 제약 조건](datatable-constraints.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="173cf-107">For more information about these default constraints, see [DataTable Constraints](datatable-constraints.md).</span></span>  
  
 <span data-ttu-id="173cf-108">다음 코드 예제에서는에 두 개의 개체를 사용 하 여 **DataRelation** 을 만듭니다 <xref:System.Data.DataTable> <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="173cf-108">The following code example creates a **DataRelation** using two <xref:System.Data.DataTable> objects in a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="173cf-109">각에는 <xref:System.Data.DataTable> 두 개체 간의 링크 역할을 하는 **CustID**라는 열이 포함 되어 있습니다 <xref:System.Data.DataTable> .</span><span class="sxs-lookup"><span data-stu-id="173cf-109">Each <xref:System.Data.DataTable> contains a column named **CustID**, which serves as a link between the two <xref:System.Data.DataTable> objects.</span></span> <span data-ttu-id="173cf-110">이 예에서는 단일 **DataRelation** 을의 **관계** 컬렉션에 추가 합니다 <xref:System.Data.DataSet> .</span><span class="sxs-lookup"><span data-stu-id="173cf-110">The example adds a single **DataRelation** to the **Relations** collection of the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="173cf-111">예제의 첫 번째 인수는 만들 **DataRelation** 의 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="173cf-111">The first argument in the example specifies the name of the **DataRelation** being created.</span></span> <span data-ttu-id="173cf-112">두 번째 인수는 부모 **datacolumn** 을 설정 하 고 세 번째 인수는 자식 **datacolumn**을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="173cf-112">The second argument sets the parent **DataColumn** and the third argument sets the child **DataColumn**.</span></span>  
  
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
  
 <span data-ttu-id="173cf-113">또한 **DataRelation** 에는 **중첩** 된 속성이 있습니다 .이 속성을 **true**로 설정 하면를 사용 하 여 XML 요소로 작성 될 때 자식 테이블의 행이 부모 테이블의 연결 된 행 내에 중첩 됩니다 <xref:System.Data.DataSet.WriteXml%2A> .</span><span class="sxs-lookup"><span data-stu-id="173cf-113">A **DataRelation** also has a **Nested** property which, when set to **true**, causes the rows from the child table to be nested within the associated row from the parent table when written as XML elements using <xref:System.Data.DataSet.WriteXml%2A> .</span></span> <span data-ttu-id="173cf-114">자세한 내용은 [데이터 세트에서 XML 사용](using-xml-in-a-dataset.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="173cf-114">For more information, see [Using XML in a DataSet](using-xml-in-a-dataset.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="173cf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="173cf-115">See also</span></span>

- [<span data-ttu-id="173cf-116">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="173cf-116">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="173cf-117">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="173cf-117">ADO.NET Overview</span></span>](../ado-net-overview.md)
