---
title: null 허용 연산자
description: F# 프로그래밍 언어에서 사용할 수 있는 nullable 연산자에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 9c747cf5c2e07ca9f80cef741d71d892fb437b3a
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424038"
---
# <a name="nullable-operators"></a><span data-ttu-id="25e5d-103">null 허용 연산자</span><span class="sxs-lookup"><span data-stu-id="25e5d-103">Nullable Operators</span></span>

<span data-ttu-id="25e5d-104">Nullable 연산자는 하나 또는 양쪽 모두에서 nullable 산술 형식으로 작업 하는 이항 산술 또는 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-104">Nullable operators are binary arithmetic or comparison operators that work with nullable arithmetic types on one or both sides.</span></span> <span data-ttu-id="25e5d-105">Null 허용 형식은 실제 값 대신 null을 허용 하는 데이터베이스와 같은 원본의 데이터로 작업 하는 경우에 자주 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-105">Nullable types arise frequently when you work with data from sources such as databases that allow nulls in place of actual values.</span></span> <span data-ttu-id="25e5d-106">Nullable 연산자는 쿼리 식에서 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-106">Nullable operators are used frequently in query expressions.</span></span> <span data-ttu-id="25e5d-107">산술 및 비교를 위한 nullable 연산자 외에도 변환 연산자를 사용 하 여 nullable 형식 간에 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-107">In addition to nullable operators for arithmetic and comparison, conversion operators can be used to convert between nullable types.</span></span> <span data-ttu-id="25e5d-108">특정 쿼리 연산자의 nullable 버전도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-108">There are also nullable versions of certain query operators.</span></span>

## <a name="table-of-nullable-operators"></a><span data-ttu-id="25e5d-109">Nullable 연산자 표</span><span class="sxs-lookup"><span data-stu-id="25e5d-109">Table of Nullable Operators</span></span>

<span data-ttu-id="25e5d-110">다음 표에서는 해당 F# 언어로 지원 되는 null 허용 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-110">The following table lists nullable operators supported in the F# language.</span></span>

