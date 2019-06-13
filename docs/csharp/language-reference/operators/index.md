---
title: 및 += 연산자 - C# 참조
ms.date: 04/30/2019
f1_keywords:
- cs.operators
helpviewer_keywords:
- boolean operators [C#]
- expressions [C#], operators
- logical operators [C#]
- operators [C#]
- Visual C#, operators
- indirection operators [C#]
- assignment operators [C#]
- shift operators [C#]
- relational operators [C#]
- bitwise operators [C#]
- address operators [C#]
- keywords [C#], operators
- arithmetic operators [C#]
ms.assetid: 0301e31f-22ad-49af-ac3c-d5eae7f0ac43
ms.openlocfilehash: 98f73ed958f8b43cd4fea700a478cf3337ea68db
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025141"
---
# <a name="c-operators-c-reference"></a>+ 및 += 연산자(C# 참조)

C#은 기본 제공 형식에서 지원되는 미리 정의된 여러 연산자를 제공합니다. 예를 들어 [산술 연산자](arithmetic-operators.md)는 기본 제공 숫자 형식의 피연산자를 사용하여 산술 연산을 수행하고 [부울 논리 연산자](boolean-logical-operators.md)는 [bool](../keywords/bool.md) 피연산자를 사용하여 논리 연산을 수행합니다.

사용자 정의 형식은 특정 연산자를 오버로드하여 해당 형식의 피연산자에 대한 해당 동작을 정의할 수 있습니다. 자세한 내용은 [연산자](../keywords/operator.md) 키워드 문서를 참조하세요.

다음 섹션에서는 우선순위가 가장 높은 것부터 시작하여 순서대로 C# 연산자를 나열합니다. 각 섹션 내의 연산자는 동일한 우선 순위 수준을 공유합니다.

## <a name="primary-operators"></a>기본 연산자

우선 순위가 가장 높은 연산자입니다.

[x.y](member-access-operators.md#member-access-operator-) – 멤버 액세스

[x?.y](member-access-operators.md#null-conditional-operators--and-) – null 조건부 멤버 액세스 왼쪽 피연산자가 `null`로 확인되면 `null`을 반환합니다.

[x?[y]](member-access-operators.md#null-conditional-operators--and-) - null 조건부 배열 요소 또는 형식 인덱서 액세스. 왼쪽 피연산자가 `null`로 확인되면 `null`을 반환합니다.

[f (x)](member-access-operators.md#invocation-operator-) - 메서드 호출 또는 대리자 호출.

[&#91;x&#93;](member-access-operators.md#indexer-operator-) – 배열 요소 또는 형식 인덱서 액세스.

[x++](arithmetic-operators.md#increment-operator-) – 후위 증가. x의 값을 반환하고 1보다 큰 x 값(일반적으로 정수 1을 더함)으로 스토리지 위치를 업데이트합니다.

[x--](arithmetic-operators.md#decrement-operator---) –  후위 감소. x의 값을 반환하고 1보다 작은 x 값(일반적으로 정수 1을 뺌)으로 스토리지 위치를 업데이트합니다.

[new](../keywords/new-operator.md) – 형식 인스턴스화.

[typeof](../keywords/typeof.md) – 피연산자를 나타내는 <xref:System.Type> 개체를 반환합니다.

[checked](../keywords/checked.md) – 정수 연산에 오버플로 검사를 사용하도록 설정합니다.

[unchecked](../keywords/unchecked.md) – 정수 연산에 오버플로 검사를 사용하지 않도록 설정합니다. 이것은 기본 컴파일러 동작입니다.

[default(T)](../../programming-guide/statements-expressions-operators/default-value-expressions.md) – T 형식의 기본값을 생성합니다.

[nameof](../keywords/nameof.md) - 변수, 형식 또는 멤버의 단순(정규화되지 않은) 이름을 상수 문자열로 가져옵니다.

[delegate](../../programming-guide/statements-expressions-operators/anonymous-methods.md) – 대리자 인스턴스를 선언하고 반환합니다.

[sizeof](../keywords/sizeof.md) – 형식 피연산자의 크기(바이트)를 반환합니다.

[stackalloc](stackalloc.md) - 스택의 메모리 블록을 할당합니다.

[->](pointer-related-operators.md#pointer-member-access-operator--) – 멤버 액세스와 결합된 포인터 간접 참조입니다.

## <a name="unary-operators"></a>단항 연산자

이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[+x](addition-operator.md) – x의 값을 반환합니다.

[-x](subtraction-operator.md) – 숫자 부정

[\!x](boolean-logical-operators.md#logical-negation-operator-) – 논리 부정

[~x](bitwise-and-shift-operators.md#bitwise-complement-operator-) – 비트 보수

[++x](arithmetic-operators.md#increment-operator-) – 전위 증가 1보다 큰 x 값(일반적으로 정수 1을 더함)으로 스토리지 위치를 업데이트한 후 x의 값을 반환합니다.

[--x](arithmetic-operators.md#decrement-operator---) – 전위 감소 1보다 작은 x 값(일반적으로 정수 1을 뺌)으로 스토리지 위치를 업데이트한 후 x의 값을 반환합니다.

[(T)x](invocation-operator.md) – 형식 캐스팅

[await](../keywords/await.md) – `Task`를 대기합니다.

[&x](pointer-related-operators.md#address-of-operator-) – 변수의 주소입니다.

[* x](pointer-related-operators.md#pointer-indirection-operator-) – 포인터 간접 참조 또는 역참조입니다.

[true 연산자](true-false-operators.md) - [bool](../keywords/bool.md) 값 `true`를 반환하여 피연산자가 확실히 true임을 나타냅니다.

[false 연산자](true-false-operators.md) - [bool](../keywords/bool.md) 값 `true`를 반환하여 피연산자가 확실히 false임을 나타냅니다.

## <a name="multiplicative-operators"></a>곱하기 연산자

이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[x * y](arithmetic-operators.md#multiplication-operator-) – 곱하기

[x / y](arithmetic-operators.md#division-operator-) – 나누기 피연산자가 정수인 경우 결과는 0으로 잘린 정수입니다(예: `-7 / 2 is -3`).

[x % y](arithmetic-operators.md#remainder-operator-) - 나머지. 피연산자가 정수인 경우 x를 y로 나눈 나머지를 반환합니다.  `q = x / y`이고 `r = x % y`인 경우 `x = q * y + r`입니다.

## <a name="additive-operators"></a>더하기 연산자

이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[x + y](arithmetic-operators.md#addition-operator-) – 더하기

[x – y](arithmetic-operators.md#subtraction-operator--) – 빼기

## <a name="shift-operators"></a>시프트 연산자

이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[x <\<  y](bitwise-and-shift-operators.md#left-shift-operator-) – 왼쪽 비트를 시프트하고 오른쪽을 0으로 채웁니다.

[x >> y](bitwise-and-shift-operators.md#right-shift-operator-) – 오른쪽 비트를 시프트합니다. 왼쪽 피연산자가 `int` 또는 `long`이면 왼쪽 비트는 부호 비트로 채워집니다. 왼쪽 피연산자가 `uint` 또는 `ulong`이면 왼쪽 비트는 0으로 채워집니다.

## <a name="relational-and-type-testing-operators"></a>관계형 및 형식 테스트 연산자

이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[x \< y](comparison-operators.md#less-than-operator-) –보다 작음(x가 y보다 작은 경우 true)

[x > y](comparison-operators.md#greater-than-operator-) – 보다 큼(x가 y보다 큰 경우 true)

[x \<= y](comparison-operators.md#less-than-or-equal-operator-) – 크거나 같음

[x >= y](comparison-operators.md#greater-than-or-equal-operator-) – 보다 크거나 같음

[is](../keywords/is.md) – 형식 호환성. 계산된 왼쪽 피연산자를 오른쪽 피연산자에 지정된 형식(정적 형식)으로 캐스팅할 수 있는 경우 true를 반환합니다.

[as](../keywords/as.md) – 형식 변환. 오른쪽 피연산자에 지정된 형식(정적 유형)으로 캐스팅된 왼쪽 피연산자를 반환하지만 `(T)x`가 예외를 throw하는 경우 `as`는 `null`을 반환합니다.

## <a name="equality-operators"></a>같음 연산자

이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[x == y](equality-operators.md#equality-operator-) – 같음. 기본적으로 `string`이 아닌 참조 형식에 대해 참조 같음(ID 테스트)을 반환합니다. 그러나 형식이 `==`를 오버로드할 수 있으므로 ID를 테스트하려는 경우에는 `object`에서 `ReferenceEquals` 메서드를 사용하는 것이 가장 좋습니다.

[x != y](equality-operators.md#inequality-operator-) – 같지 않음. `==`에 대한 설명을 참조하세요. 형식이 `==`를 오버로드하는 경우 `!=`를 오버로드해야 합니다.

## <a name="logical-and-operator"></a>논리곱 연산자

이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

`x & y` – `bool` 피연산자의 경우 [논리 AND](boolean-logical-operators.md#logical-and-operator-)이고, 정수 형식 피연산자의 경우 [비트 논리 AND](bitwise-and-shift-operators.md#logical-and-operator-)입니다.

## <a name="logical-xor-operator"></a>논리적 XOR 연산자

이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

`x ^ y` – `bool` 피연산자의 경우 [논리 XOR](boolean-logical-operators.md#logical-exclusive-or-operator-)이고, 정수 형식 피연산자의 경우 [비트 논리 XOR](bitwise-and-shift-operators.md#logical-exclusive-or-operator-)입니다.

## <a name="logical-or-operator"></a>이는 논리 OR 연산자입니다

이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

`x | y` – `bool` 피연산자의 경우 [논리 OR](boolean-logical-operators.md#logical-or-operator-)이고, 정수 형식 피연산자의 경우 [비트 논리 OR](bitwise-and-shift-operators.md#logical-or-operator-)입니다.

## <a name="conditional-and-operator"></a>조건부 AND 연산자

이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[x && y](boolean-logical-operators.md#conditional-logical-and-operator-) – 논리적 AND. 첫 번째 피연산자가 false로 확인되면, C#에서 두 번째 피연산자를 계산하지 않습니다.

## <a name="conditional-or-operator"></a>조건부 OR 연산자

이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[x &#124;&#124; y](boolean-logical-operators.md#conditional-logical-or-operator-) – 논리적 OR. 첫 번째 피연산자가 true로 확인되면, C#에서 두 번째 피연산자를 계산하지 않습니다.

## <a name="null-coalescing-operator"></a>Null 병합 연산자

이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[x ?? y](null-coalescing-operator.md) – `null`이 아닌 경우 `x`를 반환하고, 그렇지 않은 경우 `y`를 반환합니다.

## <a name="conditional-operator"></a>조건 연산자

이 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[t ? x : y](conditional-operator.md) - 테스트 `t`가 true로 확인되면 `x`를 계산하여 반환하고, 그렇지 않은 경우 `y`를 계산하여 반환합니다.

## <a name="assignment-and-lambda-operators"></a>할당 및 람다 연산자

이러한 연산자는 다음 섹션보다 우선 순위가 높고 이전 섹션보다 우선 순위가 낮습니다.

[x = y](assignment-operator.md) – 할당

[x += y](arithmetic-operators.md#compound-assignment) – 증가. `y`의 값을 `x` 값에 더하고 결과를 `x`에 저장한 다음 새 값을 반환합니다. `x`가 [이벤트](../keywords/event.md)를 지정하는 경우 `y`는 C#에서 이벤트 처리기로 추가하는 적절한 방법이어야 합니다.

[x -= y](arithmetic-operators.md#compound-assignment) – 감소. `x`의 값에서 `y`의 값을 빼고 결과를 `x`에 저장한 다음 새 값을 반환합니다. `x`가 [이벤트](../keywords/event.md)를 지정하는 경우 `y`는 C#에서 이벤트 처리기로 제거하는 적절한 방법이어야 합니다.

[x *= y](arithmetic-operators.md#compound-assignment) – 곱하기 대입. `y`의 값을 `x`의 값에 곱하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.

[x /= y](arithmetic-operators.md#compound-assignment) – 나누기 대입. `x`의 값을 `y`의 값으로 나누고 결과를 `x`에 저장한 다음 새 값을 반환합니다.

[x %= y](arithmetic-operators.md#compound-assignment) – 나머지 할당. `x`의 값을 `y`의 값으로 나누고 나머지를 `x`에 저장한 다음 새 값을 반환합니다.

[x &= y](boolean-logical-operators.md#compound-assignment) – AND 대입. `y`의 값을 `x`의 값과 AND하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.

[x &#124;= y](boolean-logical-operators.md#compound-assignment) – OR 대입. `y`의 값을 `x`의 값과 OR하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.

[x ^= y](boolean-logical-operators.md#compound-assignment) – XOR 대입. `y`의 값을 `x`의 값과 XOR하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.

[x <<= y](bitwise-and-shift-operators.md#compound-assignment) – 왼쪽 시프트 대입. `x`의 값을 왼쪽으로 `y` 위치만큼 시프트하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.

[x >>= y](bitwise-and-shift-operators.md#compound-assignment) – 오른쪽 시프트 대입. `x`의 값을 오른쪽으로 `y` 위치만큼 시프트하고 결과를 `x`에 저장한 다음 새 값을 반환합니다.

[=>](lambda-operator.md) – 람다 선언.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [연산자](../../programming-guide/statements-expressions-operators/operators.md)
- [오버로드할 수 있는 연산자](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
