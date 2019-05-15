---
title: null 허용 연산자
description: 사용할 수 있는 null 허용 연산자에 알아봅니다는 F# 프로그래밍 언어입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 79165f35258b414624174153d2cd729b301cf389
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642088"
---
# <a name="nullable-operators"></a><span data-ttu-id="3f051-103">null 허용 연산자</span><span class="sxs-lookup"><span data-stu-id="3f051-103">Nullable Operators</span></span>

<span data-ttu-id="3f051-104">Null 허용 연산자는 nullable 산술 형식의 한쪽 또는 양쪽에서 작동 하는 이진 산술 또는 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-104">Nullable operators are binary arithmetic or comparison operators that work with nullable arithmetic types on one or both sides.</span></span> <span data-ttu-id="3f051-105">Nullable 형식에는 실제 값 대신 null을 허용 하는 데이터베이스와 같은 원본에서 데이터로 작업 하는 경우에 자주 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-105">Nullable types arise frequently when you work with data from sources such as databases that allow nulls in place of actual values.</span></span> <span data-ttu-id="3f051-106">Null 허용 연산자는 쿼리 식에 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-106">Nullable operators are used frequently in query expressions.</span></span> <span data-ttu-id="3f051-107">산술 및 비교에 대 한 null 허용 연산자 외에도 변환 연산자 nullable 형식 간의 변환에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-107">In addition to nullable operators for arithmetic and comparison, conversion operators can be used to convert between nullable types.</span></span> <span data-ttu-id="3f051-108">특정 쿼리 연산자의 nullable 버전 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-108">There are also nullable versions of certain query operators.</span></span>

## <a name="table-of-nullable-operators"></a><span data-ttu-id="3f051-109">Null 허용 연산자의 테이블</span><span class="sxs-lookup"><span data-stu-id="3f051-109">Table of Nullable Operators</span></span>

<span data-ttu-id="3f051-110">다음 표에 지원 되는 null 허용 연산자는 F# 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-110">The following table lists nullable operators supported in the F# language.</span></span>

