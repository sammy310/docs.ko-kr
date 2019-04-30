---
title: Visual Basic에서의 연산자 우선 순위
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
ms.openlocfilehash: 568927eb4759c214311ad34a5b45e28094dd80be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013532"
---
# <a name="operator-precedence-in-visual-basic"></a><span data-ttu-id="adb7c-102">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="adb7c-102">Operator Precedence in Visual Basic</span></span>
<span data-ttu-id="adb7c-103">각 파트 평가 되 고 호출 하는 미리 결정 된 순서 대로 확인 식에서 여러 작업 발생 *연산자 우선 순위*합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-103">When several operations occur in an expression, each part is evaluated and resolved in a predetermined order called *operator precedence*.</span></span>  
  
## <a name="precedence-rules"></a><span data-ttu-id="adb7c-104">우선 순위 규칙</span><span class="sxs-lookup"><span data-stu-id="adb7c-104">Precedence Rules</span></span>  
 <span data-ttu-id="adb7c-105">식에서 연산자는 둘 이상의 범주에서에 포함 하는 경우 다음 규칙에 따라 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-105">When expressions contain operators from more than one category, they are evaluated according to the following rules:</span></span>  
  
- <span data-ttu-id="adb7c-106">산술 연산 및 연결 연산자는 다음 섹션에 설명 된 우선 순위를 있고 모든 비교, 논리 보다 높은 우선 순위 및 비트 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-106">The arithmetic and concatenation operators have the order of precedence described in the following section, and all have greater precedence than the comparison, logical, and bitwise operators.</span></span>  
  
- <span data-ttu-id="adb7c-107">모든 비교 연산자는 동등한 우선 순위 및 논리 및 비트 연산자 보다 높은 우선 순위를 갖지만 산술 및 연결 연산자 보다 우선 순위가 모든 경우</span><span class="sxs-lookup"><span data-stu-id="adb7c-107">All comparison operators have equal precedence, and all have greater precedence than the logical and bitwise operators, but lower precedence than the arithmetic and concatenation operators.</span></span>  
  
- <span data-ttu-id="adb7c-108">논리 및 비트 연산자는 다음 섹션에 설명 된 우선 순위를 있고 모든 산술 연산, 연결 및 비교 연산자 보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-108">The logical and bitwise operators have the order of precedence described in the following section, and all have lower precedence than the arithmetic, concatenation, and comparison operators.</span></span>  
  
- <span data-ttu-id="adb7c-109">우선 순위가 같은 연산자는 왼쪽에서 오른쪽으로 계산 됩니다 식에서 나타나는 순서입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-109">Operators with equal precedence are evaluated left to right in the order in which they appear in the expression.</span></span>  
  
## <a name="precedence-order"></a><span data-ttu-id="adb7c-110">우선 순위</span><span class="sxs-lookup"><span data-stu-id="adb7c-110">Precedence Order</span></span>  
 <span data-ttu-id="adb7c-111">연산자 우선 순위 순서로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-111">Operators are evaluated in the following order of precedence:</span></span>  
  
### <a name="await-operator"></a><span data-ttu-id="adb7c-112">Await 연산자</span><span class="sxs-lookup"><span data-stu-id="adb7c-112">Await Operator</span></span>  
 <span data-ttu-id="adb7c-113">Await</span><span class="sxs-lookup"><span data-stu-id="adb7c-113">Await</span></span>  
  
