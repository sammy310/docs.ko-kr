---
title: Null 값 처리
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f18b288f-b265-4bbe-957f-c6833c0645ef
ms.openlocfilehash: c45c6672983866df6c47ec84981cc7bd11637c0c
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249079"
---
# <a name="handling-null-values"></a><span data-ttu-id="d7488-102">Null 값 처리</span><span class="sxs-lookup"><span data-stu-id="d7488-102">Handling Null Values</span></span>
<span data-ttu-id="d7488-103">관계형 데이터베이스에서 null 값은 열 값을 알 수 없거나 값이 누락된 경우에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-103">A null value in a relational database is used when the value in a column is unknown or missing.</span></span> <span data-ttu-id="d7488-104">Null은 빈 문자열(문자 또는 날짜/시간 데이터 형식의 경우)도 아니고 0 값(숫자 데이터 형식의 경우)도 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-104">A null is neither an empty string (for character or datetime data types) nor a zero value (for numeric data types).</span></span> <span data-ttu-id="d7488-105">ANSI SQL-92 사양에서는 모든 null이 일관되게 처리되도록 null이 모든 데이터 형식에 대해 동일해야 함을 명시합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-105">The ANSI SQL-92 specification states that a null must be the same for all data types, so that all nulls are handled consistently.</span></span> <span data-ttu-id="d7488-106"><xref:System.Data.SqlTypes> 네임스페이스는 <xref:System.Data.SqlTypes.INullable> 인터페이스를 구현하여 null 의미 체계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-106">The <xref:System.Data.SqlTypes> namespace provides null semantics by implementing the <xref:System.Data.SqlTypes.INullable> interface.</span></span> <span data-ttu-id="d7488-107"><xref:System.Data.SqlTypes>의 각 데이터 형식에는 해당 데이터 형식의 인스턴스에 할당할 수 있는 고유한 `IsNull` 속성과 `Null` 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-107">Each of the data types in <xref:System.Data.SqlTypes> has its own `IsNull` property and a `Null` value that can be assigned to an instance of that data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7488-108">.NET Framework 버전 2.0에서는 nullable 값 형식에 대한 지원을 도입하여 프로그래머가 기본 형식의 모든 값을 나타내도록 값 형식을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-108">The .NET Framework version 2.0 introduced support for nullable value types, which allow programmers to extend a value type to represent all values of the underlying type.</span></span> <span data-ttu-id="d7488-109">이러한 CLR nullable 값 형식은 <xref:System.Nullable> 구조의 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-109">These CLR nullable value types represent an instance of the <xref:System.Nullable> structure.</span></span> <span data-ttu-id="d7488-110">이 기능은 값 형식이 boxed 및 unboxed인 경우에 특히 유용하며 개체 유형과의 호환성을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-110">This capability is especially useful when value types are boxed and unboxed, providing enhanced compatibility with object types.</span></span> <span data-ttu-id="d7488-111">CLR nullable 값 형식은 ANSI SQL null이 `null` 참조(또는 `Nothing` Visual Basic)와 동일한 방식으로 작동하지 않기 때문에 데이터베이스 null을 저장하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-111">CLR nullable value types are not intended for storage of database nulls because an ANSI SQL null does not behave the same way as a `null` reference (or `Nothing` in Visual Basic).</span></span> <span data-ttu-id="d7488-112">데이터베이스 ANSI SQL null 값에 대한 작업을 수행하려면 <xref:System.Nullable> 대신 <xref:System.Data.SqlTypes> null을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-112">For working with database ANSI SQL null values, use <xref:System.Data.SqlTypes> nulls rather than <xref:System.Nullable>.</span></span> <span data-ttu-id="d7488-113">시각적 기본에서 CLR 값 nullable 형식작업에 대한 자세한 내용은 [Nullable 값 형식을](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)참조하고 C#에 대한 [Nullable 값 형식을](../../../../csharp/language-reference/builtin-types/nullable-value-types.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d7488-113">For more information on working with CLR value nullable types in Visual Basic see [Nullable Value Types](../../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md), and for C# see [Nullable value types](../../../../csharp/language-reference/builtin-types/nullable-value-types.md).</span></span>  
  
