---
title: 값 형식 - C# 참조
ms.date: 11/26/2018
f1_keywords:
- cs.valuetypes
helpviewer_keywords:
- value types [C#]
- types [C#], value types
- C# language, value types
ms.assetid: 471eb994-2958-49d5-a6be-19b4313f80a3
ms.openlocfilehash: 0ab9b6e089f5add9963ffae73e196643ad999763
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712912"
---
# <a name="value-types-c-reference"></a><span data-ttu-id="84ae6-102">값 형식(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="84ae6-102">Value types (C# Reference)</span></span>

<span data-ttu-id="84ae6-103">다음 두 가지 종류의 값 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-103">There are two kinds of value types:</span></span>

- [<span data-ttu-id="84ae6-104">구조체</span><span class="sxs-lookup"><span data-stu-id="84ae6-104">Structs</span></span>](struct.md)

- [<span data-ttu-id="84ae6-105">열거형</span><span class="sxs-lookup"><span data-stu-id="84ae6-105">Enumerations</span></span>](../builtin-types/enum.md)

## <a name="main-features-of-value-types"></a><span data-ttu-id="84ae6-106">값 형식의 주요 기능</span><span class="sxs-lookup"><span data-stu-id="84ae6-106">Main features of value types</span></span>

<span data-ttu-id="84ae6-107">값 형식의 변수에는 형식의 값이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-107">A variable of a value type contains a value of the type.</span></span> <span data-ttu-id="84ae6-108">예를 들어 `int` 형식의 변수에는 `42` 값이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-108">For example, a variable of the `int` type might contain the value `42`.</span></span> <span data-ttu-id="84ae6-109">이는 개체라고도 하는 형식 인스턴스에 대한 참조를 포함하는 참조 형식의 변수와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-109">This differs from a variable of a reference type, which contains a reference to an instance of the type, also known as an object.</span></span> <span data-ttu-id="84ae6-110">값 형식의 변수에 새 값을 할당하면 해당 값이 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-110">When you assign a new value to a variable of a value type, that value is copied.</span></span> <span data-ttu-id="84ae6-111">참조 형식의 변수에 새 값을 할당하면 개체 자체가 아니라 참조가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-111">When you assign a new value to a variable of a reference type, the reference is copied, not the object itself.</span></span>

<span data-ttu-id="84ae6-112">모든 값 형식은 <xref:System.ValueType?displayProperty=nameWithType>에서 암시적으로 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-112">All value types are derived implicitly from the <xref:System.ValueType?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="84ae6-113">참조 형식과 달리 값 형식에서는 새 형식을 파생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-113">Unlike with reference types, you cannot derive a new type from a value type.</span></span> <span data-ttu-id="84ae6-114">그러나 참조 형식과 마찬가지로 구조체가 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-114">However, like reference types, structs can implement interfaces.</span></span>

<span data-ttu-id="84ae6-115">값 형식 변수는 기본적으로 `null`일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-115">Value type variables cannot be `null` by default.</span></span> <span data-ttu-id="84ae6-116">그러나 해당 [nullable 값 형식](../builtin-types/nullable-value-types.md)의 변수는 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-116">However, variables of the corresponding [nullable value types](../builtin-types/nullable-value-types.md) can be `null`.</span></span>

<span data-ttu-id="84ae6-117">각 값 형식에는 해당 형식의 기본값을 초기화하는 암시적 매개 변수 없는 생성자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-117">Each value type has an implicit parameterless constructor that initializes the default value of that type.</span></span> <span data-ttu-id="84ae6-118">값 형식의 기본값에 대한 자세한 내용은 [기본값 표](default-values-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae6-118">For information about default values of value types, see [Default values table](default-values-table.md).</span></span>

## <a name="simple-types"></a><span data-ttu-id="84ae6-119">단순 형식</span><span class="sxs-lookup"><span data-stu-id="84ae6-119">Simple types</span></span>

<span data-ttu-id="84ae6-120">*단순 형식*은 C#에서 제공하는 미리 정의된 구조체 형식 세트이며, 다음과 같은 형식으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-120">The *simple types* are a set of predefined struct types provided by C# and comprise the following types:</span></span>

- <span data-ttu-id="84ae6-121">[정수 형식](../builtin-types/integral-numeric-types.md): 정수 숫자 형식 및 [char](../builtin-types/char.md) 형식</span><span class="sxs-lookup"><span data-stu-id="84ae6-121">[Integral types](../builtin-types/integral-numeric-types.md): integer numeric types and the [char](../builtin-types/char.md) type</span></span>
- [<span data-ttu-id="84ae6-122">부동 소수점 형식</span><span class="sxs-lookup"><span data-stu-id="84ae6-122">Floating-point types</span></span>](../builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="84ae6-123">bool</span><span class="sxs-lookup"><span data-stu-id="84ae6-123">bool</span></span>](../builtin-types/bool.md)

<span data-ttu-id="84ae6-124">단순 형식은 키워드를 통해 식별되지만, 이러한 키워드는 단순히 <xref:System> 네임스페이스에 미리 정의된 구조체 형식의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-124">The simple types are identified through keywords, but these keywords are simply aliases for predefined struct types in the <xref:System> namespace.</span></span> <span data-ttu-id="84ae6-125">예를 들어 [int](../builtin-types/integral-numeric-types.md)는 <xref:System.Int32?displayProperty=nameWithType>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-125">For example, [int](../builtin-types/integral-numeric-types.md) is an alias of <xref:System.Int32?displayProperty=nameWithType>.</span></span> <span data-ttu-id="84ae6-126">별칭의 전체 목록은 [기본 제공 형식 표](built-in-types-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae6-126">For a complete list of aliases, see [Built-in types table](built-in-types-table.md).</span></span>

<span data-ttu-id="84ae6-127">단순 형식은 특정 추가 작업을 허용한다는 점에서 다른 구조체 형식과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-127">The simple types differ from other struct types in that they permit certain additional operations:</span></span>

- <span data-ttu-id="84ae6-128">리터럴을 사용하여 단순 형식을 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-128">Simple types can be initialized by using literals.</span></span> <span data-ttu-id="84ae6-129">예를 들어 `'A'`는 `char` 형식의 리터럴이고, `2001`은 `int` 형식의 리터럴입니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-129">For example, `'A'` is a literal of the type `char` and `2001` is a literal of the type `int`.</span></span>

- <span data-ttu-id="84ae6-130">[const](const.md) 키워드를 사용하여 단순 형식의 상수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-130">You can declare constants of the simple types with the [const](const.md) keyword.</span></span> <span data-ttu-id="84ae6-131">다른 구조체 형식의 상수는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-131">It's not possible to have constants of other struct types.</span></span>

- <span data-ttu-id="84ae6-132">해당 피연산자가 모두 단순 형식 상수인 상수 식은 컴파일 시간에 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-132">Constant expressions, whose operands are all simple type constants, are evaluated at compile time.</span></span>

<span data-ttu-id="84ae6-133">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [단순 형식](~/_csharplang/spec/types.md#simple-types) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae6-133">For more information, see the [Simple types](~/_csharplang/spec/types.md#simple-types) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="initializing-value-types"></a><span data-ttu-id="84ae6-134">값 형식 초기화</span><span class="sxs-lookup"><span data-stu-id="84ae6-134">Initializing value types</span></span>

<span data-ttu-id="84ae6-135">C#의 지역 변수는 사용하기 전에 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-135">Local variables in C# must be initialized before they are used.</span></span> <span data-ttu-id="84ae6-136">예를 들어 다음 예제와 같이 초기화하지 않고 지역 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-136">For example, you might declare a local variable without initialization as in the following example:</span></span>

```csharp
int myInt;
```

<span data-ttu-id="84ae6-137">초기화하기 전에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-137">You cannot use it before you initialize it.</span></span> <span data-ttu-id="84ae6-138">다음 문을 사용하여 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-138">You can initialize it using the following statement:</span></span>

```csharp
myInt = new int();  // Invoke parameterless constructor for int type.
```

<span data-ttu-id="84ae6-139">이 문은 다음 문과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-139">This statement is equivalent to the following statement:</span></span>

```csharp
myInt = 0;         // Assign an initial value, 0 in this example.
```

<span data-ttu-id="84ae6-140">물론, 다음 예제와 같이 선언과 초기화를 동일한 문에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-140">You can, of course, have the declaration and the initialization in the same statement as in the following examples:</span></span>

```csharp
int myInt = new int();
```

<span data-ttu-id="84ae6-141">– 또는 –</span><span class="sxs-lookup"><span data-stu-id="84ae6-141">–or–</span></span>

```csharp
int myInt = 0;
```

<span data-ttu-id="84ae6-142">[new](../operators/new-operator.md) 연산자를 사용하면 특정 형식의 매개 변수 없는 생성자가 호출되고 변수에 기본값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-142">Using the [new](../operators/new-operator.md) operator calls the parameterless constructor of the specific type and assigns the default value to the variable.</span></span> <span data-ttu-id="84ae6-143">앞의 예제에서는 매개 변수 없는 생성자가 `0` 값을 `myInt`에 할당했습니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-143">In the preceding example, the parameterless constructor assigned the value `0` to `myInt`.</span></span> <span data-ttu-id="84ae6-144">매개 변수가 없는 생성자를 호출하여 할당된 값에 대한 자세한 내용은 [기본값 표](default-values-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae6-144">For more information about values assigned by calling parameterless constructors, see [Default values table](default-values-table.md).</span></span>

<span data-ttu-id="84ae6-145">사용자 정의 형식의 경우 [new](../operators/new-operator.md)를 사용하여 매개 변수 없는 생성자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-145">With user-defined types, use [new](../operators/new-operator.md) to invoke the parameterless constructor.</span></span> <span data-ttu-id="84ae6-146">예를 들어 다음 명령문은 `Point` 구조체의 매개 변수 없는 생성자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-146">For example, the following statement invokes the parameterless constructor of the `Point` struct:</span></span>

```csharp
var p = new Point(); // Invoke parameterless constructor for the struct.
```

<span data-ttu-id="84ae6-147">이 호출 후에는 구조체가 한정적으로 할당된 것으로 간주됩니다. 즉, 모든 멤버가 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="84ae6-147">After this call, the struct is considered to be definitely assigned; that is, all its members are initialized to their default values.</span></span>

<span data-ttu-id="84ae6-148">`new` 연산자에 대한 자세한 내용은 [new](../operators/new-operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae6-148">For more information about the `new` operator, see [new](../operators/new-operator.md).</span></span>

<span data-ttu-id="84ae6-149">숫자 형식의 출력에 서식을 지정하는 방법에 대한 자세한 내용은 [숫자 결과 형식 지정 표](formatting-numeric-results-table.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84ae6-149">For information about formatting the output of numeric types, see [Formatting numeric results table](formatting-numeric-results-table.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="84ae6-150">참조</span><span class="sxs-lookup"><span data-stu-id="84ae6-150">See also</span></span>

- [<span data-ttu-id="84ae6-151">C# 참조</span><span class="sxs-lookup"><span data-stu-id="84ae6-151">C# reference</span></span>](../index.md)
- [<span data-ttu-id="84ae6-152">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="84ae6-152">C# keywords</span></span>](index.md)
- [<span data-ttu-id="84ae6-153">참조 형식</span><span class="sxs-lookup"><span data-stu-id="84ae6-153">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="84ae6-154">Nullable 값 형식</span><span class="sxs-lookup"><span data-stu-id="84ae6-154">Nullable value types</span></span>](../builtin-types/nullable-value-types.md)
