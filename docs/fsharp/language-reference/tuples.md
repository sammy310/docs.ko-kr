---
title: 튜플
description: 알아봅니다는 F# 튜플 명명 되지는 않았지만 순서가 지정 된 값의 그룹화 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 950451ad1672e0c9fc609773f1bc32fc13636ddb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645110"
---
# <a name="tuples"></a>튜플

A *튜플* 명명 되지는 않았지만 순서가 지정 된 값의 그룹화입니다.  참조 형식 또는 구조체에는 튜플 일 수 있습니다.

## <a name="syntax"></a>구문

```fsharp
(element, ... , element)
struct(element, ... ,element )
```

## <a name="remarks"></a>설명

각 *요소* 위 구문에서 든 사용할 수 F# 식입니다.

## <a name="examples"></a>예제

튜플의 예로 쌍, 삼중 쌍, 등과 같은 또는 다른 형식의 들 수 있습니다. 몇 가지 예는 다음 코드에 나와 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L6-L21)]

## <a name="obtaining-individual-values"></a>개별 값 가져오기

사용할 수 있습니다 패턴 일치 액세스 및 튜플 요소에 대 한 이름을 할당 하려면 다음 코드 에서처럼.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L27-L29)]

또한 외부 패턴 일치를 통해 튜플을 분해할 수는 `match` 식을 통해 `let` 바인딩:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L34-L37)]

Or 패턴 수 튜플 함수에 대 한 입력으로 일치 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L43-L47)]

튜플 요소가 하나만 필요한 경우 와일드 카드 문자 (밑줄) 필요 하지 않은 값에 대 한 새 이름을 만들지 않도록 방지 하려면 사용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L53-L54)]

구조체 튜플로 참조 튜플에서 요소를 복사 하는 작업도 간단 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L62-L66)]

함수 `fst` 고 `snd` (튜플만 참조) 첫 번째 반환 된 튜플의 요소를 각각 두 번째 및 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L72-L73)]

튜플의 세 번째 요소를 반환 하는 기본 제공 함수가 있지만 쉽게 작성할 수 있습니다 하나 다음과 같습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L78-L78)]

일반적으로 개별 튜플 요소에 액세스 하려면 패턴 일치를 사용 하는 것이 좋습니다.

## <a name="using-tuples"></a>튜플을 사용 하 여

튜플 다음 예와에서 같이 함수에서 여러 값을 반환 하는 편리한 방법을 제공 합니다. 이 예제에서는 정수 나누기를 수행 하 고 튜플 쌍의 첫 번째 멤버로 작업 쌍의 두 번째 구성원으로 나머지의 반올림 된 결과 반환 합니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L83-L86)]

튜플 암시 일반적인 함수 구문 하는 함수 인수 암시적 커리 방지 하려는 경우 함수 인수로 사용할 수도 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L88-L88)]

함수를 정의 하는 일반적인 구문은 `let sum a b = a + b` 다음 코드 에서처럼는 함수의 첫 번째 인수의 부분 적용 하는 함수를 정의할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/basic-examples.fsx#L90-L94)]

튜플을 사용 하 여 매개 변수로 (currying) 사용 하지 않도록 설정 합니다. 자세한 내용은 "응용 프로그램의 인수 부분"를 참조 하세요 [함수](functions/index.md)합니다.

## <a name="names-of-tuple-types"></a>튜플 형식의 이름

튜플 형식 이름을 작성 하는 경우 사용할는 `*` 요소를 구분 하는 기호입니다. 구성 된 튜플에 대 한는 `int`, `float`, 및 `string`, 같은 `(10, 10.0, "ten")`, 종류는 다음과 같이 작성 될 수입니다.

```fsharp
int * float * string
```

## <a name="interoperation-with-c-tuples"></a>C# 튜플와의 상호 운용

C# 7.0에서는 튜플 언어 소개합니다.  튜플 C# 구조체 되며에서 구조체 튜플에 해당 하는 F#합니다.  C#을 사용 하 여 상호 운용 해야 하는 경우에 구조체 튜플을 사용 해야 합니다.

작업을 수행 하는 것과 쉽습니다.  예를 들어 C# 클래스에 튜플을 전달 하 고는 튜플을 해당 결과 사용할 수 있다고 가정해 보겠습니다.

```csharp
namespace CSharpTupleInterop
{
    public static class Example
    {
        public static (int, int) AddOneToXAndY((int x, int y) a) =>
            (a.x + 1, a.y + 1);
    }
}
```

에 F# 코드를 다음 구조체 튜플 매개 변수로 전달 하 고 구조체 튜플 결과 사용할 수 있습니다.

```fsharp
open TupleInterop

let struct (newX, newY) = Example.AddOneToXAndY(struct (1, 2))
// newX is now 2, and newY is now 3
```

### <a name="converting-between-reference-tuples-and-struct-tuples"></a>참조 튜플과 구조체 형식 사이의 변환

참조 튜플과 구조체에 완전히 다른 내부 표현 되어 암시적으로 변환할 수는 없습니다.  즉, 다음과 같은 코드가 컴파일되지 않습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L5-L12)]

패턴 해야 1 개의 튜플이 일치 및 다른 구성 요소를 생성 합니다.  예를 들어:

[!code-fsharp[Main](../../../samples/snippets/fsharp/tuples/interop.fsx#L18-L22)]

## <a name="compiled-form-of-reference-tuples"></a>컴파일된 참조 튜플 형식

이 섹션에서는 컴파일하면 튜플 형식의 설명 합니다.  정보에는.NET Framework 3.5를 대상으로 하는 경우가 아니면를 읽는 데 필요한 이하로 하지 않습니다.

튜플 형식의 몇 가지 일반, 모든 명명 된 개체 컴파일됩니다 `System.Tuple`, 인자 수, 또는 형식 매개 변수의 개수를 오버 로드 됩니다.입니다. 볼 때 다른 언어에서 같은 튜플 형식이 형태로 나타나는 C# 또는 Visual Basic의 인식 되지 않는 도구를 사용 하는 경우 또는 F# 를 생성 합니다. `Tuple` 형식을.NET Framework 4에서 도입 되었습니다. 이전 버전의.NET Framework를 대상으로 하는 경우 컴파일러의 버전을 사용 [System.Tuple](https://msdn.microsoft.com/library/5ac7953d-acdc-4a58-bfb7-c1f6406c0fa3) 의 2.0 버전에서의 F# 핵심 라이브러리입니다. 이 라이브러리의 형식은 2.0, 3.0 및 3.5 버전의.NET Framework를 대상으로 하는 응용 프로그램에만 사용 됩니다. 형식 전달을.NET Framework 2.0 및.NET Framework 4 간의 이진 호환성을 유지 하는 데 사용 됩니다 F# 구성 요소입니다.

### <a name="compiled-form-of-struct-tuples"></a>컴파일된 구조체 튜플 형식

구조체 튜플 (예를 들어 `struct (x, y)`), 참조 튜플에 근본적으로 다릅니다.  컴파일되지는 <xref:System.ValueTuple> 형식, 형식 매개 변수의 개수나 인자 수, 오버 로드 됩니다.  동일 [C# 7.0 튜플](../../csharp/tuples.md) 및 [Visual Basic 2017 튜플](../../visual-basic/programming-guide/language-features/data-types/tuples.md), 양방향 상호 운용 합니다.

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
- [F# 형식](fsharp-types.md)
