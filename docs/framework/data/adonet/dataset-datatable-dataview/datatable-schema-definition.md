---
title: DataTable 스키마 정의
ms.date: 03/30/2017
ms.assetid: efbcdda4-f5a9-421d-8be2-4c194c74552f
ms.openlocfilehash: 0c14c6012c65039e1e2e7e2d2d8c38c4202b45a7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153250"
---
# <a name="datatable-schema-definition"></a><span data-ttu-id="baac5-102">DataTable 스키마 정의</span><span class="sxs-lookup"><span data-stu-id="baac5-102">DataTable Schema Definition</span></span>

<span data-ttu-id="baac5-103">테이블의 스키마나 구조는 열이나 제약 조건에 의해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-103">The schema, or structure, of a table is represented by columns and constraints.</span></span> <span data-ttu-id="baac5-104"><xref:System.Data.DataTable>의 스키마는 <xref:System.Data.DataColumn> 개체를 비롯하여 <xref:System.Data.ForeignKeyConstraint> 및 <xref:System.Data.UniqueConstraint> 개체를 사용하여 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-104">You define the schema of a <xref:System.Data.DataTable> using <xref:System.Data.DataColumn> objects as well as <xref:System.Data.ForeignKeyConstraint> and <xref:System.Data.UniqueConstraint> objects.</span></span> <span data-ttu-id="baac5-105">테이블 열은 데이터 소스 열에 매핑될 수 있습니다. 또한 이 열은 식에서 계산된 값을 포함하며 값을 자동으로 증가시키고 기본 키 값을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-105">The columns in a table can map to columns in a data source, contain calculated values from expressions, automatically increment their values, or contain primary key values.</span></span>  
  
 <span data-ttu-id="baac5-106">테이블의 열, 관계 및 제약 조건을 이름에 따라 참조하는 경우 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-106">References by name to columns, relations, and constraints in a table are case-sensitive.</span></span> <span data-ttu-id="baac5-107">따라서 이름이 동일한 열, 관계 또는 제약 조건이 테이블에 두 개 이상 존재할 수 있지만, 대/소문자는 다르게 표기됩니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-107">Two or more columns, relations, or constraints can therefore exist in a table that have the same name, but that differ in case.</span></span> <span data-ttu-id="baac5-108">예를 들어 **col1** 및 **col1**을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-108">For example, you can have **Col1** and **col1**.</span></span> <span data-ttu-id="baac5-109">이러한 경우 이름에 따라 열을 참조하려면 열 이름의 대/소문자가 정확하게 일치해야 하며, 그렇지 않으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-109">In such as case, a reference to one of the columns by name must match the case of the column name exactly; otherwise an exception is thrown.</span></span> <span data-ttu-id="baac5-110">예를 들어 테이블 **myTable** 이 **col1** 및 **col1**열을 포함 하는 경우 이름으로 이름으로 **col1** **. Columns ["col1"]**, **col1** 은 **mytable ["col1"]** 으로 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-110">For example, if the table **myTable** contains the columns **Col1** and **col1**, you would reference **Col1** by name as **myTable.Columns["Col1"]**, and **col1** as **myTable.Columns["col1"]**.</span></span> <span data-ttu-id="baac5-111">열 중 하나를 **myTable. columns ["COL1"]** 로 참조 하려고 하면 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-111">Attempting to reference either of the columns as **myTable.Columns["COL1"]** would generate an exception.</span></span>  
  
 <span data-ttu-id="baac5-112">특정 이름의 열, 관계 또는 제약 조건이 하나만 있으면 대/소문자 구분 규칙이 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-112">The case-sensitivity rule does not apply if only one column, relation, or constraint  with a particular name exists.</span></span> <span data-ttu-id="baac5-113">즉, 테이블에 있는 기타 열, 관계 또는 제약 조건 개체의 이름이 특정한 열, 관계 또는 제약 조건 개체의 이름과 일치하지 않더라도 이름에 따라 대/소문자 구분 없이 해당 개체를 참조할 수 있으며, 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-113">That is, if no other column, relation, or constraint object in the table matches the name of that particular column, relation, or constraint object, you may reference the object by name using any case, and no exception is thrown.</span></span> <span data-ttu-id="baac5-114">예를 들어 테이블에 **Col1**만 있는 경우 my를 사용 하 여 참조할 수 있습니다 **. 열 ["COL1"]**.</span><span class="sxs-lookup"><span data-stu-id="baac5-114">For example, if the table has only **Col1**, you can reference it using **my.Columns["COL1"]**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="baac5-115"><xref:System.Data.DataTable.CaseSensitive%2A> **DataTable** 의 속성은이 동작에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-115">The <xref:System.Data.DataTable.CaseSensitive%2A> property of the **DataTable** does not affect this behavior.</span></span> <span data-ttu-id="baac5-116">**CaseSensitive** 속성은 테이블의 데이터에 적용 되며 정렬, 검색, 필터링, 제약 조건 적용 등에 영향을 주지만 열, 관계 및 제약 조건에 대 한 참조에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-116">The **CaseSensitive** property applies to the data in a table and affects sorting, searching, filtering, enforcing constraints, and so on, but not to references to the columns, relations, and constraints.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="baac5-117">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="baac5-117">In This Section</span></span>  

 [<span data-ttu-id="baac5-118">DataTable에 열 추가</span><span class="sxs-lookup"><span data-stu-id="baac5-118">Adding Columns to a DataTable</span></span>](adding-columns-to-a-datatable.md)  
 <span data-ttu-id="baac5-119">**DataColumn** 개체를 사용 하 여 테이블의 열을 정의 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-119">Describes how to define the columns of a table using **DataColumn** objects.</span></span>  
  
 [<span data-ttu-id="baac5-120">식 열 만들기</span><span class="sxs-lookup"><span data-stu-id="baac5-120">Creating Expression Columns</span></span>](creating-expression-columns.md)  
 <span data-ttu-id="baac5-121">열의 **식** 속성을 사용 하 여 행의 다른 열 값을 기준으로 값을 계산 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-121">Explains how the **Expression** property of a column can be used to calculate values based on the values from other columns in the row.</span></span>  
  
 [<span data-ttu-id="baac5-122">AutoIncrement 열 만들기</span><span class="sxs-lookup"><span data-stu-id="baac5-122">Creating AutoIncrement Columns</span></span>](creating-autoincrement-columns.md)  
 <span data-ttu-id="baac5-123">숫자 값을 자동으로 증가시켜 행마다 열 값이 고유하도록 열을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-123">Describes how a column can be set to automatically increment numerical values to ensure a unique column value per row.</span></span>  
  
 [<span data-ttu-id="baac5-124">기본 키 정의</span><span class="sxs-lookup"><span data-stu-id="baac5-124">Defining Primary Keys</span></span>](defining-primary-keys.md)  
 <span data-ttu-id="baac5-125">하나 이상의 **DataColumn** 개체에서 테이블의 기본 키를 지정 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-125">Describes how to specify the primary key of a table from one or more **DataColumn** objects.</span></span>  
  
 [<span data-ttu-id="baac5-126">DataTable 제약 조건</span><span class="sxs-lookup"><span data-stu-id="baac5-126">DataTable Constraints</span></span>](datatable-constraints.md)  
 <span data-ttu-id="baac5-127">테이블에서 열의 외래 키와 UNIQUE 제약 조건을 정의하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="baac5-127">Describes how to define foreign key and unique constraints for columns in a table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baac5-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="baac5-128">See also</span></span>

- [<span data-ttu-id="baac5-129">DataTables</span><span class="sxs-lookup"><span data-stu-id="baac5-129">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="baac5-130">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="baac5-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
