---
description: '자세한 정보: DataTable 스키마 정의'
title: DataTable 스키마 정의
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: b1a48c8a129607dc8d683aa4735ea0e86ed32cc2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99652616"
---
# <a name="datatable-schema-definition"></a><span data-ttu-id="400e1-103">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="400e1-103">DataTable Schema Definition</span></span>

<span data-ttu-id="400e1-104">테이블의 스키마나 구조는 열이나 제약 조건에 의해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-104">The schema, or structure, of a table is represented by columns and constraints.</span></span> <span data-ttu-id="400e1-105"><xref:System.Data.DataTable>의 스키마는 <xref:System.Data.DataColumn> 개체를 비롯하여 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint> 개체를 사용하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-105">You define the schema of a <xref:System.Data.DataTable> using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="400e1-106">테이블 열은 데이터 소스 열에 매핑될 수 있습니다. 또한 이 열은 식에서 계산된 값을 포함하며 값을 자동으로 증가시키고 기본 키 값을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-106">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="400e1-107">테이블의 열, 관계 및 제약 조건을 이름에 따라 참조하는 경우 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-107">References by name to columns, relations, and constraints in a table are case-sensitive.</span></span> <span data-ttu-id="400e1-108">따라서 이름이 동일한 열, 관계 또는 제약 조건이 테이블에 두 개 이상 존재할 수 있지만, 대/소문자는 다르게 표기됩니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-108">Two or more columns, relations, or constraints can therefore exist in a table that have the same name, but that differ in case.</span></span> <span data-ttu-id="400e1-109">예를 들어 **col1** 및 **col1** 을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-109">For example, you can have **Col1** and **col1**.</span></span> <span data-ttu-id="400e1-110">이러한 경우 이름에 따라 열을 참조하려면 열 이름의 대/소문자가 정확하게 일치해야 하며, 그렇지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-110">In such as case, a reference to one of the columns by name must match the case of the column name exactly; otherwise an exception is thrown.</span></span> <span data-ttu-id="400e1-111">예를 들어 테이블 **myTable** 이 **col1** 및 **col1** 열을 포함 하는 경우 이름으로 이름으로 **col1** **. Columns ["col1"]**, **col1** 은 **mytable ["col1"]** 으로 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-111">For example, if the table **myTable** contains the columns **Col1** and **col1**, you would reference **Col1** by name as **myTable.Columns["Col1"]**, and **col1** as **myTable.Columns["col1"]**.</span></span> <span data-ttu-id="400e1-112">열 중 하나를 **myTable. columns ["COL1"]** 로 참조 하려고 하면 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-112">Attempting to reference either of the columns as **myTable.Columns["COL1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="400e1-113">특정 이름의 열, 관계 또는 제약 조건이 하나만 있으면 대/소문자 구분 규칙이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-113">The case-sensitivity rule does not apply if only one column, relation, or constraint  with a particular name exists.</span></span> <span data-ttu-id="400e1-114">즉, 테이블에 있는 기타 열, 관계 또는 제약 조건 개체의 이름이 특정한 열, 관계 또는 제약 조건 개체의 이름과 일치하지 않더라도 이름에 따라 대/소문자 구분 없이 해당 개체를 참조할 수 있으며, 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-114">That is, if no other column, relation, or constraint object in the table matches the name of that particular column, relation, or constraint object, you may reference the object by name using any case, and no exception is thrown.</span></span> <span data-ttu-id="400e1-115">예를 들어 테이블에 **Col1** 만 있는 경우 my를 사용 하 여 참조할 수 있습니다 **. 열 ["COL1"]**.</span><span class="sxs-lookup"><span data-stu-id="400e1-115">For example, if the table has only **Col1**, you can reference it using **my.Columns["COL1"]**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="400e1-116"><xref:System.Data.DataTable.CaseSensitive%2A> **DataTable** 의 속성은이 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-116">The <xref:System.Data.DataTable.CaseSensitive%2A> property of the **DataTable** does not affect this behavior.</span></span> <span data-ttu-id="400e1-117">**CaseSensitive** 속성은 테이블의 데이터에 적용 되며 정렬, 검색, 필터링, 제약 조건 적용 등에 영향을 주지만 열, 관계 및 제약 조건에 대 한 참조에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-117">The **CaseSensitive** property applies to the data in a table and affects sorting, searching, filtering, enforcing constraints, and so on, but not to references to the columns, relations, and constraints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="400e1-118">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="400e1-118">In This Section</span></span>  

 [<span data-ttu-id="400e1-119">DataTable에 열 추가</span><span class="sxs-lookup"><span data-stu-id="400e1-119">Adding Columns to a DataTable</span></span>](adding-columns-to-a-datatable.md)  
 <span data-ttu-id="400e1-120">**DataColumn** 개체를 사용 하 여 테이블의 열을 정의 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-120">Describes how to define the columns of a table using **DataColumn** objects.</span></span>  
  
 [<span data-ttu-id="400e1-121">식 열 만들기</span><span class="sxs-lookup"><span data-stu-id="400e1-121">Creating Expression Columns</span></span>](creating-expression-columns.md)  
 <span data-ttu-id="400e1-122">열의 **식** 속성을 사용 하 여 행의 다른 열 값을 기준으로 값을 계산 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-122">Explains how the **Expression** property of a column can be used to calculate values based on the values from other columns in the row.</span></span>  
  
 [<span data-ttu-id="400e1-123">AutoIncrement 열 만들기</span><span class="sxs-lookup"><span data-stu-id="400e1-123">Creating AutoIncrement Columns</span></span>](creating-autoincrement-columns.md)  
 <span data-ttu-id="400e1-124">숫자 값을 자동으로 증가시켜 행마다 열 값이 고유하도록 열을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-124">Describes how a column can be set to automatically increment numerical values to ensure a unique column value per row.</span></span>  
  
 [<span data-ttu-id="400e1-125">기본 키 정의</span><span class="sxs-lookup"><span data-stu-id="400e1-125">Defining Primary Keys</span></span>](defining-primary-keys.md)  
 <span data-ttu-id="400e1-126">하나 이상의 **DataColumn** 개체에서 테이블의 기본 키를 지정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-126">Describes how to specify the primary key of a table from one or more **DataColumn** objects.</span></span>  
  
 [<span data-ttu-id="400e1-127">DataTable 제약 조건</span><span class="sxs-lookup"><span data-stu-id="400e1-127">DataTable Constraints</span></span>](datatable-constraints.md)  
 <span data-ttu-id="400e1-128">테이블에서 열의 외래 키와 UNIQUE 제약 조건을 정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="400e1-128">Describes how to define foreign key and unique constraints for columns in a table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="400e1-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="400e1-129">See also</span></span>

- [<span data-ttu-id="400e1-130">DataTables</span><span class="sxs-lookup"><span data-stu-id="400e1-130">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="400e1-131">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="400e1-131">ADO.NET Overview</span></span>](../ado-net-overview.md)
