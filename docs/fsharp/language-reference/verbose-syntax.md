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
# <a name="verbose-syntax"></a><span data-ttu-id="4c5dd-103">자세한 구문</span><span class="sxs-lookup"><span data-stu-id="4c5dd-103">Verbose Syntax</span></span>

<span data-ttu-id="4c5dd-104">F# 언어의 많은 구문에사용할 수 있는 구문은 두 가지 형태가 있습니다: *자세한 구문과* *간단한 구문.*</span><span class="sxs-lookup"><span data-stu-id="4c5dd-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="4c5dd-105">자세한 구문은 일반적으로 사용되지 않지만 들여쓰기에 덜 민감하다는 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5dd-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="4c5dd-106">간단한 구문은 짧으며 들여쓰기를 사용하여 구문 및 구문의 시작과 끝을 `begin`알리는 `end` `in`대신 " 및 와 같은 추가 키워드를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5dd-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="4c5dd-107">기본 구문은 간단한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="4c5dd-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="4c5dd-108">이 항목에서는 경량 구문을 사용할 수 없는 경우 F# 구문에 대한 구문을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4c5dd-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="4c5dd-109">자세한 구문은 항상 활성화되므로 간단한 구문을 사용하도록 설정하더라도 일부 구문에 대한 자세한 구문을 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5dd-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="4c5dd-110">지시문을 사용하여 간단한 구문을 `#light "off"` 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5dd-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="4c5dd-111">구문 표</span><span class="sxs-lookup"><span data-stu-id="4c5dd-111">Table of Constructs</span></span>

<span data-ttu-id="4c5dd-112">다음 표에서는 두 양식 간에 차이가 있는 컨텍스트에서 F# 언어 구문에 대한 가볍고 자세한 구문을 보여 준다.</span><span class="sxs-lookup"><span data-stu-id="4c5dd-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="4c5dd-113">이 표에서 각도 대괄호 ()&lt;&gt;사용자가 제공한 구문 요소를 둘러싸고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4c5dd-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="4c5dd-114">이러한 구문 내에서 사용되는 구문에 대한 자세한 내용은 각 언어 구문에 대한 설명서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4c5dd-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="4c5dd-115">언어 구문</span><span class="sxs-lookup"><span data-stu-id="4c5dd-115">Language construct</span></span></th>
<th><span data-ttu-id="4c5dd-116">경량 구문</span><span class="sxs-lookup"><span data-stu-id="4c5dd-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="4c5dd-117">자세한 구문</span><span class="sxs-lookup"><span data-stu-id="4c5dd-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="4c5dd-118">복합 식</span><span class="sxs-lookup"><span data-stu-id="4c5dd-118">compound expressions</span></span>
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

<span data-ttu-id="4c5dd-119">중첩 `let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="4c5dd-119">nested `let` bindings</span></span>

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
<span data-ttu-id="4c5dd-120">코드 블록</span><span class="sxs-lookup"><span data-stu-id="4c5dd-120">code block</span></span>
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
<tr><td><span data-ttu-id="4c5dd-121">레코드(record)</span><span class="sxs-lookup"><span data-stu-id="4c5dd-121">record</span></span>
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
<tr><td><span data-ttu-id="4c5dd-122">class</span><span class="sxs-lookup"><span data-stu-id="4c5dd-122">class</span></span>
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
<tr><td><span data-ttu-id="4c5dd-123">structure</span><span class="sxs-lookup"><span data-stu-id="4c5dd-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="4c5dd-124">차별된 노조</span><span class="sxs-lookup"><span data-stu-id="4c5dd-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="4c5dd-125">interface(인터페이스)</span><span class="sxs-lookup"><span data-stu-id="4c5dd-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="4c5dd-126">개체 표현식</span><span class="sxs-lookup"><span data-stu-id="4c5dd-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="4c5dd-127">인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="4c5dd-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="4c5dd-128">유형 확장</span><span class="sxs-lookup"><span data-stu-id="4c5dd-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="4c5dd-129">module</span><span class="sxs-lookup"><span data-stu-id="4c5dd-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="4c5dd-130">참조</span><span class="sxs-lookup"><span data-stu-id="4c5dd-130">See also</span></span>

- [<span data-ttu-id="4c5dd-131">F # 언어 참조</span><span class="sxs-lookup"><span data-stu-id="4c5dd-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="4c5dd-132">컴파일러 지시문</span><span class="sxs-lookup"><span data-stu-id="4c5dd-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="4c5dd-133">코드 서식 지정 지침</span><span class="sxs-lookup"><span data-stu-id="4c5dd-133">Code Formatting Guidelines</span></span>](../style-guide/formatting.md)
