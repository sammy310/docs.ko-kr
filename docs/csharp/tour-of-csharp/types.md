---
title: 형식과 그 멤버 정의하기 - C# 둘러보기
description: 형식은 프로그램의 기본적인 구성 요소입니다. C#에서 클래스, 구조체, 인터페이스 등을 만드는 방법을 알아봅니다.
ms.date: 08/06/2020
ms.openlocfilehash: efd353fe8c1e6a57952bcb2586a05ad38ecd52b9
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "88559117"
---
# <a name="types-and-members"></a><span data-ttu-id="5ab47-104">형식 및 멤버</span><span class="sxs-lookup"><span data-stu-id="5ab47-104">Types and members</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="5ab47-105">클래스 및 개체</span><span class="sxs-lookup"><span data-stu-id="5ab47-105">Classes and objects</span></span>

<span data-ttu-id="5ab47-106">*클래스* 는 C#의 가장 기본적인 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-106">*Classes* are the most fundamental of C#’s types.</span></span> <span data-ttu-id="5ab47-107">클래스는 상태(필드)와 작업(메서드 및 기타 함수 멤버)을 하나의 단위로 결합하는 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-107">A class is a data structure that combines state (fields) and actions (methods and other function members) in a single unit.</span></span> <span data-ttu-id="5ab47-108">클래스는 해당 클래스의 ‘인스턴스’(‘개체’라고도 함)에 대한 정의를 제공합니다. </span><span class="sxs-lookup"><span data-stu-id="5ab47-108">A class provides a definition for *instances* of the class, also known as *objects*.</span></span> <span data-ttu-id="5ab47-109">클래스는 *상속* 및 *다형성* 과 *파생된 클래스* 가 *기본 클래스* 를 확장하고 특수화할 수 있는 메커니즘을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-109">Classes support *inheritance* and *polymorphism*, mechanisms whereby *derived classes* can extend and specialize *base classes*.</span></span>

<span data-ttu-id="5ab47-110">새 클래스는 클래스 선언을 사용하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-110">New classes are created using class declarations.</span></span> <span data-ttu-id="5ab47-111">클래스 선언은 헤더로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-111">A class declaration starts with a header.</span></span> <span data-ttu-id="5ab47-112">헤더는 다음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-112">The header specifies:</span></span>

