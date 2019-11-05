---
title: 제약 조건
description: 제네릭 형식 F# 매개 변수에 적용 되는 제약 조건에 대해 학습 하 여 제네릭 형식 또는 함수에서 형식 인수에 대 한 요구 사항을 지정 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 70a8bec1ad67d7e814cb7a96b1876bb22399c5e7
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425013"
---
# <a name="constraints"></a><span data-ttu-id="d20d6-103">제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-103">Constraints</span></span>

<span data-ttu-id="d20d6-104">이 항목에서는 제네릭 형식 매개 변수에 적용할 수 있는 제약 조건에 대해 설명 하 여 제네릭 형식 또는 함수의 형식 인수에 대 한 요구 사항을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-104">This topic describes constraints that you can apply to generic type parameters to specify the requirements for a type argument in a generic type or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="d20d6-105">구문</span><span class="sxs-lookup"><span data-stu-id="d20d6-105">Syntax</span></span>

```fsharp
type-parameter-list when constraint1 [ and constraint2]
```

## <a name="remarks"></a><span data-ttu-id="d20d6-106">주의</span><span class="sxs-lookup"><span data-stu-id="d20d6-106">Remarks</span></span>

<span data-ttu-id="d20d6-107">제네릭 형식에 사용할 수 있는 형식을 제한 하기 위해 적용할 수 있는 여러 가지 제약 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-107">There are several different constraints you can apply to limit the types that can be used in a generic type.</span></span> <span data-ttu-id="d20d6-108">다음 표에서는 이러한 제약 조건을 나열 하 고 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-108">The following table lists and describes these constraints.</span></span>

