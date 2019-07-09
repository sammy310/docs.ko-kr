---
title: 연산자 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 04/30/2019
helpviewer_keywords:
- operators [C#]
- C# language, operators
- operators [C#], about operators
ms.assetid: 214e7b83-1a41-4f7c-9867-64e9c0bab39f
ms.openlocfilehash: 551d4cd8bf26a1c1caf3cbf611d9f338ae2581be
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2019
ms.locfileid: "67609498"
---
# <a name="operators-c-programming-guide"></a>연산자(C# 프로그래밍 가이드)

C#에서 *연산자* 는 식 또는 문에서 하나 이상의 *피연산자* 에 적용되는 프로그램 요소입니다. 증가 연산자(`++`)나 `new`같이 피연산자 하나를 사용하는 연산자를 *단항* 연산자라고 합니다. 산술 연산자(`+`,`-`,`*`,`/`) 같이 피연산자 두 개를 사용하는 연산자를 *이항* 연산자라고 합니다. 조건 연산자(`?:`)는 피연산자 세 개를 사용하며 이는 C#에서 유일한 삼진 연산자입니다.  
  
 다음 C# 문에는 단항 연산자 하나와 피연산자 하나가 들어 있습니다. 증가 연산자 `++`는 피연산자 `y`의 값을 수정합니다.  
  
 [!code-csharp[csProgGuideStatements#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#5)]  
  
 다음 C# 문에는 이항 연산자가 두 개 있습니다. 각 연산자는 피연산자를 두 개씩 사용합니다. 할당 연산자 `=`에는 정수 변수 `y` 와 식 `2 + 3` 이 피연산자로 사용됩니다. 식 `2 + 3` 자체는 더하기 연산자와 두 개의 피연산자, `2` 및 `3`으로 구성됩니다.  
  
 [!code-csharp[csProgGuideStatements#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#6)]  
  
피연산자는 모든 길이의 코드로 구성된 유효한 식이 될 수 있으며 모든 개수의 하위 식으로 구성될 수 있습니다. 여러 연산자를 포함하는 식에서 연산자가 적용되는 순서는 *operator precedence*, *associativity*및 괄호로 결정됩니다.  

## <a name="operator-precedence"></a>연산자 우선 순위
  
각 연산자에는 정의된 우선 순위가 있습니다. 다른 우선 순위 수준을 가진 여러 연산자가 포함된 식에서 연산자의 우선 순위는 연산자가 평가되는 순서를 결정합니다. 예를 들어 다음 명령문은 `n1`에 3을 할당합니다.

```csharp
n1 = 11 - 2 * 4;
```

곱셈은 뺄셈보다 우선하기 때문에 곱하기가 가장 먼저 실행됩니다.

우선 순위 수준에 따라 정렬된 전체 연산자 목록은 [C# 연산자](../../language-reference/operators/index.md)를 참조하세요.
  
## <a name="associativity"></a>associativity

 우선 순위가 동일한 연산자 두 개 이상이 식 하나에 있으면 두 연산자의 결합성에 따라 연산 순서가 결정됩니다. 왼쪽 결합성이 있는 연산자는 왼쪽에서 오른쪽으로 계산됩니다. 예를 들어, `x * y / z` 는 `(x * y) / z`로 계산됩니다. 오른쪽 결합성이 있는 연산자는 오른쪽에서 왼쪽으로 계산됩니다. 예를 들어, 할당 연산자는 오른쪽 결합성이 있는 연산자입니다. 아닌 경우 다음 코드 오류가 발생합니다.  
  
```csharp  
int a, b, c;  
c = 1;  
// The following two lines are equivalent.  
a = b = c;  
a = (b = c);  
  
// The following line, which forces left associativity, causes an error.  
//(a = b) = c;  
```  
  
 또 다른 예로, 3개로 구성된 연산자([?:](../../../csharp/language-reference/operators/conditional-operator.md))는 오른쪽 결합형이고, 대부분의 이항 연산자는 왼쪽 결합형입니다.  
  
 식에서 연산자가 왼쪽 결합성인지, 오른쪽 결합성인지에 따라 각 식의 피연산자가 먼저 평가됩니다. 다음 예제는 연산자와 피연산자의 계산 순서를 보여 줍니다.  
  
|문|계산 순서|  
|---------------|-------------------------|  
|`a = b`|a, b, =|  
|`a = b + c`|a, b, c, +, =|  
|`a = b + c * d`|a, b, c, d, *, +, =|  
|`a = b * c + d`|a, b, c, *, d, +, =|  
|`a = b - c + d`|a, b, c, -, d, +, =|  
|`a += b -= c`|a, b, c, -=, +=|  
  
## <a name="adding-parentheses"></a>괄호 추가

 괄호를 사용하여 연산자 우선 순위와 연결을 통해 부과된 실행 순서를 변경할 수 있습니다. 예를 들어, `2 + 3 * 2` 는 일반적으로 승제 연산자가 가감 연산자보다 우선하기 때문에 8로 평가됩니다. 그러나 식을 `(2 + 3) * 2`처럼 작성하는 경우 곱셈 전에 덧셈이 계산되고 결과는 10입니다. 다음 예제는 괄호로 묶인 식의 계산 순서를 보여 줍니다. 이전 예제에서와 같이 피연산자는 연산자가 적용되기 전에 평가됩니다.  
  
|문|계산 순서|  
|---------------|-------------------------|  
|`a = (b + c) * d`|a, b, c, +, d, *, =|  
|`a = b - (c + d)`|a, b, c, d, +, -, =|  
|`a = (b + c) * (d - e)`|a, b, c, +, d, e, -, *, =|  
  
## <a name="operator-overloading"></a>연산자 오버로드

사용자 지정 클래스 및 구조체에 대한 특정 연산자의 동작을 정의할 수 있습니다. 이러한 과정을 *연산자 오버로드*라고 합니다. 자세한 내용은 [연산자 오버로드](../../language-reference/operators/operator-overloading.md)를 참조하세요.
  
## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [문, 식, 연산자](index.md)
- [C# 연산자](../../language-reference/operators/index.md)