|<span data-ttu-id="25e5d-111">왼쪽에서 null 허용</span><span class="sxs-lookup"><span data-stu-id="25e5d-111">Nullable on left</span></span>|<span data-ttu-id="25e5d-112">Right에서 Nullable</span><span class="sxs-lookup"><span data-stu-id="25e5d-112">Nullable on right</span></span>|<span data-ttu-id="25e5d-113">양쪽에서 nullable</span><span class="sxs-lookup"><span data-stu-id="25e5d-113">Both sides nullable</span></span>|
|---|---|---|
|[<span data-ttu-id="25e5d-114">? > =</span><span class="sxs-lookup"><span data-stu-id="25e5d-114">?>=</span></span>](https://msdn.microsoft.com/library/94d29e32-a204-4f60-a527-6b0af86268f3)|[<span data-ttu-id="25e5d-115">> =?</span><span class="sxs-lookup"><span data-stu-id="25e5d-115">>=?</span></span>](https://msdn.microsoft.com/library/0a255d8e-8cae-4160-ae61-243a5d96583f)|[<span data-ttu-id="25e5d-116">? > =?</span><span class="sxs-lookup"><span data-stu-id="25e5d-116">?>=?</span></span>](https://msdn.microsoft.com/library/3051a50f-d276-4c84-9d73-bf2efeddef94)|
|[<span data-ttu-id="25e5d-117">? ></span><span class="sxs-lookup"><span data-stu-id="25e5d-117">?></span></span>](https://msdn.microsoft.com/library/62dc0021-1312-4ac3-be87-798b60b81bb6)|[<span data-ttu-id="25e5d-118">>?</span><span class="sxs-lookup"><span data-stu-id="25e5d-118">>?</span></span>](https://msdn.microsoft.com/library/0ad1284b-de48-4a04-83d8-b6f13c9c8936)|[<span data-ttu-id="25e5d-119">? >?</span><span class="sxs-lookup"><span data-stu-id="25e5d-119">?>?</span></span>](https://msdn.microsoft.com/library/dc18b6fa-30c4-47b0-9057-794439378a05)|
|[<span data-ttu-id="25e5d-120">? < =</span><span class="sxs-lookup"><span data-stu-id="25e5d-120">?<=</span></span>](https://msdn.microsoft.com/library/56fddf0a-e4ca-4891-a3be-fad1876be3b6)|[<span data-ttu-id="25e5d-121">< =?</span><span class="sxs-lookup"><span data-stu-id="25e5d-121"><=?</span></span>](https://msdn.microsoft.com/library/02454a0f-30ca-4e77-ad84-ee7837461804)|[<span data-ttu-id="25e5d-122">? < =?</span><span class="sxs-lookup"><span data-stu-id="25e5d-122">?<=?</span></span>](https://msdn.microsoft.com/library/5c37c28c-0b57-4da5-be11-5a123f7e8ee4)|
|[<span data-ttu-id="25e5d-123">? <</span><span class="sxs-lookup"><span data-stu-id="25e5d-123">?<</span></span>](https://msdn.microsoft.com/library/b71897f0-6e29-4c58-b0a7-a5bfa6f88917)|[<span data-ttu-id="25e5d-124"><?</span><span class="sxs-lookup"><span data-stu-id="25e5d-124"><?</span></span>](https://msdn.microsoft.com/library/be9ea40f-a67f-4e98-8067-a14046752e8b)|[<span data-ttu-id="25e5d-125">? <?</span><span class="sxs-lookup"><span data-stu-id="25e5d-125">?<?</span></span>](https://msdn.microsoft.com/library/6f1962c8-5605-468c-94ae-f379ae98e17d)|
|[<span data-ttu-id="25e5d-126">?=</span><span class="sxs-lookup"><span data-stu-id="25e5d-126">?=</span></span>](https://msdn.microsoft.com/library/5cdc8ff6-244b-49cf-9376-69ecf249fd7c)|[<span data-ttu-id="25e5d-127">=?</span><span class="sxs-lookup"><span data-stu-id="25e5d-127">=?</span></span>](https://msdn.microsoft.com/library/d2102894-6a51-475d-890a-735568c31f87)|[<span data-ttu-id="25e5d-128">?=?</span><span class="sxs-lookup"><span data-stu-id="25e5d-128">?=?</span></span>](https://msdn.microsoft.com/library/5f793f29-1084-4570-b1c1-17c1b7ef764b)|
|[<span data-ttu-id="25e5d-129">? < ></span><span class="sxs-lookup"><span data-stu-id="25e5d-129">?<></span></span>](https://msdn.microsoft.com/library/3643a5a8-2ea5-4ad6-82c4-83927c3884a0)|[<span data-ttu-id="25e5d-130">> <?</span><span class="sxs-lookup"><span data-stu-id="25e5d-130"><>?</span></span>](https://msdn.microsoft.com/library/3179aace-70c4-4911-9258-619592214976)|[<span data-ttu-id="25e5d-131">? < >?</span><span class="sxs-lookup"><span data-stu-id="25e5d-131">?<>?</span></span>](https://msdn.microsoft.com/library/5da813d8-ee75-45b8-9ef4-146dcb6d394d)|
|[<span data-ttu-id="25e5d-132">?+</span><span class="sxs-lookup"><span data-stu-id="25e5d-132">?+</span></span>](https://msdn.microsoft.com/library/2e8ddd05-b3f3-41b3-9d73-938d9e540f3f)|[<span data-ttu-id="25e5d-133">+?</span><span class="sxs-lookup"><span data-stu-id="25e5d-133">+?</span></span>](https://msdn.microsoft.com/library/74772ea8-f010-493e-bdb5-ba347f2fd4f1)|[<span data-ttu-id="25e5d-134">?+?</span><span class="sxs-lookup"><span data-stu-id="25e5d-134">?+?</span></span>](https://msdn.microsoft.com/library/57f28137-0f42-43d2-92af-cad8c6c9d05f)|
|[<span data-ttu-id="25e5d-135">?-</span><span class="sxs-lookup"><span data-stu-id="25e5d-135">?-</span></span>](https://msdn.microsoft.com/library/f237a7a6-89f2-48b2-a2fe-f0b98a2bedc2)|[<span data-ttu-id="25e5d-136">-?</span><span class="sxs-lookup"><span data-stu-id="25e5d-136">-?</span></span>](https://msdn.microsoft.com/library/4a345c07-314a-48f1-b557-ce072583589c)|[<span data-ttu-id="25e5d-137">?-?</span><span class="sxs-lookup"><span data-stu-id="25e5d-137">?-?</span></span>](https://msdn.microsoft.com/library/e0024142-1d2a-4607-a39c-1eb1e86fa25a)|
|[<span data-ttu-id="25e5d-138">?\*</span><span class="sxs-lookup"><span data-stu-id="25e5d-138">?\*</span></span>](https://msdn.microsoft.com/library/519da708-5ad6-4075-9d74-d00441cd6078)|[<span data-ttu-id="25e5d-139">\*?</span><span class="sxs-lookup"><span data-stu-id="25e5d-139">\*?</span></span>](https://msdn.microsoft.com/library/04c47870-de7b-480d-98a0-f47593b4ffac)|[<span data-ttu-id="25e5d-140">?\*?</span><span class="sxs-lookup"><span data-stu-id="25e5d-140">?\*?</span></span>](https://msdn.microsoft.com/library/e57057ba-9c3a-40ec-8401-150c2b25f75b)|
|[<span data-ttu-id="25e5d-141">?/</span><span class="sxs-lookup"><span data-stu-id="25e5d-141">?/</span></span>](https://msdn.microsoft.com/library/add02a42-f556-40a7-a168-fbf2053322e3)|[<span data-ttu-id="25e5d-142">/?</span><span class="sxs-lookup"><span data-stu-id="25e5d-142">/?</span></span>](https://msdn.microsoft.com/library/1de07646-3778-476d-8c61-5d37495d463c)|[<span data-ttu-id="25e5d-143">?/?</span><span class="sxs-lookup"><span data-stu-id="25e5d-143">?/?</span></span>](https://msdn.microsoft.com/library/b17be0ac-bf98-4590-861d-a4dd6c6fa535)|
|[<span data-ttu-id="25e5d-144">?%</span><span class="sxs-lookup"><span data-stu-id="25e5d-144">?%</span></span>](https://msdn.microsoft.com/library/44297bba-1bd9-4ed2-a848-f1e1e598db87)|[<span data-ttu-id="25e5d-145">%?</span><span class="sxs-lookup"><span data-stu-id="25e5d-145">%?</span></span>](https://msdn.microsoft.com/library/a4c178e5-eec4-42e8-847f-90b24fc609fe)|[<span data-ttu-id="25e5d-146">?%?</span><span class="sxs-lookup"><span data-stu-id="25e5d-146">?%?</span></span>](https://msdn.microsoft.com/library/dd555f20-1be3-4b8d-81f1-bf1921e62fda)|

## <a name="remarks"></a><span data-ttu-id="25e5d-147">주의</span><span class="sxs-lookup"><span data-stu-id="25e5d-147">Remarks</span></span>

<span data-ttu-id="25e5d-148">Nullable 연산자는 [fsharp.core](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d)네임 스페이스의 [NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007) 모듈에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-148">The nullable operators are included in the [NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007) module in the namespace [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d).</span></span> <span data-ttu-id="25e5d-149">Nullable 데이터의 형식이 `System.Nullable<'T>`입니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-149">The type for nullable data is `System.Nullable<'T>`.</span></span>

<span data-ttu-id="25e5d-150">쿼리 식에서 null 허용 형식은 값 대신 null을 허용 하는 데이터 소스에서 데이터를 선택 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-150">In query expressions, nullable types arise when selecting data from a data source that allows nulls instead of values.</span></span> <span data-ttu-id="25e5d-151">SQL Server 데이터베이스에서 테이블의 각 데이터 열에는 null이 허용 되는지 여부를 나타내는 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-151">In a SQL Server database, each data column in a table has an attribute that indicates whether nulls are allowed.</span></span> <span data-ttu-id="25e5d-152">Null이 허용 되는 경우 데이터베이스에서 반환 된 데이터에는 `int`, `float`등의 기본 데이터 형식으로 나타낼 수 없는 null이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-152">If nulls are allowed, the data returned from the database can contain nulls that cannot be represented by a primitive data type such as `int`, `float`, and so on.</span></span> <span data-ttu-id="25e5d-153">따라서 데이터는 `int`대신 `System.Nullable<int>`으로 반환 되며 `float`대신 `System.Nullable<float>` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-153">Therefore, the data is returned as a `System.Nullable<int>` instead of `int`, and `System.Nullable<float>` instead of `float`.</span></span> <span data-ttu-id="25e5d-154">실제 값은 `Value` 속성을 사용 하 여 `System.Nullable<'T>` 개체에서 가져올 수 있으며 `HasValue` 메서드를 호출 하 여 `System.Nullable<'T>` 개체에 값이 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-154">The actual value can be obtained from a `System.Nullable<'T>` object by using the `Value` property, and you can determine if a `System.Nullable<'T>` object has a value by calling the `HasValue` method.</span></span> <span data-ttu-id="25e5d-155">또 다른 유용한 방법은 값 또는 적절 한 형식의 기본값을 가져올 수 있는 `System.Nullable<'T>.GetValueOrDefault` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-155">Another useful method is the `System.Nullable<'T>.GetValueOrDefault` method, which allows you to get the value or a default value of the appropriate type.</span></span> <span data-ttu-id="25e5d-156">기본값은 0, 0.0, `false`등의 "0" 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-156">The default value is some form of "zero" value, such as 0, 0.0, or `false`.</span></span>

<span data-ttu-id="25e5d-157">`int` 또는 `float`와 같은 일반적인 변환 연산자를 사용 하 여 nullable 형식을 nullable이 아닌 기본 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-157">Nullable types may be converted to non-nullable primitive types using the usual conversion operators such as `int` or `float`.</span></span> <span data-ttu-id="25e5d-158">Nullable 형식에 대 한 변환 연산자를 사용 하 여 하나의 nullable 형식에서 다른 nullable 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-158">It is also possible to convert from one nullable type to another nullable type by using the conversion operators for nullable types.</span></span> <span data-ttu-id="25e5d-159">적절 한 변환 연산자는 표준 이름과 동일 하지만 [fsharp.core](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d) 네임 스페이스의 [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e) 모듈인 별도의 모듈에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-159">The appropriate conversion operators have the same name as the standard ones, but they are in a separate module, the [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e) module in the [Microsoft.FSharp.Linq](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d) namespace.</span></span> <span data-ttu-id="25e5d-160">일반적으로 쿼리 식으로 작업할 때이 네임 스페이스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-160">Typically, you open this namespace when working with query expressions.</span></span> <span data-ttu-id="25e5d-161">이 경우 다음 코드와 같이 적절 한 변환 연산자에 `Nullable.` 접두사를 추가 하 여 nullable 변환 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-161">In that case, you can use the nullable conversion operators by adding the prefix `Nullable.` to the appropriate conversion operator, as shown in the following code.</span></span>

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn "%f" (float nullableFloat)
```

<span data-ttu-id="25e5d-162">출력은 `10.000000`입니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-162">The output is `10.000000`.</span></span>

<span data-ttu-id="25e5d-163">`sumByNullable`와 같은 nullable 데이터 필드에 대 한 쿼리 연산자도 쿼리 식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-163">Query operators on nullable data fields, such as `sumByNullable`, also exist for use in query expressions.</span></span> <span data-ttu-id="25e5d-164">Nullable이 아닌 형식에 대 한 쿼리 연산자는 nullable 형식과 형식이 호환 되지 않으므로 nullable 데이터 값으로 작업할 때 적절 한 쿼리 연산자의 nullable 버전을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-164">The query operators for non-nullable types are not type-compatible with nullable types, so you must use the nullable version of the appropriate query operator when you are working with nullable data values.</span></span> <span data-ttu-id="25e5d-165">자세한 내용은 [쿼리 식](../query-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25e5d-165">For more information, see [Query Expressions](../query-expressions.md).</span></span>

<span data-ttu-id="25e5d-166">다음 예에서는 F# 쿼리 식에서 nullable 연산자를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-166">The following example shows the use of nullable operators in an F# query expression.</span></span> <span data-ttu-id="25e5d-167">첫 번째 쿼리는 null 허용 연산자 없이 쿼리를 작성 하는 방법을 보여 줍니다. 두 번째 쿼리는 nullable 연산자를 사용 하는 동일한 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25e5d-167">The first query shows how you would write a query without a nullable operator; the second query shows an equivalent query that uses a nullable operator.</span></span> <span data-ttu-id="25e5d-168">이 샘플 코드를 사용 하도록 데이터베이스를 설정 하는 방법을 비롯 한 전체 컨텍스트는 [연습: 형식 공급자를 사용 하 여 SQL Database 액세스](../../tutorials/type-providers/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25e5d-168">For the full context, including how to set up the database to use this sample code, see [Walkthrough: Accessing a SQL Database by Using Type Providers](../../tutorials/type-providers/index.md).</span></span>

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

## <a name="see-also"></a><span data-ttu-id="25e5d-169">참조</span><span class="sxs-lookup"><span data-stu-id="25e5d-169">See also</span></span>

- [<span data-ttu-id="25e5d-170">형식 공급자</span><span class="sxs-lookup"><span data-stu-id="25e5d-170">Type Providers</span></span>](../../tutorials/type-providers/index.md)
- [<span data-ttu-id="25e5d-171">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="25e5d-171">Query Expressions</span></span>](../query-expressions.md)
