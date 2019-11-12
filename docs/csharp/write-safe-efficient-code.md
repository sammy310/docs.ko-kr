---
title: 안전하고 효율적인 C# 코드 작성
description: 최근 C# 언어의 향상된 기능을 통해 성능이 이전에는 안전하지 않은 코드와 연결되어 있는 안정형 안전 코드를 작성할 수 있습니다.
ms.date: 10/23/2018
ms.technology: csharp-advanced-concepts
ms.custom: mvc
ms.openlocfilehash: 3dc3213cf24f4cdd8f0f1b7752263b4a609b2fa2
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039636"
---
# <a name="write-safe-and-efficient-c-code"></a><span data-ttu-id="895c0-103">안전하고 효율적인 C# 코드 작성</span><span class="sxs-lookup"><span data-stu-id="895c0-103">Write safe and efficient C# code</span></span>

<span data-ttu-id="895c0-104">C#의 새 기능을 사용하면 향상된 성능으로 안정형의 안전 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-104">New features in C# enable you to write verifiable safe code with better performance.</span></span> <span data-ttu-id="895c0-105">이러한 기술을 신중하게 적용한다면 안전하지 않은 코드가 필요한 시나리오는 더 적어집니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-105">If you carefully apply these techniques, fewer scenarios require unsafe code.</span></span> <span data-ttu-id="895c0-106">이러한 기능을 통해 값 형식에 대한 참조를 메서드 인수 및 메서드 반환 값으로 사용하기가 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-106">These features make it easier to use references to value types as method arguments and method returns.</span></span> <span data-ttu-id="895c0-107">안전하게 수행하면 이러한 기술로 값 형식 복사가 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-107">When done safely, these techniques minimize copying value types.</span></span> <span data-ttu-id="895c0-108">값 형식을 사용하면 할당 수 및 가비지 수집 단계를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-108">By using value types, you can minimize the number of allocations and garbage collection passes.</span></span>

<span data-ttu-id="895c0-109">이 문서의 샘플 코드 상당수는 C# 7.2에 추가된 기능을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-109">Much of the sample code in this article uses features added in C# 7.2.</span></span> <span data-ttu-id="895c0-110">이러한 기능을 사용하려면 C# 7.2 이상을 사용하도록 프로젝트를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-110">To use those features, you must configure your project to use C# 7.2 or later.</span></span> <span data-ttu-id="895c0-111">언어 버전 설정에 대한 자세한 내용은 [언어 버전 구성](language-reference/configure-language-version.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="895c0-111">For more information on setting the language version, see [configure the language version](language-reference/configure-language-version.md).</span></span>

<span data-ttu-id="895c0-112">이 문서에서는 효율적인 리소스 관리를 위한 기술에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-112">This article focuses on techniques for efficient resource management.</span></span> <span data-ttu-id="895c0-113">값 형식을 사용할 경우 한 가지 장점은 대개 힙 할당을 할 필요가 없다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-113">One advantage to using value types is that they often avoid heap allocations.</span></span> <span data-ttu-id="895c0-114">단점은 값으로 복사된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-114">The disadvantage is that they're copied by value.</span></span> <span data-ttu-id="895c0-115">이러한 장단점 간에 균형을 잡으려고 하니 많은 양의 데이터에서 작동하는 알고리즘을 최적화하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-115">This tradeoff makes it harder to optimize algorithms that operate on large amounts of data.</span></span> <span data-ttu-id="895c0-116">C# 7.2의 새로운 언어 기능은 값 형식에 대한 참조를 사용하여 안전하고 효율적인 코드를 가능하게 하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-116">New language features in C# 7.2 provide mechanisms that enable safe efficient code using references to value types.</span></span> <span data-ttu-id="895c0-117">이러한 기능을 현명하게 사용하여 할당 및 복사 작업을 최소화하세요.</span><span class="sxs-lookup"><span data-stu-id="895c0-117">Use these features wisely to minimize both allocations and copy operations.</span></span> <span data-ttu-id="895c0-118">이 문서에서는 이러한 새로운 기능을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-118">This article explores those new features.</span></span>

<span data-ttu-id="895c0-119">이 문서에서는 다음과 같은 리소스 관리 기술에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-119">This article focuses on the following resource management techniques:</span></span>

