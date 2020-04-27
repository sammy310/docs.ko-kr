---
title: 'C# 예약된 특성: null 허용 정적 분석'
ms.date: 04/14/2020
description: null 허용 참조 형식 및 null을 허용하지 않는 참조 형식에 대한 더 나은 정적 분석을 제공하기 위해 컴파일러가 이 특성을 해석합니다.
ms.openlocfilehash: 33521133a6a01196e6e1ab9c3cdc191a24f1ecf3
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102712"
---
# <a name="reserved-attributes-contribute-to-the-compilers-null-state-static-analysis"></a>예약된 특성은 컴파일러의 null 상태 정적 분석에 사용됩니다.

null 허용 컨텍스트에서 컴파일러는 코드의 정적 분석을 수행하여 모든 참조 형식 변수의 null 상태를 확인합니다.

- ‘null이 아님’:  정적 분석에서 변수에 null이 아닌 값이 할당된 것으로 확인되었습니다.
- ‘null일 수 있음’:  정적 분석에서 변수에 null이 아닌 값이 할당되었는지 확인할 수 없습니다.

API의 의미 체계에 대한 정보를 컴파일러에 제공하는 다양한 특성을 적용할 수 있습니다. 이 정보는 컴파일러에서 정적 분석을 수행하고 변수가 null이 아닌 경우를 확인하는 데 도움이 됩니다. 이 문서에서는 각 특성 및 사용 방법에 대해 간단하게 설명합니다. 모든 예제에서는 C# 8.0 이상을 사용한다고 가정하며 코드는 null 허용 컨텍스트에 있습니다.

친숙한 예제부터 살펴보겠습니다. 라이브러리에 리소스 문자열을 검색하는 다음 API가 있다고 가정합니다.

```csharp
bool TryGetMessage(string key, out string message)
```

앞의 예제는 .NET의 친숙한 `Try*` 패턴을 따릅니다. 이 API에 대한 두 개의 참조 인수인 `key` 및 `message` 매개 변수가 있습니다. 이 API에는 해당 인수의 nullness에 관련된 다음 규칙이 있습니다.

- 호출자는 `null`을 `key`의 인수로 전달하지 않아야 합니다.
- 호출자는 값이 `null`인 변수를 `message`의 인수로 전달할 수 있습니다.
- `TryGetMessage` 메서드가 `true`를 반환하면 `message` 값은 null이 아닙니다. 반환 값이 `false,`이면 `message`의 값과 해당 null 상태는 null입니다.

`key`에 대한 규칙은 변수 형식으로 표현될 수 있습니다. `key`는 null을 허용하지 않는 참조 형식이어야 합니다. `message` 매개 변수는 더 복잡합니다. `null`을 인수로 허용하지만, 성공 시 해당 `out` 인수가 null이 아님을 보장합니다. 이 시나리오의 경우 기대치를 설명하는 더 다양한 어휘가 필요합니다.

변수의 null 상태에 대한 추가 정보를 표현하기 위해 여러 가지 특성이 추가되었습니다. C# 8에 null 허용 참조 형식을 도입하기 전에 작성한 모든 코드는 ‘null 인식 불가능’이었습니다.  즉, 모든 참조 형식 변수가 null일 수 있지만 null 검사가 필요하지 않습니다. 코드가 ‘null 허용 인식’이 되면 해당 규칙이 변경됩니다.  참조 형식은 `null` 값이 아니어야 하며 null 허용 참조 형식은 참조되기 전에 `null`에 대해 검사되어야 합니다.