## <a name="nulls-and-three-valued-logic"></a><span data-ttu-id="d7488-114">Null과 3중값 논리</span><span class="sxs-lookup"><span data-stu-id="d7488-114">Nulls and Three-Valued Logic</span></span>  
 <span data-ttu-id="d7488-115">열 정의에 null 값을 허용하면 애플리케이션에 값이 3치 논리가 도입됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-115">Allowing null values in column definitions introduces three-valued logic into your application.</span></span> <span data-ttu-id="d7488-116">비교는 다음 세 가지 조건 중 하나로 평가될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-116">A comparison can evaluate to one of three conditions:</span></span>  
  
- <span data-ttu-id="d7488-117">True</span><span class="sxs-lookup"><span data-stu-id="d7488-117">True</span></span>  
  
- <span data-ttu-id="d7488-118">False</span><span class="sxs-lookup"><span data-stu-id="d7488-118">False</span></span>  
  
- <span data-ttu-id="d7488-119">알 수 없음</span><span class="sxs-lookup"><span data-stu-id="d7488-119">Unknown</span></span>  
  
 <span data-ttu-id="d7488-120">Null은 unknown으로 간주되기 때문에 서로 비교되는 두 null 값은 동일한 것으로 간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-120">Because null is considered to be unknown, two null values compared to each other are not considered to be equal.</span></span> <span data-ttu-id="d7488-121">산술 연산자를 사용하는 식에서 피연산자 중 하나라도 null이면 결과도 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-121">In expressions using arithmetic operators, if any of the operands is null, the result is null as well.</span></span>  
  
