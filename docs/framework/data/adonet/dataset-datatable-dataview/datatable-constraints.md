---
title: DataTable 제약 조건
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 4b7972c281786a4e36d0e9c1e455776a293423ee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151288"
---
# <a name="datatable-constraints"></a><span data-ttu-id="ae857-102">DataTable 제약 조건</span><span class="sxs-lookup"><span data-stu-id="ae857-102">DataTable Constraints</span></span>
<span data-ttu-id="ae857-103">제약 조건을 사용하여 <xref:System.Data.DataTable>의 데이터를 제한함으로써 데이터 무결성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-103">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="ae857-104">제약 조건은 자동 규칙이기 때문에 행 값이 조금이라도 변경되면 열 또는 관련 열에 적용되어 작업 과정을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-104">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="ae857-105">구속조건은 의 `System.Data.DataSet.EnforceConstraints` <xref:System.Data.DataSet> 속성이 **true일**때 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-105">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="ae857-106">`EnforceConstraints` 속성을 설정하는 방법을 보여 주는 코드 예제는 <xref:System.Data.DataSet.EnforceConstraints%2A> 참조 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae857-106">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="ae857-107">ADO.NET에는 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint>의 두 가지 제약 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-107">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="ae857-108">기본적으로 두 제약 조건은 <xref:System.Data.DataRelation> **DataSet**에 a를 추가하여 두 개 이상의 테이블 간의 관계를 만들 때 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-108">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="ae857-109">그러나 관계를 만들**때** false **만들기를** = 지정하여 이 동작을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-109">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="ae857-110">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="ae857-110">ForeignKeyConstraint</span></span>  
 <span data-ttu-id="ae857-111">**ForeignKeyConstraint는** 관련 테이블에 대한 업데이트 및 삭제가 전파되는 방법에 대한 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-111">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="ae857-112">예를 들어 한 테이블의 행에 있는 값이 업데이트되거나 삭제되고 동일한 값이 하나 이상의 관련 테이블에서도 사용되는 경우 **ForeignKeyConstraint는** 관련 테이블에서 발생하는 일을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-112">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="ae857-113"><xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> **ForeignKeyConstraint의** 및 <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> 속성은 사용자가 관련 테이블에서 행을 삭제하거나 업데이트하려고 할 때 수행되는 작업을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-113">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="ae857-114">다음 표는 **ForeignKeyConstraint의** **DeleteRule** 및 **UpdateRule** 속성에 사용할 수 있는 다른 설정에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-114">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="ae857-115">규칙 설정</span><span class="sxs-lookup"><span data-stu-id="ae857-115">Rule setting</span></span>|<span data-ttu-id="ae857-116">Description</span><span class="sxs-lookup"><span data-stu-id="ae857-116">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="ae857-117">**캐스케이드**</span><span class="sxs-lookup"><span data-stu-id="ae857-117">**Cascade**</span></span>|<span data-ttu-id="ae857-118">관련 행을 삭제하거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-118">Delete or update related rows.</span></span>|  
|<span data-ttu-id="ae857-119">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="ae857-119">**SetNull**</span></span>|<span data-ttu-id="ae857-120">관련 행의 값을 **DBNull로**설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-120">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="ae857-121">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="ae857-121">**SetDefault**</span></span>|<span data-ttu-id="ae857-122">관련 행의 값을 기본값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-122">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="ae857-123">**없음**</span><span class="sxs-lookup"><span data-stu-id="ae857-123">**None**</span></span>|<span data-ttu-id="ae857-124">관련 행에 대해 아무 동작도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-124">Take no action on related rows.</span></span> <span data-ttu-id="ae857-125">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-125">This is the default.</span></span>|  
  
 <span data-ttu-id="ae857-126">**ForeignKeyConstraint는** 관련 열에 대한 변경 내용을 제한하고 전파할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-126">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="ae857-127">열의 **ForeignKeyConstraint에** 대해 설정된 속성에 따라 **DataSet의** **EnforceConstraints** 속성이 **true인**경우 부모 행에서 특정 작업을 수행하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-127">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="ae857-128">예를 들어 **ForeignKeyConstraint의** **DeleteRule** 속성이 **없음인**경우 하위 행이 있는 경우 부모 행을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-128">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="ae857-129">**ForeignKeyConstraint** 생성자사용으로 단일 열 간에 또는 열 배열 사이에 외래 키 제약 조건을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-129">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="ae857-130">결과 **ForeignKeyConstraint** 개체를 테이블의 **제약 조건** 속성의 **메서드 추가** **메서드에**전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-130">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="ae857-131">생성자 인수를 **제약 조건** 의 **Add** 메서드의 여러 오버로드에 전달하여 **ForeignKeyConstraint을**만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-131">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="ae857-132">**ForeignKeyConstraint를**만들 때 **DeleteRule** 및 **UpdateRule** 값을 생성자에게 인수로 전달하거나 다음 예제와 같이 속성으로 설정할 수 있습니다(DeleteRule 값이 **없음으로**설정된 경우). **DeleteRule**</span><span class="sxs-lookup"><span data-stu-id="ae857-132">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
