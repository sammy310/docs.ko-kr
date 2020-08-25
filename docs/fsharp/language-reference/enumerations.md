---
title: 열거형
description: '리터럴 대신 F # 열거를 사용 하 여 코드를 보다 쉽게 읽고 유지 관리할 수 있도록 하는 방법을 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 5f298691ce48a06c203930c7742cf007c819dc33
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812109"
---
# <a name="enumerations"></a>열거형

열거형 ( *열거형* *이 라고도*함)은 레이블이 값의 하위 집합에 할당 되는 정수 계열 형식입니다. 코드를 더 읽기 쉽고 유지 가능하도록 만들기 위해 리터럴 대신 이를 사용할 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
type enum-name =
| value1 = integer-literal1
| value2 = integer-literal2
...
```

## <a name="remarks"></a>설명

열거형은 값을 지정할 수 있는 경우를 제외 하 고는 단순 값을 포함 하는 구별 된 공용 구조체와 매우 유사 하 게 보입니다. 값은 일반적으로 0 또는 1에서 시작 하는 정수 이거나 비트 위치를 나타내는 정수입니다. 열거형이 비트 위치를 나타내도록 하려는 경우 [Flags](xref:System.FlagsAttribute) 특성도 사용 해야 합니다.

열거형의 기본 형식은 사용 된 리터럴에 따라 결정 됩니다. 예를 들어, 등의 접미사를 사용 하 여, 등의 `1u` `2u` 부호 없는 정수 () 형식에 대해 리터럴을 사용할 수 있습니다 `uint32` .

명명 된 값을 참조 하는 경우 열거형 형식의 이름을 한정자로 사용 해야 `enum-name.value1` 합니다. 즉, 뿐 `value1` 입니다. 이 동작은 구별 된 공용 구조체의 동작과 다릅니다. 열거형은 항상 [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html) 특성을 포함 하기 때문입니다.

다음 코드에서는 열거형을 선언 하 고 사용 하는 방법을 보여 줍니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2101.fs)]

다음 코드와 같이 적절 한 연산자를 사용 하 여 열거형을 기본 형식으로 쉽게 변환할 수 있습니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2102.fs)]

열거 형식은,,,,,,,, `sbyte` `byte` `int16` `uint16` `int32` `uint32` `int64` `uint16` `uint64` 및와 `char` 같은 기본 형식 중 하나를 사용할 수 있습니다. 열거형 형식은 .NET Framework에서 상속 되는 형식으로 표현 됩니다 `System.Enum` `System.ValueType` . 따라서 이러한 값 형식은 스택에 있고 포함 하는 개체의 인라인 값 형식으로, 기본 형식의 값은 열거형의 유효한 값입니다. 이는 명명 되지 않은 값을 catch 하는 패턴을 제공 해야 하기 때문에 열거 값에 대 한 패턴 일치에서 중요 합니다.

`enum`F # 라이브러리의 함수를 사용 하 여 미리 정의 된 명명 된 값 중 하나 이외의 값을 포함 하 여 열거형 값을 생성할 수 있습니다. `enum`다음과 같이 함수를 사용 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2103.fs)]

기본 `enum` 함수는 형식에서 작동 합니다 `int32` . 따라서 다른 기본 형식을 가진 열거형 형식에는 사용할 수 없습니다. 대신 다음을 사용 합니다.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet2104.fs)]

또한 열거형의 사례는 항상로 내보내집니다 `public` . 이것은 c # 및 .NET 플랫폼의 나머지 부분에 맞게 정렬 됩니다.

## <a name="see-also"></a>참고 항목

- [F# 언어 참조](index.md)
- [캐스팅 및 변환](casting-and-conversions.md)
