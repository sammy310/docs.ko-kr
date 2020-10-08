---
title: 로컬 함수 - C# 프로그래밍 가이드
description: C#의 로컬 함수는 다른 멤버에 중첩되어 포함된 멤버에서 호출할 수 있는 전용 메서드입니다.
ms.date: 10/02/2020
helpviewer_keywords:
- local functions [C#]
ms.openlocfilehash: a91995757048c8c54253d7f4b923d5194f69bc7b
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654922"
---
# <a name="local-functions-c-programming-guide"></a>로컬 함수(C# 프로그래밍 가이드)

C# 7.0부터 C#에서는 *로컬 함수*를 지원합니다. 로컬 함수는 다른 멤버에 중첩된 형식의 private 메서드입니다. 포함하는 멤버에서만 호출할 수 있습니다. 로컬 함수는 다음에서 선언하고 호출할 수 있습니다.

- 메서드, 특히 반복기 메서드 및 비동기 메서드
- 생성자
- 속성 접근자
- 이벤트 접근자
- 무명 메서드
- 람다 식
- 종료자
- 다른 로컬 함수

그러나 식 본문 멤버 내에서는 로컬 함수를 선언할 수 없습니다.

> [!NOTE]
> 로컬 함수에서도 지원하는 기능을 람다 식으로 구현할 수 있는 경우도 있습니다. 비교를 보려면 [로컬 함수 및 람다 식](#local-functions-vs-lambda-expressions)을 참조하세요.

로컬 함수는 코드의 의도를 명확하게 합니다. 코드를 읽는 모든 사용자가 포함하는 메서드를 통해서만 메서드를 호출할 수 있음을 알 수 있습니다. 팀 프로젝트의 경우 로컬 함수를 사용하면 다른 개발자가 실수로 클래스 또는 구조체의 다른 곳에서 직접 메서드를 호출하는 경우를 방지할 수도 있습니다.

## <a name="local-function-syntax"></a>로컬 함수 구문

로컬 함수는 포함하는 멤버 내의 중첩 메서드로 정의됩니다. 해당 정의는 다음 구문을 사용합니다.

```csharp
<modifiers> <return-type> <method-name> <parameter-list>
```

로컬 함수에 다음 한정자를 사용할 수 있습니다.

- [`async`](../../language-reference/keywords/async.md)
- [`unsafe`](../../language-reference/keywords/unsafe.md)
- [`static`](../../language-reference/keywords/static.md)(C# 8.0 이상). 정적 로컬 함수는 지역 변수 또는 인스턴스 상태를 캡처할 수 없습니다.
- [`extern`](../../language-reference/keywords/extern.md)(C# 9.0 이상). 외부 로컬 함수는 `static`이어야 합니다.

해당 메서드 매개 변수를 비롯하여 포함하는 멤버에 정의된 모든 지역 변수는 정적이지 않은 로컬 함수에서 액세스할 수 있습니다.

메서드 정의와 달리 로컬 함수 정의에는 멤버 액세스 한정자를 포함할 수 없습니다. 모든 로컬 함수는 private이므로 `private` 키워드 등의 액세스 한정자를 포함하면 컴파일러 오류 CS0106,“이 항목의 ‘private’ 한정자가 유효하지 않습니다.”가 생성됩니다.

또한 로컬 함수나 해당 매개 변수 및 형식 매개 변수에는 특성을 적용할 수 없습니다.

다음 예제에서는 `GetText` 메서드에 대해 private인 로컬 함수 `AppendPathSeparator`를 정의합니다.

[!code-csharp[LocalFunctionExample](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions1.cs)]  

## <a name="local-functions-and-exceptions"></a>로컬 함수 및 예외

로컬 함수의 유용한 기능 중 하나는 예외가 즉시 나타나도록 할 수 있다는 것입니다. 메서드 반복기의 경우 반환된 시퀀스가 열거된 경우에만 예외가 나타나고 반복기를 검색할 때는 나타나지 않습니다. 비동기 메서드의 경우 비동기 메서드에서 throw된 예외는 반환된 작업을 대기할 때 관찰됩니다.

다음 예제에서는 지정된 범위 사이의 홀수를 열거하는 `OddSequence` 메서드를 정의합니다. 100보다 큰 숫자를 `OddSequence` 열거자 메서드에 전달하기 때문에 메서드가 <xref:System.ArgumentOutOfRangeException>을 throw합니다. 예제의 출력에서 볼 수 있듯이 예외는 숫자를 반복하는 경우에만 나타나고 열거자를 검색할 때는 나타나지 않습니다.

[!code-csharp[LocalFunctionIterator1](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator1.cs)]

대신, 다음 예제와 같이 로컬 함수에서 반복기를 반환하여 유효성 검사를 수행할 때, 반복기를 검색하기 전에 예외를 throw할 수 있습니다.

[!code-csharp[LocalFunctionIterator2](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-iterator2.cs)]

유사한 방식으로 로컬 함수를 사용하여 비동기 작업 외부에서 예외를 처리할 수 있습니다. 일반적으로 비동기 메서드에서 throw된 예외의 경우 <xref:System.AggregateException>의 내부 예외를 검사해야 합니다. 로컬 함수를 사용하면 코드가 빨리 실패하여 예외가 throw되는 동시에 관찰할 수 있습니다.

다음 예제에서는 `GetMultipleAsync`라는 비동기 메서드를 사용하여 지정된 시간(초) 동안 일시 중지하고 해당 시간(초)의 임의 배수인 값을 반환합니다. 최대 지연 시간은 5초입니다. 값이 5보다 크면 <xref:System.ArgumentOutOfRangeException>이 발생합니다. 다음 예제와 같이 값 6이 `GetMultipleAsync` 메서드에 전달될 때 throw되는 예외는 `GetMultipleAsync` 메서드 실행이 시작된 후에 <xref:System.AggregateException>에 래핑됩니다.

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async1.cs)]

메서드 반복기와 마찬가지로, 이 예제의 코드를 리팩터링하여 비동기 메서드를 호출하기 전에 유효성 검사를 수행할 수 있습니다. 다음 예제의 출력에서 볼 수 있듯이, <xref:System.ArgumentOutOfRangeException>이 <xref:System.AggregateException>에 래핑되지 않습니다.

[!code-csharp[LocalFunctionAsync](~/samples/snippets/csharp/programming-guide/classes-and-structs/local-functions-async2.cs)]

## <a name="local-functions-vs-lambda-expressions"></a>로컬 함수 및 람다 식

얼핏 보기에 로컬 함수와 [람다 식](../../language-reference/operators/lambda-expressions.md)은 매우 유사합니다. 대부분의 경우 람다 식과 로컬 함수 사용 간 선택은 스타일 및 개인 기본 설정의 문제입니다. 그러나 하나 또는 다른 것을 사용할 수 있는 것에 알고 있어야 하는 실제 차이점이 있습니다.

계승 알고리즘의 로컬 함수 및 람다 식 구현 간의 차이점을 살펴보겠습니다. 먼저 로컬 함수를 사용하는 버전은 다음과 같습니다.

[!code-csharp[LocalFunctionFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#37_LocalFunctionFactorial "Recursive factorial using local function")]

람다 식을 사용하는 버전과 해당 구현을 비교해 보세요.

[!code-csharp[26_LambdaFactorial](../../../../samples/snippets/csharp/new-in-7/MathUtilities.cs#38_LambdaFactorial "Recursive factorial using lambda expressions")]

로컬 함수에는 이름이 있습니다. 람다 식은 `Func` 또는 `Action` 형식인 변수에 할당된 무명 메서드입니다. 로컬 함수를 선언하는 경우 인수 형식 및 반환 형식은 함수 선언의 일부입니다. 람다 식 본문에 포함되는 대신 인수 형식 및 반환 형식은 람다 식의 변수 형식 선언의 일부입니다. 이러한 두 가지 차이점은 코드를 더 명확하게 할 수 있습니다.

로컬 함수는 람다 식보다 한정된 할당에 대한 다양한 규칙을 갖고 있습니다. 로컬 함수 선언은 범위에 있는 모든 코드 위치에서 참조될 수 있습니다. 람다 식을 액세스하려면 대리자 변수에 할당해야 합니다(또는 람다 식을 참조하는 대리자를 통해 호출). 람다 식을 사용하는 버전은 람다 식 `nthFactorial`을 정의하기 전에 선언하고 초기화해야 합니다. 이렇게 하지 않으면 `nthFactorial`을 할당하기 전에 참조하여 컴파일 시간 오류가 발생합니다. 이러한 차이점은 로컬 함수를 사용하여 재귀 알고리즘을 쉽게 만들 수 있음을 의미합니다. 자신을 호출하는 로컬 함수를 선언하고 정의할 수 있습니다. 람다 식을 동일한 람다 식을 참조하는 본문에 다시 할당하려면 선언하고, 기본 값을 할당해야 합니다.

한정된 할당 규칙은 로컬 함수 또는 람다 식에서 캡처되는 변수에도 영향을 줍니다. 로컬 함수와 람다 식 규칙 모두는 로컬 함수 또는 람다 식이 대리자로 변환되는 시점에 캡처된 변수를 한정적으로 할당해야 합니다. 차이점은 선언될 때 람다 식이 대리자로 변환된다는 점입니다. 로컬 함수는 대리자로 사용되는 경우에만 대리자로 변환됩니다. 로컬 함수를 선언하고 메서드처럼 호출하여 참조하는 경우 대리자로 변환되지 않습니다. 해당 규칙을 통해 포함된 범위 내의 모든 편리한 위치에서 로컬 함수를 선언할 수 있습니다. 모든 return 문 뒤의 부모 메서드 끝에 로컬 함수를 선언하는 것은 일반적입니다.

세 번째, 컴파일러는 로컬 함수가 포함된 범위에서 캡처된 변수를 한정적으로 할당할 수 있도록 하는 정적 분석을 수행할 수 있습니다. 다음 예제를 고려해 보세요.

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

컴파일러는 `LocalFunction`에서 호출될 때 `y`를 한정적으로 할당하는지 확인할 수 있습니다. `LocalFunction`은 `return` 문 전에 호출되므로 `y`는 `return` 문에서 한정적으로 할당됩니다.

예제 분석을 활성화하는 분석은 네 번째 차이점을 활성화합니다. 해당 용도에 따라 로컬 함수는 람다 식에 항상 필요한 힙 할당을 피할 수 있습니다. 로컬 함수가 대리자로 변환되지 않고 로컬 함수에 의해 캡처된 변수가 대리자로 변환된 다른 람다 식 또는 로컬 함수에 의해 캡처되지 않는 경우 컴파일러는 힙 할당을 피할 수 있습니다.

다음 비동기 예제를 살펴보세요.

[!code-csharp[TaskLambdaExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#36_TaskLambdaExample "Task returning method with lambda expression")]

이 람다 식의 클로저에는 `address`, `index` 및 `name` 변수가 포함됩니다. 로컬 함수의 경우 클로저를 구현하는 개체는 `struct` 형식일 수 있습니다. 해당 구조체 형식은 로컬 함수에 참조로 전달됩니다. 구현에서 이러한 차이점은 할당에 저장됩니다.

람다 식에 필요한 인스턴스화는 추가 메모리 할당을 의미하며, 시간이 중요한 코드 경로에서 성능에 영향을 줄 수 있습니다. 로컬 함수는 이러한 오버헤드를 유발하지 않습니다. 위의 예제에서 로컬 함수 버전은 람다 식 버전보다 할당 수가 2개 더 적습니다.

> [!NOTE]
> 이 메서드에 해당하는 로컬 함수는 클로저에 클래스도 사용합니다. 로컬 함수의 클로저가 `class` 또는 `struct`로 구현되는지 여부는 구현 세부 정보입니다. 로컬 함수는 `struct`를 사용할 수 있는 반면, 람다는 항상 `class`를 사용합니다.

[!code-csharp[TaskLocalFunctionExample](../../../../samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

이 샘플에서 설명하지 않은 한 가지 최종 장점은 `yield return` 구문을 사용해서 로컬 함수를 반복기로 구현하여 값 시퀀스를 생성할 수 있다는 것입니다. `yield return` 문은 람다 식에 허용되지 않습니다.

로컬 함수는 람다 식과 중복되는 것처럼 보일 수도 있지만, 실제로 다른 용도로 다르게 사용됩니다. 로컬 함수는 다른 메서드의 컨텍스트에서만 호출되는 함수를 작성하려는 경우에 더 효율적입니다.

## <a name="see-also"></a>참조

- [메서드](methods.md)
