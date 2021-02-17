---
title: DebugView 속성에서 사용 되는 구문
description: 식 트리의 문자열 표현을 생성하기 위해 DebugView 속성이 사용하는 특수 구문을 설명합니다.
author: zspitz
ms.author: wiwagn
ms.date: 02/14/2021
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 1b6d117bb1ce0cb13344c72be3b55742c443448f
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100639191"
---
# <a name="debugview-syntax"></a>**Debugview** 구문

**Debugview** 속성 (디버깅 하는 경우에만 사용 가능)은 식 트리의 문자열 렌더링을 제공 합니다. 대부분의 구문은 이해하기 쉽습니다. 특별한 경우는 다음 섹션에서 설명합니다.

각 예제 다음에는 **Debugview** 를 포함 하는 주석 블록이 나옵니다.

## <a name="parameterexpression"></a>ParameterExpression

<xref:System.Linq.Expressions.ParameterExpression> 변수 이름의 시작 부분에 “$” 기호가 표시됩니다.

매개 변수에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `$var1` 또는 `$var2`).

### <a name="examples"></a>예

```vb
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")
'
'    $num
'

Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer))
'
'    $var1
'
```

## <a name="constantexpressions"></a>ConstantExpressions

정수 값, 문자열 및 `null`을 나타내는 <xref:System.Linq.Expressions.ConstantExpression> 개체의 경우 상수 값이 표시됩니다.

일부 숫자 형식의 경우 값에 접미사를 추가 합니다.

| 유형 | 키워드 | 접미사 |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [UInteger](../../../language-reference/data-types/uinteger-data-type.md) | U |
| <xref:System.Int64?displayProperty=nameWithType> | [Long](../../../language-reference/data-types/long-data-type.md) | L |
| <xref:System.UInt64?displayProperty=nameWithType> | [ULong](../../../language-reference/data-types/ulong-data-type.md) | UL |
| <xref:System.Double?displayProperty=nameWithType> | [double](../../../language-reference/data-types/double-data-type.md) | D |
| <xref:System.Single?displayProperty=nameWithType> | [Single](../../../language-reference/data-types/single-data-type.md) | F |
| <xref:System.Decimal?displayProperty=nameWithType> | [10진수](../../../language-reference/data-types/decimal-data-type.md) | M |

### <a name="examples"></a>예제

```vb
Dim num as Integer = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10
'

Dim num As Double = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10D
'
```

## <a name="blockexpression"></a>BlockExpression

<xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 블록에 있는 마지막 식의 형식과 다를 경우 형식은 꺾쇠 괄호(`<` 및 `>`) 안에 표시됩니다. 같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.

### <a name="examples"></a>예제

```vb
Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
'
'    .Block() {
'        "test"
'    }
'

Dim block As BlockExpression = Expression.Block(
    GetType(Object),
    Expression.Constant("test")
)
'
'    .Block<System.Object>() {
'        "test"
'    }
'
```

## <a name="lambdaexpression"></a>LambdaExpression

<xref:System.Linq.Expressions.LambdaExpression> 개체는 대리자 형식과 함께 표시됩니다.

람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).

### <a name="examples"></a>예제

```vb
Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1)
)
'
'    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
'        1
'    }
'

Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1),
    "SampleLambda",
    Nothing
)
'
'    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
'        1
'    }
'
```

## <a name="labelexpression"></a>LabelExpression

<xref:System.Linq.Expressions.LabelExpression> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget> 개체 앞에 표시됩니다.

`.Label` 토큰은 레이블의 시작을 나타냅니다. `.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.

레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).

### <a name="examples"></a>예제

```vb
Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
)
'
'    .Block() {
'        .Goto SampleLabel { 0 };
'        .Label
'            -1
'        .LabelTarget SampleLabel:
'    }
'

Dim target As LabelTarget = Expression.Label()
Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
)
'
'    .Block() {
'        .Goto #Label1 { };
'        .Label
'        .LabelTarget #Label1:
'    }
'
```

## <a name="checked-operators"></a>확인된 연산자

확인된 연산자는 연산자 앞에 `#` 기호가 표시됩니다. 예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.

### <a name="examples"></a>예

```vb
Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1),
    Expression.Constant(2)
)
'
'     1 #+ 2
'

Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0),
    GetType(Integer)
)
'
'    #(System.Int32)10D
'
```