- <span data-ttu-id="895c0-120">형식이 **변경할 수 없음** 상태이며 [`in`](language-reference/keywords/in-parameter-modifier.md) 매개 변수를 사용하는 경우 컴파일러가 복사본을 저장할 수 있음을 나타내도록 [`readonly struct`](language-reference/keywords/readonly.md#readonly-struct-example)를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-120">Declare a [`readonly struct`](language-reference/keywords/readonly.md#readonly-struct-example) to express that a type is **immutable** and enables the compiler to save copies when using [`in`](language-reference/keywords/in-parameter-modifier.md) parameters.</span></span>
- <span data-ttu-id="895c0-121">형식을 변경할 수 없는 경우, `struct` 멤버를 `readonly`로 선언하여 멤버가 상태를 수정하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-121">If a type can't be immutable, declare `struct` members `readonly` to indicate that the member doesn't modify state.</span></span>
- <span data-ttu-id="895c0-122">반환 값이 <xref:System.IntPtr.Size?displayProperty=nameWithType>보다 큰 `struct`이고 스토리지 수명이 값을 반환하는 메서드보다 클 경우 [`ref readonly`](language-reference/keywords/ref.md#reference-return-values) 반환을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-122">Use a [`ref readonly`](language-reference/keywords/ref.md#reference-return-values) return when the return value is a `struct` larger than <xref:System.IntPtr.Size?displayProperty=nameWithType> and the storage lifetime is greater than the method returning the value.</span></span>
- <span data-ttu-id="895c0-123">성능 상의 이유로 `readonly struct`의 크기가 <xref:System.IntPtr.Size?displayProperty=nameWithType>보다 큰 경우 `in` 매개 변수로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-123">When the size of a `readonly struct` is bigger than <xref:System.IntPtr.Size?displayProperty=nameWithType>, you should pass it as an `in` parameter for performance reasons.</span></span>
- <span data-ttu-id="895c0-124">`readonly` 한정자로 선언되었거나 메서드가 구조체의 `readonly` 멤버만 호출하는 경우를 제외하고 `struct`를 `in` 매개 변수로 전달하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-124">Never pass a `struct` as an `in` parameter unless it's declared with the `readonly` modifier or the method calls only `readonly` members of the struct.</span></span> <span data-ttu-id="895c0-125">이 지침을 위반하면 성능이 저하되고 모호한 동작이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-125">Violating this guidance may negatively affect performance and could lead to an obscure behavior.</span></span>
- <span data-ttu-id="895c0-126">메모리를 바이트의 시퀀스로 사용하도록[`ref struct`](language-reference/keywords/ref.md#ref-struct-types) 또는 `readonly ref struct`(예: <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601>)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-126">Use a [`ref struct`](language-reference/keywords/ref.md#ref-struct-types), or a `readonly ref struct` such as <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> to work with memory as a sequence of bytes.</span></span>

<span data-ttu-id="895c0-127">이러한 기술을 통해 **참조** 및 **값**에 관한 상충적인 두 가지 목표 간에 균형을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-127">These techniques force you to balance two competing goals with regard to **references** and **values**.</span></span> <span data-ttu-id="895c0-128">[참조 형식](programming-guide/types/index.md#reference-types)인 변수는 메모리의 위치에 대한 참조를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-128">Variables that are [reference types](programming-guide/types/index.md#reference-types) hold a reference to the location in memory.</span></span> <span data-ttu-id="895c0-129">[값 형식](programming-guide/types/index.md#value-types)인 변수는 직접 해당 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-129">Variables that are [value types](programming-guide/types/index.md#value-types) directly contain their value.</span></span> <span data-ttu-id="895c0-130">이러한 차이는 메모리 리소스를 관리하는 데 중요한 차이점을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-130">These differences highlight the key differences that are important for managing memory resources.</span></span> <span data-ttu-id="895c0-131">**값 형식**은 일반적으로 메서드에 전달되거나 메서드에서 반환된 경우 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-131">**Value types** are typically copied when passed to a method or returned from a method.</span></span> <span data-ttu-id="895c0-132">이 동작에는 값 형식의 멤버를 호출하는 경우 `this`의 값을 복사하는 동작이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-132">This behavior includes copying the value of `this` when calling members of a value type.</span></span> <span data-ttu-id="895c0-133">복사의 비용은 형식의 크기와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-133">The cost of the copy is related to the size of the type.</span></span> <span data-ttu-id="895c0-134">**참조 형식**은 관리형 힙에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-134">**Reference types** are allocated on the managed heap.</span></span> <span data-ttu-id="895c0-135">각 새 개체는 새로 할당해야 하고 이후에 회수되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-135">Each new object requires a new allocation, and subsequently must be reclaimed.</span></span> <span data-ttu-id="895c0-136">이러한 두 작업은 모두 시간이 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-136">Both these operations take time.</span></span> <span data-ttu-id="895c0-137">참조 형식이 메서드에 인수로 전달되거나 메서드에서 반환되면 참조가 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-137">The reference is copied when a reference type is passed as an argument to a method or returned from a method.</span></span>

<span data-ttu-id="895c0-138">이 문서에서는 이러한 권장 사항을 설명하기 위해 3D 요소 구조체의 다음 예제 개념을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-138">This article uses the following example concept of the 3D-point structure to explain these recommendations:</span></span>

```csharp
public struct Point3D
{
    public double X;
    public double Y;
    public double Z;
}
```

<span data-ttu-id="895c0-139">다른 예제에서는 이 개념의 다른 구현을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-139">Different examples use different implementations of this concept.</span></span>

## <a name="declare-readonly-structs-for-immutable-value-types"></a><span data-ttu-id="895c0-140">변경할 수 없는 값 형식에 대해 읽기 전용 구조체 선언</span><span class="sxs-lookup"><span data-stu-id="895c0-140">Declare readonly structs for immutable value types</span></span>

<span data-ttu-id="895c0-141">`readonly` 한정자를 사용하여 `struct`를 선언하면 변경할 수 없는 형식을 만들려는 의도를 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-141">Declaring a `struct` using the `readonly` modifier informs the compiler that your intent is to create an immutable type.</span></span> <span data-ttu-id="895c0-142">컴파일러는 다음 규칙을 사용하여 해당 디자인 결정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-142">The compiler enforces that design decision with the following rules:</span></span>

- <span data-ttu-id="895c0-143">모든 필드 멤버는 `readonly`여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-143">All field members must be `readonly`</span></span>
- <span data-ttu-id="895c0-144">모든 속성은 자동으로 구현된 속성을 포함하여 읽기 전용이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-144">All properties must be read-only, including auto-implemented properties.</span></span>

<span data-ttu-id="895c0-145">이러한 두 규칙으로 `readonly struct`의 멤버가 해당 구조체 상태를 수정하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-145">These two rules are sufficient to ensure that no member of a `readonly struct` modifies the state of that struct.</span></span> <span data-ttu-id="895c0-146">`struct`는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-146">The `struct` is immutable.</span></span> <span data-ttu-id="895c0-147">`Point3D` 구조체는 다음 예제에 나온 것처럼 변경할 수 없는 구조체로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-147">The `Point3D` structure could be defined as an immutable struct as shown in the following example:</span></span>

```csharp
readonly public struct ReadonlyPoint3D
{
    public ReadonlyPoint3D(double x, double y, double z)
    {
        this.X = x;
        this.Y = y;
        this.Z = z;
    }

    public double X { get; }
    public double Y { get; }
    public double Z { get; }
}
```

<span data-ttu-id="895c0-148">디자인 의도가 변경할 수 없는 값 형식을 만드는 것이라면 이 권장 사항을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-148">Follow this recommendation whenever your design intent is to create an immutable value type.</span></span> <span data-ttu-id="895c0-149">성능 개선 사항은 추가적인 혜택입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-149">Any performance improvements are an added benefit.</span></span> <span data-ttu-id="895c0-150">`readonly struct`는 디자인 의도를 명확하게 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-150">The `readonly struct` clearly expresses your design intent.</span></span>

## <a name="declare-readonly-members-when-a-struct-cant-be-immutable"></a><span data-ttu-id="895c0-151">구조체를 변경할 수 없는 경우 readonly 멤버 선언</span><span class="sxs-lookup"><span data-stu-id="895c0-151">Declare readonly members when a struct can't be immutable</span></span>

<span data-ttu-id="895c0-152">C# 8.0 이상에서는 구조체 형식이 변경 가능한 경우 `readonly`로 변경되지 않는 멤버를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-152">In C# 8.0 and later, when a struct type is mutable, you should declare members that don't cause mutation to be `readonly`.</span></span> <span data-ttu-id="895c0-153">예를 들어 다음은 3D 요소 구조의 변경 가능한 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-153">For example, the following is a mutable variation of the 3D point structure:</span></span>

```csharp
public struct Point3D
{
    public Point3D(double x, double y, double z)
    {
        this.X = x;
        this.Y = y;
        this.Z = z;
    }

    private double _x;
    public double X 
    { 
        readonly get { return _x;}; 
        set { _x = value; }
    }
    
    private double _y;
    public double Y 
    { 
        readonly get { return _y;}; 
        set { _y = value; }
    }

    private double _z;
    public double Z 
    { 
        readonly get { return _z;}; 
        set { _z = value; }
    }

    public readonly double Distance => Math.Sqrt(X * X + Y * Y + Z * Z);

    public readonly override string ToString() => $"{X, Y, Z }";
}
```

<span data-ttu-id="895c0-154">위의 샘플에서는 `readonly` 한정자를 적용할 수 있는 여러 위치(메서드, 속성, 속성 접근자)를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-154">The preceding sample shows many of the locations where you can apply the `readonly` modifier: methods, properties, and property accessors.</span></span> <span data-ttu-id="895c0-155">자동 구현 속성을 사용하는 경우, 컴파일러에서 읽기/쓰기 속성의 `get` 접근자에 `readonly` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-155">If you use auto-implemented properties, the compiler adds the `readonly` modifier to the `get` accessor for read-write properties.</span></span> <span data-ttu-id="895c0-156">컴파일러는 `get` 접근자만 있는 속성의 자동 구현 속성 선언에 `readonly` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-156">The compiler adds the `readonly` modifier to the auto-implemented property declarations for properties with only a `get` accessor.</span></span>

<span data-ttu-id="895c0-157">상태를 변경하지 않는 멤버에 `readonly` 한정자를 추가하면 두 가지 관련 혜택이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-157">Adding the `readonly` modifier to members that don't mutate state provides two related benefits.</span></span> <span data-ttu-id="895c0-158">첫째, 컴파일러에서 의도를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-158">First, the compiler enforces your intent.</span></span> <span data-ttu-id="895c0-159">해당 멤버는 구조체 상태를 변경할 수 없으며, `readonly`로 표시되지 않은 멤버에 액세스할 수도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-159">That member can't mutate the struct's state, nor can it access a member that isn't also marked `readonly`.</span></span> <span data-ttu-id="895c0-160">둘째, 컴파일러에서 `readonly` 멤버에 액세스할 때 `in` 매개 변수의 방어형 복사본을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-160">Second, the compiler won't create defensive copies of `in` parameters when accessing a `readonly` member.</span></span> <span data-ttu-id="895c0-161">컴파일러는 `readonly` 멤버가 `struct`를 수정하지 않도록 하여 이 최적화를 안전하게 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-161">The compiler can make this optimization safely because it guarantees that the `struct` is not modified by a `readonly` member.</span></span>

## <a name="use-ref-readonly-return-statements-for-large-structures-when-possible"></a><span data-ttu-id="895c0-162">가능하면 큰 구조체에 `ref readonly return` 문 사용</span><span class="sxs-lookup"><span data-stu-id="895c0-162">Use `ref readonly return` statements for large structures when possible</span></span>

<span data-ttu-id="895c0-163">반환되는 값이 반환 메서드에 로컬이 아닐 경우 참조로 값을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-163">You can return values by reference when the value being returned isn't local to the returning method.</span></span> <span data-ttu-id="895c0-164">참조로 반환하는 것은 구조체가 아니라 참조만 복사된다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-164">Returning by reference means that only the reference is copied, not the structure.</span></span> <span data-ttu-id="895c0-165">다음 예제에서는 반환되는 값이 로컬 변수이므로 `Origin` 속성은 `ref` 반환을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-165">In the following example, the `Origin` property can't use a `ref` return because the value being returned is a local variable:</span></span>

```csharp
public Point3D Origin => new Point3D(0,0,0);
```

<span data-ttu-id="895c0-166">단, 반환된 값이 정적 멤버이므로 다음 속성 정의를 참조로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-166">However, the following property definition can be returned by reference because the returned value is a static member:</span></span>

```csharp
public struct Point3D
{
    private static Point3D origin = new Point3D(0,0,0);

    // Dangerous! returning a mutable reference to internal storage
    public ref Point3D Origin => ref origin;

    // other members removed for space
}
```

<span data-ttu-id="895c0-167">호출자가 원점을 수정하지 않도록 하려면 `readonly ref`로 값을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-167">You don't want callers modifying the origin, so you should return the value by `readonly ref`:</span></span>

```csharp
public struct Point3D
{
    private static Point3D origin = new Point3D(0,0,0);

    public static ref readonly Point3D Origin => ref origin;

    // other members removed for space
}
```

<span data-ttu-id="895c0-168">`ref readonly`를 반환하면 더 큰 구조체 복사본을 저장하고 내부 데이터 멤버의 불변성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-168">Returning `ref readonly` enables you to save copying larger structures and preserve the immutability of your internal data members.</span></span>

<span data-ttu-id="895c0-169">호출 사이트에서 호출자가 `Origin` 속성을 `readonly ref` 또는 값으로 사용하도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-169">At the call site, callers make the choice to use the `Origin` property as a `readonly ref` or as a value:</span></span>

[!code-csharp[AssignRefReadonly](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

<span data-ttu-id="895c0-170">이전 코드의 첫 번째 할당에서는 `Origin` 상수의 복사본을 만들고 해당 복사본을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-170">The first assignment in the preceding code makes a copy of the `Origin` constant and assigns that copy.</span></span> <span data-ttu-id="895c0-171">두 번째 할당에서는 참조를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-171">The second assigns a reference.</span></span> <span data-ttu-id="895c0-172">`readonly` 한정자는 변수 선언의 일부여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-172">Notice that the `readonly` modifier must be part of the declaration of the variable.</span></span> <span data-ttu-id="895c0-173">참조하는 항목에 대한 참조는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-173">The reference to which it refers can't be modified.</span></span> <span data-ttu-id="895c0-174">이를 수행하려고 시도하면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-174">Attempts to do so result in a compile-time error.</span></span>

<span data-ttu-id="895c0-175">`readonly` 한정자는 `originReference` 선언에 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-175">The `readonly` modifier is required on the declaration of `originReference`.</span></span>

<span data-ttu-id="895c0-176">컴파일러는 호출자가 참조를 수정할 수 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-176">The compiler enforces that the caller can't modify the reference.</span></span> <span data-ttu-id="895c0-177">값을 직접 할당하려고 하면 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-177">Attempts to assign the value directly generate a compile-time error.</span></span> <span data-ttu-id="895c0-178">그러나 컴파일러는 멤버 메서드가 구조체의 상태를 수정하는지를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-178">However, the compiler can't know if any member method modifies the state of the struct.</span></span>
<span data-ttu-id="895c0-179">개체가 수정되지 않도록 하기 위해 컴파일러는 복사본을 만들고 해당 복사본을 사용하여 멤버 참조를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-179">To ensure that the object isn't modified, the compiler creates a copy and calls member references using that copy.</span></span> <span data-ttu-id="895c0-180">모든 수정은 해당 방어 복사본에 대한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-180">Any modifications are to that defensive copy.</span></span>

## <a name="apply-the-in-modifier-to-readonly-struct-parameters-larger-than-systemintptrsize"></a><span data-ttu-id="895c0-181">`in` 한정자를 `System.IntPtr.Size`보다 큰 `readonly struct` 매개 변수에 적용</span><span class="sxs-lookup"><span data-stu-id="895c0-181">Apply the `in` modifier to `readonly struct` parameters larger than `System.IntPtr.Size`</span></span>

<span data-ttu-id="895c0-182">`in` 키워드는 기존 `ref` 및 `out` 키워드를 보완하여 참조로 인수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-182">The `in` keyword complements the existing `ref` and `out` keywords to pass arguments by reference.</span></span> <span data-ttu-id="895c0-183">`in` 키워드는 인수를 참조로 전달하도록 지정하지만 호출된 메서드는 값을 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-183">The `in` keyword specifies passing the argument by reference, but the called method doesn't modify the value.</span></span>

<span data-ttu-id="895c0-184">이 추가는 설계 의도를 표현하기 위한 완벽한 어휘를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-184">This addition provides a full vocabulary to express your design intent.</span></span>
<span data-ttu-id="895c0-185">메서드 서명에 다음 한정자 중 어떤 것도 지정하지 않으면 호출된 메서드에 전달될 때 값 형식이 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-185">Value types are copied when passed to a called method when you don't specify any of the following modifiers in the method signature.</span></span> <span data-ttu-id="895c0-186">이러한 각 한정자는 변수가 참조로 전달되도록 지정하여 복사를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-186">Each of these modifiers specifies that a variable is passed by reference, avoiding the copy.</span></span> <span data-ttu-id="895c0-187">각 한정자는 각기 다른 의도를 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-187">Each modifier expresses a different intent:</span></span>

- <span data-ttu-id="895c0-188">`out`: 이 메서드는 이 매개 변수로 사용되는 인수의 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-188">`out`: This method sets the value of the argument used as this parameter.</span></span>
- <span data-ttu-id="895c0-189">`ref`: 이 메서드는 이 매개 변수로 사용되는 인수의 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-189">`ref`: This method may set the value of the argument used as this parameter.</span></span>
- <span data-ttu-id="895c0-190">`in`: 이 메서드는 이 매개 변수로 사용되는 인수의 값을 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-190">`in`: This method doesn't modify the value of the argument used as this parameter.</span></span>

<span data-ttu-id="895c0-191">참조로 인수를 전달하기 위해 `in` 한정자를 추가하고 불필요한 복사를 방지하기 위해 참조로 인수를 전달할 디자인 의도를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-191">Add the `in` modifier to pass an argument by reference and declare your design intent to pass arguments by reference to avoid unnecessary copying.</span></span> <span data-ttu-id="895c0-192">해당 인수로 사용되는 개체를 수정할 의도가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-192">You don't intend to modify the object used as that argument.</span></span>

<span data-ttu-id="895c0-193">이 방법은 종종 <xref:System.IntPtr.Size?displayProperty=nameWithType>보다 큰 읽기 전용 값 형식에 대한 성능을 향상시킵니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-193">This practice often improves performance for readonly value types that are larger than <xref:System.IntPtr.Size?displayProperty=nameWithType>.</span></span> <span data-ttu-id="895c0-194">단순 형식(`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal`, `bool` 및 `enum` 형식)의 경우 모든 잠재적 성능 향상이 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-194">For simple types (`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` and `bool`, and `enum` types), any potential performance gains are minimal.</span></span> <span data-ttu-id="895c0-195">사실 <xref:System.IntPtr.Size?displayProperty=nameWithType>보다 작은 형식에 참조로 전달을 사용하면 성능이 저하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-195">In fact, performance may degrade by using pass-by-reference for types smaller than <xref:System.IntPtr.Size?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="895c0-196">다음 코드는 3D 공간에서 두 점 사이의 거리를 계산하는 메서드의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-196">The following code shows an example of a method that calculates the distance between two points in 3D space.</span></span>

[!code-csharp[InArgument](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgument "Specifying an in argument")]

<span data-ttu-id="895c0-197">인수는 각각 세 개의 double을 포함하는 두 개의 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-197">The arguments are two structures that each contain three doubles.</span></span> <span data-ttu-id="895c0-198">double은 8바이트이므로 각 인수는 24바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-198">A double is 8 bytes, so each argument is 24 bytes.</span></span> <span data-ttu-id="895c0-199">`in` 한정자를 지정하여 머신 아키텍처에 따라 해당 인수에 4바이트 또는 8바이트 참조를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-199">By specifying the `in` modifier, you pass a 4 byte or 8-byte reference to those arguments, depending on the architecture of the machine.</span></span> <span data-ttu-id="895c0-200">크기의 차이는 작지만, 애플리케이션이 다양한 값을 사용하여 연속 루프에서 이 메서드를 호출하면 늘어납니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-200">The difference in size is small, but it adds up when your application calls this method in a tight loop using many different values.</span></span>

<span data-ttu-id="895c0-201">`in` 한정자는 `out` 및 `ref`를 다른 방식으로도 보완합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-201">The `in` modifier complements `out` and `ref` in other ways as well.</span></span> <span data-ttu-id="895c0-202">`in`, `out` 또는 `ref`가 있는 경우에만 다른 메서드의 오버로드는 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-202">You can't create overloads of a method that differ only in the presence of `in`, `out`, or `ref`.</span></span> <span data-ttu-id="895c0-203">이러한 새 규칙은 항상 `out` 및 `ref` 매개 변수에 대해 정의된 같은 동작을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-203">These new rules extend the same behavior that had always been defined for `out` and `ref` parameters.</span></span> <span data-ttu-id="895c0-204">`out` 및 `ref` 한정자와 마찬가지로 `in` 한정자가 적용되므로 값 형식이 boxing되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-204">Like the `out` and `ref` modifiers, value types aren't boxed because the `in` modifier is applied.</span></span>

<span data-ttu-id="895c0-205">`in` 한정자는 메서드, 대리자, 람다, 로컬 함수, 인덱서, 연산자 매개 변수를 사용하는 모든 멤버에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-205">The `in` modifier may be applied to any member that takes parameters: methods, delegates, lambdas, local functions, indexers, operators.</span></span>

<span data-ttu-id="895c0-206">`in` 매개 변수의 다른 기능은 `in` 매개 변수에 대한 인수에 리터럴 값 또는 상수를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-206">Another feature of `in` parameters is that you may use literal values or constants for the argument to an `in` parameter.</span></span> <span data-ttu-id="895c0-207">또한 `ref` 또는 `out` 매개 변수와 달리 호출 사이트에서 `in` 한정자를 적용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-207">Also, unlike a `ref` or `out` parameter, you don't need to apply the `in` modifier at the call site.</span></span> <span data-ttu-id="895c0-208">다음 코드는 `CalculateDistance` 메서드를 호출하는 두 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-208">The following code shows you two examples of calling the `CalculateDistance` method.</span></span> <span data-ttu-id="895c0-209">첫 번째 예에서는 참조로 전달된 두 개의 로컬 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-209">The first uses two local variables passed by reference.</span></span> <span data-ttu-id="895c0-210">두 번째 예는 메서드 호출의 일부로 만들어진 임시 변수를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-210">The second includes a temporary variable created as part of the method call.</span></span>

[!code-csharp[UseInArgument](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#UseInArgument "Specifying an In argument")]

<span data-ttu-id="895c0-211">컴파일러가 `in` 인수의 읽기 전용 특성을 강제 적용하는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-211">There are several ways in which the compiler enforces the read-only nature of an `in` argument.</span></span>  <span data-ttu-id="895c0-212">먼저, 호출된 메서드는 `in` 매개 변수에 직접 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-212">First of all, the called method can't directly assign to an `in` parameter.</span></span> <span data-ttu-id="895c0-213">값이 `struct` 형식일 때 `in` 매개 변수의 모든 필드에 직접 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-213">It can't directly assign to any field of an `in` parameter when that value is a `struct` type.</span></span> <span data-ttu-id="895c0-214">또한 `ref` 또는 `out` 한정자를 사용하여 모든 메서드에 `in` 매개 변수를 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-214">In addition, you can't pass an `in` parameter to any method using the `ref` or `out` modifier.</span></span>
<span data-ttu-id="895c0-215">이러한 규칙은 필드가 `struct` 형식이고 매개 변수 또한 `struct` 형식인 경우 `in` 매개 변수의 모든 필드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-215">These rules apply to any field of an `in` parameter, provided the field is a `struct` type and the parameter is also a `struct` type.</span></span> <span data-ttu-id="895c0-216">사실 이러한 규칙은 멤버 액세스의 모든 수준에서 형식이 `structs`인 경우 멤버 액세스의 여러 계층에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-216">In fact, these rules apply for multiple layers of member access provided the types at all levels of member access are `structs`.</span></span>
<span data-ttu-id="895c0-217">컴파일러는 `in` 인수로 전달된 `struct` 형식과 그 `struct` 멤버가 다른 메서드에 대한 인수로 사용될 경우 읽기 전용 변수가 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-217">The compiler enforces that `struct` types passed as  `in` arguments and their `struct` members are read-only variables when used as arguments to other methods.</span></span>

<span data-ttu-id="895c0-218">`in` 매개 변수를 사용하면 복사본 작성 시 발생할 수 있는 잠재적인 성능 비용을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-218">The use of `in` parameters can avoid the potential performance costs of making copies.</span></span> <span data-ttu-id="895c0-219">어떠한 메서드 호출의 의미 체계도 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-219">It doesn't change the semantics of any method call.</span></span> <span data-ttu-id="895c0-220">따라서 호출 사이트에서 `in` 한정자를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-220">Therefore, you don't need to specify the `in` modifier at the call site.</span></span> <span data-ttu-id="895c0-221">호출 사이트에서 `in` 한정자를 생략하면 다음과 같은 이유로 인수의 복사본을 만들 수 있음을 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-221">Omitting the `in` modifier at the call site informs the compiler that it's allowed to make a copy of the argument for the following reasons:</span></span>

- <span data-ttu-id="895c0-222">암시적 변환은 있지만 인수 유형에서 매개 변수 유형으로의 ID 변환이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-222">There exists an implicit conversion but not an identity conversion from the argument type to the parameter type.</span></span>
- <span data-ttu-id="895c0-223">인수는 식이지만 알려진 스토리지 변수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-223">The argument is an expression but doesn't have a known storage variable.</span></span>
- <span data-ttu-id="895c0-224">`in`의 유무의 따라 달라지는 오버로드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-224">An overload exists that differs by the presence or absence of `in`.</span></span> <span data-ttu-id="895c0-225">이 경우에는 by 값 오버로드가 더 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-225">In that case, the by value overload is a better match.</span></span>

<span data-ttu-id="895c0-226">이러한 규칙은 읽기 전용 참조 인수를 사용하도록 기존 코드를 업데이트할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-226">These rules are useful as you update existing code to use read-only reference arguments.</span></span> <span data-ttu-id="895c0-227">호출된 메서드 내에서 by 값 매개 변수를 사용하는 모든 인스턴스 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-227">Inside the called method, you can call any instance method that uses by value parameters.</span></span> <span data-ttu-id="895c0-228">이러한 경우 `in` 매개 변수의 복사본이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-228">In those instances, a copy of the `in` parameter is created.</span></span> <span data-ttu-id="895c0-229">컴파일러가 `in` 매개 변수에 대한 임시 변수를 만들 수 있으므로 사용자는 `in` 매개 변수에 대한 기본값을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-229">Because the compiler may create a temporary variable for any `in` parameter, you can also specify default values for any `in` parameter.</span></span> <span data-ttu-id="895c0-230">다음 코드에서는 원점(포인트 0,0)을 두 번째 점의 기본값으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-230">The following code specifies the origin (point 0,0) as the default value for the second point:</span></span>

[!code-csharp[InArgumentDefault](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

<span data-ttu-id="895c0-231">컴파일러가 읽기 전용 인수를 참조로 전달하도록 하려면 다음 코드에 나와 있는 것처럼 호출 사이트의 인수에 `in` 한정자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-231">To force the compiler to pass read-only arguments by reference, specify the `in` modifier on the arguments at the call site, as shown in the following code:</span></span>

[!code-csharp[UseInArgument](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#ExplicitInArgument "Specifying an In argument")]

<span data-ttu-id="895c0-232">이 동작을 통해 성능 향상이 가능한 대규모 코드 베이스에서 시간이 지남에 따라 `in` 매개 변수를 보다 쉽게 채택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-232">This behavior makes it easier to adopt `in` parameters over time in large codebases where performance gains are possible.</span></span> <span data-ttu-id="895c0-233">먼저 메서드 서명에 `in` 한정자를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-233">You add the `in` modifier to method signatures first.</span></span> <span data-ttu-id="895c0-234">그런 다음, 호출 사이트에 `in` 한정자를 추가하고 `readonly struct` 형식을 생성하여 컴파일러가 더 많은 위치에서 `in` 매개 변수의 방어 복사본을 만들지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-234">Then, you can add the `in` modifier at call sites and create `readonly struct` types to enable the compiler to avoid creating defensive copies of `in` parameters in more locations.</span></span>

<span data-ttu-id="895c0-235">`in` 매개 변수 지정은 참조 형식 또는 숫자 값과 함께 사용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-235">The `in` parameter designation can also be used with reference types or numeric values.</span></span> <span data-ttu-id="895c0-236">그러나 두 경우 모두의 이점은 있다고 하더라도 아주 적습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-236">However, the benefits in both cases are minimal, if any.</span></span>

## <a name="never-use-mutable-structs-as-in-in-argument"></a><span data-ttu-id="895c0-237">`in` 인수와 마찬가지로 변경할 수 있는 구조체 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="895c0-237">Never use mutable structs as in `in` argument</span></span>

<span data-ttu-id="895c0-238">앞에서 설명한 기술은 반환 참조에 의한 복사 및 참조로 값 전달을 방지하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-238">The techniques described above explain how to avoid copies by returning references and passing values by reference.</span></span> <span data-ttu-id="895c0-239">이러한 기술은 인수 형식이 `readonly struct` 형식으로 선언되는 경우에 가장 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-239">These techniques work best when the argument types are declared as `readonly struct` types.</span></span> <span data-ttu-id="895c0-240">그렇지 않은 경우, 인수의 읽기 전용 특성을 적용하기 위해 많은 상황에서 컴파일러는 **방어 복사본**을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-240">Otherwise, the compiler must create **defensive copies** in many situations to enforce the readonly-ness of any arguments.</span></span> <span data-ttu-id="895c0-241">원점에서 3D 요소의 거리를 계산하는 다음과 같은 예제를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="895c0-241">Consider the following example that calculates the distance of a 3D point from the origin:</span></span>

[!code-csharp[InArgument](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#InArgument "Specifying an in argument")]

<span data-ttu-id="895c0-242">`Point3D` 구조체는 읽기 전용 구조체가 *아닙니다*.</span><span class="sxs-lookup"><span data-stu-id="895c0-242">The `Point3D` structure is *not* a readonly struct.</span></span> <span data-ttu-id="895c0-243">이 메서드의 본문에는 6개의 서로 다른 속성 액세스 호출이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-243">There are six different property access calls in the body of this method.</span></span> <span data-ttu-id="895c0-244">첫 번째 검사에서 이러한 액세스가 안전하다고 생각했을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-244">On first examination, you may have thought these accesses were safe.</span></span> <span data-ttu-id="895c0-245">결국 `get` 접근자는 개체의 상태를 수정하면 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-245">After all, a `get` accessor shouldn't modify the state of the object.</span></span> <span data-ttu-id="895c0-246">하지만 이를 적용하는 언어 규칙이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-246">But there's no language rule that enforces that.</span></span> <span data-ttu-id="895c0-247">일반적인 관습일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-247">It's only a common convention.</span></span> <span data-ttu-id="895c0-248">모든 형식은 내부 상태를 수정한 `get` 접근자를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-248">Any type could implement a `get` accessor that modified the internal state.</span></span> <span data-ttu-id="895c0-249">일부 언어 보장 없이 컴파일러는 모든 멤버를 호출하기 전에 인수의 임시 복사본을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-249">Without some language guarantee, the compiler must create a temporary copy of the argument before calling any member.</span></span> <span data-ttu-id="895c0-250">임시 스토리지가 스택에 만들어지고, 인수 값이 임시 스토리지에 복사되며, 값이 `this` 인수로 각 멤버 액세스에 대한 스택으로 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-250">The temporary storage is created on the stack, the values of the argument are copied to the temporary storage, and the value is copied to the stack for each member access as the `this` argument.</span></span> <span data-ttu-id="895c0-251">다양한 상황에서 이러한 복사는 인수 형식이 `readonly struct`가 아닌 경우 값으로 전달이 읽기 전용 참조로 전달보다 더 빠를 정도로 성능을 저하시킵니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-251">In many situations, these copies harm performance enough that pass-by-value is faster than pass-by-readonly-reference when the argument type isn't a `readonly struct`.</span></span>

<span data-ttu-id="895c0-252">대신, 거리 계산에서 변경이 불가능한 구조체인 `ReadonlyPoint3D`를 사용하는 경우에는 임시 개체가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-252">Instead, if the distance calculation uses the immutable struct, `ReadonlyPoint3D`, temporary objects aren't needed:</span></span>

[!code-csharp[readonlyInArgument](../../samples/csharp/safe-efficient-code/ref-readonly-struct/Program.cs#ReadOnlyInArgument "Specifying a readonly in argument")]

<span data-ttu-id="895c0-253">컴파일러가 `readonly struct`의 멤버를 호출할 때 더 효율적인 코드를 생성합니다. 수신기의 복사본 대신 `this` 참조는 항상 멤버 메서드에 대한 참조로 전달된 `in` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-253">The compiler generates more efficient code when you call members of a `readonly struct`: The `this` reference, instead of a copy of the receiver, is always an `in` parameter passed by reference to the member method.</span></span> <span data-ttu-id="895c0-254">이 최적화는 `readonly struct`를 `in` 인수로 사용하는 경우 복사본을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-254">This optimization saves copying when you use a `readonly struct` as an `in` argument.</span></span>

<span data-ttu-id="895c0-255">null 허용 값 형식은 `in` 인수로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-255">You shouldn't pass a nullable value type as an `in` argument.</span></span> <span data-ttu-id="895c0-256"><xref:System.Nullable%601> 형식은 읽기 전용 구조체로 선언되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-256">The <xref:System.Nullable%601> type isn't declared as a read-only struct.</span></span> <span data-ttu-id="895c0-257">즉 컴파일러가 매개 변수 선언에서 `in` 수정자를 사용하여 메서드에 전달된 모든 null 허용 값 형식 인수에 대해 방어용 복사본을 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-257">That means the compiler must generate defensive copies for any nullable value type argument passed to a method using the `in` modifier on the parameter declaration.</span></span>

<span data-ttu-id="895c0-258">GitHub에 있는 [샘플 리포지토리](https://github.com/dotnet/samples/tree/master/csharp/safe-efficient-code/benchmark)에서 [BenchmarkDotNet](https://www.nuget.org/packages/BenchmarkDotNet/)을 사용하여 성능 차이를 설명하는 예제 프로그램을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-258">You can see an example program that demonstrates the performance differences using [BenchmarkDotNet](https://www.nuget.org/packages/BenchmarkDotNet/) in our [samples repository](https://github.com/dotnet/samples/tree/master/csharp/safe-efficient-code/benchmark) on GitHub.</span></span> <span data-ttu-id="895c0-259">값으로 및 참조로 변경할 수 있는 구조체를 전달하는 것과 값으로 및 참조로 변경할 수 없는 구조체를 전달하는 것을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-259">It compares passing a mutable struct by value and by reference with passing an immutable struct by value and by reference.</span></span> <span data-ttu-id="895c0-260">변경할 수 없는 구조체를 사용하고 참조로 전달하는 것이 가장 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-260">The use of the immutable struct and pass by reference is fastest.</span></span>

## <a name="use-ref-struct-types-to-work-with-blocks-or-memory-on-a-single-stack-frame"></a><span data-ttu-id="895c0-261">단일 스택 프레임의 블록 또는 메모리를 작업하기 위해 `ref struct` 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-261">Use `ref struct` types to work with blocks or memory on a single stack frame</span></span>

<span data-ttu-id="895c0-262">관련 언어 기능은 단일 스택 프레임에 제한되어야 하는 값 형식을 선언하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-262">A related language feature is the ability to declare a value type that must be constrained to a single stack frame.</span></span> <span data-ttu-id="895c0-263">이 제한을 통해 컴파일러는 몇 가지 최적화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-263">This restriction enables the compiler to make several optimizations.</span></span> <span data-ttu-id="895c0-264">이 기능의 기본 동기 부여는 <xref:System.Span%601> 및 관련 구조였습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-264">The primary motivation for this feature was <xref:System.Span%601> and related structures.</span></span> <span data-ttu-id="895c0-265"><xref:System.Span%601> 유형을 사용하는 새롭고 업데이트된 .NET API를 사용함으로써 이러한 향상된 기능으로부터 성능 향상을 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-265">You'll achieve performance improvements from these enhancements by using new and updated .NET APIs that make use of the <xref:System.Span%601> type.</span></span>

<span data-ttu-id="895c0-266">[`stackalloc`](language-reference/operators/stackalloc.md)을 사용하여 만들어진 메모리로 작업할 때나 interop API에서 메모리를 사용할 때도 유사한 요구 사항이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-266">You may have similar requirements working with memory created using [`stackalloc`](language-reference/operators/stackalloc.md) or when using memory from interop APIs.</span></span> <span data-ttu-id="895c0-267">해당 요구 사항에 대한 사용자 고유의 `ref struct` 형식을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-267">You can define your own `ref struct` types for those needs.</span></span>

## <a name="readonly-ref-struct-type"></a><span data-ttu-id="895c0-268">`readonly ref struct` 형식</span><span class="sxs-lookup"><span data-stu-id="895c0-268">`readonly ref struct` type</span></span>

<span data-ttu-id="895c0-269">구조체를 `readonly ref`로 선언하면 `ref struct` 및 `readonly struct` 선언의 이점과 제한이 결합됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-269">Declaring a struct as `readonly ref` combines the benefits and restrictions of `ref struct` and `readonly struct` declarations.</span></span> <span data-ttu-id="895c0-270">읽기 전용 범위에서 사용된 메모리는 단일 스택 프레임으로 제한되며 읽기 전용 범위에서 사용된 메모리는 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-270">The memory used by the readonly span is restricted to a single stack frame, and the memory used by the readonly span can't be modified.</span></span>

## <a name="conclusions"></a><span data-ttu-id="895c0-271">결론</span><span class="sxs-lookup"><span data-stu-id="895c0-271">Conclusions</span></span>

<span data-ttu-id="895c0-272">값 형식을 사용하면 할당 작업 수가 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-272">Using value types minimizes the number of allocation operations:</span></span>

- <span data-ttu-id="895c0-273">값 형식에 대한 스토리지는 로컬 변수와 메서드 인수에 스택 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-273">Storage for value types is stack allocated for local variables and method arguments.</span></span>
- <span data-ttu-id="895c0-274">다른 개체의 멤버인 값 형식에 대한 스토리지는 별도 할당이 아니라 해당 개체의 일부로 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-274">Storage for value types that are members of other objects is allocated as part of that object, not as a separate allocation.</span></span>
- <span data-ttu-id="895c0-275">값 형식 반환 값에 대한 스토리지는 스택 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-275">Storage for value type return values is stack allocated.</span></span>

<span data-ttu-id="895c0-276">그러한 동일한 상황에서 참조 형식과 대조를 보입니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-276">Contrast that with reference types in those same situations:</span></span>

- <span data-ttu-id="895c0-277">참조 형식에 대한 스토리지는 로컬 변수 및 메서드 인수에 힙 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-277">Storage for reference types are heap allocated for local variables and method arguments.</span></span> <span data-ttu-id="895c0-278">참조는 스택에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-278">The reference is stored on the stack.</span></span>
- <span data-ttu-id="895c0-279">다른 개체의 멤버인 참조 형식에 대한 스토리지는 별도로 힙에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-279">Storage for reference types that are members of other objects are separately allocated on the heap.</span></span> <span data-ttu-id="895c0-280">포함하는 개체는 참조를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-280">The containing object stores the reference.</span></span>
- <span data-ttu-id="895c0-281">참조 형식 반환 값에 대한 스토리지는 힙 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-281">Storage for reference type return values is heap allocated.</span></span> <span data-ttu-id="895c0-282">해당 스토리지에 대한 참조는 스택에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-282">The reference to that storage is stored on the stack.</span></span>

<span data-ttu-id="895c0-283">할당을 최소화하는 작업에는 장단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-283">Minimizing allocations comes with tradeoffs.</span></span> <span data-ttu-id="895c0-284">`struct`의 크기가 참조의 크기보다 큰 경우 더 많은 메모리를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-284">You copy more memory when the size of the `struct` is larger than the size of a reference.</span></span> <span data-ttu-id="895c0-285">참조는 일반적으로 64비트 또는 32비트이며 대상 머신 CPU에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-285">A reference is typically 64 bits or 32 bits, and depends on the target machine CPU.</span></span>

<span data-ttu-id="895c0-286">이러한 장단점은 일반적으로 성능에 거의 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-286">These tradeoffs generally have minimal performance impact.</span></span> <span data-ttu-id="895c0-287">그러나 구조체 또는 컬렉션이 더 큰 경우 성능에 미치는 영향은 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-287">However, for large structs or larger collections, the performance impact increases.</span></span> <span data-ttu-id="895c0-288">연속 루프 및 과다 경로에서는 프로그램에 대한 영향이 더 커질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-288">The impact can be large in tight loops and hot paths for programs.</span></span>

<span data-ttu-id="895c0-289">C# 언어에 대한 이러한 향상된 기능은 메모리 할당을 최소화하는 것이 필요한 성능을 달성하는 데 중요한 요인이 되는 성능 중요 알고리즘을 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-289">These enhancements to the C# language are designed for performance critical algorithms where minimizing memory allocations is a major factor in achieving the necessary performance.</span></span> <span data-ttu-id="895c0-290">작성하는 코드에서 이러한 기능을 자주 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-290">You may find that you don't often use these features in the code you write.</span></span> <span data-ttu-id="895c0-291">그러나 이러한 향상된 기능은 .NET 전반에서 채택되었습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-291">However, these enhancements have been adopted throughout .NET.</span></span> <span data-ttu-id="895c0-292">점점 더 많은 API에서 이러한 기능을 사용하므로 사용자의 애플리케이션 성능이 개선되는 것을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="895c0-292">As more and more APIs make use of these features, you'll see the performance of your applications improve.</span></span>

## <a name="see-also"></a><span data-ttu-id="895c0-293">참고 항목</span><span class="sxs-lookup"><span data-stu-id="895c0-293">See also</span></span>

- [<span data-ttu-id="895c0-294">ref 키워드</span><span class="sxs-lookup"><span data-stu-id="895c0-294">ref keyword</span></span>](language-reference/keywords/ref.md)
- [<span data-ttu-id="895c0-295">Ref return 및 ref local</span><span class="sxs-lookup"><span data-stu-id="895c0-295">Ref returns and ref locals</span></span>](programming-guide/classes-and-structs/ref-returns.md)