|<span data-ttu-id="3f051-111">왼쪽에서 null을 허용</span><span class="sxs-lookup"><span data-stu-id="3f051-111">Nullable on left</span></span>|<span data-ttu-id="3f051-112">오른쪽에서 null을 허용</span><span class="sxs-lookup"><span data-stu-id="3f051-112">Nullable on right</span></span>|<span data-ttu-id="3f051-113">양쪽 null 허용</span><span class="sxs-lookup"><span data-stu-id="3f051-113">Both sides nullable</span></span>|
|---|---|---|
|[<span data-ttu-id="3f051-114">?>=</span><span class="sxs-lookup"><span data-stu-id="3f051-114">?>=</span></span>](https://msdn.microsoft.com/library/94d29e32-a204-4f60-a527-6b0af86268f3)|[<span data-ttu-id="3f051-115">>=?</span><span class="sxs-lookup"><span data-stu-id="3f051-115">>=?</span></span>](https://msdn.microsoft.com/library/0a255d8e-8cae-4160-ae61-243a5d96583f)|[<span data-ttu-id="3f051-116">?>=?</span><span class="sxs-lookup"><span data-stu-id="3f051-116">?>=?</span></span>](https://msdn.microsoft.com/library/3051a50f-d276-4c84-9d73-bf2efeddef94)|
|[<span data-ttu-id="3f051-117">?></span><span class="sxs-lookup"><span data-stu-id="3f051-117">?></span></span>](https://msdn.microsoft.com/library/62dc0021-1312-4ac3-be87-798b60b81bb6)|[<span data-ttu-id="3f051-118">>?</span><span class="sxs-lookup"><span data-stu-id="3f051-118">>?</span></span>](https://msdn.microsoft.com/library/0ad1284b-de48-4a04-83d8-b6f13c9c8936)|[<span data-ttu-id="3f051-119">?>?</span><span class="sxs-lookup"><span data-stu-id="3f051-119">?>?</span></span>](https://msdn.microsoft.com/library/dc18b6fa-30c4-47b0-9057-794439378a05)|
|[<span data-ttu-id="3f051-120">?<=</span><span class="sxs-lookup"><span data-stu-id="3f051-120">?<=</span></span>](https://msdn.microsoft.com/library/56fddf0a-e4ca-4891-a3be-fad1876be3b6)|[<span data-ttu-id="3f051-121"><=?</span><span class="sxs-lookup"><span data-stu-id="3f051-121"><=?</span></span>](https://msdn.microsoft.com/library/02454a0f-30ca-4e77-ad84-ee7837461804)|[<span data-ttu-id="3f051-122">?<=?</span><span class="sxs-lookup"><span data-stu-id="3f051-122">?<=?</span></span>](https://msdn.microsoft.com/library/5c37c28c-0b57-4da5-be11-5a123f7e8ee4)|
|[<span data-ttu-id="3f051-123">?<</span><span class="sxs-lookup"><span data-stu-id="3f051-123">?<</span></span>](https://msdn.microsoft.com/library/b71897f0-6e29-4c58-b0a7-a5bfa6f88917)|[<span data-ttu-id="3f051-124"><?</span><span class="sxs-lookup"><span data-stu-id="3f051-124"><?</span></span>](https://msdn.microsoft.com/library/be9ea40f-a67f-4e98-8067-a14046752e8b)|[<span data-ttu-id="3f051-125">?<?</span><span class="sxs-lookup"><span data-stu-id="3f051-125">?<?</span></span>](https://msdn.microsoft.com/library/6f1962c8-5605-468c-94ae-f379ae98e17d)|
|[<span data-ttu-id="3f051-126">?=</span><span class="sxs-lookup"><span data-stu-id="3f051-126">?=</span></span>](https://msdn.microsoft.com/library/5cdc8ff6-244b-49cf-9376-69ecf249fd7c)|[<span data-ttu-id="3f051-127">=?</span><span class="sxs-lookup"><span data-stu-id="3f051-127">=?</span></span>](https://msdn.microsoft.com/library/d2102894-6a51-475d-890a-735568c31f87)|[<span data-ttu-id="3f051-128">?=?</span><span class="sxs-lookup"><span data-stu-id="3f051-128">?=?</span></span>](https://msdn.microsoft.com/library/5f793f29-1084-4570-b1c1-17c1b7ef764b)|
|[<span data-ttu-id="3f051-129">?<></span><span class="sxs-lookup"><span data-stu-id="3f051-129">?<></span></span>](https://msdn.microsoft.com/library/3643a5a8-2ea5-4ad6-82c4-83927c3884a0)|[<span data-ttu-id="3f051-130"><>?</span><span class="sxs-lookup"><span data-stu-id="3f051-130"><>?</span></span>](https://msdn.microsoft.com/library/3179aace-70c4-4911-9258-619592214976)|[<span data-ttu-id="3f051-131">?<>?</span><span class="sxs-lookup"><span data-stu-id="3f051-131">?<>?</span></span>](https://msdn.microsoft.com/library/5da813d8-ee75-45b8-9ef4-146dcb6d394d)|
|[<span data-ttu-id="3f051-132">?+</span><span class="sxs-lookup"><span data-stu-id="3f051-132">?+</span></span>](https://msdn.microsoft.com/library/2e8ddd05-b3f3-41b3-9d73-938d9e540f3f)|[<span data-ttu-id="3f051-133">+?</span><span class="sxs-lookup"><span data-stu-id="3f051-133">+?</span></span>](https://msdn.microsoft.com/library/74772ea8-f010-493e-bdb5-ba347f2fd4f1)|[<span data-ttu-id="3f051-134">?+?</span><span class="sxs-lookup"><span data-stu-id="3f051-134">?+?</span></span>](https://msdn.microsoft.com/library/57f28137-0f42-43d2-92af-cad8c6c9d05f)|
|[<span data-ttu-id="3f051-135">?-</span><span class="sxs-lookup"><span data-stu-id="3f051-135">?-</span></span>](https://msdn.microsoft.com/library/f237a7a6-89f2-48b2-a2fe-f0b98a2bedc2)|[<span data-ttu-id="3f051-136">-?</span><span class="sxs-lookup"><span data-stu-id="3f051-136">-?</span></span>](https://msdn.microsoft.com/library/4a345c07-314a-48f1-b557-ce072583589c)|[<span data-ttu-id="3f051-137">?-?</span><span class="sxs-lookup"><span data-stu-id="3f051-137">?-?</span></span>](https://msdn.microsoft.com/library/e0024142-1d2a-4607-a39c-1eb1e86fa25a)|
|[<span data-ttu-id="3f051-138">?\*</span><span class="sxs-lookup"><span data-stu-id="3f051-138">?\*</span></span>](https://msdn.microsoft.com/library/519da708-5ad6-4075-9d74-d00441cd6078)|[<span data-ttu-id="3f051-139">\*?</span><span class="sxs-lookup"><span data-stu-id="3f051-139">\*?</span></span>](https://msdn.microsoft.com/library/04c47870-de7b-480d-98a0-f47593b4ffac)|[<span data-ttu-id="3f051-140">?\*?</span><span class="sxs-lookup"><span data-stu-id="3f051-140">?\*?</span></span>](https://msdn.microsoft.com/library/e57057ba-9c3a-40ec-8401-150c2b25f75b)|
|[<span data-ttu-id="3f051-141">?/</span><span class="sxs-lookup"><span data-stu-id="3f051-141">?/</span></span>](https://msdn.microsoft.com/library/add02a42-f556-40a7-a168-fbf2053322e3)|[<span data-ttu-id="3f051-142">/?</span><span class="sxs-lookup"><span data-stu-id="3f051-142">/?</span></span>](https://msdn.microsoft.com/library/1de07646-3778-476d-8c61-5d37495d463c)|[<span data-ttu-id="3f051-143">?/?</span><span class="sxs-lookup"><span data-stu-id="3f051-143">?/?</span></span>](https://msdn.microsoft.com/library/b17be0ac-bf98-4590-861d-a4dd6c6fa535)|
|[<span data-ttu-id="3f051-144">?%</span><span class="sxs-lookup"><span data-stu-id="3f051-144">?%</span></span>](https://msdn.microsoft.com/library/44297bba-1bd9-4ed2-a848-f1e1e598db87)|[<span data-ttu-id="3f051-145">%?</span><span class="sxs-lookup"><span data-stu-id="3f051-145">%?</span></span>](https://msdn.microsoft.com/library/a4c178e5-eec4-42e8-847f-90b24fc609fe)|[<span data-ttu-id="3f051-146">?%?</span><span class="sxs-lookup"><span data-stu-id="3f051-146">?%?</span></span>](https://msdn.microsoft.com/library/dd555f20-1be3-4b8d-81f1-bf1921e62fda)|

## <a name="remarks"></a><span data-ttu-id="3f051-147">설명</span><span class="sxs-lookup"><span data-stu-id="3f051-147">Remarks</span></span>

<span data-ttu-id="3f051-148">에 포함 된 null 허용 연산자는 [NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007) 네임 스페이스에는 모듈 [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-148">The nullable operators are included in the [NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007) module in the namespace [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d).</span></span> <span data-ttu-id="3f051-149">Null 허용 데이터의 형식이 `System.Nullable<'T>`합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-149">The type for nullable data is `System.Nullable<'T>`.</span></span>

<span data-ttu-id="3f051-150">쿼리 식의 null 허용 형식 값 대신 null을 허용 하는 데이터 원본에서 데이터를 선택할 때 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-150">In query expressions, nullable types arise when selecting data from a data source that allows nulls instead of values.</span></span> <span data-ttu-id="3f051-151">SQL Server 데이터베이스 테이블의 각 데이터 열에는 null 허용 되는지 여부를 나타내는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-151">In a SQL Server database, each data column in a table has an attribute that indicates whether nulls are allowed.</span></span> <span data-ttu-id="3f051-152">데이터베이스에서 반환 되는 데이터와 같은 기본 데이터 형식으로 표현할 수 없는 null을 포함할 수 있습니다 null 허용 되 면 `int`, `float`등입니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-152">If nulls are allowed, the data returned from the database can contain nulls that cannot be represented by a primitive data type such as `int`, `float`, and so on.</span></span> <span data-ttu-id="3f051-153">따라서 데이터로 반환 됩니다는 `System.Nullable<int>` of `int`, 및 `System.Nullable<float>` 대신 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-153">Therefore, the data is returned as a `System.Nullable<int>` instead of `int`, and `System.Nullable<float>` instead of `float`.</span></span> <span data-ttu-id="3f051-154">실제 값을 가져올 수 있습니다는 `System.Nullable<'T>` 개체를 사용 하 여는 `Value` 속성 수를 확인 하는 경우를 `System.Nullable<'T>` 호출 하 여 개체에 값을 `HasValue` 메서드.</span><span class="sxs-lookup"><span data-stu-id="3f051-154">The actual value can be obtained from a `System.Nullable<'T>` object by using the `Value` property, and you can determine if a `System.Nullable<'T>` object has a value by calling the `HasValue` method.</span></span> <span data-ttu-id="3f051-155">또 다른 유용한 방법은 `System.Nullable<'T>.GetValueOrDefault` 메서드 값 또는 적절 한 형식의 기본값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-155">Another useful method is the `System.Nullable<'T>.GetValueOrDefault` method, which allows you to get the value or a default value of the appropriate type.</span></span> <span data-ttu-id="3f051-156">기본값은 "0" 값을 0과 같은 형태의 0.0 또는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-156">The default value is some form of "zero" value, such as 0, 0.0, or `false`.</span></span>

<span data-ttu-id="3f051-157">Nullable 형식은 nullable이 아닌 기본 형식과 같은 일반적인 변환 연산자를 사용 하 여 변환 될 수 있습니다 `int` 또는 `float`합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-157">Nullable types may be converted to non-nullable primitive types using the usual conversion operators such as `int` or `float`.</span></span> <span data-ttu-id="3f051-158">Nullable 형식에 대 한 변환 연산자를 사용 하 여 다른 nullable 형식으로 null 허용 형식 간에 변환할 수 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-158">It is also possible to convert from one nullable type to another nullable type by using the conversion operators for nullable types.</span></span> <span data-ttu-id="3f051-159">적절 한 변환 연산자, 표준으로 동일한 이름을 갖지만 별도 모듈에 있는 합니다 [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e) 모듈에는 [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d) 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-159">The appropriate conversion operators have the same name as the standard ones, but they are in a separate module, the [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e) module in the [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d) namespace.</span></span> <span data-ttu-id="3f051-160">일반적으로 쿼리 식을 사용 하 여 작업할 때이 네임 스페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-160">Typically, you open this namespace when working with query expressions.</span></span> <span data-ttu-id="3f051-161">이 경우 접두사를 추가 하 여 nullable 변환 연산자를 사용할 수 있습니다 `Nullable.` 다음 코드에 표시 된 대로 적절 한 변환 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-161">In that case, you can use the nullable conversion operators by adding the prefix `Nullable.` to the appropriate conversion operator, as shown in the following code.</span></span>

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn "%f" (float nullableFloat)
```

<span data-ttu-id="3f051-162">출력은 `10.000000`입니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-162">The output is `10.000000`.</span></span>

<span data-ttu-id="3f051-163">Null 허용 데이터 필드에는 연산자와 같은 쿼리 `sumByNullable`, 쿼리 식에서 사용 하기 위해 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-163">Query operators on nullable data fields, such as `sumByNullable`, also exist for use in query expressions.</span></span> <span data-ttu-id="3f051-164">Nullable이 아닌 형식에 대 한 쿼리 연산자는 nullable 형식과 호환 되는 형식 아니므로 null 허용 데이터 값을 사용 하 여 작업 하는 경우 적절 한 쿼리 연산자의 null 허용 버전을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-164">The query operators for non-nullable types are not type-compatible with nullable types, so you must use the nullable version of the appropriate query operator when you are working with nullable data values.</span></span> <span data-ttu-id="3f051-165">자세한 내용은 [쿼리 식](../query-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-165">For more information, see [Query Expressions](../query-expressions.md).</span></span>

<span data-ttu-id="3f051-166">다음 예제에서는 null 허용 연산자의 사용을 보여 줍니다.는 F# 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-166">The following example shows the use of nullable operators in an F# query expression.</span></span> <span data-ttu-id="3f051-167">첫 번째 쿼리는 null 허용 연산자; 않고 쿼리를 작성 하는 방법을 보여 줍니다. 두 번째 쿼리는 null 허용 연산자를 사용 하는 해당 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-167">The first query shows how you would write a query without a nullable operator; the second query shows an equivalent query that uses a nullable operator.</span></span> <span data-ttu-id="3f051-168">이 샘플 코드를 사용 하 여 데이터베이스를 설정 하는 방법을 포함 하 여 전체 컨텍스트를 참조 하세요. [연습: 형식 공급자를 사용 하 여 SQL Database에 액세스](../../tutorials/type-providers/accessing-a-sql-database.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3f051-168">For the full context, including how to set up the database to use this sample code, see [Walkthrough: Accessing a SQL Database by Using Type Providers](../../tutorials/type-providers/accessing-a-sql-database.md).</span></span>

```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq

[<Generate>]
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">

let db = dbSchema.GetDataContext()

query {
    for row in db.Table2 do
    where (row.TestData1.HasValue && row.TestData1.Value > 2)
    select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
    for row in db.Table2 do
    // Use a nullable operator ?>
    where (row.TestData1 ?> 2)
    select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="see-also"></a><span data-ttu-id="3f051-169">참고자료</span><span class="sxs-lookup"><span data-stu-id="3f051-169">See also</span></span>

- [<span data-ttu-id="3f051-170">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="3f051-170">Type Providers</span></span>](../../tutorials/type-providers/index.md)
- [<span data-ttu-id="3f051-171">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="3f051-171">Query Expressions</span></span>](../query-expressions.md)
