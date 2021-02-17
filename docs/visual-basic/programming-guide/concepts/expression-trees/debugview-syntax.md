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
# <a name="debugview-syntax"></a><span data-ttu-id="d3cc0-103">**Debugview** 구문</span><span class="sxs-lookup"><span data-stu-id="d3cc0-103">**DebugView** syntax</span></span>

<span data-ttu-id="d3cc0-104">**Debugview** 속성 (디버깅 하는 경우에만 사용 가능)은 식 트리의 문자열 렌더링을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-104">The **DebugView** property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="d3cc0-105">대부분의 구문은 이해하기 쉽습니다. 특별한 경우는 다음 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="d3cc0-106">각 예제 다음에는 **Debugview** 를 포함 하는 주석 블록이 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-106">Each example is followed by a comment block containing the **DebugView**.</span></span>

## <a name="parameterexpression"></a><span data-ttu-id="d3cc0-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="d3cc0-107">ParameterExpression</span></span>

<span data-ttu-id="d3cc0-108"><xref:System.Linq.Expressions.ParameterExpression> 변수 이름의 시작 부분에 “$” 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-108"><xref:System.Linq.Expressions.ParameterExpression> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="d3cc0-109">매개 변수에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `$var1` 또는 `$var2`).</span><span class="sxs-lookup"><span data-stu-id="d3cc0-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="d3cc0-110">예</span><span class="sxs-lookup"><span data-stu-id="d3cc0-110">Examples</span></span>

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

## <a name="constantexpressions"></a><span data-ttu-id="d3cc0-111">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="d3cc0-111">ConstantExpressions</span></span>

<span data-ttu-id="d3cc0-112">정수 값, 문자열 및 `null`을 나타내는 <xref:System.Linq.Expressions.ConstantExpression> 개체의 경우 상수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-112">For <xref:System.Linq.Expressions.ConstantExpression> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="d3cc0-113">일부 숫자 형식의 경우 값에 접미사를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-113">For some numeric types, a suffix is added to the value:</span></span>

| <span data-ttu-id="d3cc0-114">유형</span><span class="sxs-lookup"><span data-stu-id="d3cc0-114">Type</span></span> | <span data-ttu-id="d3cc0-115">키워드</span><span class="sxs-lookup"><span data-stu-id="d3cc0-115">Keyword</span></span> | <span data-ttu-id="d3cc0-116">접미사</span><span class="sxs-lookup"><span data-stu-id="d3cc0-116">Suffix</span></span> |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [<span data-ttu-id="d3cc0-117">UInteger</span><span class="sxs-lookup"><span data-stu-id="d3cc0-117">UInteger</span></span>](../../../language-reference/data-types/uinteger-data-type.md) | <span data-ttu-id="d3cc0-118">U</span><span class="sxs-lookup"><span data-stu-id="d3cc0-118">U</span></span> |
| <xref:System.Int64?displayProperty=nameWithType> | [<span data-ttu-id="d3cc0-119">Long</span><span class="sxs-lookup"><span data-stu-id="d3cc0-119">Long</span></span>](../../../language-reference/data-types/long-data-type.md) | <span data-ttu-id="d3cc0-120">L</span><span class="sxs-lookup"><span data-stu-id="d3cc0-120">L</span></span> |
| <xref:System.UInt64?displayProperty=nameWithType> | [<span data-ttu-id="d3cc0-121">ULong</span><span class="sxs-lookup"><span data-stu-id="d3cc0-121">ULong</span></span>](../../../language-reference/data-types/ulong-data-type.md) | <span data-ttu-id="d3cc0-122">UL</span><span class="sxs-lookup"><span data-stu-id="d3cc0-122">UL</span></span> |
| <xref:System.Double?displayProperty=nameWithType> | [<span data-ttu-id="d3cc0-123">double</span><span class="sxs-lookup"><span data-stu-id="d3cc0-123">Double</span></span>](../../../language-reference/data-types/double-data-type.md) | <span data-ttu-id="d3cc0-124">D</span><span class="sxs-lookup"><span data-stu-id="d3cc0-124">D</span></span> |
| <xref:System.Single?displayProperty=nameWithType> | [<span data-ttu-id="d3cc0-125">Single</span><span class="sxs-lookup"><span data-stu-id="d3cc0-125">Single</span></span>](../../../language-reference/data-types/single-data-type.md) | <span data-ttu-id="d3cc0-126">F</span><span class="sxs-lookup"><span data-stu-id="d3cc0-126">F</span></span> |
| <xref:System.Decimal?displayProperty=nameWithType> | [<span data-ttu-id="d3cc0-127">10진수</span><span class="sxs-lookup"><span data-stu-id="d3cc0-127">Decimal</span></span>](../../../language-reference/data-types/decimal-data-type.md) | <span data-ttu-id="d3cc0-128">M</span><span class="sxs-lookup"><span data-stu-id="d3cc0-128">M</span></span> |

### <a name="examples"></a><span data-ttu-id="d3cc0-129">예제</span><span class="sxs-lookup"><span data-stu-id="d3cc0-129">Examples</span></span>

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

## <a name="blockexpression"></a><span data-ttu-id="d3cc0-130">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="d3cc0-130">BlockExpression</span></span>

<span data-ttu-id="d3cc0-131"><xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 블록에 있는 마지막 식의 형식과 다를 경우 형식은 꺾쇠 괄호(`<` 및 `>`) 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-131">If the type of a <xref:System.Linq.Expressions.BlockExpression> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="d3cc0-132">같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-132">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="d3cc0-133">예제</span><span class="sxs-lookup"><span data-stu-id="d3cc0-133">Examples</span></span>

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

## <a name="lambdaexpression"></a><span data-ttu-id="d3cc0-134">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="d3cc0-134">LambdaExpression</span></span>

<span data-ttu-id="d3cc0-135"><xref:System.Linq.Expressions.LambdaExpression> 개체는 대리자 형식과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-135"><xref:System.Linq.Expressions.LambdaExpression> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="d3cc0-136">람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).</span><span class="sxs-lookup"><span data-stu-id="d3cc0-136">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="d3cc0-137">예제</span><span class="sxs-lookup"><span data-stu-id="d3cc0-137">Examples</span></span>

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

## <a name="labelexpression"></a><span data-ttu-id="d3cc0-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="d3cc0-138">LabelExpression</span></span>

<span data-ttu-id="d3cc0-139"><xref:System.Linq.Expressions.LabelExpression> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget> 개체 앞에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget> object.</span></span>

<span data-ttu-id="d3cc0-140">`.Label` 토큰은 레이블의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="d3cc0-141">`.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="d3cc0-142">레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="d3cc0-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="d3cc0-143">예제</span><span class="sxs-lookup"><span data-stu-id="d3cc0-143">Examples</span></span>

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

## <a name="checked-operators"></a><span data-ttu-id="d3cc0-144">확인된 연산자</span><span class="sxs-lookup"><span data-stu-id="d3cc0-144">Checked Operators</span></span>

<span data-ttu-id="d3cc0-145">확인된 연산자는 연산자 앞에 `#` 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-145">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="d3cc0-146">예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3cc0-146">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="d3cc0-147">예</span><span class="sxs-lookup"><span data-stu-id="d3cc0-147">Examples</span></span>

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