- <span data-ttu-id="5ab47-113">클래스의 특성 및 한정자</span><span class="sxs-lookup"><span data-stu-id="5ab47-113">The attributes and modifiers of the class</span></span>
- <span data-ttu-id="5ab47-114">클래스의 이름</span><span class="sxs-lookup"><span data-stu-id="5ab47-114">The name of the class</span></span>
- <span data-ttu-id="5ab47-115">기본 클래스([기본 클래스](#base-classes)에서 상속하는 경우)</span><span class="sxs-lookup"><span data-stu-id="5ab47-115">The base class (when inheriting from a [base class](#base-classes))</span></span>
- <span data-ttu-id="5ab47-116">이 클래스에서 구현한 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ab47-116">The interfaces implemented by the class.</span></span>

<span data-ttu-id="5ab47-117">헤더 다음에는 구분 기호 `{` 및 `}` 간에 작성되는 멤버 선언 목록으로 구성되는 클래스 본문이 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-117">The header is followed by the class body, which consists of a list of member declarations written between the delimiters `{` and `}`.</span></span>

<span data-ttu-id="5ab47-118">다음 코드는 `Point`라는 간단한 클래스의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-118">The following code shows a declaration of a simple class named `Point`:</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="PointClass":::

<span data-ttu-id="5ab47-119">클래스의 인스턴스는 새 인스턴스에 대한 메모리를 할당하고, 인스턴스를 초기화하는 생성자를 호출하고, 인스턴스에 대한 참조를 반환하는 `new` 연산자를 사용하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-119">Instances of classes are created using the `new` operator, which allocates memory for a new instance, invokes a constructor to initialize the instance, and returns a reference to the instance.</span></span> <span data-ttu-id="5ab47-120">다음 문은 두 개의 `Point` 개체를 만들고 해당 개체에 대한 참조를 두 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-120">The following statements create two `Point` objects and store references to those objects in two variables:</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="CreatePoints":::

<span data-ttu-id="5ab47-121">개체가 차지하는 메모리는 개체에 더 이상 연결할 수 없을 때 자동으로 회수됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-121">The memory occupied by an object is automatically reclaimed when the object is no longer reachable.</span></span> <span data-ttu-id="5ab47-122">C#에서는 개체를 명시적으로 할당 취소할 필요가 없으며 가능하지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-122">It's neither necessary nor possible to explicitly deallocate objects in C#.</span></span>

### <a name="type-parameters"></a><span data-ttu-id="5ab47-123">형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ab47-123">Type parameters</span></span>

<span data-ttu-id="5ab47-124">제네릭 클래스는 [ **‘형식 매개 변수’** ](../programming-guide/generics/index.md)를 정의합니다.\*</span><span class="sxs-lookup"><span data-stu-id="5ab47-124">Generic classes define [\***type parameters** _](../programming-guide/generics/index.md).</span></span> <span data-ttu-id="5ab47-125">형식 매개 변수는 대괄호로 묶인 형식 매개 변수 이름 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-125">Type parameters are a list of type parameter names enclosed in angle brackets.</span></span> <span data-ttu-id="5ab47-126">형식 매개 변수는 클래스 이름을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-126">Type parameters follow the class name.</span></span> <span data-ttu-id="5ab47-127">그런 후 형식 매개 변수를 클래스 선언 본문에 사용하여 클래스의 멤버를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-127">The type parameters can then be used in the body of the class declarations to define the members of the class.</span></span> <span data-ttu-id="5ab47-128">다음 예제에서 `Pair`의 형식 매개 변수는 `TFirst` 및 `TSecond`입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-128">In the following example, the type parameters of `Pair` are `TFirst` and `TSecond`:</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DefinePairClass":::

<span data-ttu-id="5ab47-129">형식 매개 변수를 사용하도록 선언된 클래스 형식을 ‘제네릭 클래스 형식’이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-129">A class type that is declared to take type parameters is called a _generic class type\*.</span></span> <span data-ttu-id="5ab47-130">구조체, 인터페이스 및 대리자 형식도 제네릭일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-130">Struct, interface, and delegate types can also be generic.</span></span>
<span data-ttu-id="5ab47-131">제네릭 클래스를 사용하는 경우 각 형식 매개 변수에 대해 다음과 같은 형식 인수가 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-131">When the generic class is used, type arguments must be provided for each of the type parameters:</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="CreatePairObject":::

<span data-ttu-id="5ab47-132">위의 `Pair<int,string>`과 같이 형식 인수가 제공된 제네릭 형식을 *생성된 형식* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-132">A generic type with type arguments provided, like `Pair<int,string>` above, is called a *constructed type*.</span></span>

### <a name="base-classes"></a><span data-ttu-id="5ab47-133">기본 클래스</span><span class="sxs-lookup"><span data-stu-id="5ab47-133">Base classes</span></span>

<span data-ttu-id="5ab47-134">클래스 선언은 기본 클래스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-134">A class declaration may specify a base class.</span></span> <span data-ttu-id="5ab47-135">클래스 이름 및 형식 매개 변수 뒤에 콜론과 기본 클래스의 이름을 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-135">Follow the class name and type parameters with a colon and the name of the base class.</span></span> <span data-ttu-id="5ab47-136">기본 클래스 지정을 생략하면 `object` 형식에서 파생되는 클래스와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-136">Omitting a base class specification is the same as deriving from type `object`.</span></span> <span data-ttu-id="5ab47-137">다음 예제에서 `Point3D`의 기본 클래스는 `Point`입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-137">In the following example, the base class of `Point3D` is `Point`.</span></span> <span data-ttu-id="5ab47-138">첫 번째 예제에서 `Point`의 기본 클래스는 `object`입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-138">From the first example, the base class of `Point` is `object`:</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="Create3DPoint":::

<span data-ttu-id="5ab47-139">클래스는 기본 클래스의 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-139">A class inherits the members of its base class.</span></span> <span data-ttu-id="5ab47-140">상속은 클래스가 기본 클래스의 거의 모든 멤버를 암시적으로 포함함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-140">Inheritance means that a class implicitly contains almost all members of its base class.</span></span> <span data-ttu-id="5ab47-141">클래스는 인스턴스 및 정적 생성자와 종결자는 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-141">A class doesn't inherit the instance and static constructors, and the finalizer.</span></span> <span data-ttu-id="5ab47-142">파생 클래스는 해당 파생된 클래스를 상속하는 멤버에 새 멤버를 추가할 수 있지만 상속된 멤버의 정의를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-142">A derived class can add new members to those members it inherits, but it can't remove the definition of an inherited member.</span></span> <span data-ttu-id="5ab47-143">앞의 예제에서 `Point3D`는 `Point`에서 `X` 및 `Y` 멤버를 상속하고 모든 `Point3D` 인스턴스는 세 개의 속성, 즉 `X`, `Y` 및 `Z`를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-143">In the previous example, `Point3D` inherits the `X` and `Y` members from `Point`, and every `Point3D` instance contains three properties, `X`, `Y`, and `Z`.</span></span>

<span data-ttu-id="5ab47-144">클래스 형식에서 해당 기본 클래스 형식 간에 암시적 변환이 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-144">An implicit conversion exists from a class type to any of its base class types.</span></span> <span data-ttu-id="5ab47-145">클래스 형식의 변수는 해당 클래스의 인스턴스 또는 모든 파생 클래스의 인스턴스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-145">A variable of a class type can reference an instance of that class or an instance of any derived class.</span></span> <span data-ttu-id="5ab47-146">예를 들어 이전 클래스 선언에서 형식 `Point`의 변수는 `Point` 또는 `Point3D`를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-146">For example, given the previous class declarations, a variable of type `Point` can reference either a `Point` or a `Point3D`:</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="ImplicitCastToBase":::

## <a name="structs"></a><span data-ttu-id="5ab47-147">구조체</span><span class="sxs-lookup"><span data-stu-id="5ab47-147">Structs</span></span>

<span data-ttu-id="5ab47-148">클래스는 상속과 다형성을 지원하는 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-148">Classes define types that support inheritance and polymorphism.</span></span> <span data-ttu-id="5ab47-149">이를 통해 파생 클래스의 계층 구조를 기반으로 정교한 동작을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-149">They enable you to create sophisticated behaviors based on hierarchies of derived classes.</span></span> <span data-ttu-id="5ab47-150">이와 대조적으로 [ **‘구조체’** ](../language-reference/builtin-types/struct.md) 형식은 보다 단순한 형식으로, 기본 용도는 데이터 값을 저장하는 것입니다.\*</span><span class="sxs-lookup"><span data-stu-id="5ab47-150">By contrast, [\***struct** _](../language-reference/builtin-types/struct.md) types are simpler types whose primary purpose is to store data values.</span></span> <span data-ttu-id="5ab47-151">구조체는 기본 형식을 선언할 수 없으며, <xref:System.ValueType?displayProperty=nameWithType>에서 암시적으로 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-151">Structs can't declare a base type; they implicitly derive from <xref:System.ValueType?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5ab47-152">`struct` 형식에서 다른 `struct` 형식을 파생할 수 없으며</span><span class="sxs-lookup"><span data-stu-id="5ab47-152">You can't derive other `struct` types from a `struct` type.</span></span> <span data-ttu-id="5ab47-153">암시적으로 봉인됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-153">They're implicitly sealed.</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="PointStruct":::

## <a name="interfaces"></a><span data-ttu-id="5ab47-154">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5ab47-154">Interfaces</span></span>

<span data-ttu-id="5ab47-155">[‘인터페이스’](../programming-guide/interfaces/index.md)는 클래스 및 구조체로 구현할 수 있는 계약을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-155">An [_*_interface_*_](../programming-guide/interfaces/index.md) defines a contract that can be implemented by classes and structs.</span></span> <span data-ttu-id="5ab47-156">인터페이스는 메서드, 속성, 이벤트 및 인덱서를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-156">An interface can contain methods, properties, events, and indexers.</span></span> <span data-ttu-id="5ab47-157">인터페이스는 일반적으로 해당 인터페이스가 정의하는 멤버의 구현을 제공하지 않으며 단지 해당 인터페이스를 구현하는 클래스 또는 구조체에서 제공해야 하는 멤버를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-157">An interface typically doesn't provide implementations of the members it defines—it merely specifies the members that must be supplied by classes or structs that implement the interface.</span></span>

<span data-ttu-id="5ab47-158">인터페이스는 ‘다중 상속’을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-158">Interfaces may employ _*_multiple inheritance_*_.</span></span> <span data-ttu-id="5ab47-159">다음 예제에서 인터페이스 `IComboBox`는 `ITextBox` 및 `IListBox`를 둘 다 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-159">In the following example, the interface `IComboBox` inherits from both `ITextBox` and `IListBox`.</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="FirstInterfaces":::

<span data-ttu-id="5ab47-160">클래스 및 구조체는 여러 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-160">Classes and structs can implement multiple interfaces.</span></span> <span data-ttu-id="5ab47-161">다음 예제에서 클래스 `EditBox`는 `IControl` 및 `IDataBound`를 둘 다 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-161">In the following example, the class `EditBox` implements both `IControl` and `IDataBound`.</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="ImplementInterfaces":::

<span data-ttu-id="5ab47-162">클래스 또는 구조체가 특정 인터페이스를 구현하는 경우 해당 클래스 또는 구조체의 인스턴스를 해당 인터페이스 형식으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-162">When a class or struct implements a particular interface, instances of that class or struct can be implicitly converted to that interface type.</span></span> <span data-ttu-id="5ab47-163">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-163">For example</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="UseInterfaces":::

## <a name="enums"></a><span data-ttu-id="5ab47-164">열거형</span><span class="sxs-lookup"><span data-stu-id="5ab47-164">Enums</span></span>

<span data-ttu-id="5ab47-165">[‘열거형’](../language-reference/builtin-types/enum.md) 형식은 상수 값 세트를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-165">An [_*_Enum_*_](../language-reference/builtin-types/enum.md) type defines a set of constant values.</span></span> <span data-ttu-id="5ab47-166">다음 `enum`은 여러 뿌리채소를 정의하는 상수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-166">The following `enum` declares constants that define different root vegetables:</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="EnumDeclaration":::

<span data-ttu-id="5ab47-167">플래그와 함께 사용되도록 `enum`을 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-167">You can also define an `enum` to be used in combination as flags.</span></span> <span data-ttu-id="5ab47-168">다음 선언은 사계절에 대한 플래그 세트를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-168">The following declaration declares a set of flags for the four seasons.</span></span> <span data-ttu-id="5ab47-169">모든 계절을 포함하는 `All` 값을 비롯해 계절의 모든 조합을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-169">Any combination of the seasons may be applied, including an `All` value that includes all seasons:</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="FlagsEnumDeclaration":::

<span data-ttu-id="5ab47-170">다음 예제에서는 위 열거형의 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-170">The following example shows declarations of both the preceding enums:</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="UsingEnums":::

## <a name="nullable-types"></a><span data-ttu-id="5ab47-171">Nullable 유형</span><span class="sxs-lookup"><span data-stu-id="5ab47-171">Nullable types</span></span>

<span data-ttu-id="5ab47-172">모든 형식의 변수는 ‘null을 허용하지 않는’ 또는 ‘null 허용’으로 선언할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="5ab47-172">Variables of any type may be declared as _*_non-nullable_*_ or _*_nullable_*_.</span></span> <span data-ttu-id="5ab47-173">null 허용 변수는 값이 없음을 나타내는 추가 `null` 값을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-173">A nullable variable can hold an additional `null` value, indicating no value.</span></span> <span data-ttu-id="5ab47-174">null 허용 값 형식(구조체 또는 열거형)은 <xref:System.Nullable%601?displayProperty=nameWithType>로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-174">Nullable Value types (structs or enums) are represented by <xref:System.Nullable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="5ab47-175">null을 허용하지 않는 형식과 null 참조 형식은 모두 기본 참조 형식으로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-175">Non-nullable and Nullable Reference types are both represented by the underlying reference type.</span></span> <span data-ttu-id="5ab47-176">둘 사이의 구분은 컴파일러와 일부 라이브러리에서 읽어 들이는 메타데이터로 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-176">The distinction is represented by metadata read by the compiler and some libraries.</span></span> <span data-ttu-id="5ab47-177">컴파일러는 null 참조가 먼저 `null`에 대해 값을 검사하지 않고 역참조될 경우 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-177">The compiler provides warnings when nullable references are dereferenced without first checking their value against `null`.</span></span> <span data-ttu-id="5ab47-178">컴파일러는 null을 허용하지 않는 참조에 `null`일 수 있는 값을 할당하는 경우에도 경고를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-178">The compiler also provides warnings when non-nullable references are assigned a value that may be `null`.</span></span> <span data-ttu-id="5ab47-179">다음 예제에서는 ‘null 허용 int’를 선언하고 `null`로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-179">The following example declares a _*_nullable int_*_, initializing it to `null`.</span></span> <span data-ttu-id="5ab47-180">그런 다음 값을 `5`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-180">Then, it sets the value to `5`.</span></span> <span data-ttu-id="5ab47-181">이 예제는 ‘null 허용 문자열’과 동일한 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-181">It demonstrates the same concept with a _*_nullable string_*_.</span></span> <span data-ttu-id="5ab47-182">자세한 내용은 [null 허용 값 형식](../language-reference/builtin-types/nullable-value-types.md) 및 [null 허용 참조 형식](../nullable-references.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab47-182">For more information, see [nullable value types](../language-reference/builtin-types/nullable-value-types.md) and [nullable reference types](../nullable-references.md).</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DeclareNullable":::

## <a name="tuples"></a><span data-ttu-id="5ab47-183">튜플</span><span class="sxs-lookup"><span data-stu-id="5ab47-183">Tuples</span></span>

<span data-ttu-id="5ab47-184">C#은 간단한 데이터 구조로 여러 데이터 요소를 그룹화하는 간결한 구문을 제공하는 [‘튜플’](../language-reference/builtin-types/value-tuples.md)을 지원합니다.\*</span><span class="sxs-lookup"><span data-stu-id="5ab47-184">C# supports [_ *_tuples_*\*](../language-reference/builtin-types/value-tuples.md), which provides concise syntax to group multiple data elements in a lightweight data structure.</span></span> <span data-ttu-id="5ab47-185">다음 예제에서 볼 수 있듯이 튜플은 `(`와 `)` 사이에서 멤버의 형식과 이름을 선언함으로써 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-185">You instantiate a tuple by declaring the types and names of the members between `(` and `)`, as shown in the following example:</span></span>

:::code language="csharp" source="./snippets/shared/Types.cs" ID="DeclareTuples":::

<span data-ttu-id="5ab47-186">튜플은 다음 문서에서 설명하는 기본 구성 요소를 사용하지 않고도 여러 멤버를 위한 또 다른 데이터 구조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab47-186">Tuples provide an alternative for data structure with multiple members, without using the building blocks described in the next article.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="5ab47-187">[이전](index.md)
>[다음](program-building-blocks.md)</span><span class="sxs-lookup"><span data-stu-id="5ab47-187">[Previous](index.md)
[Next](program-building-blocks.md)</span></span>
