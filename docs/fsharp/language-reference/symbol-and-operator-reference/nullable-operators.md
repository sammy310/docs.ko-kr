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
# <a name="nullable-operators"></a>null 허용 연산자

Nullable 연산자는 하나 또는 양쪽 모두에서 nullable 산술 형식으로 작업 하는 이항 산술 또는 비교 연산자입니다. Null 허용 형식은 실제 값 대신 null을 허용 하는 데이터베이스와 같은 원본의 데이터로 작업 하는 경우에 자주 발생 합니다. Nullable 연산자는 쿼리 식에서 자주 사용 됩니다. 산술 및 비교를 위한 nullable 연산자 외에도 변환 연산자를 사용 하 여 nullable 형식 간에 변환할 수 있습니다. 특정 쿼리 연산자의 nullable 버전도 있습니다.

## <a name="table-of-nullable-operators"></a>Nullable 연산자 표

다음 표에서는 해당 F# 언어로 지원 되는 null 허용 연산자를 보여 줍니다.

|왼쪽에서 null 허용|Right에서 Nullable|양쪽에서 nullable|
|---|---|---|
|[? > =](https://msdn.microsoft.com/library/94d29e32-a204-4f60-a527-6b0af86268f3)|[> =?](https://msdn.microsoft.com/library/0a255d8e-8cae-4160-ae61-243a5d96583f)|[? > =?](https://msdn.microsoft.com/library/3051a50f-d276-4c84-9d73-bf2efeddef94)|
|[? >](https://msdn.microsoft.com/library/62dc0021-1312-4ac3-be87-798b60b81bb6)|[>?](https://msdn.microsoft.com/library/0ad1284b-de48-4a04-83d8-b6f13c9c8936)|[? >?](https://msdn.microsoft.com/library/dc18b6fa-30c4-47b0-9057-794439378a05)|
|[? < =](https://msdn.microsoft.com/library/56fddf0a-e4ca-4891-a3be-fad1876be3b6)|[< =?](https://msdn.microsoft.com/library/02454a0f-30ca-4e77-ad84-ee7837461804)|[? < =?](https://msdn.microsoft.com/library/5c37c28c-0b57-4da5-be11-5a123f7e8ee4)|
|[? <](https://msdn.microsoft.com/library/b71897f0-6e29-4c58-b0a7-a5bfa6f88917)|[<?](https://msdn.microsoft.com/library/be9ea40f-a67f-4e98-8067-a14046752e8b)|[? <?](https://msdn.microsoft.com/library/6f1962c8-5605-468c-94ae-f379ae98e17d)|
|[?=](https://msdn.microsoft.com/library/5cdc8ff6-244b-49cf-9376-69ecf249fd7c)|[=?](https://msdn.microsoft.com/library/d2102894-6a51-475d-890a-735568c31f87)|[?=?](https://msdn.microsoft.com/library/5f793f29-1084-4570-b1c1-17c1b7ef764b)|
|[? < >](https://msdn.microsoft.com/library/3643a5a8-2ea5-4ad6-82c4-83927c3884a0)|[> <?](https://msdn.microsoft.com/library/3179aace-70c4-4911-9258-619592214976)|[? < >?](https://msdn.microsoft.com/library/5da813d8-ee75-45b8-9ef4-146dcb6d394d)|
|[?+](https://msdn.microsoft.com/library/2e8ddd05-b3f3-41b3-9d73-938d9e540f3f)|[+?](https://msdn.microsoft.com/library/74772ea8-f010-493e-bdb5-ba347f2fd4f1)|[?+?](https://msdn.microsoft.com/library/57f28137-0f42-43d2-92af-cad8c6c9d05f)|
|[?-](https://msdn.microsoft.com/library/f237a7a6-89f2-48b2-a2fe-f0b98a2bedc2)|[-?](https://msdn.microsoft.com/library/4a345c07-314a-48f1-b557-ce072583589c)|[?-?](https://msdn.microsoft.com/library/e0024142-1d2a-4607-a39c-1eb1e86fa25a)|
|[?*](https://msdn.microsoft.com/library/519da708-5ad6-4075-9d74-d00441cd6078)|[*?](https://msdn.microsoft.com/library/04c47870-de7b-480d-98a0-f47593b4ffac)|[?*?](https://msdn.microsoft.com/library/e57057ba-9c3a-40ec-8401-150c2b25f75b)|
|[?/](https://msdn.microsoft.com/library/add02a42-f556-40a7-a168-fbf2053322e3)|[/?](https://msdn.microsoft.com/library/1de07646-3778-476d-8c61-5d37495d463c)|[?/?](https://msdn.microsoft.com/library/b17be0ac-bf98-4590-861d-a4dd6c6fa535)|
|[?%](https://msdn.microsoft.com/library/44297bba-1bd9-4ed2-a848-f1e1e598db87)|[%?](https://msdn.microsoft.com/library/a4c178e5-eec4-42e8-847f-90b24fc609fe)|[?%?](https://msdn.microsoft.com/library/dd555f20-1be3-4b8d-81f1-bf1921e62fda)|

## <a name="remarks"></a>주의

Nullable 연산자는 [fsharp.core](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d)네임 스페이스의 [NullableOperators](https://msdn.microsoft.com/library/2c3633c5-3f31-4d62-a9f8-272ad6b19007) 모듈에 포함 됩니다. Nullable 데이터의 형식이 `System.Nullable<'T>`입니다.

쿼리 식에서 null 허용 형식은 값 대신 null을 허용 하는 데이터 소스에서 데이터를 선택 하는 경우에 발생 합니다. SQL Server 데이터베이스에서 테이블의 각 데이터 열에는 null이 허용 되는지 여부를 나타내는 특성이 있습니다. Null이 허용 되는 경우 데이터베이스에서 반환 된 데이터에는 `int`, `float`등의 기본 데이터 형식으로 나타낼 수 없는 null이 포함 될 수 있습니다. 따라서 데이터는 `int`대신 `System.Nullable<int>`으로 반환 되며 `float`대신 `System.Nullable<float>` 됩니다. 실제 값은 `Value` 속성을 사용 하 여 `System.Nullable<'T>` 개체에서 가져올 수 있으며 `HasValue` 메서드를 호출 하 여 `System.Nullable<'T>` 개체에 값이 있는지 여부를 확인할 수 있습니다. 또 다른 유용한 방법은 값 또는 적절 한 형식의 기본값을 가져올 수 있는 `System.Nullable<'T>.GetValueOrDefault` 메서드입니다. 기본값은 0, 0.0, `false`등의 "0" 값 형식입니다.

`int` 또는 `float`와 같은 일반적인 변환 연산자를 사용 하 여 nullable 형식을 nullable이 아닌 기본 형식으로 변환할 수 있습니다. Nullable 형식에 대 한 변환 연산자를 사용 하 여 하나의 nullable 형식에서 다른 nullable 형식으로 변환할 수 있습니다. 적절 한 변환 연산자는 표준 이름과 동일 하지만 [fsharp.core](https://msdn.microsoft.com/library/4765b4e8-4006-4d8c-a405-39c218b3c82d) 네임 스페이스의 [Nullable](https://msdn.microsoft.com/library/e7a4ea13-28cc-462e-bc3a-33131ace976e) 모듈인 별도의 모듈에 있습니다. 일반적으로 쿼리 식으로 작업할 때이 네임 스페이스를 엽니다. 이 경우 다음 코드와 같이 적절 한 변환 연산자에 `Nullable.` 접두사를 추가 하 여 nullable 변환 연산자를 사용할 수 있습니다.

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn "%f" (float nullableFloat)
```

출력은 `10.000000`입니다.

`sumByNullable`와 같은 nullable 데이터 필드에 대 한 쿼리 연산자도 쿼리 식에 사용할 수 있습니다. Nullable이 아닌 형식에 대 한 쿼리 연산자는 nullable 형식과 형식이 호환 되지 않으므로 nullable 데이터 값으로 작업할 때 적절 한 쿼리 연산자의 nullable 버전을 사용 해야 합니다. 자세한 내용은 [쿼리 식](../query-expressions.md)을 참조 하세요.

다음 예에서는 F# 쿼리 식에서 nullable 연산자를 사용 하는 방법을 보여 줍니다. 첫 번째 쿼리는 null 허용 연산자 없이 쿼리를 작성 하는 방법을 보여 줍니다. 두 번째 쿼리는 nullable 연산자를 사용 하는 동일한 쿼리를 보여 줍니다. 이 샘플 코드를 사용 하도록 데이터베이스를 설정 하는 방법을 비롯 한 전체 컨텍스트는 [연습: 형식 공급자를 사용 하 여 SQL Database 액세스](../../tutorials/type-providers/index.md)를 참조 하세요.

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

## <a name="see-also"></a>참조

- [형식 공급자](../../tutorials/type-providers/index.md)
- [쿼리 식](../query-expressions.md)
