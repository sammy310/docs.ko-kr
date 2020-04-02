---
title: readonly 키워드 - C# 참조
ms.date: 03/26/2020
f1_keywords:
- readonly_CSharpKeyword
- readonly
helpviewer_keywords:
- readonly keyword [C#]
ms.assetid: 2f8081f6-0de2-4903-898d-99696c48d2f4
ms.openlocfilehash: 344d5e54fcd500e283c52fa7953c6366823f13f0
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345145"
---
# <a name="readonly-c-reference"></a>readonly(C# 참조)

`readonly` 키워드는 다음 네 가지 컨텍스트에서 사용할 수 있는 한정자입니다.

- [필드 선언](#readonly-field-example)에서 필드에 대한 할당을 나타내는 `readonly`는 선언의 일부로 또는 동일한 클래스의 생성자에서만 발생할 수 있습니다. 필드 선언과 생성자 내에서 읽기 전용 필드를 여러 번 할당 및 재할당할 수 있습니다.
  
  생성자가 종료된 후에는 `readonly` 필드를 할당할 수 없습니다. 이 규칙의 의미는 값 형식과 참조 형식에서 서로 다릅니다.
  
  - 값 형식에는 해당 데이터가 직접 포함되므로, `readonly` 값 형식인 필드는 변경할 수 없습니다.
  - 참조 형식에는 해당 데이터에 대한 참조가 포함되므로, `readonly` 참조 형식인 필드는 항상 같은 개체를 참조해야 합니다. 해당 개체는 변경할 수 있습니다. `readonly` 한정자는 필드가 참조 형식의 다른 인스턴스로 바뀌지 않도록 합니다. 그러나 이 한정자는 필드의 인스턴스 데이터가 읽기 전용 필드를 통해 수정되는 것을 방지하지는 않습니다.

  > [!WARNING]
  > 변경 가능한 참조 형식인, 외부에서 볼 수 있는 읽기 전용 필드가 포함된 외부에서 볼 수 있는 형식은 보안상 취약할 수 있으며 경고 [CA2104](/visualstudio/code-quality/ca2104) : “변경 가능한 읽기 전용 참조 형식을 선언하지 마세요.”를 실행할 수 있습니다.

- `readonly struct` 형식 정의에서 `readonly`는 구조체 형식을 변경할 수 없음을 나타냅니다. 자세한 내용은 [구조체 형식](../builtin-types/struct.md) 문서의 [`readonly` 구조체](../builtin-types/struct.md#readonly-struct) 섹션을 참조하세요.
- [`readonly` 멤버 정의](#readonly-member-examples)에서 `readonly`는 `struct`의 멤버가 구조체의 내부 상태를 변경하지 않음을 나타냅니다.
- [`ref readonly` 메서드 반환](#ref-readonly-return-example)에서 `readonly` 한정자는 메서드가 참조를 반환하고 해당 참조에 쓰기가 허용되지 않음을 나타냅니다.

`readonly struct` 및 `ref readonly` 컨텍스트는 C# 7.2에서 추가되었습니다. `readonly` 구조체 멤버는 C# 8.0에서 추가되었습니다.

## <a name="readonly-field-example"></a>읽기 전용 필드 예제

이 예제에서 `year` 필드의 값은 클래스 생성자에서 할당되었지만 `ChangeYear` 메서드에서 변경할 수 없습니다.

[!code-csharp[Readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyField)]

다음 컨텍스트에서만 `readonly` 필드에 값을 할당할 수 있습니다.

- 변수가 선언에서 초기화될 때. 예를 들면 다음과 같습니다.

  ```csharp
  public readonly int y = 5;
  ```

- 인스턴스 필드 선언을 포함하는 클래스의 인스턴스 생성자.
- 정적 필드 선언을 포함하는 클래스의 정적 생성자.

또한 이러한 생성자 컨텍스트에서는 `readonly` 필드를 [out](out-parameter-modifier.md) 또는 [ref](ref.md) 매개 변수로 전달하는 것이 유효합니다.

> [!NOTE]
> `readonly` 키워드와 [const](const.md) 키워드와 다릅니다. `const` 필드는 필드 선언에서만 초기화될 수 있습니다. 필드 선언과 임의 생성자에서 `readonly` 필드를 여러 번 할당할 수 있습니다. 따라서 `readonly` 필드는 사용된 생성자에 따라 다른 값을 가질 수 있습니다. 또한 `const` 필드는 컴파일 시간 상수인 반면, `readonly` 필드는 다음 예제와 같이 런타임 상수에 사용될 수 있습니다.
>
> ```csharp
> public static readonly uint timeStamp = (uint)DateTime.Now.Ticks;
> ```

[!code-csharp[Initialize readonly Field example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#InitReadonlyField)]

위 예제에서 다음 예제와 같은 명령문을 사용하는 경우

```csharp
p2.y = 66;        // Error
```

컴파일러 오류 메시지가 표시됩니다.

**읽기 전용 필드에는 할당할 수 없습니다. 단 생성자 또는 변수 이니셜라이저에서는 예외입니다.**

## <a name="readonly-member-examples"></a>Readonly 멤버 예제

변경을 지원하는 구조체를 만들 수 있는 경우도 있습니다. 이러한 경우 몇 개의 인스턴스 멤버는 구조체의 내부 상태를 수정하지 않을 가능성이 큽니다. `readonly` 한정자를 사용하여 해당 인스턴스 멤버를 선언할 수 있습니다. 컴파일러에서 의도를 적용합니다. 해당 멤버가 상태를 직접 수정하거나 `readonly` 한정자로 선언되지 않은 멤버에 액세스하는 경우 컴파일 시간 오류가 발생합니다. `readonly` 한정자는 `struct` 멤버에서 유효하지만, `class` 또는 `interface` 멤버 선언에서는 유효하지 않습니다.

해당하는 `struct` 메서드에 `readonly` 한정자를 적용하면 두 가지 이점이 있습니다. 가장 중요한 이점은 컴파일러에서 의도를 적용하는 것입니다. 상태를 수정하는 코드는 `readonly` 메서드에서 유효하지 않습니다. 컴파일러는 `readonly` 한정자를 사용하여 성능을 최적화할 수도 있습니다. 큰 `struct` 형식을 `in` 참조로 전달할 때, 구조체의 상태를 수정할 수 있는 경우 컴파일러에서 방어형 복사본을 생성해야 합니다. `readonly` 멤버에만 액세스하는 경우에는 컴파일러에서 방어형 복사본을 만들 수 없습니다.

`readonly` 한정자는 <xref:System.Object?displayProperty=nameWithType>에 선언된 메서드를 재정의하는 메서드를 포함하여 대부분의 `struct` 멤버에서 유효합니다. 단, 다음과 같은 몇 가지 제한 사항이 있습니다.

- `readonly` 정적 메서드 또는 속성을 선언할 수 없습니다.
- `readonly` 생성자를 선언할 수 없습니다.

속성 또는 인덱서 선언에 `readonly` 한정자를 추가할 수 있습니다.

```csharp
readonly public int Counter
{
  get { return 0; }
  set {} // not useful, but legal
}
```

속성 또는 인덱서의 개별 `get` 또는 `set` 접근자에 `readonly` 한정자를 추가할 수도 있습니다.

```csharp
public int Counter
{
  readonly get { return _counter; }
  set { _counter = value; }
}
int _counter;
```

속성과 해당 속성의 접근자 중 하나 이상에 `readonly` 한정자를 모두 추가할 수 없습니다. 동일한 제한이 인덱서에도 적용됩니다.

컴파일러는 컴파일러 구현 코드에서 상태를 수정하지 않는 자동 구현 속성에 `readonly` 한정자를 암시적으로 적용합니다. 다음 선언과 동일합니다.

```csharp
public readonly int Index { get; }
// Or:
public int Number { readonly get; }
public string Message { readonly get; set; }
```

해당 위치에 `readonly` 한정자를 추가할 수도 있지만 아무 의미도 없습니다. 자동 구현 속성 setter 또는 읽기/쓰기 자동 구현 속성에 `readonly` 한정자를 추가할 수 없습니다.

## <a name="ref-readonly-return-example"></a>참조 읽기 전용 반환 예

`ref return`의 `readonly` 한정자는 반환된 참조를 수정할 수 없음을 나타냅니다. 다음 예제는 원점에 대한 참조를 반환합니다. 예제에서는 `readonly` 한정자를 사용하여 호출자가 원본을 수정할 수 없음을 나타냅니다.

[!code-csharp[readonly struct example](~/samples/snippets/csharp/keywords/ReadonlyKeywordExamples.cs#ReadonlyReturn)]

반환된 유형은 `readonly struct`일 필요는 없습니다. `ref readonly`를 통해 `ref`에서 반환될 수 있는 모든 형식을 반환할 수 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

언어 사양 제안도 확인할 수 있습니다.

- [readonly ref 및 readonly 구조체](~/_csharplang/proposals/csharp-7.2/readonly-ref.md)
- [readonly 구조체 멤버](~/_csharplang/proposals/csharp-8.0/readonly-instance-members.md)

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [한정자](index.md)
- [const](const.md)
- [Fields](../../programming-guide/classes-and-structs/fields.md)