API에 대한 규칙은 `TryGetValue` API 시나리오에서 살펴본 것처럼 더 복잡할 수 있습니다. 대부분의 API에는 변수가 `null`일 수 있거나 없는 경우에 대한 더 복잡한 규칙이 있습니다. 이 경우에는 다음 특성 중 하나를 사용하여 해당 규칙을 표현합니다.

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): null을 허용하지 않는 입력 인수는 null일 수 있습니다.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): null 허용 입력 인수는 null이 아니어야 합니다.
- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): null을 허용하지 않는 반환 값은 null일 수 있습니다.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): null 허용 반환 값은 null이 아닙니다.
- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null을 허용하지 않는 입력 인수는 null일 수 있습니다.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null 허용 입력 인수는 null이 아닙니다.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): 지정된 매개 변수의 인수가 null이 아닌 경우 반환 값은 null이 아닙니다.
- [DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): 메서드는 값을 반환하지 않습니다. 즉, 항상 예외를 throw합니다.
- [DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): 연결된 `bool` 매개 변수에 지정된 값이 있는 경우 이 메서드는 값을 반환하지 않습니다.

앞의 설명은 각 특성이 수행하는 작업에 대한 빠른 참조입니다. 다음 각 섹션에서는 동작과 의미에 대해 더 자세히 설명합니다.

이 특성을 추가하면 API 규칙에 대한 자세한 정보가 컴파일러에 제공됩니다. 호출 코드가 null 허용 사용 가능 컨텍스트에서 컴파일되는 경우 컴파일러는 해당 규칙을 위반할 때 호출자에게 경고를 표시합니다. 이 특성은 구현에 대한 추가 검사를 사용하지 않습니다.

## <a name="specify-preconditions-allownull-and-disallownull"></a>전제 조건 지정: `AllowNull` 및 `DisallowNull`

읽기/쓰기 속성에는 적절한 기본값이 있으므로 `null`을 반환하지 않는 읽기/쓰기 속성을 살펴봅니다. 호출자는 속성을 해당 기본값으로 설정할 때 set 접근자에 `null`을 전달합니다. 예를 들어 대화방에서 화면 이름을 요청하는 메시지 시스템을 살펴봅니다. 아무것도 제공되지 않으면 시스템은 임의 이름을 생성합니다.

```csharp
public string ScreenName
{
   get => screenName;
   set => screenName = value ?? GenerateRandomScreenName();
}
private string screenName;
```

null 허용 인식 불가능 컨텍스트에서 이전 코드를 컴파일하면 정상적으로 작동합니다. null 허용 참조 형식을 사용하도록 설정하면 `ScreenName` 속성이 null을 허용하지 않는 참조가 됩니다. `get` 접근자의 경우도 마찬가지입니다. 이 접근자는 `null`을 반환하지 않습니다. 호출자는 `null`에 대해 반환된 속성을 검사할 필요가 없습니다. 그러나 지금 속성을 `null`로 설정하면 경고가 생성됩니다. 이 형식의 코드를 계속 지원하기 위해 다음 코드와 같이 속성에 <xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute?displayProperty=nameWithType> 특성을 추가합니다.

```csharp
[AllowNull]
public string ScreenName
{
   get => screenName;
   set => screenName = value ?? GenerateRandomScreenName();
}
private string screenName = GenerateRandomScreenName();
```

이 특성과 이 문서에 설명된 다른 특성을 사용하려면 <xref:System.Diagnostics.CodeAnalysis>에 대한 `using` 지시문을 추가해야 할 수 있습니다. 이 특성은 `set` 접근자가 아니라 속성에 적용됩니다. `AllowNull` 특성은 ‘전제 조건’을 지정하며 입력에만 적용됩니다.  `get` 접근자에는 반환 값이 있지만 입력 인수가 없습니다. 따라서 `AllowNull` 특성은 `set` 접근자에만 적용됩니다.

앞의 예제에서는 인수에 대한 `AllowNull` 특성을 추가할 때 검색할 항목을 보여 줍니다.

1. 해당 변수에 대한 일반 계약은 `null`이 아니어야 하므로 null을 허용하지 않는 참조 형식이 필요합니다.
1. 가장 일반적인 사용은 아니지만 입력 변수가 `null`이 되는 시나리오가 있습니다.

일반적으로 속성이나 `in`, `out` 및 `ref` 인수의 경우 이 특성이 필요합니다. `AllowNull` 특성은 일반적으로 변수가 null이 아닌 경우에 가장 적합하지만, `null`을 전제 조건으로 허용해야 합니다.

