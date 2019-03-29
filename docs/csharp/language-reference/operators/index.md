---
title: 'C# 연산자'
ms.date: 04/04/2018
f1_keywords:
  - cs.operators
helpviewer_keywords:
  - 'boolean operators [C#]'
  - 'expressions [C#], operators'
  - 'logical operators [C#]'
  - 'operators [C#]'
  - 'Visual C#, operators'
  - 'indirection operators [C#]'
  - 'assignment operators [C#]'
  - 'shift operators [C#]'
  - 'relational operators [C#]'
  - 'bitwise operators [C#]'
  - 'address operators [C#]'
  - 'keywords [C#], operators'
  - 'arithmetic operators [C#]'
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
---
# <a name="c-operators"></a><span data-ttu-id="bf966-102">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-102">C# operators</span></span>

<span data-ttu-id="bf966-103">C#에서는 많은 연산자를 제공하며, 이러한 연산자는 식에서 수행할 연산(수학, 인덱싱, 함수 호출 등)을 지정하는 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-103">C# provides many operators, which are symbols that specify which operations (math, indexing, function call, etc.) to perform in an expression.</span></span> <span data-ttu-id="bf966-104">많은 연산자를 [오버로드](../../programming-guide/statements-expressions-operators/overloadable-operators.md)하여 사용자 정의 형식에 적용되는 경우의 의미를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-104">You can [overload](../../programming-guide/statements-expressions-operators/overloadable-operators.md) many operators to change their meaning when applied to a user-defined type.</span></span>

