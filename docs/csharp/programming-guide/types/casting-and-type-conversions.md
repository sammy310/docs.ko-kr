---
title: 캐스팅 및 형식 변환 - C# 프로그래밍 가이드
description: 암시적, 명시적(캐스트) 및 사용자 정의 변환과 같은 캐스팅 및 형식 변환에 대해 알아봅니다.
ms.date: 07/06/2020
helpviewer_keywords:
- type conversion [C#]
- data type conversion [C#]
- numeric conversions [C#]
- conversions [C#], type
- casting [C#]
- converting types [C#]
ms.assetid: 568df58a-d292-4b55-93ba-601578722878
ms.openlocfilehash: cfe5376675808559f4bf9c9cd8b21180dcd0cc49
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555330"
---
# <a name="casting-and-type-conversions-c-programming-guide"></a><span data-ttu-id="97aaa-103">캐스팅 및 형식 변환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="97aaa-103">Casting and type conversions (C# Programming Guide)</span></span>

<span data-ttu-id="97aaa-104">C#은 컴파일 시간에 정적으로 형식화되므로 변수가 선언된 후에는 다시 선언되거나 다른 형식의 값이 할당될 수 없습니다. 단, 형식이 변수의 형식으로 암시적으로 변환될 수 있는 경우는 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-104">Because C# is statically-typed at compile time, after a variable is declared, it cannot be declared again or assigned a value of another type unless that type is implicitly convertible to the variable's type.</span></span> <span data-ttu-id="97aaa-105">예를 들어 `string`은 `int`로 암시적으로 변환될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-105">For example, the `string` cannot be implicitly converted to `int`.</span></span> <span data-ttu-id="97aaa-106">따라서 `i`를 `int`로 선언한 후에는 다음 코드와 같이 문자열 "Hello"를 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-106">Therefore, after you declare `i` as an `int`, you cannot assign the string "Hello" to it, as the following code shows:</span></span>

```csharp
int i;

// error CS0029: Cannot implicitly convert type 'string' to 'int'
i = "Hello";
```

<span data-ttu-id="97aaa-107">그러나 다른 형식의 변수 또는 메서드 매개 변수에 값을 복사해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-107">However, you might sometimes need to copy a value into a variable or method parameter of another type.</span></span> <span data-ttu-id="97aaa-108">예를 들어 매개 변수가 `double`로 형식화된 메서드에 전달해야 하는 정수 변수가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-108">For example, you might have an integer variable that you need to pass to a method whose parameter is typed as `double`.</span></span> <span data-ttu-id="97aaa-109">또는 인터페이스 형식의 변수에 클래스 변수를 할당해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-109">Or you might need to assign a class variable to a variable of an interface type.</span></span> <span data-ttu-id="97aaa-110">이러한 작업을 *형식 변환*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-110">These kinds of operations are called *type conversions*.</span></span> <span data-ttu-id="97aaa-111">C#에서는 다음과 같은 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-111">In C#, you can perform the following kinds of conversions:</span></span>

- <span data-ttu-id="97aaa-112">**암시적 변환**: 변환은 항상 성공하고 데이터가 손실되지 않으므로 특수 구문이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-112">**Implicit conversions**: No special syntax is required because the conversion always succeeds and no data will be lost.</span></span> <span data-ttu-id="97aaa-113">예제에는 작은 정수 형식에서 큰 정수 형식으로의 변환 및 파생 클래스에서 기본 클래스로의 변환이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-113">Examples include conversions from smaller to larger integral types, and conversions from derived classes to base classes.</span></span>

- <span data-ttu-id="97aaa-114">**명시적 변환(캐스트)** : 명시적 변환에는 [캐스트 식](../../language-reference/operators/type-testing-and-cast.md#cast-expression)이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-114">**Explicit conversions (casts)**: Explicit conversions require a [cast expression](../../language-reference/operators/type-testing-and-cast.md#cast-expression).</span></span> <span data-ttu-id="97aaa-115">변환 시 정보가 손실되거나 다른 이유로 변환에 실패할 경우 캐스팅이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-115">Casting is required when information might be lost in the conversion, or when the conversion might not succeed for other reasons.</span></span> <span data-ttu-id="97aaa-116">일반적인 예제에는 숫자를 정밀도가 낮거나 범위가 더 작은 형식으로 변환하는 작업과 기본 클래스 인스턴스를 파생 클래스로 변환하는 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-116">Typical examples include numeric conversion to a type that has less precision or a smaller range, and conversion of a base-class instance to a derived class.</span></span>

- <span data-ttu-id="97aaa-117">**사용자 정의 변환**: 사용자 정의 변환은 기본 클래스-파생 클래스 관계가 없는 사용자 지정 형식 간의 명시적 및 암시적 변환을 사용하도록 정의할 수 있는 특수 메서드를 통해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-117">**User-defined conversions**: User-defined conversions are performed by special methods that you can define to enable explicit and implicit conversions between custom types that do not have a base class–derived class relationship.</span></span> <span data-ttu-id="97aaa-118">자세한 내용은 [사용자 정의 변환 연산자](../../language-reference/operators/user-defined-conversion-operators.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97aaa-118">For more information, see [User-defined conversion operators](../../language-reference/operators/user-defined-conversion-operators.md).</span></span>

- <span data-ttu-id="97aaa-119">**도우미 클래스를 사용한 변환**: 정수와 <xref:System.DateTime?displayProperty=nameWithType> 개체, 16진수 문자열과 바이트 배열 등 호환되지 않는 형식 간에 변환하려면 <xref:System.BitConverter?displayProperty=nameWithType> 클래스, <xref:System.Convert?displayProperty=nameWithType> 클래스 및 기본 제공 숫자 형식(예: <xref:System.Int32.Parse%2A?displayProperty=nameWithType>)의 `Parse` 메서드를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-119">**Conversions with helper classes**: To convert between non-compatible types, such as integers and <xref:System.DateTime?displayProperty=nameWithType> objects, or hexadecimal strings and byte arrays, you can use the <xref:System.BitConverter?displayProperty=nameWithType> class, the <xref:System.Convert?displayProperty=nameWithType> class, and the `Parse` methods of the built-in numeric types, such as <xref:System.Int32.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="97aaa-120">자세한 내용은 [바이트 배열을 int로 변환하는 방법](./how-to-convert-a-byte-array-to-an-int.md), [문자열을 숫자로 변환하는 방법](./how-to-convert-a-string-to-a-number.md) 및 [16진수 문자열과 숫자 형식 간에 변환하는 방법](./how-to-convert-between-hexadecimal-strings-and-numeric-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97aaa-120">For more information, see [How to convert a byte array to an int](./how-to-convert-a-byte-array-to-an-int.md), [How to convert a string to a number](./how-to-convert-a-string-to-a-number.md), and [How to convert between hexadecimal strings and numeric types](./how-to-convert-between-hexadecimal-strings-and-numeric-types.md).</span></span>

## <a name="implicit-conversions"></a><span data-ttu-id="97aaa-121">암시적 변환</span><span class="sxs-lookup"><span data-stu-id="97aaa-121">Implicit conversions</span></span>

<span data-ttu-id="97aaa-122">기본 제공 숫자 형식의 경우 저장되는 값이 잘리거나 반올림되지 않고 변수에 맞출 수 있을 때 암시적 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-122">For built-in numeric types, an implicit conversion can be made when the value to be stored can fit into the variable without being truncated or rounded off.</span></span> <span data-ttu-id="97aaa-123">이것은 정수 형식의 경우 소스 형식의 범위가 대상 유형에 대한 범위의 적절한 하위 집합임을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-123">For integral types, this means the range of the source type is a proper subset of the range for the target type.</span></span> <span data-ttu-id="97aaa-124">예를 들어 [long](../../language-reference/builtin-types/integral-numeric-types.md) 형식의 변수(64비트 정수)는 [int](../../language-reference/builtin-types/integral-numeric-types.md)(32비트 정수)가 저장할 수 있는 모든 값을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-124">For example, a variable of type [long](../../language-reference/builtin-types/integral-numeric-types.md) (64-bit integer) can store any value that an [int](../../language-reference/builtin-types/integral-numeric-types.md) (32-bit integer) can store.</span></span> <span data-ttu-id="97aaa-125">다음 예제에서 컴파일러는 오른쪽의 `num` 값을 `long` 형식으로 암시적으로 변환한 후 `bigNum`에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-125">In the following example, the compiler implicitly converts the value of `num` on the right to a type `long` before assigning it to `bigNum`.</span></span>

[!code-csharp[csProgGuideTypes#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#34)]

<span data-ttu-id="97aaa-126">모든 암시적 숫자 변환의 전체 목록은 [기본 제공 숫자 변환](../../language-reference/builtin-types/numeric-conversions.md) 문서의 [암시적 숫자 변환](../../language-reference/builtin-types/numeric-conversions.md#implicit-numeric-conversions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97aaa-126">For a complete list of all implicit numeric conversions, see the [Implicit numeric conversions](../../language-reference/builtin-types/numeric-conversions.md#implicit-numeric-conversions) section of the [Built-in numeric conversions](../../language-reference/builtin-types/numeric-conversions.md) article.</span></span>

<span data-ttu-id="97aaa-127">참조 형식의 경우 클래스에서 직접 또는 간접 기본 클래스나 인터페이스로의 암시적 변환이 항상 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-127">For reference types, an implicit conversion always exists from a class to any one of its direct or indirect base classes or interfaces.</span></span> <span data-ttu-id="97aaa-128">파생 클래스에 항상 기본 클래스의 모든 멤버가 포함되므로 특수 구문이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-128">No special syntax is necessary because a derived class always contains all the members of a base class.</span></span>

```csharp
Derived d = new Derived();

// Always OK.
Base b = d;
```

## <a name="explicit-conversions"></a><span data-ttu-id="97aaa-129">명시적 변환</span><span class="sxs-lookup"><span data-stu-id="97aaa-129">Explicit conversions</span></span>

<span data-ttu-id="97aaa-130">그러나 변환을 수행할 때 정보 손실의 위험이 있는 경우에는 컴파일러에서 *캐스트*라는 명시적 변환을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-130">However, if a conversion cannot be made without a risk of losing information, the compiler requires that you perform an explicit conversion, which is called a *cast*.</span></span> <span data-ttu-id="97aaa-131">캐스트는 변환을 수행하고자 하고 데이터 손실이 발생하거나 런타임에 캐스트가 실패할 가능성을 알고 있음을 컴파일러에 명시적으로 알리는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-131">A cast is a way of explicitly informing the compiler that you intend to make the conversion and that you are aware that data loss might occur, or the cast may fail at runtime.</span></span> <span data-ttu-id="97aaa-132">캐스트를 수행하려면 변환할 값 또는 변수 앞에 캐스트할 형식을 괄호 안에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-132">To perform a cast, specify the type that you are casting to in parentheses in front of the value or variable to be converted.</span></span> <span data-ttu-id="97aaa-133">다음 프로그램은 [double](../../language-reference/builtin-types/floating-point-numeric-types.md)을 [int](../../language-reference/builtin-types/integral-numeric-types.md)로 캐스트합니다. 캐스트가 없으면 프로그램이 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-133">The following program casts a [double](../../language-reference/builtin-types/floating-point-numeric-types.md) to an [int](../../language-reference/builtin-types/integral-numeric-types.md). The program will not compile without the cast.</span></span>

[!code-csharp[csProgGuideTypes#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#2)]

<span data-ttu-id="97aaa-134">지원되는 명시적 숫자 변환의 전체 목록은 [기본 제공 숫자 변환](../../language-reference/builtin-types/numeric-conversions.md) 문서의 [명시적 숫자 변환](../../language-reference/builtin-types/numeric-conversions.md#explicit-numeric-conversions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97aaa-134">For a complete list of supported explicit numeric conversions, see the [Explicit numeric conversions](../../language-reference/builtin-types/numeric-conversions.md#explicit-numeric-conversions) section of the [Built-in numeric conversions](../../language-reference/builtin-types/numeric-conversions.md) article.</span></span>

<span data-ttu-id="97aaa-135">참조 형식의 경우 기본 형식에서 파생 형식으로 변환해야 할 경우에는 명시적 캐스트가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-135">For reference types, an explicit cast is required if you need to convert from a base type to a derived type:</span></span>

```csharp
// Create a new derived type.
Giraffe g = new Giraffe();

// Implicit conversion to base type is safe.
Animal a = g;

// Explicit conversion is required to cast back
// to derived type. Note: This will compile but will
// throw an exception at run time if the right-side
// object is not in fact a Giraffe.
Giraffe g2 = (Giraffe)a;
```

<span data-ttu-id="97aaa-136">참조 형식 간 캐스트 작업은 기본 개체의 런타임 형식을 변경하지 않습니다. 참조로 사용되는 값의 형식을 해당 개체로만 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-136">A cast operation between reference types does not change the run-time type of the underlying object; it only changes the type of the value that is being used as a reference to that object.</span></span> <span data-ttu-id="97aaa-137">자세한 내용은 [다형성](../classes-and-structs/polymorphism.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97aaa-137">For more information, see [Polymorphism](../classes-and-structs/polymorphism.md).</span></span>

## <a name="type-conversion-exceptions-at-run-time"></a><span data-ttu-id="97aaa-138">런타임의 형식 변환 예외</span><span class="sxs-lookup"><span data-stu-id="97aaa-138">Type conversion exceptions at run time</span></span>

<span data-ttu-id="97aaa-139">일부 참조 형식 변환 시에는 컴파일러에서 캐스트가 유효한지 여부를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-139">In some reference type conversions, the compiler cannot determine whether a cast will be valid.</span></span> <span data-ttu-id="97aaa-140">제대로 컴파일되는 캐스트 작업이 런타임에 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-140">It is possible for a cast operation that compiles correctly to fail at run time.</span></span> <span data-ttu-id="97aaa-141">다음 예제와 같이 런타임에 형식 캐스트가 실패하면 <xref:System.InvalidCastException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-141">As shown in the following example, a type cast that fails at run time will cause an <xref:System.InvalidCastException> to be thrown.</span></span>

[!code-csharp[csProgGuideTypes#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsProgGuideTypes/CS/Class1.cs#41)]

<span data-ttu-id="97aaa-142">`Test` 메서드에 `Animal` 매개 변수가 있으므로 인수 `a`를 `Reptile`로 명시적으로 캐스팅하면 위험한 가정이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-142">The `Test` method has an `Animal` parameter, thus explicitly casting the argument `a` to a `Reptile` makes a dangerous assumption.</span></span> <span data-ttu-id="97aaa-143">가정을 생성하지 않고 형식을 확인하는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-143">It is safer to not make assumptions, but rather check the type.</span></span> <span data-ttu-id="97aaa-144">C#에서는 실제로 캐스트를 수행하기 전에 호환성을 테스트할 수 있도록 [is](../../language-reference/operators/type-testing-and-cast.md#is-operator) 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97aaa-144">C# provides the [is](../../language-reference/operators/type-testing-and-cast.md#is-operator) operator to enable you to test for compatibility before actually performing a cast.</span></span> <span data-ttu-id="97aaa-145">자세한 내용은 [패턴 일치, as 및 is 연산자를 사용하여 안전하게 캐스트하는 방법](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97aaa-145">For more information, see [How to safely cast using pattern matching and the as and is operators](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="97aaa-146">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="97aaa-146">C# language specification</span></span>

<span data-ttu-id="97aaa-147">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [전환](~/_csharplang/spec/conversions.md) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97aaa-147">For more information, see the [Conversions](~/_csharplang/spec/conversions.md) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="97aaa-148">참조</span><span class="sxs-lookup"><span data-stu-id="97aaa-148">See also</span></span>

- [<span data-ttu-id="97aaa-149">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="97aaa-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="97aaa-150">유형</span><span class="sxs-lookup"><span data-stu-id="97aaa-150">Types</span></span>](./index.md)
- [<span data-ttu-id="97aaa-151">캐스트 식</span><span class="sxs-lookup"><span data-stu-id="97aaa-151">Cast expression</span></span>](../../language-reference/operators/type-testing-and-cast.md#cast-expression)
- [<span data-ttu-id="97aaa-152">사용자 정의 전환 연산자</span><span class="sxs-lookup"><span data-stu-id="97aaa-152">User-defined conversion operators</span></span>](../../language-reference/operators/user-defined-conversion-operators.md)
- <span data-ttu-id="97aaa-153">[일반화된 형식 변환](/previous-versions/visualstudio/visual-studio-2013/yy580hbd(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="97aaa-153">[Generalized Type Conversion](/previous-versions/visualstudio/visual-studio-2013/yy580hbd(v=vs.120))</span></span>
- [<span data-ttu-id="97aaa-154">문자열을 숫자로 변환하는 방법</span><span class="sxs-lookup"><span data-stu-id="97aaa-154">How to convert a string to a number</span></span>](./how-to-convert-a-string-to-a-number.md)