### <a name="arithmetic-and-concatenation-operators"></a><span data-ttu-id="adb7c-114">산술 연산 및 연결 연산자</span><span class="sxs-lookup"><span data-stu-id="adb7c-114">Arithmetic and Concatenation Operators</span></span>  
 <span data-ttu-id="adb7c-115">지 수 (`^`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-115">Exponentiation (`^`)</span></span>  
  
 <span data-ttu-id="adb7c-116">단항 id 및 부정 연산자 (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-116">Unary identity and negation (`+`, `–`)</span></span>  
  
 <span data-ttu-id="adb7c-117">곱하기와 부동 소수점 나누기 (`*`, `/`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-117">Multiplication and floating-point division (`*`, `/`)</span></span>  
  
 <span data-ttu-id="adb7c-118">정수 나누기 (`\`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-118">Integer division (`\`)</span></span>  
  
 <span data-ttu-id="adb7c-119">모듈러스 산술 (`Mod`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-119">Modulus arithmetic (`Mod`)</span></span>  
  
 <span data-ttu-id="adb7c-120">더하기 및 빼기 (`+`, `–`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-120">Addition and subtraction (`+`, `–`)</span></span>  
  
 <span data-ttu-id="adb7c-121">문자열 연결 (`&`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-121">String concatenation (`&`)</span></span>  
  
 <span data-ttu-id="adb7c-122">산술 비트 시프트 (`<<`, `>>`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-122">Arithmetic bit shift (`<<`, `>>`)</span></span>  
  
### <a name="comparison-operators"></a><span data-ttu-id="adb7c-123">비교 연산자</span><span class="sxs-lookup"><span data-stu-id="adb7c-123">Comparison Operators</span></span>  
 <span data-ttu-id="adb7c-124">모든 비교 연산자 (`=`, `<>`, `<`, `<=`, `>`를 `>=`, `Is`를 `IsNot`를 `Like`, `TypeOf`... `Is`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-124">All comparison operators (`=`, `<>`, `<`, `<=`, `>`, `>=`, `Is`, `IsNot`, `Like`, `TypeOf`...`Is`)</span></span>  
  
### <a name="logical-and-bitwise-operators"></a><span data-ttu-id="adb7c-125">논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="adb7c-125">Logical and Bitwise Operators</span></span>  
 <span data-ttu-id="adb7c-126">부정 (`Not`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-126">Negation (`Not`)</span></span>  
  
 <span data-ttu-id="adb7c-127">함께 (`And`, `AndAlso`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-127">Conjunction (`And`, `AndAlso`)</span></span>  
  
 <span data-ttu-id="adb7c-128">포함 논리합 (`Or`, `OrElse`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-128">Inclusive disjunction (`Or`, `OrElse`)</span></span>  
  
 <span data-ttu-id="adb7c-129">배타적 논리합 (`Xor`)</span><span class="sxs-lookup"><span data-stu-id="adb7c-129">Exclusive disjunction (`Xor`)</span></span>  
  
### <a name="comments"></a><span data-ttu-id="adb7c-130">설명</span><span class="sxs-lookup"><span data-stu-id="adb7c-130">Comments</span></span>  
 <span data-ttu-id="adb7c-131">`=` 연산자는 같음 비교 연산자만, 대입 연산자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-131">The `=` operator is only the equality comparison operator, not the assignment operator.</span></span>  
  
 <span data-ttu-id="adb7c-132">문자열 연결 연산자 (`&`) 산술 연산자, 되지 않지만 산술 연산자를 사용 하 여 그룹화는 우선 순위에서입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-132">The string concatenation operator (`&`) is not an arithmetic operator, but in precedence it is grouped with the arithmetic operators.</span></span>  
  
 <span data-ttu-id="adb7c-133">합니다 `Is` 고 `IsNot` 연산자는 개체 참조 비교 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-133">The `Is` and `IsNot` operators are object reference comparison operators.</span></span> <span data-ttu-id="adb7c-134">두 개체의 값을 비교 하지 않습니다. 이러한 두 개의 개체 변수가 같은 개체 인스턴스를 참조 하는지 여부 확인에이 옵션을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-134">They do not compare the values of two objects; they check only to determine whether two object variables refer to the same object instance.</span></span>  
  
## <a name="associativity"></a><span data-ttu-id="adb7c-135">associativity</span><span class="sxs-lookup"><span data-stu-id="adb7c-135">Associativity</span></span>  
 <span data-ttu-id="adb7c-136">우선 순위가 같은 연산자는 곱하기 및 나누기, 예를 들어 식에서 함께 표시 되 면 컴파일러도 왼쪽에서 오른쪽으로 각 작업을 평가 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-136">When operators of equal precedence appear together in an expression, for example multiplication and division, the compiler evaluates each operation as it encounters it from left to right.</span></span> <span data-ttu-id="adb7c-137">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-137">The following example illustrates this.</span></span>  
  
```  
Dim n1 As Integer = 96 / 8 / 4  
Dim n2 As Integer = (96 / 8) / 4  
Dim n3 As Integer = 96 / (8 / 4)  
```  
  
 <span data-ttu-id="adb7c-138">첫 번째 식이 96 나누기 / 8 (12 결과) 및 다음 나누기 12 / 결과 3 4입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-138">The first expression evaluates the division 96 / 8 (which results in 12) and then the division 12 / 4, which results in three.</span></span> <span data-ttu-id="adb7c-139">에 대 한 작업으로 계산 하므로 `n1` 왼쪽에서 오른쪽으로 평가 때 동일한 순서에 대 한 명시적으로 표시 됩니다 `n2`합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-139">Because the compiler evaluates the operations for `n1` from left to right, the evaluation is the same when that order is explicitly indicated for `n2`.</span></span> <span data-ttu-id="adb7c-140">둘 다 `n1` 고 `n2` 의 결과는 3입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-140">Both `n1` and `n2` have a result of three.</span></span> <span data-ttu-id="adb7c-141">반면, `n3` 괄호 8을 평가 하는 컴파일러가 있으므로 결과는 48에 / 4 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-141">By contrast, `n3` has a result of 48, because the parentheses force the compiler to evaluate 8 / 4 first.</span></span>  
  
 <span data-ttu-id="adb7c-142">이 동작으로 인해 연산자 있다고 *왼쪽 결합형* Visual Basic의 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-142">Because of this behavior, operators are said to be *left associative* in Visual Basic.</span></span>  
  
## <a name="overriding-precedence-and-associativity"></a><span data-ttu-id="adb7c-143">재정의 우선 순위 및 결합성</span><span class="sxs-lookup"><span data-stu-id="adb7c-143">Overriding Precedence and Associativity</span></span>  
 <span data-ttu-id="adb7c-144">다른 사용자가 하기 전에 평가할 식의 일부를 적용할 괄호를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-144">You can use parentheses to force some parts of an expression to be evaluated before others.</span></span> <span data-ttu-id="adb7c-145">이 우선 순위 순서와 왼쪽된 결합성 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-145">This can override both the order of precedence and the left associativity.</span></span> <span data-ttu-id="adb7c-146">Visual Basic에는 항상 외부 보다 먼저 괄호로 묶이지 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-146">Visual Basic always performs operations that are enclosed in parentheses before those outside.</span></span> <span data-ttu-id="adb7c-147">그러나 괄호 안에서 유지 일반 우선 순위와 결합성 괄호 안에서 괄호를 사용 하지 않는 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-147">However, within parentheses, it maintains ordinary precedence and associativity, unless you use parentheses within the parentheses.</span></span> <span data-ttu-id="adb7c-148">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="adb7c-148">The following example illustrates this.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="adb7c-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="adb7c-149">See also</span></span>

- [<span data-ttu-id="adb7c-150">= 연산자</span><span class="sxs-lookup"><span data-stu-id="adb7c-150">= Operator</span></span>](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [<span data-ttu-id="adb7c-151">Is 연산자</span><span class="sxs-lookup"><span data-stu-id="adb7c-151">Is Operator</span></span>](../../../visual-basic/language-reference/operators/is-operator.md)
- [<span data-ttu-id="adb7c-152">IsNot 연산자</span><span class="sxs-lookup"><span data-stu-id="adb7c-152">IsNot Operator</span></span>](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [<span data-ttu-id="adb7c-153">Like 연산자</span><span class="sxs-lookup"><span data-stu-id="adb7c-153">Like Operator</span></span>](../../../visual-basic/language-reference/operators/like-operator.md)
- [<span data-ttu-id="adb7c-154">TypeOf 연산자</span><span class="sxs-lookup"><span data-stu-id="adb7c-154">TypeOf Operator</span></span>](../../../visual-basic/language-reference/operators/typeof-operator.md)
- [<span data-ttu-id="adb7c-155">Await 연산자</span><span class="sxs-lookup"><span data-stu-id="adb7c-155">Await Operator</span></span>](../../../visual-basic/language-reference/operators/await-operator.md)
- [<span data-ttu-id="adb7c-156">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="adb7c-156">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="adb7c-157">연산자 및 식</span><span class="sxs-lookup"><span data-stu-id="adb7c-157">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