|<span data-ttu-id="d20d6-109">제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-109">Constraint</span></span>|<span data-ttu-id="d20d6-110">구문</span><span class="sxs-lookup"><span data-stu-id="d20d6-110">Syntax</span></span>|<span data-ttu-id="d20d6-111">설명</span><span class="sxs-lookup"><span data-stu-id="d20d6-111">Description</span></span>|
|----------|------|-----------|
|<span data-ttu-id="d20d6-112">형식 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-112">Type Constraint</span></span>|<span data-ttu-id="d20d6-113">*형식-매개 변수* :&gt; *형식*</span><span class="sxs-lookup"><span data-stu-id="d20d6-113">*type-parameter* :&gt; *type*</span></span>|<span data-ttu-id="d20d6-114">제공 된 형식은 지정 된 형식에서 파생 되거나 지정 된 형식에서 파생 되어야 합니다. 형식이 인터페이스 이면 제공 된 형식이 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-114">The provided type must be equal to or derived from the type specified, or, if the type is an interface, the provided type must implement the interface.</span></span>|
|<span data-ttu-id="d20d6-115">Null 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-115">Null Constraint</span></span>|<span data-ttu-id="d20d6-116">*유형-매개 변수* : null</span><span class="sxs-lookup"><span data-stu-id="d20d6-116">*type-parameter* : null</span></span>|<span data-ttu-id="d20d6-117">제공 된 형식은 null 리터럴을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-117">The provided type must support the null literal.</span></span> <span data-ttu-id="d20d6-118">여기에는 모든 .NET 개체 형식이 포함 F# 되지만 목록, 튜플, 함수, 클래스, 레코드 또는 공용 구조체 형식은 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-118">This includes all .NET object types but not F# list, tuple, function, class, record, or union types.</span></span>|
|<span data-ttu-id="d20d6-119">명시적 멤버 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-119">Explicit Member Constraint</span></span>|<span data-ttu-id="d20d6-120">[(]*형식 매개 변수* [또는 ... 또는 *형식 매개 변수*)]: (*멤버 시그니처*)</span><span class="sxs-lookup"><span data-stu-id="d20d6-120">[(]*type-parameter* [or ... or *type-parameter*)] : (*member-signature*)</span></span>|<span data-ttu-id="d20d6-121">제공 된 형식 인수 중 하나 이상에 지정 된 서명이 있는 멤버가 있어야 합니다. 일반적인 용도로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-121">At least one of the type arguments provided must have a member that has the specified signature; not intended for common use.</span></span> <span data-ttu-id="d20d6-122">명시적 멤버 제약 조건의 유효한 대상이 되려면 암시적 형식 확장의 일부 또는 형식에 대해 명시적으로 멤버를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-122">Members must be either explicitly defined on the type or part of an implicit type extension to be valid targets for an Explicit Member Constraint.</span></span>|
|<span data-ttu-id="d20d6-123">생성자 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-123">Constructor Constraint</span></span>|<span data-ttu-id="d20d6-124">*형식-매개 변수* : (new: unit-&gt; ' a)</span><span class="sxs-lookup"><span data-stu-id="d20d6-124">*type-parameter* : ( new : unit -&gt; 'a )</span></span>|<span data-ttu-id="d20d6-125">제공 된 형식에는 매개 변수가 없는 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-125">The provided type must have a parameterless constructor.</span></span>|
|<span data-ttu-id="d20d6-126">값 형식 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-126">Value Type Constraint</span></span>|<span data-ttu-id="d20d6-127">: struct</span><span class="sxs-lookup"><span data-stu-id="d20d6-127">: struct</span></span>|<span data-ttu-id="d20d6-128">제공 된 형식은 .NET 값 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-128">The provided type must be a .NET value type.</span></span>|
|<span data-ttu-id="d20d6-129">참조 형식 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-129">Reference Type Constraint</span></span>|<span data-ttu-id="d20d6-130">: 구조체가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-130">: not struct</span></span>|<span data-ttu-id="d20d6-131">제공 된 형식은 .NET 참조 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-131">The provided type must be a .NET reference type.</span></span>|
|<span data-ttu-id="d20d6-132">열거형 형식 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-132">Enumeration Type Constraint</span></span>|<span data-ttu-id="d20d6-133">: 열거형&lt;*기본 형식*&gt;</span><span class="sxs-lookup"><span data-stu-id="d20d6-133">: enum&lt;*underlying-type*&gt;</span></span>|<span data-ttu-id="d20d6-134">제공 된 형식은 지정 된 기본 형식을 포함 하는 열거형 형식 이어야 합니다. 일반적인 용도로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-134">The provided type must be an enumerated type that has the specified underlying type; not intended for common use.</span></span>|
|<span data-ttu-id="d20d6-135">대리자 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-135">Delegate Constraint</span></span>|<span data-ttu-id="d20d6-136">:&lt;*튜플-매개 변수 형식*, *반환 형식*&gt;</span><span class="sxs-lookup"><span data-stu-id="d20d6-136">: delegate&lt;*tuple-parameter-type*, *return-type*&gt;</span></span>|<span data-ttu-id="d20d6-137">제공 된 형식은 지정 된 인수와 반환 값을 포함 하는 대리자 형식 이어야 합니다. 일반적인 용도로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-137">The provided type must be a delegate type that has the specified arguments and return value; not intended for common use.</span></span>|
|<span data-ttu-id="d20d6-138">비교 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-138">Comparison Constraint</span></span>|<span data-ttu-id="d20d6-139">: 비교</span><span class="sxs-lookup"><span data-stu-id="d20d6-139">: comparison</span></span>|<span data-ttu-id="d20d6-140">제공 된 형식은 비교를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-140">The provided type must support comparison.</span></span>|
|<span data-ttu-id="d20d6-141">같음 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-141">Equality Constraint</span></span>|<span data-ttu-id="d20d6-142">: 같음</span><span class="sxs-lookup"><span data-stu-id="d20d6-142">: equality</span></span>|<span data-ttu-id="d20d6-143">제공 된 형식이 같음을 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-143">The provided type must support equality.</span></span>|
|<span data-ttu-id="d20d6-144">관리 되지 않는 제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-144">Unmanaged Constraint</span></span>|<span data-ttu-id="d20d6-145">: 관리 되지 않음</span><span class="sxs-lookup"><span data-stu-id="d20d6-145">: unmanaged</span></span>|<span data-ttu-id="d20d6-146">제공 된 형식은 관리 되지 않는 형식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-146">The provided type must be an unmanaged type.</span></span> <span data-ttu-id="d20d6-147">관리 되지 않는 형식은 특정 기본 형식 (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, 또는 `decimal`), 열거형 형식, `nativeptr<_>`또는 필드가 모두 관리 되지 않는 형식인 제네릭이 아닌 구조체.</span><span class="sxs-lookup"><span data-stu-id="d20d6-147">Unmanaged types are either certain primitive types (`sbyte`, `byte`, `char`, `nativeint`, `unativeint`, `float32`, `float`, `int16`, `uint16`, `int32`, `uint32`, `int64`, `uint64`, or `decimal`), enumeration types, `nativeptr<_>`, or a non-generic structure whose fields are all unmanaged types.</span></span>|

<span data-ttu-id="d20d6-148">코드에서 제약 조건 형식에 사용할 수 있지만 일반적으로 형식이 아닌 기능을 사용 해야 하는 경우 제약 조건을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-148">You have to add a constraint when your code has to use a feature that is available on the constraint type but not on types in general.</span></span> <span data-ttu-id="d20d6-149">예를 들어 형식 제약 조건을 사용 하 여 클래스 형식을 지정 하는 경우 제네릭 함수 또는 형식에서 해당 클래스의 메서드 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-149">For example, if you use the type constraint to specify a class type, you can use any one of the methods of that class in the generic function or type.</span></span>