`DisallowNull` 사용에 대한 시나리오와 비교해 보세요. 이 특성을 사용하여 null 허용 참조 형식의 입력 변수가 `null`이 아니도록 지정합니다. 기본값이 `null`이지만 클라이언트에서 null이 아닌 값으로만 설정할 수 있는 속성을 살펴봅니다. 다음 코드를 살펴보세요.

```csharp
public string ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string _comment;
```

이전 코드는 `ReviewComment`가 `null`일 수 있지만 `null`로 설정될 수 없는 의도를 표현하는 가장 좋은 방법입니다. 이 코드가 null 허용 인식이 되면 <xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute?displayProperty=nameWithType>를 사용하여 호출자에게 이 개념을 보다 명확하게 표현할 수 있습니다.

```csharp
[DisallowNull]
public string? ReviewComment
{
    get => _comment;
    set => _comment = value ?? throw new ArgumentNullException(nameof(value), "Cannot set to null");
}
string? _comment;
```

null 허용 컨텍스트에서 `ReviewComment` `get` 접근자는 `null`의 기본값을 반환할 수 있습니다. 컴파일러는 액세스하기 전에 검사해야 한다는 경고를 표시합니다. 또한 `null`일 수 있는 경우에도 호출자가 명시적으로 `null`로 설정하지 않아야 한다는 경고를 호출자에게 표시합니다. 또한 `DisallowNull` 특성은 ‘전제 조건’을 지정하며 `get` 접근자에는 영향을 주지 않습니다.  다음에 대해 이 특성을 관찰할 때 `DisallowNull` 특성을 사용합니다.

1. 변수는 처음 인스턴스화될 때 주로 핵심 시나리오에서 `null`일 수 있습니다.
1. 변수를 명시적으로 `null`로 설정하면 안 됩니다.

이 상황은 원래 ‘null 인식 불가능’이었던 코드에서 일반적입니다.  개체 속성은 두 개의 개별 초기화 작업에서 설정될 수 있습니다. 일부 속성은 일부 비동기 작업이 완료된 후에만 설정될 수 있습니다.

`AllowNull` 및 `DisallowNull` 특성을 사용하여 변수에 대한 전제 조건이 해당 변수의 null 허용 주석과 일치하지 않을 수 있도록 지정할 수 있습니다. 이 특성은 API의 특징에 대한 자세한 정보를 제공합니다. 이 추가 정보는 호출자가 API를 올바르게 사용하는 데 도움이 됩니다. 다음 특성을 사용하여 전제 조건을 지정해야 합니다.

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): null을 허용하지 않는 입력 인수는 null일 수 있습니다.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): null 허용 입력 인수는 null이 아니어야 합니다.

## <a name="specify-post-conditions-maybenull-and-notnull"></a>사후 조건 지정: `MaybeNull` 및 `NotNull`

다음 시그니처를 사용하는 메서드가 있다고 가정합니다.

```csharp
public Customer FindCustomer(string lastName, string firstName)
```

검색한 이름을 찾을 수 없는 경우 `null`을 반환하도록 이 메서드를 작성했을 수 있습니다. `null`은 분명히 레코드를 찾을 수 없음을 나타냅니다. 이 예제에서는 반환 형식을 `Customer`에서 `Customer?`로 변경할 수 있습니다. 반환 값을 null 허용 참조 형식으로 선언하면 이 API의 의도가 분명하게 지정됩니다.

