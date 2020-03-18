---
title: DebugView 속성이 사용하는 구문(C#)
description: 식 트리의 문자열 표현을 생성하기 위해 DebugView 속성이 사용하는 특수 구문을 설명합니다.
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: ba695fc808108c49a4eee3c70a305b24c91769d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "67661724"
---
# <a name="debugview-syntax"></a><span data-ttu-id="472a9-103">`DebugView` 구문</span><span class="sxs-lookup"><span data-stu-id="472a9-103">`DebugView` syntax</span></span>

<span data-ttu-id="472a9-104">`DebugView` 속성(디버깅할 때만 사용 가능)은 식 트리의 문자열 렌더링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-104">The `DebugView` property (available only when debugging) provides a string rendering of expression trees.</span></span> <span data-ttu-id="472a9-105">대부분의 구문은 이해하기 쉽습니다. 특별한 경우는 다음 섹션에서 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-105">Most of the syntax is fairly straightforward to understand; the special cases are described in the following sections.</span></span>

<span data-ttu-id="472a9-106">각 예제 다음에는 `DebugView`를 포함한 블록 주석이 이어집니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-106">Each example is followed by a block comment, containing the `DebugView`.</span></span>

## <a name="parameterexpression"></a><span data-ttu-id="472a9-107">ParameterExpression</span><span class="sxs-lookup"><span data-stu-id="472a9-107">ParameterExpression</span></span>

<span data-ttu-id="472a9-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> 변수 이름의 시작 부분에 `$` 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-108"><xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> variable names are displayed with a `$` symbol at the beginning.</span></span>

<span data-ttu-id="472a9-109">매개 변수에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `$var1` 또는 `$var2`).</span><span class="sxs-lookup"><span data-stu-id="472a9-109">If a parameter does not have a name, it is assigned an automatically generated name, such as `$var1` or `$var2`.</span></span>

### <a name="examples"></a><span data-ttu-id="472a9-110">예</span><span class="sxs-lookup"><span data-stu-id="472a9-110">Examples</span></span>

```csharp
ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");
/*
    $num
*/

ParameterExpression numParam =  Expression.Parameter(typeof(int));
/*
    $var1
*/
```

## <a name="constantexpression"></a><span data-ttu-id="472a9-111">ConstantExpression</span><span class="sxs-lookup"><span data-stu-id="472a9-111">ConstantExpression</span></span>

<span data-ttu-id="472a9-112">정수 값, 문자열 및 <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType>을 나타내는 `null` 개체의 경우 상수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-112">For <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType> objects that represent integer values, strings, and `null`, the value of the constant is displayed.</span></span>

<span data-ttu-id="472a9-113">표준 접미사인 C# 리터럴이 있는 숫자 형식의 경우 접미사가 값에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-113">For numeric types that have standard suffixes as C# literals, the suffix is added to the value.</span></span> <span data-ttu-id="472a9-114">다음 표에서는 다양한 숫자 형식과 연결된 접미사를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-114">The following table shows the suffixes associated with various numeric types.</span></span>

| <span data-ttu-id="472a9-115">형식</span><span class="sxs-lookup"><span data-stu-id="472a9-115">Type</span></span> | <span data-ttu-id="472a9-116">키워드</span><span class="sxs-lookup"><span data-stu-id="472a9-116">Keyword</span></span> | <span data-ttu-id="472a9-117">접미사</span><span class="sxs-lookup"><span data-stu-id="472a9-117">Suffix</span></span> |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [<span data-ttu-id="472a9-118">uint</span><span class="sxs-lookup"><span data-stu-id="472a9-118">uint</span></span>](../../../language-reference/builtin-types/integral-numeric-types.md) | <span data-ttu-id="472a9-119">U</span><span class="sxs-lookup"><span data-stu-id="472a9-119">U</span></span> |
| <xref:System.Int64?displayProperty=nameWithType> | [<span data-ttu-id="472a9-120">long</span><span class="sxs-lookup"><span data-stu-id="472a9-120">long</span></span>](../../../language-reference/builtin-types/integral-numeric-types.md) | <span data-ttu-id="472a9-121">L</span><span class="sxs-lookup"><span data-stu-id="472a9-121">L</span></span> |
| <xref:System.UInt64?displayProperty=nameWithType> | [<span data-ttu-id="472a9-122">ulong</span><span class="sxs-lookup"><span data-stu-id="472a9-122">ulong</span></span>](../../../language-reference/builtin-types/integral-numeric-types.md) | <span data-ttu-id="472a9-123">UL</span><span class="sxs-lookup"><span data-stu-id="472a9-123">UL</span></span> |
| <xref:System.Double?displayProperty=nameWithType> | [<span data-ttu-id="472a9-124">double</span><span class="sxs-lookup"><span data-stu-id="472a9-124">double</span></span>](../../../language-reference/builtin-types/floating-point-numeric-types.md) | <span data-ttu-id="472a9-125">D</span><span class="sxs-lookup"><span data-stu-id="472a9-125">D</span></span> |
| <xref:System.Single?displayProperty=nameWithType> | [<span data-ttu-id="472a9-126">float</span><span class="sxs-lookup"><span data-stu-id="472a9-126">float</span></span>](../../../language-reference/builtin-types/floating-point-numeric-types.md) | <span data-ttu-id="472a9-127">F</span><span class="sxs-lookup"><span data-stu-id="472a9-127">F</span></span> |
| <xref:System.Decimal?displayProperty=nameWithType> | [<span data-ttu-id="472a9-128">decimal</span><span class="sxs-lookup"><span data-stu-id="472a9-128">decimal</span></span>](../../../language-reference/builtin-types/floating-point-numeric-types.md) | <span data-ttu-id="472a9-129">M</span><span class="sxs-lookup"><span data-stu-id="472a9-129">M</span></span> |

