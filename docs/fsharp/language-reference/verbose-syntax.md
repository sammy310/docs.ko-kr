---
title: 자세한 구문
description: F# 프로그래밍 언어의 자세한 정보 표시와 간단한 구문 간의 차이점을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: 575585b201acc1366980cfc5cf523c4117259084
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73421174"
---
# <a name="verbose-syntax"></a><span data-ttu-id="c759b-103">자세한 구문</span><span class="sxs-lookup"><span data-stu-id="c759b-103">Verbose Syntax</span></span>

<span data-ttu-id="c759b-104">F# 언어의 여러 구문에 사용할 수 있는 구문에는 *자세한 구문* 및 *간단한*구문 이라는 두 가지 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-104">There are two forms of syntax available for many constructs in the F# language: *verbose syntax* and *lightweight syntax*.</span></span> <span data-ttu-id="c759b-105">자세한 구문은 일반적으로 사용 되지 않지만 들여쓰기에 대 한 덜 중요 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-105">The verbose syntax is not as commonly used, but has the advantage of being less sensitive to indentation.</span></span> <span data-ttu-id="c759b-106">간단한 구문은 더 짧고 들여쓰기를 사용 하 여 `begin`, `end`, `in`등의 추가 키워드가 아닌 구문의 시작과 끝을 신호로 알립니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-106">The lightweight syntax is shorter and uses indentation to signal the beginning and end of constructs, rather than additional keywords like `begin`, `end`, `in`, and so on.</span></span> <span data-ttu-id="c759b-107">기본 구문은 간단한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-107">The default syntax is the lightweight syntax.</span></span> <span data-ttu-id="c759b-108">이 항목에서는 간단한 구문을 사용 F# 하지 않는 경우의 구문에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-108">This topic describes the syntax for F# constructs when lightweight syntax is not enabled.</span></span> <span data-ttu-id="c759b-109">Verbose 구문은 항상 사용 하도록 설정 되어 있으므로 간단한 구문을 사용 하는 경우에도 일부 구문에 대해 자세한 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-109">Verbose syntax is always enabled, so even if you enable lightweight syntax, you can still use verbose syntax for some constructs.</span></span> <span data-ttu-id="c759b-110">`#light "off"` 지시어를 사용 하 여 간단한 구문을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-110">You can disable lightweight syntax by using the `#light "off"` directive.</span></span>

## <a name="table-of-constructs"></a><span data-ttu-id="c759b-111">구문 테이블</span><span class="sxs-lookup"><span data-stu-id="c759b-111">Table of Constructs</span></span>

<span data-ttu-id="c759b-112">다음 표에서는 두 형식 간에 차이가 있는 컨텍스트에서 F# 언어 구문의 간단한 구문 및 자세한 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-112">The following table shows the lightweight and verbose syntax for F# language constructs in contexts where there is a difference between the two forms.</span></span> <span data-ttu-id="c759b-113">이 표에서 꺾쇠 괄호 (&lt;&gt;)는 사용자가 제공 하는 구문 요소를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="c759b-113">In this table, angle brackets (&lt;&gt;) enclose user-supplied syntax elements.</span></span> <span data-ttu-id="c759b-114">이러한 구문 내에서 사용 되는 구문에 대 한 자세한 내용은 각 언어 구문에 대 한 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c759b-114">Refer to the documentation for each language construct for more detailed information about the syntax used within these constructs.</span></span>

<table>
<tr>
<th><span data-ttu-id="c759b-115">언어 구문</span><span class="sxs-lookup"><span data-stu-id="c759b-115">Language construct</span></span></th>
<th><span data-ttu-id="c759b-116">간단한 구문</span><span class="sxs-lookup"><span data-stu-id="c759b-116">Lightweight syntax</span></span></th>
<th><span data-ttu-id="c759b-117">자세한 구문</span><span class="sxs-lookup"><span data-stu-id="c759b-117">Verbose syntax</span></span></th>
</tr>
<tr>
<td>
<span data-ttu-id="c759b-118">복합 식</span><span class="sxs-lookup"><span data-stu-id="c759b-118">compound expressions</span></span>
</td>
<td>

```xml
<expression1>
<expression2>
```

</td><td>

```fsharp
<expression1>; <expression2>
```

</td>
</tr>
<tr><td>

<span data-ttu-id="c759b-119">중첩 된 `let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="c759b-119">nested `let` bindings</span></span>

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
<span data-ttu-id="c759b-120">코드 블록</span><span class="sxs-lookup"><span data-stu-id="c759b-120">code block</span></span>
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
<tr><td><span data-ttu-id="c759b-121">기록은</span><span class="sxs-lookup"><span data-stu-id="c759b-121">record</span></span>
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
<tr><td><span data-ttu-id="c759b-122">클래스</span><span class="sxs-lookup"><span data-stu-id="c759b-122">class</span></span>
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
<tr><td><span data-ttu-id="c759b-123">구조체(structure)</span><span class="sxs-lookup"><span data-stu-id="c759b-123">structure</span></span></td><td>

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
<tr><td><span data-ttu-id="c759b-124">구별 된 공용 구조체</span><span class="sxs-lookup"><span data-stu-id="c759b-124">discriminated union</span></span></td><td>

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
<tr><td><span data-ttu-id="c759b-125">interface(인터페이스)</span><span class="sxs-lookup"><span data-stu-id="c759b-125">interface</span></span></td><td>

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
<tr><td><span data-ttu-id="c759b-126">개체 식</span><span class="sxs-lookup"><span data-stu-id="c759b-126">object expression</span></span></td><td>

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
<tr><td><span data-ttu-id="c759b-127">인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="c759b-127">interface implementation</span></span></td><td>

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
<tr><td><span data-ttu-id="c759b-128">형식 확장</span><span class="sxs-lookup"><span data-stu-id="c759b-128">type extension</span></span></td><td>

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
<tr><td><span data-ttu-id="c759b-129">모듈(module)</span><span class="sxs-lookup"><span data-stu-id="c759b-129">module</span></span></td><td>

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

## <a name="see-also"></a><span data-ttu-id="c759b-130">참조</span><span class="sxs-lookup"><span data-stu-id="c759b-130">See also</span></span>

- [<span data-ttu-id="c759b-131">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="c759b-131">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="c759b-132">컴파일러 지시문</span><span class="sxs-lookup"><span data-stu-id="c759b-132">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="c759b-133">코드 서식 지정 지침</span><span class="sxs-lookup"><span data-stu-id="c759b-133">Code Formatting Guidelines</span></span>](../style-guide/formatting.md)