[제네릭 정의 및 null 허용 여부](../../nullable-migration-strategies.md#generic-definitions-and-nullability)에서 설명되는 이유로 해당 기술은 제네릭 메서드에서 작동하지 않습니다. 비슷한 패턴을 따르는 제네릭 메서드가 있을 수 있습니다.

```csharp
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> match)
```

반환 값이 `T?`이도록 지정할 수 없습니다. 검색한 항목을 찾을 수 없는 경우 메서드는 `null`을 반환합니다. `T?` 반환 형식을 선언할 수 없으므로 `MaybeNull` 주석을 메서드 반환에 추가합니다.

```csharp
[return: MaybeNull]
public T Find<T>(IEnumerable<T> sequence, Func<T, bool> match)
```

이전 코드는 계약이 null을 허용하지 않는 형식을 의미한다는 것을 호출자에게 알리지만, 반환 값은 실제로 null’일 수 있습니다’.   API가 null을 허용하지 않는 형식(일반적으로 제네릭 형식 매개 변수)이어야 하지만 `null`이 반환되는 인스턴스가 있을 수 있는 경우 `MaybeNull` 특성을 사용합니다.

형식이 null 허용 참조 형식인 경우에도 반환 값이나 `out` 또는 `ref` 인수가 null이 아니도록 지정할 수도 있습니다. 배열이 많은 요소를 포함할 만큼 충분히 큰지 확인하는 메서드를 살펴봅니다. 입력 인수에 용량이 없으면 루틴은 새 배열을 할당하고 기존 요소를 모두 새 배열로 복사합니다. 입력 인수가 `null`이면 루틴은 새 스토리지를 할당합니다. 충분한 용량이 있는 경우 루틴은 아무 작업도 수행하지 않습니다.

```csharp
public void EnsureCapacity<T>(ref T[] storage, int size)
```

다음과 같이 이 루틴을 호출할 수 있습니다.

```csharp
// messages has the default value (null) when EnsureCapacity is called:
EnsureCapacity<string>(ref messages, 10);
// messages is not null.
EnsureCapacity<string>(messages, 50);
```

null 참조 형식을 사용하도록 설정한 후 이전 코드가 경고 없이 컴파일되는지 확인하려고 합니다. 메서드가 반환하는 경우 `storage` 인수는 null이 아님이 보장됩니다. 그러나 null 참조를 사용하여 `EnsureCapacity`를 호출할 수 있습니다. `storage`를 null 허용 참조 형식으로 만들고 `NotNull` 사후 조건을 매개 변수 선언에 추가할 수 있습니다.

```csharp
public void EnsureCapacity<T>([NotNull]ref T[]? storage, int size)
```

이전 코드는 기존 계약을 명확하게 표현합니다. 호출자는 `null` 값과 함께 변수를 전달할 수 있지만 반환 값은 null이 아님이 보장됩니다. `null`이 인수로 전달될 수 있지만 메서드가 반환할 때 해당 인수가 null이 아님이 보장되는 경우 `NotNull` 특성은 `ref` 및 `out` 인수에 가장 유용합니다.

다음 특성을 사용하여 무조건 사후 조건을 지정합니다.

- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): null을 허용하지 않는 반환 값은 null일 수 있습니다.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): null 허용 반환 값은 null이 아닙니다.

## <a name="specify-conditional-post-conditions-notnullwhen-maybenullwhen-and-notnullifnotnull"></a>조건부 사후 조건 지정: `NotNullWhen`, `MaybeNullWhen` 및 `NotNullIfNotNull`

`string` 메서드 <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType>에 대해 잘 알고 있을 수 있습니다. 인수가 null이거나 빈 문자열인 경우 이 메서드는 `true`를 반환합니다. 이는 null 검사의 한 가지 형태입니다. 메서드가 `false`를 반환하는 경우 호출자는 인수를 null 검사할 필요가 없습니다. 메서드를 이 null 허용 인식처럼 만들려면 인수를 null 허용 참조 형식으로 설정하고 `NotNullWhen` 특성을 추가합니다.

```csharp
bool IsNullOrEmpty([NotNullWhen(false)]string? value);
```

이를 통해 반환 값이 `false`인 코드는 null 검사할 필요가 없음을 컴파일러에 알립니다. 특성을 추가하여 `IsNullOrEmpty`가 필요한 null 검사를 수행한다는 것을 컴파일러의 정적 분석에 알립니다. `false`를 반환하는 경우 입력 인수는 `null`이 아닙니다.

```csharp
string? userInput = GetUserInput();
if (!string.IsNullOrEmpty(userInput))
{
   int messageLength = userInput.Length; // no null check needed.
}
// null check needed on userInput here.
```