```vb  
Dim custOrderFK As ForeignKeyConstraint = New ForeignKeyConstraint("CustOrderFK", _  
  custDS.Tables("CustTable").Columns("CustomerID"), _  
  custDS.Tables("OrdersTable").Columns("CustomerID"))  
custOrderFK.DeleteRule = Rule.None
' Cannot delete a customer value that has associated existing orders.  
custDS.Tables("OrdersTable").Constraints.Add(custOrderFK)  
```  
  
```csharp  
ForeignKeyConstraint custOrderFK = new ForeignKeyConstraint("CustOrderFK",  
  custDS.Tables["CustTable"].Columns["CustomerID"],
  custDS.Tables["OrdersTable"].Columns["CustomerID"]);  
custOrderFK.DeleteRule = Rule.None;
// Cannot delete a customer value that has associated existing orders.  
custDS.Tables["OrdersTable"].Constraints.Add(custOrderFK);  
```  
  
### <a name="acceptrejectrule"></a><span data-ttu-id="ae857-133">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="ae857-133">AcceptRejectRule</span></span>  
 <span data-ttu-id="ae857-134">행에 대한 변경 사항은 **AcceptChanges** 메서드를 사용하여 수락하거나 **DataSet,** **DataTable**또는 **DataRow**의 **RejectChanges** 메서드를 사용하여 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-134">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="ae857-135">데이터 **집합에** **외래키제약이**포함된 경우 **AcceptChanges** 또는 **RejectChanges** 메서드를 호출하면 **AcceptRejectRule**을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-135">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="ae857-136">**ForeignKeyConstraint의** **AcceptRejectRule** 속성은 부모 행에서 **AcceptChanges** 또는 **RejectChanges가** 호출될 때 자식 행에서 수행될 작업을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-136">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="ae857-137">다음 표에는 **AcceptRejectRule**에 사용할 수 있는 설정이 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-137">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="ae857-138">규칙 설정</span><span class="sxs-lookup"><span data-stu-id="ae857-138">Rule setting</span></span>|<span data-ttu-id="ae857-139">Description</span><span class="sxs-lookup"><span data-stu-id="ae857-139">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="ae857-140">**캐스케이드**</span><span class="sxs-lookup"><span data-stu-id="ae857-140">**Cascade**</span></span>|<span data-ttu-id="ae857-141">자식 행의 변경을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-141">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="ae857-142">**없음**</span><span class="sxs-lookup"><span data-stu-id="ae857-142">**None**</span></span>|<span data-ttu-id="ae857-143">자식 행에 대해 아무 동작도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-143">Take no action on child rows.</span></span> <span data-ttu-id="ae857-144">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-144">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="ae857-145">예제</span><span class="sxs-lookup"><span data-stu-id="ae857-145">Example</span></span>  
 <span data-ttu-id="ae857-146">다음 예제에서는<xref:System.Data.ForeignKeyConstraint>를 만들고 <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>을 비롯한 해당 속성을 몇 가지 설정한 다음 <xref:System.Data.ConstraintCollection> 개체의 <xref:System.Data.DataTable>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-146">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="ae857-147">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="ae857-147">UniqueConstraint</span></span>  
 <span data-ttu-id="ae857-148">단일 열또는 **DataTable의**열 배열에 할당할 수 있는 **UniqueConstraint** 개체는 지정된 열 또는 열의 모든 데이터가 행당 고유하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-148">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="ae857-149">**UniqueConstraint** 생성자 사용을 사용하여 열 또는 열 배열에 대해 고유한 제약 조건을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-149">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="ae857-150">결과 **고유 제약 조건** 개체를 테이블의 제약 **조건** 속성의 **메서드 추가** **메서드에**전달합니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-150">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="ae857-151">생성자 인수를 **ConstraintCollection의** **Add** 메서드의 여러 오버로드에 전달하여 **고유 제약 조건을**만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-151">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="ae857-152">열 또는 열에 대한 **고유 제약 조건을** 만들 때 열 또는 열이 기본 키인지 여부를 선택적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-152">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="ae857-153">열의 **고유** 속성을 **true로**설정하여 열에 대한 고유한 제약 조건을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-153">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="ae857-154">또는 단일 열의 **고유** 속성을 **false로** 설정하면 존재할 수 있는 고유한 제약 조건이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-154">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="ae857-155">하나 이상의 열을 테이블의 기본 키로 정의하면 지정한 열에 대한 UNIQUE 제약 조건이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-155">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="ae857-156">**DataTable의** **PrimaryKey** 속성에서 열을 제거하면 **고유 제약 조건이** 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-156">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="ae857-157">다음 예제는 **DataTable**의 두 열에 대해 **고유 제약 조건을** 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ae857-157">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custUnique As UniqueConstraint = _  
    New UniqueConstraint(New DataColumn()   {custTable.Columns("CustomerID"), _  
    custTable.Columns("CompanyName")})  
custDS.Tables("Customers").Constraints.Add(custUnique)  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
UniqueConstraint custUnique = new UniqueConstraint(new DataColumn[]
    {custTable.Columns["CustomerID"],
    custTable.Columns["CompanyName"]});  
custDS.Tables["Customers"].Constraints.Add(custUnique);  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae857-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae857-158">See also</span></span>

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [<span data-ttu-id="ae857-159">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="ae857-159">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="ae857-160">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="ae857-160">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="ae857-161">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="ae857-161">ADO.NET Overview</span></span>](../ado-net-overview.md)
