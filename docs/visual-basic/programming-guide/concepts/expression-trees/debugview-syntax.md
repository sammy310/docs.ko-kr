---
title: DebugView 속성 (Visual Basic)으로 사용 되는 구문
description: DebugView 속성 하는 식 트리의 문자열 표현을 생성 하는 데 사용 하는 특수 한 구문을 설명합니다
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 1b2a1164f02208cc7578820d8f8ed3bc145fb5b8
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2019
ms.locfileid: "66196533"
---
# <a name="debugview-syntax"></a><span data-ttu-id="6099f-103">`DebugView` 구문</span><span class="sxs-lookup"><span data-stu-id="6099f-103">`DebugView` syntax</span></span> 

<span data-ttu-id="6099f-104">`DebugView` 식 트리를 문자열 렌더링을 제공 하는 속성 (디버깅 하는 경우에 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="6099f-104">The `DebugView` property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="6099f-105">알아야 구문의 대부분 꽤 쉽습니다. 특별 한 경우 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="6099f-106">각 예제는 포함 하는 주석 블록 뒤에 `DebugView`합니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-106">Each example is followed by a comment block containing the `DebugView`.</span></span> 

## <a name="parameterexpression"></a><span data-ttu-id="6099f-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="6099f-107">ParameterExpression</span></span>

<span data-ttu-id="6099f-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> 변수 이름의 시작 부분에 “$” 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> variable names are displayed with a "$" symbol at the beginning.</span></span>

<span data-ttu-id="6099f-109">매개 변수에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `$var1` 또는 `$var2`).</span><span class="sxs-lookup"><span data-stu-id="6099f-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="6099f-110">예제</span><span class="sxs-lookup"><span data-stu-id="6099f-110">Examples</span></span>

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

## <a name="constantexpressions"></a><span data-ttu-id="6099f-111">ConstantExpressions</span><span class="sxs-lookup"><span data-stu-id="6099f-111">ConstantExpressions</span></span>

<span data-ttu-id="6099f-112">정수 값, 문자열 및 `null`을 나타내는 <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> 개체의 경우 상수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-112">For <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="6099f-113">일부 숫자 형식의 경우 접미사가 값에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-113">For some numeric types, a suffix is added to the value:</span></span>

| <span data-ttu-id="6099f-114">형식</span><span class="sxs-lookup"><span data-stu-id="6099f-114">Type</span></span> | <span data-ttu-id="6099f-115">키워드</span><span class="sxs-lookup"><span data-stu-id="6099f-115">Keyword</span></span> | <span data-ttu-id="6099f-116">접미사</span><span class="sxs-lookup"><span data-stu-id="6099f-116">Suffix</span></span> |  
|--|--|--|
| <xref:System.UInt32> | [<span data-ttu-id="6099f-117">UInteger</span><span class="sxs-lookup"><span data-stu-id="6099f-117">UInteger</span></span>](../../../language-reference/data-types/uinteger-data-type.md) | <span data-ttu-id="6099f-118">U</span><span class="sxs-lookup"><span data-stu-id="6099f-118">U</span></span> |
| <xref:System.Int64> | [<span data-ttu-id="6099f-119">Long</span><span class="sxs-lookup"><span data-stu-id="6099f-119">Long</span></span>](../../../language-reference/data-types/long-data-type.md) | <span data-ttu-id="6099f-120">L</span><span class="sxs-lookup"><span data-stu-id="6099f-120">L</span></span> |
| <xref:System.UInt64> | [<span data-ttu-id="6099f-121">ULong</span><span class="sxs-lookup"><span data-stu-id="6099f-121">ULong</span></span>](../../../language-reference/data-types/ulong-data-type.md) | <span data-ttu-id="6099f-122">UL</span><span class="sxs-lookup"><span data-stu-id="6099f-122">UL</span></span> |
| <xref:System.Double> | [<span data-ttu-id="6099f-123">Double</span><span class="sxs-lookup"><span data-stu-id="6099f-123">Double</span></span>](../../../language-reference/data-types/double-data-type.md) | <span data-ttu-id="6099f-124">D</span><span class="sxs-lookup"><span data-stu-id="6099f-124">D</span></span> |
| <xref:System.Single> | [<span data-ttu-id="6099f-125">Single</span><span class="sxs-lookup"><span data-stu-id="6099f-125">Single</span></span>](../../../language-reference/data-types/single-data-type.md) | <span data-ttu-id="6099f-126">F</span><span class="sxs-lookup"><span data-stu-id="6099f-126">F</span></span> | 
| <xref:System.Decimal> | [<span data-ttu-id="6099f-127">Decimal</span><span class="sxs-lookup"><span data-stu-id="6099f-127">Decimal</span></span>](../../../language-reference/data-types/decimal-data-type.md) | <span data-ttu-id="6099f-128">M</span><span class="sxs-lookup"><span data-stu-id="6099f-128">M</span></span> |

### <a name="examples"></a><span data-ttu-id="6099f-129">예제</span><span class="sxs-lookup"><span data-stu-id="6099f-129">Examples</span></span>

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

## <a name="blockexpression"></a><span data-ttu-id="6099f-130">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="6099f-130">BlockExpression</span></span>

<span data-ttu-id="6099f-131">경우 형식의 <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> 블록의 마지막 식의 형식에서 다른 개체, 형식 꺾쇠 괄호 안에 표시 됩니다 (`<` 고 `>`).</span><span class="sxs-lookup"><span data-stu-id="6099f-131">If the type of a <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="6099f-132">같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-132">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="6099f-133">예제</span><span class="sxs-lookup"><span data-stu-id="6099f-133">Examples</span></span>

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

## <a name="lambdaexpression"></a><span data-ttu-id="6099f-134">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="6099f-134">LambdaExpression</span></span>

<span data-ttu-id="6099f-135"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> 개체는 대리자 형식과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-135"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="6099f-136">람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).</span><span class="sxs-lookup"><span data-stu-id="6099f-136">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="6099f-137">예제</span><span class="sxs-lookup"><span data-stu-id="6099f-137">Examples</span></span>

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

## <a name="labelexpression"></a><span data-ttu-id="6099f-138">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="6099f-138">LabelExpression</span></span>

<span data-ttu-id="6099f-139"><xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> 개체 앞에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-139">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="6099f-140">`.Label` 토큰은 레이블의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-140">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="6099f-141">`.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-141">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="6099f-142">레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="6099f-142">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="6099f-143">예제</span><span class="sxs-lookup"><span data-stu-id="6099f-143">Examples</span></span>

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

## <a name="checked-operators"></a><span data-ttu-id="6099f-144">확인된 연산자</span><span class="sxs-lookup"><span data-stu-id="6099f-144">Checked Operators</span></span>

<span data-ttu-id="6099f-145">확인 된 연산자와 함께 표시 됩니다는 `#` 연산자 앞에 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-145">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="6099f-146">예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6099f-146">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="6099f-147">예제</span><span class="sxs-lookup"><span data-stu-id="6099f-147">Examples</span></span>

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