.NET Core 3.0의 경우 위에 표시된 대로 <xref:System.String.IsNullOrEmpty(System.String)?DisplayProperty=nameWithType> 메서드가 주석으로 처리됩니다. null 값에 대한 개체의 상태를 확인하는 비슷한 메서드가 코드베이스에 있을 수 있습니다. 컴파일러는 사용자 지정 null 검사 메서드를 인식하지 않으며 주석을 직접 추가해야 합니다. 특성을 추가하면 컴파일러의 정적 분석은 테스트된 변수가 null 검사된 시기를 알 수 있습니다.

또한 이 특성은 `Try*` 패턴에 사용됩니다. `ref` 및 `out` 변수에 대한 사후 조건은 반환 값을 통해 전달됩니다. 앞에서 설명한 이 메서드를 살펴봅니다.

```csharp
bool TryGetMessage(string key, out string message)
```

이전 메서드는 일반적인 .NET 관용구를 따릅니다. 반환 값은 `message`가 발견된 값으로 설정되었는지 또는 메시지가 없는 경우 기본값으로 설정되었는지 여부를 나타냅니다. 메서드가 `true`를 반환하는 경우 `message`의 값은 null이 아닙니다. 이 값을 반환하지 않는 경우 메서드는 `message`를 null로 설정합니다.

`NotNullWhen` 특성을 사용하여 해당 관용구를 전달할 수 있습니다. null 허용 참조 형식의 시그니처를 업데이트하는 경우 `string?`을 `message`로 만들고 특성을 추가합니다.

```csharp
bool TryGetMessage(string key, [NotNullWhen(true)] out string? message)
```

이전 예제에서 `TryGetMessage`가 `true`를 반환하는 경우 `message` 값은 null이 아닌 것으로 알려져 있습니다. 동일한 방식으로 코드베이스에서 비슷한 메서드를 주석으로 처리해야 합니다. 인수는 `null`일 수 있으며 메서드가 `true`를 반환하는 경우 null이 아닌 것으로 알려져 있습니다.

한 가지 마지막 특성이 필요할 수도 있습니다. 경우에 따라 반환 값의 null 상태는 하나 이상 입력 인수의 null 상태에 따라 달라집니다. 해당 메서드는 특정 입력 인수가 `null`이 아닐 때마다 null이 아닌 값을 반환합니다. 해당 메서드를 주석으로 올바르게 처리하려면 `NotNullIfNotNull` 특성을 사용합니다. 다음 태그를 살펴봅니다.

```csharp
string GetTopLevelDomainFromFullUrl(string url);
```

`url` 인수가 null이 아니면 출력은 `null`이 아닙니다. null 허용 참조가 사용하도록 설정되면 API에서 null 입력을 허용하지 않는 경우 해당 시그니처가 제대로 작동합니다. 그러나 입력이 null일 수 있는 경우에는 반환 값도 null일 수 있습니다. 따라서 시그니처를 다음 코드로 변경할 수 있습니다.

```csharp
string? GetTopLevelDomainFromFullUrl(string? url);
```

또한 시그니처가 작동하지만 호출자가 추가 `null` 검사를 강제로 구현하는 경우가 많습니다. 계약은 입력 인수 `url`이 `null`인 경우에만 반환 값이 `null`이라는 것입니다. 해당 계약을 표현하려면 다음 코드와 같이 이 메서드를 주석으로 처리합니다.

```csharp
[return: NotNullIfNotNull("url")]
string? GetTopLevelDomainFromFullUrl(string? url);
```

반환 값 및 인수 중 하나가 `null`일 수 있음을 나타내는 `?`를 사용하여 두 항목을 모두 주석으로 처리했습니다. 특성은 `url` 인수가 `null`이 아닌 경우 반환 값이 null이 아님을 명확하게 설명합니다.

해당 특성을 사용하여 조건부 사후 조건을 지정합니다.

- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null을 허용하지 않는 입력 인수는 null일 수 있습니다.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null 허용 입력 인수는 null이 아닙니다.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): 지정된 매개 변수의 입력 인수가 null이 아닌 경우 반환 값은 null이 아닙니다.

