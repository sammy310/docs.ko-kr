---
description: '다음에 대 한 자세한 정보: DataTable 제약 조건'
title: DataTable 제약 조건
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 27c9f2fd-f64d-4b4e-bbf6-1d24f47067cb
ms.openlocfilehash: 0c712115fd87fefae3578b2f3fc0adfc416f412e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724910"
---
# <a name="datatable-constraints"></a><span data-ttu-id="fa881-103">DataTable 제약 조건</span><span class="sxs-lookup"><span data-stu-id="fa881-103">DataTable Constraints</span></span>

<span data-ttu-id="fa881-104">제약 조건을 사용하여 <xref:System.Data.DataTable>의 데이터를 제한함으로써 데이터 무결성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-104">You can use constraints to enforce restrictions on the data in a <xref:System.Data.DataTable>, in order to maintain the integrity of the data.</span></span> <span data-ttu-id="fa881-105">제약 조건은 자동 규칙이기 때문에 행 값이 조금이라도 변경되면 열 또는 관련 열에 적용되어 작업 과정을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-105">A constraint is an automatic rule, applied to a column or related columns, that determines the course of action when the value of a row is somehow altered.</span></span> <span data-ttu-id="fa881-106">`System.Data.DataSet.EnforceConstraints`의 속성이 <xref:System.Data.DataSet> **true 이면** 제약 조건이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-106">Constraints are enforced when the `System.Data.DataSet.EnforceConstraints` property of the <xref:System.Data.DataSet> is **true**.</span></span> <span data-ttu-id="fa881-107">`EnforceConstraints` 속성을 설정하는 방법을 보여 주는 코드 예제는 <xref:System.Data.DataSet.EnforceConstraints%2A> 참조 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fa881-107">For a code example that shows how to set the `EnforceConstraints` property, see the <xref:System.Data.DataSet.EnforceConstraints%2A> reference topic.</span></span>  
  
 <span data-ttu-id="fa881-108">ADO.NET에는 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint>의 두 가지 제약 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-108">There are two kinds of constraints in ADO.NET: the <xref:System.Data.ForeignKeyConstraint> and the <xref:System.Data.UniqueConstraint>.</span></span> <span data-ttu-id="fa881-109">기본적으로 두 제약 조건은 둘 이상의 테이블 간에 관계를 만들 때 <xref:System.Data.DataRelation> **데이터 집합** 에를 추가 하 여 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-109">By default, both constraints are created automatically when you create a relationship between two or more tables by adding a <xref:System.Data.DataRelation> to the **DataSet**.</span></span> <span data-ttu-id="fa881-110">그러나 관계를 만들 때 **createConstraints**  =  **false** 를 지정 하 여이 동작을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-110">However, you can disable this behavior by specifying **createConstraints** = **false** when creating the relation.</span></span>  
  
## <a name="foreignkeyconstraint"></a><span data-ttu-id="fa881-111">ForeignKeyConstraint</span><span class="sxs-lookup"><span data-stu-id="fa881-111">ForeignKeyConstraint</span></span>  

 <span data-ttu-id="fa881-112">**ForeignKeyConstraint** 는 관련 테이블에 대 한 업데이트 및 삭제를 전파 하는 방법에 대 한 규칙을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-112">A **ForeignKeyConstraint** enforces rules about how updates and deletes to related tables are propagated.</span></span> <span data-ttu-id="fa881-113">예를 들어 한 테이블의 행에 있는 값이 업데이트 되거나 삭제 되 고 동일한 값이 하나 이상의 관련 테이블에도 사용 되는 경우 **ForeignKeyConstraint** 는 관련 테이블에서 발생 하는 작업을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-113">For example, if a value in a row of one table is updated or deleted, and that same value is also used in one or more related tables, a **ForeignKeyConstraint** determines what happens in the related tables.</span></span>  
  
 <span data-ttu-id="fa881-114"><xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> **ForeignKeyConstraint** 의 및 속성은 사용자가 관련 테이블의 행을 삭제 하거나 업데이트 하려고 할 때 수행할 동작을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-114">The <xref:System.Data.ForeignKeyConstraint.DeleteRule%2A> and <xref:System.Data.ForeignKeyConstraint.UpdateRule%2A> properties of the **ForeignKeyConstraint** define the action to be taken when the user attempts to delete or update a row in a related table.</span></span> <span data-ttu-id="fa881-115">다음 표에서는 **ForeignKeyConstraint** 의 **DeleteRule** 및 **UpdateRule** 속성에 사용할 수 있는 다양 한 설정을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-115">The following table describes the different settings available for the **DeleteRule** and **UpdateRule** properties of the **ForeignKeyConstraint**.</span></span>  
  
