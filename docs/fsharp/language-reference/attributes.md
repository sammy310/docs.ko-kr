---
title: 특성
description: 에 대해 알아봅니다 하는 방법 F# 프로그래밍 구문에 적용할 메타 데이터 특성을 사용 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: fed4c549b95d6d3701ab81cf5d62add411c16038
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65642033"
---
# <a name="attributes"></a>특성

특성 프로그래밍 구문에 적용할 메타 데이터를 사용 하도록 설정 합니다.

## <a name="syntax"></a>구문

```fsharp
[<target:attribute-name(arguments)>]
```

## <a name="remarks"></a>설명

위 구문에는 *대상* 는 선택 사항이 며 있는 경우 특성에 적용 되는 프로그램 엔터티 종류를 지정 합니다. 유효한 값에 대 한 *대상* 이 문서의 뒷부분에 표시 되는 테이블에 표시 됩니다.

*특성 이름이* 접미사 없이 유효한 특성 형식 (네임 스페이스를 사용 하 여 정규화) 이름을 가리킵니다 `Attribute` 특성 형식 이름에서 일반적으로 사용 되는 합니다. 예를 들어, 형식 `ObsoleteAttribute` 로 줄일 수 `Obsolete` 이 컨텍스트에서 합니다.

합니다 *인수* 특성 형식에 대 한 생성자에 인수가 있습니다. 특성에 기본 생성자가 하는 경우 인수 목록 및 괄호를 생략할 수 있습니다. 특성 위치 인수와 명명 된 인수를 모두 지원합니다. *위치 인수* 나타나는 순서 대로 사용 되는 인수입니다. 특성에 public 속성이 있으면 명명 된 인수를 사용할 수 있습니다. 인수 목록에서 다음 구문을 사용 하 여이 설정할 수 있습니다.

```
*property-name* = *property-value*
```

이러한 속성 초기화 순서에 관계 없이 수는 있지만 위치 인수가 따라야 합니다. 다음은 위치 인수 및 속성 초기화를 사용 하는 특성의 예입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6202.fs)]

이 예제에서는 특성은 `DllImportAttribute`, 여기서 축약 형태로 사용 합니다. 첫 번째 인수는 위치 매개 변수 이며 두 번째 속성입니다.

특성 이라고 하는 개체를 활성화 하는.NET 프로그래밍 구문은는 *특성* 형식 또는 기타 프로그램 요소와 연결 되도록 합니다. 특성이 적용 되는 프로그램 요소 라고 합니다 *특성 대상을*합니다. 특성은 일반적으로 해당 대상에 대 한 메타 데이터를 포함 합니다. 이 컨텍스트에서 메타 데이터 필드와 멤버 이외의 형식에 대 한 모든 데이터를 수 있습니다.

특성 F# 프로그래밍 구문에 적용할 수 있습니다: 함수, 메서드, 어셈블리, 모듈, 형식 (클래스, 레코드, 구조, 인터페이스, 대리자, 열거형, 공용 구조체 및 등), 생성자, 속성, 필드 매개 변수를 매개 변수를 입력 하 고 값을 반환 합니다. 특성에서 허용 되지 않습니다 `let` 클래스, 식 또는 워크플로 식 내에서 바인딩에 있습니다.

일반적으로 특성 선언 특성 대상의 선언 바로 앞에 옵니다. 여러 특성 선언은 함께, 다음과 같이 사용할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6603.fs)]

.NET 리플렉션을 사용 하 여 런타임 시 특성을 쿼리할 수 있습니다.

이전 코드 예제와 같이 여러 특성을 개별적으로 선언할 수 있습니다 하거나 다음과 같이 개별 특성 및 생성자를 구분 하려면 세미콜론을 사용 하는 경우 대괄호 집합에서 선언할 수 있습니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6604.fs)]

일반적으로 특성을 `Obsolete` 특성, 보안 고려 사항에 대 한 COM 지원, 코드의 소유권과 관련 된 특성 및 특성 형식을 serialize 할 수 있는지 여부를 나타내는 특성입니다. 다음 예제에서는 사용 된 `Obsolete` 특성입니다.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6605.fs)]

특성 대상 `assembly` 하 고 `module`, 최상위 수준에 특성을 적용할 `do` 어셈블리의 바인딩. 단어를 포함할 수 있습니다 `assembly` 또는 `module` 다음과 같은 특성 선언에서.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6606.fs)]

특성 대상에 적용 된 특성을 생략 하면 경우를 `do` 바인딩를 F# 컴파일러에서 해당 특성에 대 한 적합 한 특성 대상을 확인 하려고 합니다. 여러 특성 클래스 형식의 특성이 `System.AttributeUsageAttribute` 해당 특성에 대해 지원 가능한 대상에 대 한 정보를 포함 하는 합니다. 경우는 `System.AttributeUsageAttribute` 는 특성의 대상으로 하는 함수 지원, 특성은 프로그램의 주 진입점에 적용 하는 데 걸린를 나타냅니다. 경우는 `System.AttributeUsageAttribute` 특성 대상으로 하는 어셈블리의 지원에 컴파일러는 어셈블리에 적용할 특성을 나타냅니다. 대부분의 특성 함수 및 어셈블리 모두에 적용 되지 않습니다 하지만 그럴 있는 경우에 프로그램의 main 함수에 적용할 특성 만들어진 합니다. 특성 대상을 명시적으로 지정 된 경우 특성은 지정된 된 대상에 적용 됩니다.

특성 대상에 대 한 유효한 값 명시적으로 지정 하려면 일반적으로 필요 하지 않습니다 하지만 *대상* 특성 사용의 예제와 함께 다음 표에 표시 됩니다.

<table>
  <tr>
    <th>특성 대상입니다.</td>
    <th>예제</td> 
  </tr>
  <tr>
    <td>어셈블리</td>
    <td><pre lang="fsharp"><code>[&lt;assembly: AssemblyVersionAttribute("1.0.0.0")&gt;]<code></pre></td> 
  </tr>
  <tr>
    <td>return</td>
    <td><pre lang="fsharp"><code>let function1 x : [&lt;return: Obsolete&gt;] int = x + 1<code></pre></td> 
  </tr>
  <tr>
    <td>필드(field)</td>
    <td><pre lang="fsharp"><code>[&lt;field: DefaultValue&gt;] val mutable x: int<code></pre></td> 
  </tr>
  <tr>
    <td>속성</td>
    <td><pre lang="fsharp"><code>[&lt;property: Obsolete&gt;] this.MyProperty = x<code></pre></td> 
  </tr>
  <tr>
    <td>param</td>
    <td><pre lang="fsharp"><code>member this.MyMethod([&lt;param: Out&gt;] x : ref&lt;int&gt;) = x := 10<code></pre></td> 
  </tr>
  <tr>
    <td>type</td>
    <td>
        <pre lang="fsharp"><code>
        [&lt;type: StructLayout(Sequential)&gt;] 
        type MyStruct = 
        struct 
        x : byte
        y : int
        end
        <code></pre>
    </td>
  </tr>
</table>

## <a name="see-also"></a>참고자료

- [F# 언어 참조](index.md)