## <a name="verify-unreachable-code"></a>접근할 수 없는 코드 확인

일반적으로 예외 도우미 또는 기타 유틸리티 메서드와 같은 일부 메서드는 항상 예외를 throw하여 종료됩니다. 또는 도우미는 부울 인수 값을 기반으로 예외를 throw할 수 있습니다.

첫 번째 경우에 `DoesNotReturn` 특성을 메서드 선언에 추가할 수 있습니다. 컴파일러는 세 가지 방법으로 도움이 됩니다. 첫째, 예외를 throw하지 않고 메서드가 종료될 수 있는 경로가 있는 경우 컴파일러는 경고를 발생시킵니다. 둘째, 컴파일러는 해당 메서드를 호출한 후 적절한 `catch` 절이 나타날 때까지 코드를 ‘접근할 수 없음’으로 표시합니다.  셋째, 접근할 수 없는 코드는 null 상태에 영향을 주지 않습니다. 이 메서드를 살펴봅니다.

```csharp
[DoesNotReturn]
private void FailFast()
{
   throw new InvalidOperationException();
}

public void SetState(object containedField)
{
   if (!isInitialized)
      FailFast();

   // unreachable code:
   this.field = containedField;
}
```

두 번째 경우에는 메서드의 부울 매개 변수에 `DoesNotReturnIf` 특성을 추가합니다. 이전 예제를 다음과 같이 수정할 수 있습니다.

```csharp
private void FailFast([DoesNotReturnIf(false)]bool isValid)
{
   if (!isValid)
       throw new InvalidOperationException();
}

public void SetState(object containedField)
{
   FailFast(isInitialized);

   // unreachable code when "isInitialized" is false:
   this.field = containedField;
}
```

## <a name="summary"></a>요약

null 허용 참조 형식을 추가하면 `null`일 수 있는 변수의 API 기대치를 설명하는 초기 어휘가 제공됩니다. 추가 특성은 변수의 null 상태를 전제 조건 및 사후 조건으로 설명하는 다양한 어휘를 제공합니다. 해당 특성은 기대치를 명확하게 설명하며 API를 사용하는 개발자에게 더 나은 환경을 제공합니다.

null 허용 컨텍스트의 라이브러리를 업데이트할 때 해당 특성을 추가하여 API 사용자가 올바르게 사용하도록 안내합니다. 해당 특성을 통해 입력 인수 및 반환 값의 null 상태를 완벽하게 설명할 수 있습니다.

- [AllowNull](xref:System.Diagnostics.CodeAnalysis.AllowNullAttribute): null을 허용하지 않는 입력 인수는 null일 수 있습니다.
- [DisallowNull](xref:System.Diagnostics.CodeAnalysis.DisallowNullAttribute): null 허용 입력 인수는 null이 아니어야 합니다.
- [MaybeNull](xref:System.Diagnostics.CodeAnalysis.MaybeNullAttribute): null을 허용하지 않는 반환 값은 null일 수 있습니다.
- [NotNull](xref:System.Diagnostics.CodeAnalysis.NotNullAttribute): null 허용 반환 값은 null이 아닙니다.
- [MaybeNullWhen](xref:System.Diagnostics.CodeAnalysis.MaybeNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null을 허용하지 않는 입력 인수는 null일 수 있습니다.
- [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute): 메서드가 지정된 `bool` 값을 반환하는 경우 null 허용 입력 인수는 null이 아닙니다.
- [NotNullIfNotNull](xref:System.Diagnostics.CodeAnalysis.NotNullIfNotNullAttribute): 지정된 매개 변수의 입력 인수가 null이 아닌 경우 반환 값은 null이 아닙니다.
- [DoesNotReturn](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnAttribute): 메서드는 값을 반환하지 않습니다. 즉, 항상 예외를 throw합니다.
- [DoesNotReturnIf](xref:System.Diagnostics.CodeAnalysis.DoesNotReturnIfAttribute): 연결된 `bool` 매개 변수에 지정된 값이 있는 경우 이 메서드는 값을 반환하지 않습니다.