|<span data-ttu-id="fa881-116">규칙 설정</span><span class="sxs-lookup"><span data-stu-id="fa881-116">Rule setting</span></span>|<span data-ttu-id="fa881-117">설명</span><span class="sxs-lookup"><span data-stu-id="fa881-117">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="fa881-118">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="fa881-118">**Cascade**</span></span>|<span data-ttu-id="fa881-119">관련 행을 삭제하거나 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-119">Delete or update related rows.</span></span>|  
|<span data-ttu-id="fa881-120">**SetNull**</span><span class="sxs-lookup"><span data-stu-id="fa881-120">**SetNull**</span></span>|<span data-ttu-id="fa881-121">관련 행의 값을 **DBNull** 로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-121">Set values in related rows to **DBNull**.</span></span>|  
|<span data-ttu-id="fa881-122">**SetDefault**</span><span class="sxs-lookup"><span data-stu-id="fa881-122">**SetDefault**</span></span>|<span data-ttu-id="fa881-123">관련 행의 값을 기본값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-123">Set values in related rows to the default value.</span></span>|  
|<span data-ttu-id="fa881-124">**없음**</span><span class="sxs-lookup"><span data-stu-id="fa881-124">**None**</span></span>|<span data-ttu-id="fa881-125">관련 행에 대해 아무 동작도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-125">Take no action on related rows.</span></span> <span data-ttu-id="fa881-126">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-126">This is the default.</span></span>|  
  
 <span data-ttu-id="fa881-127">**ForeignKeyConstraint** 는 관련 열에 대 한 변경 내용을 전파 하 고 전파를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-127">A **ForeignKeyConstraint** can restrict, as well as propagate, changes to related columns.</span></span> <span data-ttu-id="fa881-128">열의 **ForeignKeyConstraint** 설정 된 속성에 따라, **DataSet** 의 **EnforceConstraints** 속성이 **true** 이면 부모 행에 대해 특정 작업을 수행 하면 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-128">Depending on the properties set for the **ForeignKeyConstraint** of a column, if the **EnforceConstraints** property of the **DataSet** is **true**, performing certain operations on the parent row will result in an exception.</span></span> <span data-ttu-id="fa881-129">예를 들어 **ForeignKeyConstraint** 의 **DeleteRule** 속성이 **None** 이면 부모 행에 자식 행이 있는 경우 해당 행을 삭제할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-129">For example, if the **DeleteRule** property of the **ForeignKeyConstraint** is **None**, a parent row cannot be deleted if it has any child rows.</span></span>  
  
 <span data-ttu-id="fa881-130">**ForeignKeyConstraint** 생성자를 사용 하 여 단일 열 또는 열 배열 사이에서 foreign key 제약 조건을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-130">You can create a foreign key constraint between single columns or between an array of columns by using the **ForeignKeyConstraint** constructor.</span></span> <span data-ttu-id="fa881-131">결과 **ForeignKeyConstraint** 개체를 테이블의 **제약 조건** 속성 ( **ConstraintCollection**)의 **Add** 메서드에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-131">Pass the resulting **ForeignKeyConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="fa881-132">**ConstraintCollection** 의 **Add** 메서드의 여러 오버 로드에 생성자 인수를 전달 하 여 **ForeignKeyConstraint** 를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-132">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **ForeignKeyConstraint**.</span></span>  
  
 <span data-ttu-id="fa881-133">**ForeignKeyConstraint** 를 만들 때 **DeleteRule** 및 **UpdateRule** 값을 생성자에 인수로 전달 하거나 다음 예제와 같이 속성으로 설정할 수 있습니다 ( **DeleteRule** 값이 **None** 으로 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="fa881-133">When creating a **ForeignKeyConstraint**, you can pass the **DeleteRule** and **UpdateRule** values to the constructor as arguments, or you can set them as properties as in the following example (where the **DeleteRule** value is set to **None**).</span></span>  
  
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
  
### <a name="acceptrejectrule"></a><span data-ttu-id="fa881-134">AcceptRejectRule</span><span class="sxs-lookup"><span data-stu-id="fa881-134">AcceptRejectRule</span></span>  

 <span data-ttu-id="fa881-135">행에 대 한 변경 내용은 **AcceptChanges** 메서드를 사용 하 여 수락 하거나 **DataSet**, **DataTable** 또는 **DataRow** 의 **RejectChanges** 메서드를 사용 하 여 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-135">Changes to rows can be accepted using the **AcceptChanges** method or canceled using the **RejectChanges** method of the **DataSet**, **DataTable**, or **DataRow**.</span></span> <span data-ttu-id="fa881-136">**데이터 집합** 에 **ForeignKeyConstraints** 포함 된 경우 **AcceptChanges** 또는 **RejectChanges** 메서드를 호출 하면 **AcceptRejectRule** 가 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-136">When a **DataSet** contains **ForeignKeyConstraints**, invoking the **AcceptChanges** or **RejectChanges** methods enforces the **AcceptRejectRule**.</span></span> <span data-ttu-id="fa881-137">**ForeignKeyConstraint** 의 **AcceptRejectRule** 속성은 부모 행에서 **AcceptChanges** 또는 **RejectChanges** 가 호출 될 때 자식 행에 대해 수행할 동작을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-137">The **AcceptRejectRule** property of the **ForeignKeyConstraint** determines which action will be taken on the child rows when **AcceptChanges** or **RejectChanges** is called on the parent row.</span></span>  
  
 <span data-ttu-id="fa881-138">다음 표에서는 **AcceptRejectRule** 에 사용할 수 있는 설정을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-138">The following table lists the available settings for the **AcceptRejectRule**.</span></span>  
  
|<span data-ttu-id="fa881-139">규칙 설정</span><span class="sxs-lookup"><span data-stu-id="fa881-139">Rule setting</span></span>|<span data-ttu-id="fa881-140">설명</span><span class="sxs-lookup"><span data-stu-id="fa881-140">Description</span></span>|  
|------------------|-----------------|  
|<span data-ttu-id="fa881-141">**Cascade**</span><span class="sxs-lookup"><span data-stu-id="fa881-141">**Cascade**</span></span>|<span data-ttu-id="fa881-142">자식 행의 변경을 승인하거나 거부합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-142">Accept or reject changes to child rows.</span></span>|  
|<span data-ttu-id="fa881-143">**없음**</span><span class="sxs-lookup"><span data-stu-id="fa881-143">**None**</span></span>|<span data-ttu-id="fa881-144">자식 행에 대해 아무 동작도 수행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-144">Take no action on child rows.</span></span> <span data-ttu-id="fa881-145">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-145">This is the default.</span></span>|  
  
### <a name="example"></a><span data-ttu-id="fa881-146">예제</span><span class="sxs-lookup"><span data-stu-id="fa881-146">Example</span></span>  

 <span data-ttu-id="fa881-147">다음 예제에서는<xref:System.Data.ForeignKeyConstraint>를 만들고 <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>을 비롯한 해당 속성을 몇 가지 설정한 다음 <xref:System.Data.ConstraintCollection> 개체의 <xref:System.Data.DataTable>에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-147">The following example creates a <xref:System.Data.ForeignKeyConstraint>, sets several of its properties, including the <xref:System.Data.ForeignKeyConstraint.AcceptRejectRule%2A>, and adds it to the <xref:System.Data.ConstraintCollection> of a <xref:System.Data.DataTable> object.</span></span>  
  
 [!code-csharp[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/CS/source.cs#1)]
 [!code-vb[DataWorks Data.AcceptRejectRule#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks Data.AcceptRejectRule/VB/source.vb#1)]  
  
## <a name="uniqueconstraint"></a><span data-ttu-id="fa881-148">UniqueConstraint</span><span class="sxs-lookup"><span data-stu-id="fa881-148">UniqueConstraint</span></span>  

 <span data-ttu-id="fa881-149">**UniqueConstraint** 개체는 **DataTable** 의 단일 열 또는 열 배열에 할당할 수 있습니다 .이 개체는 지정 된 열에 있는 모든 데이터가 행 마다 고유 하 게 유지 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-149">The **UniqueConstraint** object, which can be assigned either to a single column or to an array of columns in a **DataTable**, ensures that all data in the specified column or columns is unique per row.</span></span> <span data-ttu-id="fa881-150">**UniqueConstraint** 생성자를 사용 하 여 열 또는 열 배열에 대 한 unique 제약 조건을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-150">You can create a unique constraint for a column or array of columns by using the **UniqueConstraint** constructor.</span></span> <span data-ttu-id="fa881-151">결과 **UniqueConstraint** 개체를 테이블의 **제약 조건** 속성 ( **ConstraintCollection**)의 **Add** 메서드에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-151">Pass the resulting **UniqueConstraint** object to the **Add** method of the table's **Constraints** property, which is a **ConstraintCollection**.</span></span> <span data-ttu-id="fa881-152">**ConstraintCollection** 의 **Add** 메서드의 여러 오버 로드에 생성자 인수를 전달 하 여 **UniqueConstraint** 를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-152">You can also pass constructor arguments to several overloads of the **Add** method of a **ConstraintCollection** to create a **UniqueConstraint**.</span></span> <span data-ttu-id="fa881-153">열 하나 이상의 열에 대 한 **UniqueConstraint** 를 만들 때 필요에 따라 열이 기본 키인지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-153">When creating a **UniqueConstraint** for a column or columns, you can optionally specify whether the column or columns are a primary key.</span></span>  
  
 <span data-ttu-id="fa881-154">열의 **unique** 속성을 **true** 로 설정 하 여 열에 대 한 unique 제약 조건을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-154">You can also create a unique constraint for a column by setting the **Unique** property of the column to **true**.</span></span> <span data-ttu-id="fa881-155">또는 단일 열의 **unique** 속성을 **false** 로 설정 하면 존재할 수 있는 unique 제약 조건이 모두 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-155">Alternatively, setting the **Unique** property of a single column to **false** removes any unique constraint that may exist.</span></span> <span data-ttu-id="fa881-156">하나 이상의 열을 테이블의 기본 키로 정의하면 지정한 열에 대한 UNIQUE 제약 조건이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-156">Defining a column or columns as the primary key for a table will automatically create a unique constraint for the specified column or columns.</span></span> <span data-ttu-id="fa881-157">**DataTable** 의 **PrimaryKey** 속성에서 열을 제거 하면 **UniqueConstraint** 이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-157">If you remove a column from the **PrimaryKey** property of a **DataTable**, the **UniqueConstraint** is removed.</span></span>  
  
 <span data-ttu-id="fa881-158">다음 예에서는 **DataTable** 의 두 열에 대해 **UniqueConstraint** 를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa881-158">The following example creates a **UniqueConstraint** for two columns of a **DataTable**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fa881-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa881-159">See also</span></span>

- <xref:System.Data.DataRelation>
- <xref:System.Data.DataTable>
- <xref:System.Data.ForeignKeyConstraint>
- <xref:System.Data.UniqueConstraint>
- [<span data-ttu-id="fa881-160">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="fa881-160">DataTable Schema Definition</span></span>](datatable-schema-definition.md)
- [<span data-ttu-id="fa881-161">DataSets, DataTables 및 DataViews</span><span class="sxs-lookup"><span data-stu-id="fa881-161">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="fa881-162">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="fa881-162">ADO.NET Overview</span></span>](../ado-net-overview.md)