<span data-ttu-id="d20d6-150">제약 조건을 사용 하지 않고 형식 매개 변수를 명시적으로 작성 하는 경우 제약 조건을 지정 해야 하는 경우가 있습니다. 컴파일러는 사용 중인 기능을 형식에 대해 런타임에 제공 될 수 있는 모든 형식에서 사용할 수 있는지 확인할 방법이 없습니다. 변수에.</span><span class="sxs-lookup"><span data-stu-id="d20d6-150">Specifying constraints is sometimes required when writing type parameters explicitly, because without a constraint, the compiler has no way of verifying that the features that you are using will be available on any type that might be supplied at run time for the type parameter.</span></span>

<span data-ttu-id="d20d6-151">코드에서 F# 사용 하는 가장 일반적인 제약 조건은 기본 클래스 또는 인터페이스를 지정 하는 형식 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-151">The most common constraints you use in F# code are type constraints that specify base classes or interfaces.</span></span> <span data-ttu-id="d20d6-152">다른 제약 조건은 산술 연산자에 대 한 F# 연산자 오버 로드를 구현 하는 데 사용 되는 명시적 멤버 제약 조건 등의 특정 기능을 구현 하기 위해 라이브러리에서 사용 되거나 주로 F# 제공 됩니다. 공용 언어 런타임에서 지 원하는 전체 제약 조건 집합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-152">The other constraints are either used by the F# library to implement certain functionality, such as the explicit member constraint, which is used to implement operator overloading for arithmetic operators, or are provided mainly because F# supports the complete set of constraints that is supported by the common language runtime.</span></span>

<span data-ttu-id="d20d6-153">형식 유추 프로세스 중에 일부 제약 조건은 컴파일러에 의해 자동으로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-153">During the type inference process, some constraints are inferred automatically by the compiler.</span></span> <span data-ttu-id="d20d6-154">예를 들어 함수에 `+` 연산자를 사용 하는 경우 컴파일러는 식에 사용 되는 변수 형식에 대해 명시적 멤버 제약 조건을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-154">For example, if you use the `+` operator in a function, the compiler infers an explicit member constraint on variable types that are used in the expression.</span></span>

<span data-ttu-id="d20d6-155">다음 코드에서는 몇 가지 제약 조건 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d20d6-155">The following code illustrates some constraint declarations:</span></span>

```fsharp
// Base Type Constraint
type Class1<'T when 'T :> System.Exception> =
class end

// Interface Type Constraint
type Class2<'T when 'T :> System.IComparable> =
class end

// Null constraint
type Class3<'T when 'T : null> =
class end

// Member constraint with instance member
type Class5<'T when 'T : (member Method1 : 'T -> int)> =
class end

// Member constraint with property
type Class6<'T when 'T : (member Property1 : int)> =
class end

// Constructor constraint
type Class7<'T when 'T : (new : unit -> 'T)>() =
member val Field = new 'T()

// Reference type constraint
type Class8<'T when 'T : not struct> =
class end

// Enumeration constraint with underlying value specified
type Class9<'T when 'T : enum<uint32>> =
class end

// 'T must implement IComparable, or be an array type with comparable
// elements, or be System.IntPtr or System.UIntPtr. Also, 'T must not have
// the NoComparison attribute.
type Class10<'T when 'T : comparison> =
class end

// 'T must support equality. This is true for any type that does not
// have the NoEquality attribute.
type Class11<'T when 'T : equality> =
class end

type Class12<'T when 'T : delegate<obj * System.EventArgs, unit>> =
class end

type Class13<'T when 'T : unmanaged> =
class end

// Member constraints with two type parameters
// Most often used with static type parameters in inline functions
let inline add(value1 : ^T when ^T : (static member (+) : ^T * ^T -> ^T), value2: ^T) =
value1 + value2

// ^T and ^U must support operator +
let inline heterogenousAdd(value1 : ^T when (^T or ^U) : (static member (+) : ^T * ^U -> ^T), value2 : ^U) =
value1 + value2

// If there are multiple constraints, use the and keyword to separate them.
type Class14<'T,'U when 'T : equality and 'U : equality> =
class end
```

## <a name="see-also"></a><span data-ttu-id="d20d6-156">참조</span><span class="sxs-lookup"><span data-stu-id="d20d6-156">See also</span></span>

- [<span data-ttu-id="d20d6-157">제네릭</span><span class="sxs-lookup"><span data-stu-id="d20d6-157">Generics</span></span>](index.md)
- [<span data-ttu-id="d20d6-158">제약 조건</span><span class="sxs-lookup"><span data-stu-id="d20d6-158">Constraints</span></span>](constraints.md)