### <a name="examples"></a><span data-ttu-id="472a9-130">예</span><span class="sxs-lookup"><span data-stu-id="472a9-130">Examples</span></span>

```csharp
int num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10
*/

double num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10D
*/
```

## <a name="blockexpression"></a><span data-ttu-id="472a9-131">BlockExpression</span><span class="sxs-lookup"><span data-stu-id="472a9-131">BlockExpression</span></span>

<span data-ttu-id="472a9-132"><xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> 개체의 형식이 블록에 있는 마지막 식의 형식과 다를 경우 형식은 꺾쇠 괄호(`<` 및 `>`) 안에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-132">If the type of a <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> object differs from the type of the last expression in the block, the type is displayed within angle brackets (`<` and `>`).</span></span> <span data-ttu-id="472a9-133">같을 경우 <xref:System.Linq.Expressions.BlockExpression> 개체의 형식이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-133">Otherwise, the type of the <xref:System.Linq.Expressions.BlockExpression> object is not displayed.</span></span>

### <a name="examples"></a><span data-ttu-id="472a9-134">예</span><span class="sxs-lookup"><span data-stu-id="472a9-134">Examples</span></span>

```csharp
BlockExpression block = Expression.Block(Expression.Constant("test"));
/*
    .Block() {
        "test"
    }
*/

BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));
/*
    .Block<System.Object>() {
        "test"
    }
*/
```

## <a name="lambdaexpression"></a><span data-ttu-id="472a9-135">LambdaExpression</span><span class="sxs-lookup"><span data-stu-id="472a9-135">LambdaExpression</span></span>

<span data-ttu-id="472a9-136"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> 개체는 대리자 형식과 함께 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-136"><xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> objects are displayed together with their delegate types.</span></span>

<span data-ttu-id="472a9-137">람다 식에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Lambda1` 또는 `#Lambda2`).</span><span class="sxs-lookup"><span data-stu-id="472a9-137">If a lambda expression does not have a name, it is assigned an automatically generated name, such as `#Lambda1` or `#Lambda2`.</span></span>

### <a name="examples"></a><span data-ttu-id="472a9-138">예</span><span class="sxs-lookup"><span data-stu-id="472a9-138">Examples</span></span>

```csharp
LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));
/*
    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
        1
    }
*/

LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);
/*
    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
        1
    }
*/
```

## <a name="labelexpression"></a><span data-ttu-id="472a9-139">LabelExpression</span><span class="sxs-lookup"><span data-stu-id="472a9-139">LabelExpression</span></span>

<span data-ttu-id="472a9-140"><xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> 개체의 기본값을 지정하면 이 값은 <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> 개체 앞에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-140">If you specify a default value for the <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType> object, this value is displayed before the <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="472a9-141">`.Label` 토큰은 레이블의 시작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-141">The `.Label` token indicates the start of the label.</span></span> <span data-ttu-id="472a9-142">`.LabelTarget` 토큰은 이동할 대상의 목적지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-142">The `.LabelTarget` token indicates the destination of the target to jump to.</span></span>

<span data-ttu-id="472a9-143">레이블에 이름이 없으면 자동으로 생성된 이름이 할당됩니다(예: `#Label1` 또는 `#Label2`).</span><span class="sxs-lookup"><span data-stu-id="472a9-143">If a label does not have a name, it is assigned an automatically generated name, such as `#Label1` or `#Label2`.</span></span>

### <a name="examples"></a><span data-ttu-id="472a9-144">예</span><span class="sxs-lookup"><span data-stu-id="472a9-144">Examples</span></span>

```csharp
LabelTarget target = Expression.Label(typeof(int), "SampleLabel");
BlockExpression block = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
);
/*
    .Block() {
        .Goto SampleLabel { 0 };
        .Label
            -1
        .LabelTarget SampleLabel:
    }
*/

LabelTarget target = Expression.Label();
BlockExpression block = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
);
/*
    .Block() {
        .Goto #Label1 { };
        .Label
        .LabelTarget #Label1:
    }
*/
```

## <a name="checked-operators"></a><span data-ttu-id="472a9-145">확인된 연산자</span><span class="sxs-lookup"><span data-stu-id="472a9-145">Checked Operators</span></span>

<span data-ttu-id="472a9-146">확인된 연산자는 연산자 앞에 `#` 기호가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-146">Checked operators are displayed with the `#` symbol in front of the operator.</span></span> <span data-ttu-id="472a9-147">예를 들어 확인된 더하기 연산자는 `#+`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="472a9-147">For example, the checked addition operator is displayed as `#+`.</span></span>

### <a name="examples"></a><span data-ttu-id="472a9-148">예</span><span class="sxs-lookup"><span data-stu-id="472a9-148">Examples</span></span>

```csharp
Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));
/*
    1 #+ 2
*/

Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));
/*
    #(System.Int32)10D
*/
```
