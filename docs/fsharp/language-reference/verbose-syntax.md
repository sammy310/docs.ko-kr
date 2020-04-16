---
title: 자세한 구문
description: F# 프로그래밍 언어에서 자세한 구문과 간단한 구문의 차이점을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 722807695c56beb0d681b95a78ed8cb8c1df3ddf
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463913"
---
# <a name="verbose-syntax"></a>자세한 구문

F# 언어의 많은 구문에사용할 수 있는 구문은 두 가지 형태가 있습니다: *자세한 구문과* *간단한 구문.* 자세한 구문은 일반적으로 사용되지 않지만 들여쓰기에 덜 민감하다는 장점이 있습니다. 간단한 구문은 짧으며 들여쓰기를 사용하여 구문 및 구문의 시작과 끝을 `begin`알리는 `end` `in`대신 " 및 와 같은 추가 키워드를 표시합니다. 기본 구문은 간단한 구문입니다. 이 항목에서는 경량 구문을 사용할 수 없는 경우 F# 구문에 대한 구문을 설명합니다. 자세한 구문은 항상 활성화되므로 간단한 구문을 사용하도록 설정하더라도 일부 구문에 대한 자세한 구문을 계속 사용할 수 있습니다. 지시문을 사용하여 간단한 구문을 `#light "off"` 비활성화할 수 있습니다.

## <a name="table-of-constructs"></a>구문 표

다음 표에서는 두 양식 간에 차이가 있는 컨텍스트에서 F# 언어 구문에 대한 가볍고 자세한 구문을 보여 준다. 이 표에서 각도 대괄호 ()&lt;&gt;사용자가 제공한 구문 요소를 둘러싸고 있습니다. 이러한 구문 내에서 사용되는 구문에 대한 자세한 내용은 각 언어 구문에 대한 설명서를 참조하십시오.

<table>
<tr>
<th>언어 구문</th>
<th>경량 구문</th>
<th>자세한 구문</th>
</tr>
<tr>
<td>
복합 식
</td>
<td>

```xml
<expression1 />
<expression2 />
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

중첩 `let` 바인딩

</td><td>

```fsharp
let f x =
    let a = 1
    let b = 2
    x + a + b
```

</td><td>

```fsharp
let f x =
    let a = 1 in
    let b = 2 in
    x + a + b
```

</td>
</tr>
<tr><td>
코드 블록
</td><td>

```fsharp
(
    <expression1>
    <expression2>
)
```

</td><td>

```fsharp
begin
    <expression1>;
    <expression2>;
end
```

</td>
</tr>
<tr><td>
`for...do`
</td><td>

```fsharp
for counter = start to finish do
    ...
```

</td><td>

```fsharp
for counter = start to finish do
    ...
done
```

</td>
</tr>
<tr><td>
`while...do`
</td><td>

```fsharp
while <condition> do
    ...
```

</td><td>

```fsharp
while <condition> do
    ...
done
```

</td>
</tr>
<tr><td>
`for...in`
</td><td>

```fsharp
for var in start .. finish do
    ...
```

</td><td>

```fsharp
for var in start .. finish do
    ...
done
```

</td>
</tr>
<tr><td>
`do`
</td><td>

```fsharp
do
    ...
```

</td><td>

```fsharp
do
    ...
in
```

</td>
</tr>
<tr><td>레코드(record)
</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    <value-or-member-definitions>
```

</td><td>

```fsharp
type <record-name> =
    {
        <field-declarations>
    }
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>class
</td><td>

```fsharp
type <class-name>(<params>) =
    ...
```

</td><td>

```fsharp
type <class-name>(<params>) =
    class
        ...
    end
```

</td>
</tr>
<tr><td>structure</td><td>

```fsharp
[<StructAttribute>]
type <structure-name> =
    ...
```

</td><td>

```fsharp
type <structure-name> =
    struct
        ...
    end
```

</td>
</tr>
<tr><td>차별된 노조</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    <value-or-member definitions>
```

</td><td>

```fsharp
type <union-name> =
    | ...
    | ...
    ...
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>interface(인터페이스)</td><td>

```fsharp
type <interface-name> =
    ...
```

</td><td>

```fsharp
type <interface-name> =
    interface
        ...
    end
```

</td>
</tr>
<tr><td>개체 표현식</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
        <interface-implementations>
}
```

</td><td>

```fsharp
{ new <type-name>
    with
        <value-or-member-definitions>
    end
    <interface-implementations>
}
```

</td>
</tr>
<tr><td>인터페이스 구현</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
interface <interface-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>유형 확장</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
```

</td><td>

```fsharp
type <type-name>
    with
        <value-or-member-definitions>
    end
```

</td>
</tr>
<tr><td>module</td><td>

```fsharp
module <module-name> =
    ...
```

</td><td>

```fsharp
module <module-name> =
    begin
        ...
    end
```

</td>
</tr>
</table>

## <a name="see-also"></a>참조

- [F # 언어 참조](index.md)
- [컴파일러 지시문](compiler-directives.md)
- [코드 서식 지정 지침](../style-guide/formatting.md)