## <a name="nulls-and-sqlboolean"></a><span data-ttu-id="d7488-122">Null 및 SqlBoolean</span><span class="sxs-lookup"><span data-stu-id="d7488-122">Nulls and SqlBoolean</span></span>  
 <span data-ttu-id="d7488-123"><xref:System.Data.SqlTypes> 간 비교는 <xref:System.Data.SqlTypes.SqlBoolean>을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-123">Comparison between any <xref:System.Data.SqlTypes> will return a <xref:System.Data.SqlTypes.SqlBoolean>.</span></span> <span data-ttu-id="d7488-124">각 `SqlType`에 대한 `IsNull` 함수는 <xref:System.Data.SqlTypes.SqlBoolean>을 반환하며 null 값을 확인하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-124">The `IsNull` function for each `SqlType` returns a <xref:System.Data.SqlTypes.SqlBoolean> and can be used to check for null values.</span></span> <span data-ttu-id="d7488-125">다음 진리표에서는 null 값이 있는 경우 AND, OR 및 NOT 연산자가 작동하는 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-125">The following truth tables show how the AND, OR, and NOT operators function in the presence of a null value.</span></span> <span data-ttu-id="d7488-126">(T=true, F=false, U=unknown 또는 null)</span><span class="sxs-lookup"><span data-stu-id="d7488-126">(T=true, F=false, and U=unknown, or null.)</span></span>  
  
 <span data-ttu-id="d7488-127">![진리표](./media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")</span><span class="sxs-lookup"><span data-stu-id="d7488-127">![Truth Table](./media/truthtable-bpuedev11.gif "TruthTable_bpuedev11")</span></span>  
  
### <a name="understanding-the-ansi_nulls-option"></a><span data-ttu-id="d7488-128">ANSI_NULLS 옵션 이해</span><span class="sxs-lookup"><span data-stu-id="d7488-128">Understanding the ANSI_NULLS Option</span></span>  
 <span data-ttu-id="d7488-129"><xref:System.Data.SqlTypes>는 SQL Server에서 ANSI_NULLS 옵션이 on으로 설정된 경우와 동일한 의미 체계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-129"><xref:System.Data.SqlTypes> provides the same semantics as when the ANSI_NULLS option is set on in SQL Server.</span></span> <span data-ttu-id="d7488-130">모든 산술 연산자 (+, \*-, , -, /, %), \|bitwise 연산자 (~, &,) 및 대부분의 함수는 속성을 `IsNull`제외한 피연산자 또는 인수 중 어느 것이 null인 경우 null을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-130">All arithmetic operators (+, -, \*, /, %), bitwise operators (~, &, \|), and most functions return null if any of the operands or arguments is null, except for the property `IsNull`.</span></span>  
  
 <span data-ttu-id="d7488-131">ANSI SQL-92 표준에서는 WHERE 절에서 *columnName* = NULL을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-131">The ANSI SQL-92 standard does not support *columnName* = NULL in a WHERE clause.</span></span> <span data-ttu-id="d7488-132">SQL Server에서 ANSI_NULLS 옵션은 데이터베이스의 기본 null 허용 여부와 null 값에 대한 비교 평가를 모두 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-132">In SQL Server, the ANSI_NULLS option controls both default nullability in the database and evaluation of comparisons against null values.</span></span> <span data-ttu-id="d7488-133">ANSI_NULLS이 설정된 경우(기본값) null 값을 테스트할 때 식에서 IS NULL 연산자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-133">If ANSI_NULLS is turned on (the default), the IS NULL operator must be used in expressions when testing for null values.</span></span> <span data-ttu-id="d7488-134">예를 들어 ANSI_NULLS가 on이면 다음 비교 결과는 항상 unknown이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-134">For example, the following comparison always yields unknown when ANSI_NULLS is on:</span></span>  
  
```sql
colname > NULL  
```  
  
 <span data-ttu-id="d7488-135">Null 값을 포함하는 변수와 비교하면 unknown도 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-135">Comparison to a variable containing a null value also yields unknown:</span></span>  
  
```sql
colname > @MyVariable  
```  
  
 <span data-ttu-id="d7488-136">IS NULL 또는 IS NOT NULL 조건자를 사용하여 null 값을 테스트하세요.</span><span class="sxs-lookup"><span data-stu-id="d7488-136">Use the IS NULL or IS NOT NULL predicate to test for a null value.</span></span> <span data-ttu-id="d7488-137">그렇게 하면 WHERE 절이 복잡해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-137">This can add complexity to the WHERE clause.</span></span> <span data-ttu-id="d7488-138">예를 들어 AdventureWorks Customer 테이블의 TerritoryID 열은 null 값을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-138">For example, the TerritoryID column in the AdventureWorks Customer table allows null values.</span></span> <span data-ttu-id="d7488-139">SELECT 문이 다른 값 이외에 Null 값을 테스트하는 경우 IS NULL 조건자가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-139">If a SELECT statement is to test for null values in addition to others, it must include an IS NULL predicate:</span></span>  
  
```sql
SELECT CustomerID, AccountNumber, TerritoryID  
FROM AdventureWorks.Sales.Customer  
WHERE TerritoryID IN (1, 2, 3)  
   OR TerritoryID IS NULL  
```  
  
 <span data-ttu-id="d7488-140">SQL Server에서 ANSI_NULLS를 off로 설정한 경우 같음 연산자를 사용하여 null과 비교하는 식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-140">If you set ANSI_NULLS off in SQL Server, you can create expressions that use the equality operator to compare to null.</span></span> <span data-ttu-id="d7488-141">그러나 다른 연결이 해당 연결에 null 옵션을 설정하는 것을 방지할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-141">However, you can't prevent different connections from setting null options for that connection.</span></span> <span data-ttu-id="d7488-142">연결에 대한 ANSI_NULLS 설정에 관계없이 null 값을 테스트하기 위해 IS NULL을 사용하는 것은 항상 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-142">Using IS NULL to test for null values always works, regardless of the ANSI_NULLS settings for a connection.</span></span>  
  
 <span data-ttu-id="d7488-143"><xref:System.Data.SqlTypes>에서 null 값을 처리하기 위해 항상 ANSI SQL-92 표준을 따르는 `DataSet`에서는 ANSI_NULLS를 off로 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-143">Setting ANSI_NULLS off is not supported in a `DataSet`, which always follows the ANSI SQL-92 standard for handling null values in <xref:System.Data.SqlTypes>.</span></span>  
  
## <a name="assigning-null-values"></a><span data-ttu-id="d7488-144">Null 값 할당</span><span class="sxs-lookup"><span data-stu-id="d7488-144">Assigning Null Values</span></span>  
 <span data-ttu-id="d7488-145">Null 값은 특수하며, 저장 및 할당 의미 체계가 다양한 형식 시스템 및 스토리지 시스템에서 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-145">Null values are special, and their storage and assignment semantics differ across different type systems and storage systems.</span></span> <span data-ttu-id="d7488-146">`Dataset`는 다양한 형식 및 스토리지 시스템에서 사용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-146">A `Dataset` is designed to be used with different type and storage systems.</span></span>  
  
 <span data-ttu-id="d7488-147">이 섹션에서는 다양한 형식 시스템에서 <xref:System.Data.DataRow>의 <xref:System.Data.DataColumn>에 null 값을 할당하기 위한 null 의미 체계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-147">This section describes the null semantics for assigning null values to a <xref:System.Data.DataColumn> in a <xref:System.Data.DataRow> across the different type systems.</span></span>  
  
 `DBNull.Value`  
 <span data-ttu-id="d7488-148">이 할당은 모든 형식의 `DataColumn`에 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-148">This assignment is valid for a `DataColumn` of any type.</span></span> <span data-ttu-id="d7488-149">형식이 `INullable`를 구현하는 경우 `DBNull.Value`는 적절한 강력한 형식의 Null 값으로 강제 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-149">If the type implements `INullable`, `DBNull.Value` is coerced into the appropriate strongly typed Null value.</span></span>  
  
 `SqlType.Null`  
 <span data-ttu-id="d7488-150">모든 <xref:System.Data.SqlTypes> 데이터 형식에서 `INullable`을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-150">All <xref:System.Data.SqlTypes> data types implement `INullable`.</span></span> <span data-ttu-id="d7488-151">암시적 캐스트 연산자를 사용하여 강력한 형식의 null 값을 열의 데이터 형식으로 변환할 수 있는 경우 할당이 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-151">If the strongly typed null value can be converted into the column's data type using implicit cast operators, the assignment should go through.</span></span> <span data-ttu-id="d7488-152">그렇지 않으면 잘못된 캐스트 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-152">Otherwise an invalid cast exception is thrown.</span></span>  
  
 `null`  
 <span data-ttu-id="d7488-153">'Null'이 지정된 `DataColumn` 데이터 형식에 올바른 값이면 `INullable` 형식(`SqlType.Null`)과 연결된 적절한 `DbNull.Value` 또는 `Null`으로 강제 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-153">If 'null' is a legal value for the given `DataColumn` data type, it is coerced into the appropriate `DbNull.Value` or `Null` associated with the `INullable` type (`SqlType.Null`)</span></span>  
  
 `derivedUdt.Null`  
 <span data-ttu-id="d7488-154">UDT 열의 경우 null은 항상 `DataColumn`과 연결된 형식에 따라 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-154">For UDT columns, nulls are always stored based on the type associated with the `DataColumn`.</span></span> <span data-ttu-id="d7488-155">`DataColumn`과 연결된 UDT가 `INullable`를 구현하지 않지만 하위 클래스는 구현하는 경우를 생각해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-155">Consider the case of a UDT associated with a `DataColumn` that does not implement `INullable` while its sub-class does.</span></span> <span data-ttu-id="d7488-156">이 경우 파생 클래스와 연결된 강력한 형식의 null 값이 할당되면 해당 값은 형식화되지 않은 `DbNull.Value`로 저장됩니다. Null 저장소는 항상 DataColumn의 데이터 형식과 일치하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-156">In this case, if a strongly typed null value associated with the derived class is assigned, it is stored as an untyped `DbNull.Value`, because null storage is always consistent with the DataColumn's data type.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7488-157">`Nullable<T>` 또는 <xref:System.Nullable> 구조체는 현재 `DataSet`에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-157">The `Nullable<T>` or <xref:System.Nullable> structure is not currently supported in the `DataSet`.</span></span>  
  
### <a name="multiple-column-row-assignment"></a><span data-ttu-id="d7488-158">여러 열(행) 할당</span><span class="sxs-lookup"><span data-stu-id="d7488-158">Multiple Column (Row) Assignment</span></span>  
 <span data-ttu-id="d7488-159">`DataTable.Add`, `DataTable.LoadDataRow`또는 행에 매핑되는 <xref:System.Data.DataRow.ItemArray%2A>를 수락하는 다른 API는 'null'을 DataColumn의 기본값에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-159">`DataTable.Add`, `DataTable.LoadDataRow`, or other APIs that accept an <xref:System.Data.DataRow.ItemArray%2A> that gets mapped to a row, map 'null' to the DataColumn's default value.</span></span> <span data-ttu-id="d7488-160">배열의 개체에 `DbNull.Value` 또는 강력한 형식의 상응하는 값이 포함된 경우 위에 설명한 것과 동일한 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-160">If an object in the array contains `DbNull.Value` or its strongly typed counterpart, the same rules as described above are applied.</span></span>  
  
 <span data-ttu-id="d7488-161">또한 `DataRow.["columnName"]` null 할당 인스턴스에 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-161">In addition, the following rules apply for an instance of `DataRow.["columnName"]` null assignments:</span></span>  
  
1. <span data-ttu-id="d7488-162">강력한 형식의 null 값이 적절한 강력한 형식의 null 열을 제외한 모든 열에서 기본 *default* 값은 `DbNull.Value`입니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-162">The default *default* value is `DbNull.Value` for all except the strongly typed null columns where it is the appropriate strongly typed null value.</span></span>  
  
2. <span data-ttu-id="d7488-163">"xsi:nil"에서처럼 XML 파일로 직렬화하는 동안에는 null 값이 작성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-163">Null values are never written out during serialization to XML files (as in "xsi:nil").</span></span>  
  
3. <span data-ttu-id="d7488-164">기본값을 포함하여 null이 아닌 모든 값은 항상 XML로 직렬화하는 동안 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-164">All non-null values, including defaults, are always written out while serializing to XML.</span></span> <span data-ttu-id="d7488-165">이는 null 값(xsi: nil)이 명시적이고 기본값이 암시적인(XML에 없는 경우 유효성 검사 파서가 연결된 XSD 스키마에서 가져올 수 있음) XSD/XML 의미 체계와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-165">This is unlike XSD/XML semantics where a null value (xsi:nil) is explicit and the default value is implicit (if not present in XML, a validating parser can get it from an associated XSD schema).</span></span> <span data-ttu-id="d7488-166">`DataTable`에서는 그 반대입니다. Null 값은 암시적이고 기본값은 명시적입니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-166">The opposite is true for a `DataTable`: a null value is implicit and the default value is explicit.</span></span>  
  
4. <span data-ttu-id="d7488-167">XML 입력에서 읽은 행에 대해 누락된 모든 열 값에는 NULL이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-167">All missing column values for rows read from XML input are assigned NULL.</span></span> <span data-ttu-id="d7488-168"><xref:System.Data.DataTable.NewRow%2A> 또는 유사한 메서드를 사용하여 만든 행에는 DataColumn의 기본값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-168">Rows created using <xref:System.Data.DataTable.NewRow%2A> or similar methods are assigned the DataColumn's default value.</span></span>  
  
5. <span data-ttu-id="d7488-169"><xref:System.Data.DataRow.IsNull%2A> 메서드는 `DbNull.Value` 및 `INullable.Null`에 대해 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-169">The <xref:System.Data.DataRow.IsNull%2A> method returns `true` for both `DbNull.Value` and `INullable.Null`.</span></span>  
  
## <a name="assigning-null-values"></a><span data-ttu-id="d7488-170">Null 값 할당</span><span class="sxs-lookup"><span data-stu-id="d7488-170">Assigning Null Values</span></span>  
 <span data-ttu-id="d7488-171"><xref:System.Data.SqlTypes> 인스턴스의 기본값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-171">The default value for any <xref:System.Data.SqlTypes> instance is null.</span></span>  
  
 <span data-ttu-id="d7488-172"><xref:System.Data.SqlTypes>의 null은 형식에 따라 달라지며 `DbNull`과 같은 단일 값으로 나타낼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-172">Nulls in <xref:System.Data.SqlTypes> are type-specific and cannot be represented by a single value, such as `DbNull`.</span></span> <span data-ttu-id="d7488-173">`IsNull` 속성을 사용하여 null을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-173">Use the `IsNull` property to check for nulls.</span></span>  
  
 <span data-ttu-id="d7488-174">다음 코드 예제와 같이 <xref:System.Data.DataColumn>에 null 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-174">Null values can be assigned to a <xref:System.Data.DataColumn> as shown in the following code example.</span></span> <span data-ttu-id="d7488-175">예외를 트리거하지 않고 `SqlTypes` 변수에 null 값을 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-175">You can directly assign null values to `SqlTypes` variables without triggering an exception.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d7488-176">예제</span><span class="sxs-lookup"><span data-stu-id="d7488-176">Example</span></span>  
 <span data-ttu-id="d7488-177">다음 코드 예제에서는 <xref:System.Data.SqlTypes.SqlInt32> 및 <xref:System.Data.SqlTypes.SqlString>으로 정의된 두 개의 열이 있는 <xref:System.Data.DataTable>을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-177">The following code example creates a <xref:System.Data.DataTable> with two columns defined as <xref:System.Data.SqlTypes.SqlInt32> and <xref:System.Data.SqlTypes.SqlString>.</span></span> <span data-ttu-id="d7488-178">이 코드는 알려진 값의 행과 null 값의 행을 하나씩 추가하고 <xref:System.Data.DataTable>을 반복하여 변수에 값을 할당하고 콘솔 창에 출력을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-178">The code adds one row of known values, one row of null values and then iterates through the <xref:System.Data.DataTable>, assigning the values to variables and displaying the output in the console window.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.IsNull#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.IsNull/VB/source.vb#1)]  
  
 <span data-ttu-id="d7488-179">이 예제에서 표시되는 결과는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-179">This example displays the following results:</span></span>  
  
```output
isColumnNull=False, ID=123, Description=Side Mirror  
isColumnNull=True, ID=Null, Description=Null  
```  
  
## <a name="comparing-null-values-with-sqltypes-and-clr-types"></a><span data-ttu-id="d7488-180">SqlTypes 및 CLR 형식을 사용하여 Null 값 비교</span><span class="sxs-lookup"><span data-stu-id="d7488-180">Comparing Null Values with SqlTypes and CLR Types</span></span>  
 <span data-ttu-id="d7488-181">Null 값을 비교할 때 `Equals` 메서드가 CLR 형식에서 작동하는 방식과 비교하여 <xref:System.Data.SqlTypes>에서 null 값을 평가하는 방법 간의 차이점을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-181">When comparing null values, it is important to understand the difference between the way the `Equals` method evaluates null values in <xref:System.Data.SqlTypes> as compared with the way it works with CLR types.</span></span> <span data-ttu-id="d7488-182">모든 <xref:System.Data.SqlTypes>`Equals` 메서드는 null 값을 평가하는 데 데이터베이스 의미 체계를 사용합니다. 두 값 중 하나 또는 둘 다 null이면 비교가 null을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-182">All of the <xref:System.Data.SqlTypes>`Equals` methods use database semantics for evaluating null values: if either or both of the values is null, the comparison yields null.</span></span> <span data-ttu-id="d7488-183">반면에 두 <xref:System.Data.SqlTypes>에서 CLR `Equals` 메서드를 사용하면 둘 다 null인 경우 true가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-183">On the other hand, using the CLR `Equals` method on two <xref:System.Data.SqlTypes> will yield true if both are null.</span></span> <span data-ttu-id="d7488-184">이는 CLR `String.Equals` 메서드와 같은 인스턴스 메서드를 사용하는 경우와 정적/공유 메서드 `SqlString.Equals`를 사용하는 경우의 차이점을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-184">This reflects the difference between using an instance method such as the CLR `String.Equals` method, and using the static/shared method, `SqlString.Equals`.</span></span>  
  
 <span data-ttu-id="d7488-185">다음 예제에서는 각각에 null 값 쌍이 전달된 후 빈 문자열 쌍이 전달될 때 `SqlString.Equals` 메서드와 `String.Equals` 메서드 간의 결과 차이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-185">The following example demonstrates the difference in results between the `SqlString.Equals` method and the `String.Equals` method when each is passed a pair of null values and then a pair of empty strings.</span></span>  
  
 [!code-csharp[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.CompareNulls#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.CompareNulls/VB/source.vb#1)]  
  
 <span data-ttu-id="d7488-186">이 코드는 다음 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d7488-186">The code produces the following output:</span></span>  
  
```output
SqlString.Equals shared/static method:  
  Two nulls=Null  
  
String.Equals instance method:  
  Two nulls=True  
  
SqlString.Equals shared/static method:  
  Two empty strings=True  
  
String.Equals instance method:  
  Two empty strings=True
```  
  
## <a name="see-also"></a><span data-ttu-id="d7488-187">참조</span><span class="sxs-lookup"><span data-stu-id="d7488-187">See also</span></span>

- [<span data-ttu-id="d7488-188">SQL Server 데이터 형식 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d7488-188">SQL Server Data Types and ADO.NET</span></span>](sql-server-data-types.md)
- [<span data-ttu-id="d7488-189">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="d7488-189">ADO.NET Overview</span></span>](../ado-net-overview.md)