<span data-ttu-id="bf966-105">정수 계열 형식에 대한 연산(예: `==`, `!=`, `<`, `>`, `&`, `|`)은 일반적으로 열거형(`enum`에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-105">Operations on integral types (such as `==`, `!=`, `<`, `>`, `&`, `|`) are generally allowed on enumeration (`enum`) types.</span></span>

<span data-ttu-id="bf966-106">아래 섹션에서는 우선 순위가 가장 높은 것부터 시작하여 순서대로 C# 연산자를 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-106">The sections below list the C# operators starting with the highest precedence to the lowest.</span></span> <span data-ttu-id="bf966-107">각 섹션 내의 연산자는 동일한 우선 순위 수준을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-107">The operators within each section share the same precedence level.</span></span>

## <a name="primary-operators"></a><span data-ttu-id="bf966-108">기본 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-108">Primary operators</span></span>

<span data-ttu-id="bf966-109">우선 순위가 가장 높은 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-109">These are the highest precedence operators.</span></span>

<span data-ttu-id="bf966-110">[x.y](member-access-operator.md) – 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="bf966-110">[x.y](member-access-operator.md) – member access.</span></span>

<span data-ttu-id="bf966-111">[x?.y](null-conditional-operators.md) – null 조건부 멤버 액세스</span><span class="sxs-lookup"><span data-stu-id="bf966-111">[x?.y](null-conditional-operators.md) – null conditional member access.</span></span> <span data-ttu-id="bf966-112">왼쪽 피연산자가 `null`로 확인되면 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-112">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="bf966-113">[x?[y]](null-conditional-operators.md) - null 조건부 인덱스 액세스</span><span class="sxs-lookup"><span data-stu-id="bf966-113">[x?[y]](null-conditional-operators.md) - null conditional index access.</span></span> <span data-ttu-id="bf966-114">왼쪽 피연산자가 `null`로 확인되면 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-114">Returns `null` if the left-hand operand evaluates to `null`.</span></span>

<span data-ttu-id="bf966-115">[f(x)](invocation-operator.md) – 함수 호출</span><span class="sxs-lookup"><span data-stu-id="bf966-115">[f(x)](invocation-operator.md) – function invocation.</span></span>

<span data-ttu-id="bf966-116">[a&#91;x&#93;](index-operator.md) – 집계 개체 인덱싱</span><span class="sxs-lookup"><span data-stu-id="bf966-116">[a&#91;x&#93;](index-operator.md) – aggregate object indexing.</span></span>

<span data-ttu-id="bf966-117">[x++](arithmetic-operators.md#increment-operator-) – 후위 증가.</span><span class="sxs-lookup"><span data-stu-id="bf966-117">[x++](arithmetic-operators.md#increment-operator-) – postfix increment.</span></span> <span data-ttu-id="bf966-118">x의 값을 반환하고 1보다 큰 x 값(일반적으로 정수 1을 더함)으로 스토리지 위치를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-118">Returns the value of x and then updates the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="bf966-119">[x--](arithmetic-operators.md#decrement-operator---) –  후위 감소.</span><span class="sxs-lookup"><span data-stu-id="bf966-119">[x--](arithmetic-operators.md#decrement-operator---) –  postfix decrement.</span></span> <span data-ttu-id="bf966-120">x의 값을 반환하고 1보다 작은 x 값(일반적으로 정수 1을 뺌)으로 스토리지 위치를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-120">Returns the value of x and then updates the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="bf966-121">[new](../keywords/new-operator.md) – 형식 인스턴스화.</span><span class="sxs-lookup"><span data-stu-id="bf966-121">[new](../keywords/new-operator.md) – type instantiation.</span></span>

<span data-ttu-id="bf966-122">[typeof](../keywords/typeof.md) – 피연산자를 나타내는 <xref:System.Type> 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-122">[typeof](../keywords/typeof.md) – returns the <xref:System.Type> object representing the operand.</span></span>

<span data-ttu-id="bf966-123">[checked](../keywords/checked.md) – 정수 연산에 오버플로 검사를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-123">[checked](../keywords/checked.md) – enables overflow checking for integer operations.</span></span>

<span data-ttu-id="bf966-124">[unchecked](../keywords/unchecked.md) – 정수 연산에 오버플로 검사를 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-124">[unchecked](../keywords/unchecked.md) – disables overflow checking for integer operations.</span></span> <span data-ttu-id="bf966-125">이것은 기본 컴파일러 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-125">This is the default compiler behavior.</span></span>

<span data-ttu-id="bf966-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – T 형식의 기본값을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-126">[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – produces the default value of type T.</span></span>

<span data-ttu-id="bf966-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – 대리자 인스턴스를 선언하고 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-127">[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – declares and returns a delegate instance.</span></span>

<span data-ttu-id="bf966-128">[sizeof](../keywords/sizeof.md) – 형식 피연산자의 크기(바이트)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-128">[sizeof](../keywords/sizeof.md) – returns the size in bytes of the type operand.</span></span>

<span data-ttu-id="bf966-129">[->](dereference-operator.md) – 멤버 액세스와 결합된 포인터 역참조입니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-129">[->](dereference-operator.md) – pointer dereferencing combined with member access.</span></span>

## <a name="unary-operators"></a><span data-ttu-id="bf966-130">단항 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-130">Unary operators</span></span>

<span data-ttu-id="bf966-131">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-131">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-132">[+x](addition-operator.md) – x의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-132">[+x](addition-operator.md) – returns the value of x.</span></span>

<span data-ttu-id="bf966-133">[-x](subtraction-operator.md) – 숫자 부정</span><span class="sxs-lookup"><span data-stu-id="bf966-133">[-x](subtraction-operator.md) – numeric negation.</span></span>

<span data-ttu-id="bf966-134">[\!x](logical-negation-operator.md) – 논리 부정</span><span class="sxs-lookup"><span data-stu-id="bf966-134">[\!x](logical-negation-operator.md) – logical negation.</span></span>

<span data-ttu-id="bf966-135">[~x](bitwise-complement-operator.md) – 비트 보수</span><span class="sxs-lookup"><span data-stu-id="bf966-135">[~x](bitwise-complement-operator.md) – bitwise complement.</span></span>

<span data-ttu-id="bf966-136">[++x](arithmetic-operators.md#increment-operator-) – 전위 증가</span><span class="sxs-lookup"><span data-stu-id="bf966-136">[++x](arithmetic-operators.md#increment-operator-) – prefix increment.</span></span> <span data-ttu-id="bf966-137">1보다 큰 x 값(일반적으로 정수 1을 더함)으로 스토리지 위치를 업데이트한 후 x의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-137">Returns the value of x after updating the storage location with the value of x that is one greater (typically adds the integer 1).</span></span>

<span data-ttu-id="bf966-138">[--x](arithmetic-operators.md#decrement-operator---) – 전위 감소</span><span class="sxs-lookup"><span data-stu-id="bf966-138">[--x](arithmetic-operators.md#decrement-operator---) – prefix decrement.</span></span> <span data-ttu-id="bf966-139">1보다 작은 x 값(일반적으로 정수 1을 뺌)으로 스토리지 위치를 업데이트한 후 x의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-139">Returns the value of x after updating the storage location with the value of x that is one less (typically subtracts the integer 1).</span></span>

<span data-ttu-id="bf966-140">[(T)x](invocation-operator.md) – 형식 캐스팅</span><span class="sxs-lookup"><span data-stu-id="bf966-140">[(T)x](invocation-operator.md) – type casting.</span></span>

<span data-ttu-id="bf966-141">[await](../keywords/await.md) – `Task`를 대기합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-141">[await](../keywords/await.md) – awaits a `Task`.</span></span>

<span data-ttu-id="bf966-142">[&x](and-operator.md) – 주소</span><span class="sxs-lookup"><span data-stu-id="bf966-142">[&x](and-operator.md) – address of.</span></span>

<span data-ttu-id="bf966-143">[\*x](multiplication-operator.md) – 역참조</span><span class="sxs-lookup"><span data-stu-id="bf966-143">[\*x](multiplication-operator.md) – dereferencing.</span></span>

## <a name="multiplicative-operators"></a><span data-ttu-id="bf966-144">곱하기 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-144">Multiplicative operators</span></span>

<span data-ttu-id="bf966-145">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-145">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-146">[x \* y](arithmetic-operators.md#multiplication-operator-) – 곱하기</span><span class="sxs-lookup"><span data-stu-id="bf966-146">[x \* y](arithmetic-operators.md#multiplication-operator-) – multiplication.</span></span>

<span data-ttu-id="bf966-147">[x / y](arithmetic-operators.md#division-operator-) – 나누기</span><span class="sxs-lookup"><span data-stu-id="bf966-147">[x / y](arithmetic-operators.md#division-operator-) – division.</span></span> <span data-ttu-id="bf966-148">피연산자가 정수인 경우 결과는 0으로 잘린 정수입니다(예: `-7 / 2 is -3`).</span><span class="sxs-lookup"><span data-stu-id="bf966-148">If the operands are integers, the result is an integer truncated toward zero (for example, `-7 / 2 is -3`).</span></span>

<span data-ttu-id="bf966-149">[x % y](arithmetic-operators.md#remainder-operator-) - 나머지.</span><span class="sxs-lookup"><span data-stu-id="bf966-149">[x % y](arithmetic-operators.md#remainder-operator-) – remainder.</span></span> <span data-ttu-id="bf966-150">피연산자가 정수인 경우 x를 y로 나눈 나머지를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-150">If the operands are integers, this returns the remainder of dividing x by y.</span></span>  <span data-ttu-id="bf966-151">`q = x / y`이고 `r = x % y`인 경우 `x = q * y + r`입니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-151">If `q = x / y` and `r = x % y`, then `x = q * y + r`.</span></span>

## <a name="additive-operators"></a><span data-ttu-id="bf966-152">더하기 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-152">Additive operators</span></span>

<span data-ttu-id="bf966-153">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-153">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-154">[x + y](arithmetic-operators.md#addition-operator-) – 더하기</span><span class="sxs-lookup"><span data-stu-id="bf966-154">[x + y](arithmetic-operators.md#addition-operator-) – addition.</span></span>

<span data-ttu-id="bf966-155">[x – y](arithmetic-operators.md#subtraction-operator--) – 빼기</span><span class="sxs-lookup"><span data-stu-id="bf966-155">[x – y](arithmetic-operators.md#subtraction-operator--) – subtraction.</span></span>

## <a name="shift-operators"></a><span data-ttu-id="bf966-156">시프트 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-156">Shift operators</span></span>

<span data-ttu-id="bf966-157">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-157">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-158">[x <\<  y](left-shift-operator.md) – 왼쪽 비트를 시프트하고 오른쪽을 0으로 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-158">[x <\<  y](left-shift-operator.md) – shift bits left and fill with zero on the right.</span></span>

<span data-ttu-id="bf966-159">[x >> y](right-shift-operator.md) – 오른쪽 비트를 시프트합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-159">[x >> y](right-shift-operator.md) – shift bits right.</span></span> <span data-ttu-id="bf966-160">왼쪽 피연산자가 `int` 또는 `long`이면 왼쪽 비트는 부호 비트로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-160">If the left operand is `int` or `long`, then left bits are filled with the sign bit.</span></span> <span data-ttu-id="bf966-161">왼쪽 피연산자가 `uint` 또는 `ulong`이면 왼쪽 비트는 0으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-161">If the left operand is `uint` or `ulong`, then left bits are filled with zero.</span></span>

## <a name="relational-and-type-testing-operators"></a><span data-ttu-id="bf966-162">관계형 및 형식 테스트 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-162">Relational and type-testing operators</span></span>

<span data-ttu-id="bf966-163">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-163">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-164">[x \< y](less-than-operator.md) –보다 작음(x가 y보다 작은 경우 true)</span><span class="sxs-lookup"><span data-stu-id="bf966-164">[x \< y](less-than-operator.md) – less than (true if x is less than y).</span></span>

<span data-ttu-id="bf966-165">[x > y](greater-than-operator.md) – 보다 큼(x가 y보다 큰 경우 true)</span><span class="sxs-lookup"><span data-stu-id="bf966-165">[x > y](greater-than-operator.md) – greater than (true if x is greater than y).</span></span>

<span data-ttu-id="bf966-166">[x \<= y](less-than-equal-operator.md) – 크거나 같음</span><span class="sxs-lookup"><span data-stu-id="bf966-166">[x \<= y](less-than-equal-operator.md) – less than or equal to.</span></span>

<span data-ttu-id="bf966-167">[x >= y](greater-than-equal-operator.md) – 보다 크거나 같음</span><span class="sxs-lookup"><span data-stu-id="bf966-167">[x >= y](greater-than-equal-operator.md) – greater than or equal to.</span></span>

<span data-ttu-id="bf966-168">[is](../keywords/is.md) – 형식 호환성.</span><span class="sxs-lookup"><span data-stu-id="bf966-168">[is](../keywords/is.md) – type compatibility.</span></span> <span data-ttu-id="bf966-169">계산된 왼쪽 피연산자를 오른쪽 피연산자에 지정된 형식(정적 형식)으로 캐스팅할 수 있는 경우 true를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-169">Returns true if the evaluated left operand can be cast to the type specified in the right operand (a static type).</span></span>

<span data-ttu-id="bf966-170">[as](../keywords/as.md) – 형식 변환.</span><span class="sxs-lookup"><span data-stu-id="bf966-170">[as](../keywords/as.md) – type conversion.</span></span> <span data-ttu-id="bf966-171">오른쪽 피연산자에 지정된 형식(정적 유형)으로 캐스팅된 왼쪽 피연산자를 반환하지만 `(T)x`가 예외를 throw하는 경우 `as`는 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-171">Returns the left operand cast to the type specified by the right operand (a static type), but `as` returns `null` where `(T)x` would throw an exception.</span></span>

## <a name="equality-operators"></a><span data-ttu-id="bf966-172">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-172">Equality operators</span></span>

<span data-ttu-id="bf966-173">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-173">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-174">[x == y](equality-operators.md#equality-operator-) – 같음.</span><span class="sxs-lookup"><span data-stu-id="bf966-174">[x == y](equality-operators.md#equality-operator-) – equality.</span></span> <span data-ttu-id="bf966-175">기본적으로 `string`이 아닌 참조 형식에 대해 참조 같음(ID 테스트)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-175">By default, for reference types other than `string`, this returns reference equality (identity test).</span></span> <span data-ttu-id="bf966-176">그러나 형식이 `==`를 오버로드할 수 있으므로 ID를 테스트하려는 경우에는 `object`에서 `ReferenceEquals` 메서드를 사용하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-176">However, types can overload `==`, so if your intent is to test identity, it is best to use the `ReferenceEquals` method on `object`.</span></span>

<span data-ttu-id="bf966-177">[x != y](equality-operators.md#inequality-operator-) – 같지 않음.</span><span class="sxs-lookup"><span data-stu-id="bf966-177">[x != y](equality-operators.md#inequality-operator-) – not equal.</span></span> <span data-ttu-id="bf966-178">`==`에 대한 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf966-178">See comment for `==`.</span></span> <span data-ttu-id="bf966-179">형식이 `==`를 오버로드하는 경우 `!=`를 오버로드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-179">If a type overloads `==`, then it must overload `!=`.</span></span>

## <a name="logical-and-operator"></a><span data-ttu-id="bf966-180">논리곱 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-180">Logical AND operator</span></span>

<span data-ttu-id="bf966-181">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-181">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-182">[x & y](and-operator.md) – 논리적 또는 비트 AND.</span><span class="sxs-lookup"><span data-stu-id="bf966-182">[x & y](and-operator.md) – logical or bitwise AND.</span></span> <span data-ttu-id="bf966-183">일반적으로 정수 형식 및 `enum` 형식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-183">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-xor-operator"></a><span data-ttu-id="bf966-184">논리적 XOR 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-184">Logical XOR operator</span></span>

<span data-ttu-id="bf966-185">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-185">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-186">[x ^ y](xor-operator.md) – 논리적 또는 비트 XOR.</span><span class="sxs-lookup"><span data-stu-id="bf966-186">[x ^ y](xor-operator.md) – logical or bitwise XOR.</span></span> <span data-ttu-id="bf966-187">일반적으로 정수 형식 및 `enum` 형식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-187">You can generally use this with integer types and `enum` types.</span></span>

## <a name="logical-or-operator"></a><span data-ttu-id="bf966-188">이는 논리 OR 연산자입니다</span><span class="sxs-lookup"><span data-stu-id="bf966-188">Logical OR operator</span></span>

<span data-ttu-id="bf966-189">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-189">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-190">[x &#124; y](or-operator.md) – 논리적 또는 비트 OR.</span><span class="sxs-lookup"><span data-stu-id="bf966-190">[x &#124; y](or-operator.md) – logical or bitwise OR.</span></span> <span data-ttu-id="bf966-191">일반적으로 정수 형식 및 `enum` 형식에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-191">You can generally use this with integer types and `enum` types.</span></span>

## <a name="conditional-and-operator"></a><span data-ttu-id="bf966-192">조건부 AND 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-192">Conditional AND operator</span></span>

<span data-ttu-id="bf966-193">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-193">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-194">[x && y](conditional-and-operator.md) – 논리적 AND.</span><span class="sxs-lookup"><span data-stu-id="bf966-194">[x && y](conditional-and-operator.md) – logical AND.</span></span> <span data-ttu-id="bf966-195">첫 번째 피연산자가 false로 확인되면, C#에서 두 번째 피연산자를 계산하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-195">If the first operand evaluates to false, then C# does not evaluate the second operand.</span></span>

## <a name="conditional-or-operator"></a><span data-ttu-id="bf966-196">조건부 OR 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-196">Conditional OR operator</span></span>

<span data-ttu-id="bf966-197">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-197">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-198">[x &#124;&#124; y](conditional-or-operator.md) – 논리적 OR.</span><span class="sxs-lookup"><span data-stu-id="bf966-198">[x &#124;&#124; y](conditional-or-operator.md) – logical OR.</span></span> <span data-ttu-id="bf966-199">첫 번째 피연산자가 true로 확인되면, C#에서 두 번째 피연산자를 계산하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-199">If the first operand evaluates to true, then C# does not evaluate the second operand.</span></span>

## <a name="null-coalescing-operator"></a><span data-ttu-id="bf966-200">Null 병합 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-200">Null-coalescing operator</span></span>

<span data-ttu-id="bf966-201">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-201">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-202">[x ?? y](null-coalescing-operator.md) – `null`이 아닌 경우 `x`를 반환하고, 그렇지 않은 경우 `y`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-202">[x ?? y](null-coalescing-operator.md) – returns `x` if it is non-`null`; otherwise, returns `y`.</span></span>

## <a name="conditional-operator"></a><span data-ttu-id="bf966-203">조건 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-203">Conditional operator</span></span>

<span data-ttu-id="bf966-204">이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-204">This operator has higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-205">[t ? x : y](conditional-operator.md) - 테스트 `t`가 true로 확인되면 `x`를 계산하여 반환하고, 그렇지 않은 경우 `y`를 계산하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-205">[t ? x : y](conditional-operator.md) – if test `t` evaluates to true, then evaluate and return `x`; otherwise, evaluate and return `y`.</span></span>

## <a name="assignment-and-lambda-operators"></a><span data-ttu-id="bf966-206">할당 및 람다 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-206">Assignment and Lambda operators</span></span>

<span data-ttu-id="bf966-207">이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-207">These operators have higher precedence than the next section and lower precedence than the previous section.</span></span>

<span data-ttu-id="bf966-208">[x = y](assignment-operator.md) – 할당</span><span class="sxs-lookup"><span data-stu-id="bf966-208">[x = y](assignment-operator.md) – assignment.</span></span>

<span data-ttu-id="bf966-209">[x += y](addition-assignment-operator.md) – 증가.</span><span class="sxs-lookup"><span data-stu-id="bf966-209">[x += y](addition-assignment-operator.md) – increment.</span></span> <span data-ttu-id="bf966-210">`y`의 값을 `x` 값에 더하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-210">Add the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="bf966-211">`x`가 `event`를 지정하는 경우 `y`는 C#에서 이벤트 처리기로 추가하는 적절한 함수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-211">If `x` designates an `event`, then `y` must be an appropriate function that C# adds as an event handler.</span></span>

<span data-ttu-id="bf966-212">[x -= y](subtraction-assignment-operator.md) – 감소.</span><span class="sxs-lookup"><span data-stu-id="bf966-212">[x -= y](subtraction-assignment-operator.md) – decrement.</span></span> <span data-ttu-id="bf966-213">`x`의 값에서 `y`의 값을 빼고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-213">Subtract the value of `y` from the value of `x`, store the result in `x`, and return the new value.</span></span> <span data-ttu-id="bf966-214">`x`가 `event`를 지정하는 경우 `y`는 C#에서 이벤트 처리기로 제거하는 적절한 함수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-214">If `x` designates an `event`, then `y` must be an appropriate function that C# removes as an event handler</span></span>

<span data-ttu-id="bf966-215">[x \*= y](multiplication-assignment-operator.md) – 곱하기 대입.</span><span class="sxs-lookup"><span data-stu-id="bf966-215">[x \*= y](multiplication-assignment-operator.md) – multiplication assignment.</span></span> <span data-ttu-id="bf966-216">`y`의 값을 `x`의 값에 곱하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-216">Multiply the value of `y` to the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bf966-217">[x /= y](arithmetic-operators.md#compound-assignment) – 나누기 대입.</span><span class="sxs-lookup"><span data-stu-id="bf966-217">[x /= y](arithmetic-operators.md#compound-assignment) – division assignment.</span></span> <span data-ttu-id="bf966-218">`x`의 값을 `y`의 값으로 나누고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-218">Divide the value of `x` by the value of `y`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bf966-219">[x %= y](arithmetic-operators.md#compound-assignment) – 나머지 할당.</span><span class="sxs-lookup"><span data-stu-id="bf966-219">[x %= y](arithmetic-operators.md#compound-assignment) – remainder assignment.</span></span> <span data-ttu-id="bf966-220">`x`의 값을 `y`의 값으로 나누고 나머지를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-220">Divide the value of `x` by the value of `y`, store the remainder in `x`, and return the new value.</span></span>

<span data-ttu-id="bf966-221">[x &= y](and-assignment-operator.md) – AND 대입.</span><span class="sxs-lookup"><span data-stu-id="bf966-221">[x &= y](and-assignment-operator.md) – AND assignment.</span></span> <span data-ttu-id="bf966-222">`y`의 값을 `x`의 값과 AND하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-222">AND the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bf966-223">[x &#124;= y](or-assignment-operator.md) – OR 대입.</span><span class="sxs-lookup"><span data-stu-id="bf966-223">[x &#124;= y](or-assignment-operator.md) – OR assignment.</span></span> <span data-ttu-id="bf966-224">`y`의 값을 `x`의 값과 OR하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-224">OR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bf966-225">[x ^= y](xor-assignment-operator.md) – XOR 대입.</span><span class="sxs-lookup"><span data-stu-id="bf966-225">[x ^= y](xor-assignment-operator.md) – XOR assignment.</span></span> <span data-ttu-id="bf966-226">`y`의 값을 `x`의 값과 XOR하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-226">XOR the value of `y` with the value of `x`, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bf966-227">[x <<= y](left-shift-assignment-operator.md) – 왼쪽 시프트 대입.</span><span class="sxs-lookup"><span data-stu-id="bf966-227">[x <<= y](left-shift-assignment-operator.md) – left-shift assignment.</span></span> <span data-ttu-id="bf966-228">`x`의 값을 왼쪽으로 `y` 위치만큼 시프트하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-228">Shift the value of `x` left by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bf966-229">[x >>= y](right-shift-assignment-operator.md) – 오른쪽 시프트 대입.</span><span class="sxs-lookup"><span data-stu-id="bf966-229">[x >>= y](right-shift-assignment-operator.md) – right-shift assignment.</span></span> <span data-ttu-id="bf966-230">`x`의 값을 오른쪽으로 `y` 위치만큼 시프트하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf966-230">Shift the value of `x` right by `y` places, store the result in `x`, and return the new value.</span></span>

<span data-ttu-id="bf966-231">[=>](lambda-operator.md) – 람다 선언.</span><span class="sxs-lookup"><span data-stu-id="bf966-231">[=>](lambda-operator.md) – lambda declaration.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf966-232">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf966-232">See also</span></span>

- [<span data-ttu-id="bf966-233">C# 참조</span><span class="sxs-lookup"><span data-stu-id="bf966-233">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bf966-234">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="bf966-234">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bf966-235">C#</span><span class="sxs-lookup"><span data-stu-id="bf966-235">C#</span></span>](../../index.md)
- [<span data-ttu-id="bf966-236">오버로드할 수 있는 연산자</span><span class="sxs-lookup"><span data-stu-id="bf966-236">Overloadable Operators</span></span>](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [<span data-ttu-id="bf966-237">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="bf966-237">C# Keywords</span></span>](../keywords/index.md)