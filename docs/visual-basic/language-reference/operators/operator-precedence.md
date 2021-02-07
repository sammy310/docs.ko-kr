---
description: '에 대 한 자세한 정보: 연산자 우선 순위 Visual Basic'
title: 연산자 우선 순위
ms.date: 07/20/2015
helpviewer_keywords:
- arithmetic operators [Visual Basic], precedence
- operator precedence
- logical operators [Visual Basic], precedence
- operators [Visual Basic], associativity
- operators [Visual Basic], resolution
- associativity of operators [Visual Basic]
- operators [Visual Basic], precedence
- precedence [Visual Basic], of operators
- comparison operators [Visual Basic], precedence
- math operators [Visual Basic]
- order of precedence
ms.assetid: cbbdb282-f572-458e-a520-008a675f8063
ms.openlocfilehash: 7aa4677549328d450834f3a1ecb047d405893f69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99665291"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="ebbf3-103">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="ebbf3-103">Operator Precedence in Visual Basic</span></span>

<span data-ttu-id="ebbf3-104">식에서 여러 연산이 수행 될 때 각 부분은 *연산자 우선 순위* 라는 미리 결정 된 순서에 따라 평가 되 고 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-104">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>

## <a name="precedence-rules"></a><span data-ttu-id="ebbf3-105">선행 규칙</span><span class="sxs-lookup"><span data-stu-id="ebbf3-105">Precedence Rules</span></span>

 <span data-ttu-id="ebbf3-106">식이 둘 이상의 범주에 있는 연산자를 포함 하는 경우 다음 규칙에 따라 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-106">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>

- <span data-ttu-id="ebbf3-107">산술 및 연결 연산자는 다음 섹션에서 설명 하는 우선 순위를 가지 며 모두 비교, 논리 및 비트 연산자 보다 우선 순위가 높습니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-107">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>

- <span data-ttu-id="ebbf3-108">모든 비교 연산자는 동일한 우선 순위를 가지 며 모든 비교 연산자는 논리 및 비트 연산자 보다 우선 순위가 크므로 산술 연산자와 연결 연산자 보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-108">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>

- <span data-ttu-id="ebbf3-109">논리 및 비트 연산자는 다음 섹션에서 설명 하는 우선 순위를 가지 며 모두 산술, 연결 및 비교 연산자 보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-109">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>

- <span data-ttu-id="ebbf3-110">우선 순위가 같은 연산자는 식에 표시 되는 순서 대로 왼쪽에서 오른쪽으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-110">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>

## <a name="precedence-order"></a><span data-ttu-id="ebbf3-111">우선 순위</span><span class="sxs-lookup"><span data-stu-id="ebbf3-111">Precedence Order</span></span>

 <span data-ttu-id="ebbf3-112">연산자는 다음과 같은 우선 순위에 따라 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-112">Operators are evaluated in the following order of precedence:</span></span>

### <a name="await-operator"></a><span data-ttu-id="ebbf3-113">Await 연산자</span><span class="sxs-lookup"><span data-stu-id="ebbf3-113">Await Operator</span></span>

 <span data-ttu-id="ebbf3-114">W</span><span class="sxs-lookup"><span data-stu-id="ebbf3-114">Await</span></span>

### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="ebbf3-115">산술 및 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="ebbf3-115">Arithmetic and Concatenation Operators</span></span>

 <span data-ttu-id="ebbf3-116">지 각 ( `^` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-116">Exponentiation (`^`)</span></span>

 <span data-ttu-id="ebbf3-117">단항 id 및 부정 ( `+` , `–` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-117">Unary identity and negation (`+`, `–`)</span></span>

 <span data-ttu-id="ebbf3-118">곱하기 및 부동 소수점 나누기 ( `*` , `/` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-118">Multiplication and floating-point division (`*`, `/`)</span></span>

 <span data-ttu-id="ebbf3-119">정수 나누기 ( `\` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-119">Integer division (`\`)</span></span>

 <span data-ttu-id="ebbf3-120">모듈식 산술 ( `Mod` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-120">Modular arithmetic (`Mod`)</span></span>

 <span data-ttu-id="ebbf3-121">더하기 및 빼기 ( `+` , `–` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-121">Addition and subtraction (`+`, `–`)</span></span>

 <span data-ttu-id="ebbf3-122">문자열 연결 ( `&` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-122">String concatenation (`&`)</span></span>

 <span data-ttu-id="ebbf3-123">산술 비트 시프트 ( `<<` , `>>` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-123">Arithmetic bit shift (`<<`, `>>`)</span></span>

### <a name="comparison-operators"></a><span data-ttu-id="ebbf3-124">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="ebbf3-124">Comparison Operators</span></span>

 <span data-ttu-id="ebbf3-125">모든 비교 연산자 ( `=` , `<>` , `<` , `<=` ,,,,, `>` `>=` `Is` `IsNot` `Like` , `TypeOf` ... `Is` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-125">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>

### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="ebbf3-126">논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="ebbf3-126">Logical and Bitwise Operators</span></span>

 <span data-ttu-id="ebbf3-127">부정 ( `Not` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-127">Negation (`Not`)</span></span>

 <span data-ttu-id="ebbf3-128">결합 ( `And` , `AndAlso` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-128">Conjunction (`And`, `AndAlso`)</span></span>

 <span data-ttu-id="ebbf3-129">포함 분리 ( `Or` , `OrElse` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-129">Inclusive disjunction (`Or`, `OrElse`)</span></span>

 <span data-ttu-id="ebbf3-130">배타적 분리 ( `Xor` )</span><span class="sxs-lookup"><span data-stu-id="ebbf3-130">Exclusive disjunction (`Xor`)</span></span>

### <a name="comments"></a><span data-ttu-id="ebbf3-131">설명</span><span class="sxs-lookup"><span data-stu-id="ebbf3-131">Comments</span></span>

 <span data-ttu-id="ebbf3-132">`=`연산자는 대입 연산자가 아닌 같음 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-132">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>

 <span data-ttu-id="ebbf3-133">문자열 연결 연산자 ( `&` )는 산술 연산자가 아니지만 우선 순위는 산술 연산자와 함께 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-133">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>

 <span data-ttu-id="ebbf3-134">`Is`및 `IsNot` 연산자는 개체 참조 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-134">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="ebbf3-135">두 개체의 값을 비교 하지 않습니다. 두 개체 변수가 동일한 개체 인스턴스를 참조 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-135">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>

## <a name="associativity"></a><span data-ttu-id="ebbf3-136">associativity</span><span class="sxs-lookup"><span data-stu-id="ebbf3-136">Associativity</span></span>

 <span data-ttu-id="ebbf3-137">곱하기 및 나누기와 같이 우선 순위가 같은 연산자가 식에 함께 표시 되는 경우 컴파일러는 각 작업을 왼쪽에서 오른쪽으로 발견할 때 각 작업을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-137">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="ebbf3-138">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-138">The following example illustrates this.</span></span>

```vb
Dim n1 As Integer = 96 / 8 / 4
Dim n2 As Integer = (96 / 8) / 4
Dim n3 As Integer = 96 / (8 / 4)
```

 <span data-ttu-id="ebbf3-139">첫 번째 식은 나누기 96/8 (결과 12)을 평가한 다음 나누기 12/4를 계산 하 여 3을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-139">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="ebbf3-140">컴파일러는에 대 한 작업을 왼쪽에서 오른쪽으로 평가 하기 때문에 `n1` 에 대 한 순서가 명시적으로 지정 된 경우에도 계산이 동일 합니다 `n2` .</span><span class="sxs-lookup"><span data-stu-id="ebbf3-140">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="ebbf3-141">및는 모두 `n1` `n2` 3의 결과를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-141">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="ebbf3-142">이와 대조적으로 `n3` 괄호를 적용 하면 컴파일러가 8/4를 먼저 평가 하기 때문에 48이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-142">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>

 <span data-ttu-id="ebbf3-143">이 동작으로 인해 연산자는 Visual Basic에서 *왼쪽 결합성* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-143">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>

## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="ebbf3-144">우선 순위 및 결합성 재정의</span><span class="sxs-lookup"><span data-stu-id="ebbf3-144">Overriding Precedence and Associativity</span></span>

 <span data-ttu-id="ebbf3-145">괄호를 사용 하 여 식의 일부 부분이 다른 식 보다 먼저 계산 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-145">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="ebbf3-146">이는 우선 순위와 왼쪽 결합성의 순서를 모두 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-146">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="ebbf3-147">Visual Basic는 항상 괄호 안에 포함 된 작업을 외부에서 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-147">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="ebbf3-148">그러나 괄호 안에 괄호를 사용 하지 않으면 괄호 안에 일반적인 우선 순위와 결합성이 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-148">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="ebbf3-149">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ebbf3-149">The following example illustrates this.</span></span>

```vb
Dim a, b, c, d, e, f, g As Double
a = 8.0
b = 3.0
c = 4.0
d = 2.0
e = 1.0
f = a - b + c / d * e
' The preceding line sets f to 7.0. Because of natural operator
' precedence and associativity, it is exactly equivalent to the
' following line.
f = (a - b) + ((c / d) * e)
' The following line overrides the natural operator precedence
' and left associativity.
g = (a - (b + c)) / (d * e)
' The preceding line sets g to 0.5.
```

## <a name="see-also"></a><span data-ttu-id="ebbf3-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebbf3-150">See also</span></span>

- [<span data-ttu-id="ebbf3-151">= 연산자</span><span class="sxs-lookup"><span data-stu-id="ebbf3-151">= Operator</span></span>](assignment-operator.md)
- [<span data-ttu-id="ebbf3-152">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="ebbf3-152">Is Operator</span></span>](is-operator.md)
- [<span data-ttu-id="ebbf3-153">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="ebbf3-153">IsNot Operator</span></span>](isnot-operator.md)
- [<span data-ttu-id="ebbf3-154">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="ebbf3-154">Like Operator</span></span>](like-operator.md)
- [<span data-ttu-id="ebbf3-155">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="ebbf3-155">TypeOf Operator</span></span>](typeof-operator.md)
- [<span data-ttu-id="ebbf3-156">Await 연산자</span><span class="sxs-lookup"><span data-stu-id="ebbf3-156">Await Operator</span></span>](await-operator.md)
- [<span data-ttu-id="ebbf3-157">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="ebbf3-157">Operators Listed by Functionality</span></span>](operators-listed-by-functionality.md)
- [<span data-ttu-id="ebbf3-158">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="ebbf3-158">Operators and Expressions</span></span>](../../programming-guide/language-features/operators-and-expressions/index.md)
