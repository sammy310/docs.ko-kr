---
title: null 허용 연산자
description: 'F # 프로그래밍 언어에서 사용할 수 있는 nullable 연산자에 대해 알아봅니다.'
ms.date: 05/16/2016
ms.openlocfilehash: 9ac6afc2c3f4277ee6e93b1ccb3d21f892926b4b
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740369"
---
# <a name="nullable-operators"></a>null 허용 연산자

Nullable 연산자는 하나 또는 양쪽 모두에서 nullable 산술 형식으로 작업 하는 이항 산술 또는 비교 연산자입니다. Null 허용 형식은 실제 값 대신 null을 허용 하는 데이터베이스와 같은 원본의 데이터로 작업 하는 경우에 자주 발생 합니다. Nullable 연산자는 쿼리 식에서 자주 사용 됩니다. 산술 및 비교를 위한 nullable 연산자 외에도 변환 연산자를 사용 하 여 nullable 형식 간에 변환할 수 있습니다. 특정 쿼리 연산자의 nullable 버전도 있습니다.

## <a name="table-of-nullable-operators"></a>Nullable 연산자 표

다음 표에서는 F # 언어로 지원 되는 nullable 연산자를 나열 합니다.

|왼쪽에서 null 허용|Right에서 Nullable|양쪽에서 nullable|
|---|---|---|
|[? >=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E=%20))|[>=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3E=?%20))|[? >=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E=?%20))|
|[? >](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E%20))|[>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3E?%20))|[? >?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3E?%20))|
|[? <=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C=%20))|[<=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C=?%20))|[? <=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C=?%20))|
|[? <](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%20))|[<?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C?%20))|[? <?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C?%20))|
|[?=](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?=%20))|[=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20=?%20))|[?=?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?=?%20))|
|[? <>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%3E%20))|[<>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%3C%3E?%20))|[? <>?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%3C%3E?%20))|
|[?+](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?+%20))|[+?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20+?%20))|[?+?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?+?%20))|
|[?-](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?-%20))|[-?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20-?%20))|[?-?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?-?%20))|
|[?*](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?*%20))|[*?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20*?%20))|[?*?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?*?%20))|
|[?/](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?/%20))|[/?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20/?%20))|[?/?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?/?%20))|
|[?%](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%%20))|[%?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20%?%20))|[?%?](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html#(%20?%?%20))|

## <a name="remarks"></a>설명

Nullable 연산자는 네임 스페이스 [fsharp.core](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq.html)의 [NullableOperators](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullableoperators.html) 모듈에 포함 됩니다. Nullable 데이터의 형식은 `System.Nullable<'T>` 입니다.

쿼리 식에서 null 허용 형식은 값 대신 null을 허용 하는 데이터 소스에서 데이터를 선택 하는 경우에 발생 합니다. SQL Server 데이터베이스에서 테이블의 각 데이터 열에는 null이 허용 되는지 여부를 나타내는 특성이 있습니다. Null이 허용 되는 경우 데이터베이스에서 반환 된 데이터에는, 등의 기본 데이터 형식으로 나타낼 수 없는 null이 포함 될 수 있습니다 `int` `float` . 따라서 데이터는 대신, 대신로 반환 됩니다 `System.Nullable<int>` `int` `System.Nullable<float>` `float` . `System.Nullable<'T>`속성을 사용 하 여 개체에서 실제 값을 가져올 수 `Value` 있으며, `System.Nullable<'T>` 메서드를 호출 하 여 개체에 값이 있는지 여부를 확인할 수 있습니다 `HasValue` . 또 다른 유용한 방법은 `System.Nullable<'T>.GetValueOrDefault` 해당 형식의 값 또는 기본값을 가져올 수 있도록 하는 메서드입니다. 기본값은 0, 0.0, 등의 "0" 값 형식입니다 `false` .

또는와 같은 일반적인 변환 연산자를 사용 하 여 nullable 형식을 nullable이 아닌 기본 형식으로 변환할 수 있습니다 `int` `float` . Nullable 형식에 대 한 변환 연산자를 사용 하 여 하나의 nullable 형식에서 다른 nullable 형식으로 변환할 수 있습니다. 적절 한 변환 연산자는 표준 이름과 동일 하지만 [fsharp.core](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq.html) 네임 스페이스의 [Nullable](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-linq-nullablemodule.html) 모듈인 별도의 모듈에 있습니다. 일반적으로 쿼리 식으로 작업할 때이 네임 스페이스를 엽니다. 이 경우 `Nullable.` 다음 코드와 같이 적절 한 변환 연산자에 접두사를 추가 하 여 nullable 변환 연산자를 사용할 수 있습니다.

```fsharp
open Microsoft.FSharp.Linq

let nullableInt = new System.Nullable<int>(10)

// Use the Nullable.float conversion operator to convert from one nullable type to another nullable type.
let nullableFloat = Nullable.float nullableInt

// Use the regular non-nullable float operator to convert to a non-nullable float.
printfn $"%f{float nullableFloat}"
```

`10.000000`가 출력됩니다.

등의 nullable 데이터 필드에 대 한 쿼리 연산자는 `sumByNullable` 쿼리 식에 사용할 수 있습니다. Nullable이 아닌 형식에 대 한 쿼리 연산자는 nullable 형식과 형식이 호환 되지 않으므로 nullable 데이터 값으로 작업할 때 적절 한 쿼리 연산자의 nullable 버전을 사용 해야 합니다. 자세한 내용은 [쿼리 식](../query-expressions.md)을 참조 하세요.

다음 예에서는 F # 쿼리 식에서 nullable 연산자를 사용 하는 방법을 보여 줍니다. 첫 번째 쿼리는 null 허용 연산자 없이 쿼리를 작성 하는 방법을 보여 줍니다. 두 번째 쿼리는 nullable 연산자를 사용 하는 동일한 쿼리를 보여 줍니다. 이 샘플 코드를 사용 하도록 데이터베이스를 설정 하는 방법을 비롯 한 전체 컨텍스트는 [연습: 형식 공급자를 사용 하 여 SQL Database 액세스](../../tutorials/type-providers/index.md)를 참조 하세요.

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
} |> Seq.iter (fun row -> printfn $"%d{row.TestData1.Value} %s{row.Name}")

query {
    for row in db.Table2 do
    // Use a nullable operator ?>
    where (row.TestData1 ?> 2)
    select row
} |> Seq.iter (fun row -> printfn "%d{row.TestData1.GetValueOrDefault()} %s{row.Name}")
```

## <a name="see-also"></a>참고 항목

- [형식 공급자](../../tutorials/type-providers/index.md)
- [쿼리 식](../query-expressions.md)
