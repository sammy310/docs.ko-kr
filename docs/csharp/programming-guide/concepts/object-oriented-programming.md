---
title: 개체 지향 프로그래밍(C#)
description: C#은 추상화, 캡슐화, 상속, 다형성 등 개체 지향 프로그래밍에 대한 모든 지원을 제공합니다.
ms.date: 05/13/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 0c5495aefad73a2916ad6e2bd2bf3701d0868f24
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302817"
---
# <a name="object-oriented-programming-c"></a><span data-ttu-id="865e8-103">개체 지향 프로그래밍(C#)</span><span class="sxs-lookup"><span data-stu-id="865e8-103">Object-Oriented programming (C#)</span></span>

<span data-ttu-id="865e8-104">C#은 추상화, 캡슐화, 상속, 다형성 등 개체 지향 프로그래밍에 대한 모든 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-104">C# provides full support for object-oriented programming including abstraction, encapsulation, inheritance, and polymorphism.</span></span>

- <span data-ttu-id="865e8-105">‘추상화’는 형식 소비자의 불필요한 세부 정보를 숨기는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-105">*Abstraction* means hiding the unnecessary details from type consumers.</span></span>
- <span data-ttu-id="865e8-106">*캡슐화*는 서로 관련된 속성, 메서드 및 기타 멤버의 그룹을 하나의 단위나 개체로 취급하는 것을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-106">*Encapsulation* means that a group of related properties, methods, and other members are treated as a single unit or object.</span></span>
- <span data-ttu-id="865e8-107">*상속*은 기존 클래스를 기반으로 새로운 클래스를 만들 수 있는 능력을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-107">*Inheritance* describes the ability to create new classes based on an existing class.</span></span>
- <span data-ttu-id="865e8-108">*다형성*은 동일한 속성 또는 메서드를 각각 다른 방식으로 구현하는 여러 클래스를 서로 교체하여 사용할 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-108">*Polymorphism* means that you can have multiple classes that can be used interchangeably, even though each class implements the same properties or methods in different ways.</span></span>

## <a name="classes-and-objects"></a><span data-ttu-id="865e8-109">클래스 및 개체</span><span class="sxs-lookup"><span data-stu-id="865e8-109">Classes and objects</span></span>

<span data-ttu-id="865e8-110">‘클래스’와 ‘개체’라는 용어는 각각 개체의 ‘형식’과 클래스의 ‘인스턴스’를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-110">The terms *class* and *object* describe the *type* of objects, and the *instances* of classes, respectively.</span></span> <span data-ttu-id="865e8-111">따라서 개체를 만드는 작업을 *인스턴스화*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-111">So, the act of creating an object is called *instantiation*.</span></span> <span data-ttu-id="865e8-112">청사진에 비유한다면 클래스는 청사진이고 개체는 해당 청사진을 사용하여 만든 빌딩입니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-112">Using the blueprint analogy, a class is a blueprint, and an object is a building made from that blueprint.</span></span>

<span data-ttu-id="865e8-113">클래스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-113">To define a class:</span></span>

```csharp
class SampleClass
{
}
```

<span data-ttu-id="865e8-114">C#에는 ‘구조체’라는 형식도 있는데, 구조체는 상속이나 다형성을 지원할 필요가 없는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-114">C# also provides types called *structures* that are useful when you don't need support for inheritance or polymorphism.</span></span> <span data-ttu-id="865e8-115">자세한 내용은 [클래스와 구조체 중에 선택](../../../standard/design-guidelines/choosing-between-class-and-struct.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-115">For more information, see [Choosing between class and struct](../../../standard/design-guidelines/choosing-between-class-and-struct.md).</span></span>

<span data-ttu-id="865e8-116">구조체를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-116">To define a structure:</span></span>

```csharp
struct SampleStruct
{
}
```

<span data-ttu-id="865e8-117">자세한 내용은 [class](../../language-reference/keywords/class.md) 및 [struct](../../language-reference/builtin-types/struct.md) 키워드에 관한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-117">For more information, see the articles on the [class](../../language-reference/keywords/class.md) and [struct](../../language-reference/builtin-types/struct.md) keywords.</span></span>

### <a name="class-members"></a><span data-ttu-id="865e8-118">클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="865e8-118">Class members</span></span>

<span data-ttu-id="865e8-119">각 클래스에는 클래스 데이터를 설명하는 속성, 클래스 동작을 정의하는 메서드 및 서로 다른 클래스와 개체 간의 통신을 제공하는 이벤트가 포함된 다양한 *클래스 멤버*가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-119">Each class can have different *class members* that include properties that describe class data, methods that define class behavior, and events that provide communication between different classes and objects.</span></span>

#### <a name="properties-and-fields"></a><span data-ttu-id="865e8-120">속성 및 필드</span><span class="sxs-lookup"><span data-stu-id="865e8-120">Properties and fields</span></span>

<span data-ttu-id="865e8-121">필드 및 속성은 개체가 포함하는 정보를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-121">Fields and properties represent information that an object contains.</span></span> <span data-ttu-id="865e8-122">필드는 액세스 한정자에 따라 직접 읽거나 설정할 수 있기 때문에 변수와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-122">Fields are like variables because they can be read or set directly, subject to applicable access modifiers.</span></span>

<span data-ttu-id="865e8-123">클래스의 인스턴스 내에서 액세스할 수 있는 필드를 정의하려면:</span><span class="sxs-lookup"><span data-stu-id="865e8-123">To define a field that can be accessed from within instances of the class:</span></span>

```csharp
public class SampleClass
{
    string sampleField;
}
```

<span data-ttu-id="865e8-124">속성에는 값을 설정하고 반환하는 방법을 보다 세밀하게 제어할 수 있는 `get` 및 `set` 접근자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-124">Properties have `get` and `set` accessors, which provide more control on how values are set or returned.</span></span>

<span data-ttu-id="865e8-125">C#에서는 속성 값을 저장하기 위한 private 필드를 만들거나 이 필드를 내부적으로 자동으로 만들고 속성 프로시저에 대한 기본 논리를 제공하는 자동 구현 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-125">C# allows you either to create a private field for storing the property value or use auto-implemented properties that create this field automatically behind the scenes and provide the basic logic for the property procedures.</span></span>

<span data-ttu-id="865e8-126">자동 구현 속성을 정의하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-126">To define an auto-implemented property:</span></span>

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

<span data-ttu-id="865e8-127">속성 값을 읽고 쓰기 위해 몇 가지 추가 작업을 수행해야 하는 경우 다음과 같이 속성 값을 저장하기 위한 필드를 정의하고, 속성 값을 저장 및 검색하기 위한 기본 논리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-127">If you need to perform some additional operations for reading and writing the property value, define a field for storing the property value and provide the basic logic for storing and retrieving it:</span></span>

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

<span data-ttu-id="865e8-128">대부분의 속성에는 속성 값을 설정하고 가져오는 메서드나 프로시저가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-128">Most properties have methods or procedures to both set and get the property value.</span></span> <span data-ttu-id="865e8-129">그러나 읽기 전용 또는 쓰기 전용 속성을 만들어 속성을 수정하거나 읽지 못하도록 제한할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-129">However, you can create read-only or write-only properties to restrict them from being modified or read.</span></span> <span data-ttu-id="865e8-130">C#에서는 `get` 또는 `set` 속성 메서드를 생략하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-130">In C#, you can omit the `get` or `set` property method.</span></span> <span data-ttu-id="865e8-131">하지만 자동 구현 속성은 쓰기 전용일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-131">However, auto-implemented properties cannot be write-only.</span></span> <span data-ttu-id="865e8-132">읽기 전용 자동 구현 속성은 포함하는 클래스의 생성자에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-132">Read-only auto-implemented properties can be set in constructors of the containing class.</span></span>

<span data-ttu-id="865e8-133">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-133">For more information, see:</span></span>

- [<span data-ttu-id="865e8-134">get</span><span class="sxs-lookup"><span data-stu-id="865e8-134">get</span></span>](../../language-reference/keywords/get.md)
- [<span data-ttu-id="865e8-135">set</span><span class="sxs-lookup"><span data-stu-id="865e8-135">set</span></span>](../../language-reference/keywords/set.md)

#### <a name="methods"></a><span data-ttu-id="865e8-136">메서드</span><span class="sxs-lookup"><span data-stu-id="865e8-136">Methods</span></span>

<span data-ttu-id="865e8-137">*메서드*는 개체에서 수행할 수 있는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-137">A *method* is an action that an object can perform.</span></span>

<span data-ttu-id="865e8-138">클래스의 메서드를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-138">To define a method of a class:</span></span>

```csharp
class SampleClass
{
    public int SampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

<span data-ttu-id="865e8-139">클래스에는 매개 변수 개수나 매개 변수 형식이 다른 동일한 메서드의 구현 또는 *오버로드*가 여러 개 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-139">A class can have several implementations, or *overloads*, of the same method that differ in the number of parameters or parameter types.</span></span>

<span data-ttu-id="865e8-140">메서드를 오버로드하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-140">To overload a method:</span></span>

```csharp
public int SampleMethod(string sampleParam) { }
public int SampleMethod(int sampleParam) { }
```

<span data-ttu-id="865e8-141">대부분의 경우 클래스 정의 내에서 메서드를 선언하지만</span><span class="sxs-lookup"><span data-stu-id="865e8-141">In most cases you declare a method within a class definition.</span></span> <span data-ttu-id="865e8-142">C#에서는 클래스의 실제 정의 밖에 있는 기존 클래스에 메서드를 추가할 수 있는 *확장 메서드*도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-142">However, C# also supports *extension methods* that allow you to add methods to an existing class outside the actual definition of the class.</span></span>

<span data-ttu-id="865e8-143">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-143">For more information, see:</span></span>

- [<span data-ttu-id="865e8-144">메서드</span><span class="sxs-lookup"><span data-stu-id="865e8-144">Methods</span></span>](../classes-and-structs/methods.md)
- [<span data-ttu-id="865e8-145">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="865e8-145">Extension Methods</span></span>](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a><span data-ttu-id="865e8-146">생성자</span><span class="sxs-lookup"><span data-stu-id="865e8-146">Constructors</span></span>

<span data-ttu-id="865e8-147">생성자는 지정된 형식의 개체를 만들 때 자동으로 실행되는 클래스 메서드로,</span><span class="sxs-lookup"><span data-stu-id="865e8-147">Constructors are class methods that are executed automatically when an object of a given type is created.</span></span> <span data-ttu-id="865e8-148">일반적으로 새 개체의 데이터 멤버를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-148">Constructors usually initialize the data members of the new object.</span></span> <span data-ttu-id="865e8-149">생성자는 클래스를 만들 때 한 번만 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-149">A constructor can run only once when a class is created.</span></span> <span data-ttu-id="865e8-150">또한 생성자의 코드는 항상 클래스의 다른 코드보다 먼저 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-150">Furthermore, the code in the constructor always runs before any other code in a class.</span></span> <span data-ttu-id="865e8-151">그러나 다른 메서드를 만들 때와 동일한 방법으로 여러 생성자 오버로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-151">However, you can create multiple constructor overloads in the same way as for any other method.</span></span>

<span data-ttu-id="865e8-152">클래스의 생성자를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-152">To define a constructor for a class:</span></span>

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

<span data-ttu-id="865e8-153">자세한 내용은 [생성자](../classes-and-structs/constructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-153">For more information, see [Constructors](../classes-and-structs/constructors.md).</span></span>

#### <a name="finalizers"></a><span data-ttu-id="865e8-154">종료자</span><span class="sxs-lookup"><span data-stu-id="865e8-154">Finalizers</span></span>

<span data-ttu-id="865e8-155">종료자는 클래스의 인스턴스를 소멸하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-155">A finalizer is used to destruct instances of classes.</span></span> <span data-ttu-id="865e8-156">.NET에서는 가비지 수집기가 애플리케이션의 관리형 개체에 대해 메모리 할당 및 해제를 자동으로 관리하지만</span><span class="sxs-lookup"><span data-stu-id="865e8-156">In .NET, the garbage collector automatically manages the allocation and release of memory for the managed objects in your application.</span></span> <span data-ttu-id="865e8-157">애플리케이션이 만드는 관리되지 않는 리소스를 정리하려면 여전히 종료자가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-157">However, you may still need finalizers to clean up any unmanaged resources that your application creates.</span></span> <span data-ttu-id="865e8-158">각 클래스에는 종료자가 하나씩만 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-158">There can be only one finalizer for a class.</span></span>

<span data-ttu-id="865e8-159">.NET의 종료자 및 가비지 수집에 대한 자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-159">For more information about finalizers and garbage collection in .NET, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>

#### <a name="events"></a><span data-ttu-id="865e8-160">이벤트</span><span class="sxs-lookup"><span data-stu-id="865e8-160">Events</span></span>

<span data-ttu-id="865e8-161">클래스나 개체에서는 특정 상황이 발생할 때 이벤트를 통해 다른 클래스나 개체에 이를 알려 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-161">Events enable a class or object to notify other classes or objects when something of interest occurs.</span></span> <span data-ttu-id="865e8-162">이벤트를 보내거나 발생시키는 클래스를 *게시자*라고 하며 이벤트를 받거나 처리하는 클래스를 *구독자*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-162">The class that sends (or raises) the event is called the *publisher* and the classes that receive (or handle) the event are called *subscribers*.</span></span> <span data-ttu-id="865e8-163">이벤트를 발생시키고 처리하는 방법에 대한 자세한 내용은 [이벤트](../../../standard/events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-163">For more information about events, how they are raised and handled, see [Events](../../../standard/events/index.md).</span></span>

- <span data-ttu-id="865e8-164">클래스에서 이벤트를 선언하려면 [event](../../language-reference/keywords/event.md) 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-164">To declare an event in a class, use the [event](../../language-reference/keywords/event.md) keyword.</span></span>
- <span data-ttu-id="865e8-165">이벤트를 발생시키려면 이벤트 대리자를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-165">To raise an event, invoke the event delegate.</span></span>
- <span data-ttu-id="865e8-166">이벤트를 구독하려면 `+=` 연산자를 사용하고 이벤트를 구독 취소하려면 `-=` 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-166">To subscribe to an event, use the `+=` operator; to unsubscribe from an event, use the `-=` operator.</span></span>

#### <a name="nested-classes"></a><span data-ttu-id="865e8-167">중첩 클래스</span><span class="sxs-lookup"><span data-stu-id="865e8-167">Nested classes</span></span>

<span data-ttu-id="865e8-168">다른 클래스 내에 정의된 클래스를 *중첩 클래스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-168">A class defined within another class is called *nested*.</span></span> <span data-ttu-id="865e8-169">기본적으로 중첩 클래스는 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-169">By default, the nested class is private.</span></span>

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

<span data-ttu-id="865e8-170">중첩 클래스의 인스턴스를 만들려면 다음과 같이 컨테이너 클래스의 이름, 점, 중첩 클래스의 이름을 차례로 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-170">To create an instance of the nested class, use the name of the container class followed by the dot and then followed by the name of the nested class:</span></span>

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a><span data-ttu-id="865e8-171">액세스 한정자 및 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="865e8-171">Access modifiers and access levels</span></span>

<span data-ttu-id="865e8-172">모든 클래스 및 클래스 멤버는 *액세스 한정자*를 사용하여 다른 클래스에 제공할 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-172">All classes and class members can specify what access level they provide to other classes by using *access modifiers*.</span></span>

<span data-ttu-id="865e8-173">다음과 같은 액세스 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-173">The following access modifiers are available:</span></span>

| <span data-ttu-id="865e8-174">C# 한정자</span><span class="sxs-lookup"><span data-stu-id="865e8-174">C# Modifier</span></span> | <span data-ttu-id="865e8-175">정의</span><span class="sxs-lookup"><span data-stu-id="865e8-175">Definition</span></span> |
|--|--|
| [<span data-ttu-id="865e8-176">public</span><span class="sxs-lookup"><span data-stu-id="865e8-176">public</span></span>](../../language-reference/keywords/public.md) | <span data-ttu-id="865e8-177">동일한 어셈블리의 다른 코드나 해당 어셈블리를 참조하는 다른 어셈블리의 코드에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-177">The type or member can be accessed by any other code in the same assembly or another assembly that references it.</span></span> |
| [<span data-ttu-id="865e8-178">private</span><span class="sxs-lookup"><span data-stu-id="865e8-178">private</span></span>](../../language-reference/keywords/private.md) | <span data-ttu-id="865e8-179">동일한 클래스의 코드에서만 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-179">The type or member can only be accessed by code in the same class.</span></span> |
| [<span data-ttu-id="865e8-180">protected</span><span class="sxs-lookup"><span data-stu-id="865e8-180">protected</span></span>](../../language-reference/keywords/protected.md) | <span data-ttu-id="865e8-181">동일한 클래스의 코드나 파생 클래스의 코드에서만 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-181">The type or member can only be accessed by code in the same class or in a derived class.</span></span> |
| [<span data-ttu-id="865e8-182">internal</span><span class="sxs-lookup"><span data-stu-id="865e8-182">internal</span></span>](../../language-reference/keywords/internal.md) | <span data-ttu-id="865e8-183">동일한 어셈블리의 코드에서는 형식이나 멤버에 액세스할 수 있지만 다른 어셈블리의 코드에서는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-183">The type or member can be accessed by any code in the same assembly, but not from another assembly.</span></span> |
| [<span data-ttu-id="865e8-184">protected internal</span><span class="sxs-lookup"><span data-stu-id="865e8-184">protected internal</span></span>](../../language-reference/keywords/protected-internal.md) | <span data-ttu-id="865e8-185">동일한 어셈블리의 코드 또는 다른 어셈블리의 파생 클래스에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-185">The type or member can be accessed by any code in the same assembly, or by any derived class in another assembly.</span></span> |
| [<span data-ttu-id="865e8-186">private protected</span><span class="sxs-lookup"><span data-stu-id="865e8-186">private protected</span></span>](../../language-reference/keywords/private-protected.md) | <span data-ttu-id="865e8-187">기본 클래스 어셈블리 내 동일한 클래스 또는 파생 클래스의 코드에서 형식이나 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-187">The type or member can be accessed by code in the same class or in a derived class within the base class assembly.</span></span> |

<span data-ttu-id="865e8-188">자세한 내용은 [액세스 한정자](../classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-188">For more information, see [Access Modifiers](../classes-and-structs/access-modifiers.md).</span></span>

### <a name="instantiating-classes"></a><span data-ttu-id="865e8-189">클래스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="865e8-189">Instantiating classes</span></span>

<span data-ttu-id="865e8-190">개체를 만들려면 클래스를 인스턴스화하거나 클래스 인스턴스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-190">To create an object, you need to instantiate a class, or create a class instance.</span></span>

```csharp
SampleClass sampleObject = new SampleClass();
```

<span data-ttu-id="865e8-191">클래스를 인스턴스화한 후에는 인스턴스의 속성과 필드에 값을 할당하고 클래스 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-191">After instantiating a class, you can assign values to the instance's properties and fields and invoke class methods.</span></span>

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.SampleMethod();
```

<span data-ttu-id="865e8-192">클래스를 인스턴스화하는 동안 속성에 값을 할당하려면 다음과 같이 개체 이니셜라이저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-192">To assign values to properties during the class instantiation process, use object initializers:</span></span>

```csharp
// Set a property value.
var sampleObject = new SampleClass
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="865e8-193">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-193">For more information, see:</span></span>

- [<span data-ttu-id="865e8-194">new 연산자</span><span class="sxs-lookup"><span data-stu-id="865e8-194">new Operator</span></span>](../../language-reference/operators/new-operator.md)
- [<span data-ttu-id="865e8-195">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="865e8-195">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a><span data-ttu-id="865e8-196">정적 클래스 및 멤버</span><span class="sxs-lookup"><span data-stu-id="865e8-196">Static Classes and Members</span></span>

<span data-ttu-id="865e8-197">클래스의 정적 멤버는 클래스의 모든 인스턴스에서 공유하는 속성, 프로시저 또는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-197">A static member of the class is a property, procedure, or field that is shared by all instances of a class.</span></span>

<span data-ttu-id="865e8-198">정적 멤버를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-198">To define a static member:</span></span>

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

<span data-ttu-id="865e8-199">정적 멤버에 액세스하려면 다음과 같이 이 클래스의 개체를 만들지 않고 클래스 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-199">To access the static member, use the name of the class without creating an object of this class:</span></span>

```csharp
Console.WriteLine(SampleClass.SampleString);
```

<span data-ttu-id="865e8-200">C#의 정적 클래스는 정적 멤버만 포함하며 인스턴스화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-200">Static  classes in C# have static members only and cannot be instantiated.</span></span> <span data-ttu-id="865e8-201">또한 정적 멤버는 비정적 속성, 필드 또는 메서드에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-201">Static members also cannot access non-static  properties, fields or methods</span></span>

<span data-ttu-id="865e8-202">자세한 내용은 [static](../../language-reference/keywords/static.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-202">For more information, see: [static](../../language-reference/keywords/static.md).</span></span>

### <a name="anonymous-types"></a><span data-ttu-id="865e8-203">무명 형식</span><span class="sxs-lookup"><span data-stu-id="865e8-203">Anonymous types</span></span>

<span data-ttu-id="865e8-204">익명 형식을 사용하면 데이터 형식에 대한 클래스 정의를 작성하지 않고 개체를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-204">Anonymous types enable you to create objects without writing a class definition for the data type.</span></span> <span data-ttu-id="865e8-205">대신 컴파일러가 클래스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-205">Instead, the compiler generates a class for you.</span></span> <span data-ttu-id="865e8-206">이 클래스는 사용할 수 있는 이름이 없고 개체를 선언할 때 지정하는 속성을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-206">The class has no usable name and contains the properties you specify in declaring the object.</span></span>

<span data-ttu-id="865e8-207">익명 형식의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="865e8-207">To create an instance of an anonymous type:</span></span>

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject = new
{
    FirstProperty = "A",
    SecondProperty = "B"
};
```

<span data-ttu-id="865e8-208">자세한 내용은 다음을 참조하세요. [익명 형식](../classes-and-structs/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-208">For more information, see: [Anonymous Types](../classes-and-structs/anonymous-types.md).</span></span>

## <a name="inheritance"></a><span data-ttu-id="865e8-209">상속</span><span class="sxs-lookup"><span data-stu-id="865e8-209">Inheritance</span></span>

<span data-ttu-id="865e8-210">상속을 사용하면 다른 클래스에 정의된 동작을 다시 사용, 확장 및 수정하는 새 클래스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-210">Inheritance enables you to create a new class that reuses, extends, and modifies the behavior that is defined in another class.</span></span> <span data-ttu-id="865e8-211">멤버가 상속되는 클래스를 *기본 클래스*라고 하고 해당 멤버를 상속하는 클래스를 *파생 클래스*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-211">The class whose members are inherited is called the *base class*, and the class that inherits those members is called the *derived class*.</span></span> <span data-ttu-id="865e8-212">그러나 C#의 모든 클래스는 .NET 클래스 계층 구조를 지원하고 모든 클래스에 하위 수준 서비스를 제공하는 <xref:System.Object> 클래스에서 암시적으로 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-212">However, all classes in C# implicitly inherit from the <xref:System.Object> class that supports .NET class hierarchy and provides low-level services to all classes.</span></span>

> [!NOTE]
> <span data-ttu-id="865e8-213">C#은 다중 상속을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-213">C# doesn't support multiple inheritance.</span></span> <span data-ttu-id="865e8-214">즉, 파생된 클래스에 대해 하나의 기본 클래스만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-214">That is, you can specify only one base class for a derived class.</span></span>

<span data-ttu-id="865e8-215">기본 클래스에서 상속하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-215">To inherit from a base class:</span></span>

```csharp
class DerivedClass:BaseClass { }
```

<span data-ttu-id="865e8-216">기본적으로 모든 클래스는 상속될 수 있지만</span><span class="sxs-lookup"><span data-stu-id="865e8-216">By default all classes can be inherited.</span></span> <span data-ttu-id="865e8-217">클래스가 기본 클래스로 사용되지 않아야 하는지 여부를 지정하거나 기본 클래스로만 사용될 수 있는 클래스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-217">However, you can specify whether a class must not be used as a base class, or create a class that can be used as a base class only.</span></span>

<span data-ttu-id="865e8-218">클래스가 기본 클래스로 사용될 수 없도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-218">To specify that a class cannot be used as a base class:</span></span>

```csharp
public sealed class A { }
```

<span data-ttu-id="865e8-219">클래스가 기본 클래스로만 사용되고 인스턴스화되지 않도록 지정하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-219">To specify that a class can be used as a base class only and cannot be instantiated:</span></span>

```csharp
public abstract class B { }
```

<span data-ttu-id="865e8-220">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-220">For more information, see:</span></span>

- [<span data-ttu-id="865e8-221">sealed</span><span class="sxs-lookup"><span data-stu-id="865e8-221">sealed</span></span>](../../language-reference/keywords/sealed.md)
- [<span data-ttu-id="865e8-222">abstract</span><span class="sxs-lookup"><span data-stu-id="865e8-222">abstract</span></span>](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a><span data-ttu-id="865e8-223">멤버 재정의</span><span class="sxs-lookup"><span data-stu-id="865e8-223">Overriding Members</span></span>

<span data-ttu-id="865e8-224">기본적으로 파생 클래스는 해당 기본 클래스에서 모든 멤버를 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-224">By default, a derived class inherits all members from its base class.</span></span> <span data-ttu-id="865e8-225">상속된 멤버의 동작을 변경하려면 해당 멤버를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-225">If you want to change the behavior of the inherited member, you need to override it.</span></span> <span data-ttu-id="865e8-226">즉, 파생 클래스에 해당 메서드, 속성 또는 이벤트의 새로운 구현을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-226">That is, you can define a new implementation of the method, property or event in the derived class.</span></span>

<span data-ttu-id="865e8-227">다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-227">The following modifiers are used to control how properties and methods are overridden:</span></span>

| <span data-ttu-id="865e8-228">C# 한정자</span><span class="sxs-lookup"><span data-stu-id="865e8-228">C# Modifier</span></span> | <span data-ttu-id="865e8-229">정의</span><span class="sxs-lookup"><span data-stu-id="865e8-229">Definition</span></span> |
|--|--|
| [<span data-ttu-id="865e8-230">virtual</span><span class="sxs-lookup"><span data-stu-id="865e8-230">virtual</span></span>](../../language-reference/keywords/virtual.md) | <span data-ttu-id="865e8-231">파생 클래스에서 클래스 멤버를 재정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-231">Allows a class member to be overridden in a derived class.</span></span> |
| [<span data-ttu-id="865e8-232">override</span><span class="sxs-lookup"><span data-stu-id="865e8-232">override</span></span>](../../language-reference/keywords/override.md) | <span data-ttu-id="865e8-233">기본 클래스에 정의된 가상(재정의 가능) 멤버를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-233">Overrides a virtual (overridable) member defined in the base class.</span></span> |
| [<span data-ttu-id="865e8-234">abstract</span><span class="sxs-lookup"><span data-stu-id="865e8-234">abstract</span></span>](../../language-reference/keywords/abstract.md) | <span data-ttu-id="865e8-235">파생 클래스에서 클래스 멤버가 재정의되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-235">Requires that a class member to be overridden in the derived class.</span></span> |
| [<span data-ttu-id="865e8-236">new 한정자</span><span class="sxs-lookup"><span data-stu-id="865e8-236">new Modifier</span></span>](../../language-reference/keywords/new-modifier.md) | <span data-ttu-id="865e8-237">기본 클래스에서 상속된 멤버를 숨깁니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-237">Hides a member inherited from a base class</span></span> |

## <a name="interfaces"></a><span data-ttu-id="865e8-238">인터페이스</span><span class="sxs-lookup"><span data-stu-id="865e8-238">Interfaces</span></span>

<span data-ttu-id="865e8-239">인터페이스는 클래스와 마찬가지로 속성, 메서드 및 이벤트를 정의하지만</span><span class="sxs-lookup"><span data-stu-id="865e8-239">Interfaces, like classes, define a set of properties, methods, and events.</span></span> <span data-ttu-id="865e8-240">클래스와는 달리 구현을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-240">But unlike classes, interfaces do not provide implementation.</span></span> <span data-ttu-id="865e8-241">인터페이스는 클래스에 의해 구현되며 클래스와는 별개의 엔터티로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-241">They are implemented by classes, and defined as separate entities from classes.</span></span> <span data-ttu-id="865e8-242">인터페이스는 계약을 나타내므로 인터페이스를 구현하는 클래스에서는 해당 인터페이스의 모든 부분을 정의된 그대로 정확하게 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-242">An interface represents a contract, in that a class that implements an interface must implement every aspect of that interface exactly as it is defined.</span></span>

<span data-ttu-id="865e8-243">인터페이스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-243">To define an interface:</span></span>

```csharp
interface ISampleInterface
{
    void DoSomething();
}
```

<span data-ttu-id="865e8-244">클래스에서 인터페이스를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-244">To implement an interface in a class:</span></span>

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.DoSomething()
    {
        // Method implementation.
    }
}
```

<span data-ttu-id="865e8-245">자세한 내용은 [인터페이스](../interfaces/index.md)에 관한 프로그래밍 가이드 문서와 [interface](../../language-reference/keywords/interface.md) 키워드에 관한 언어 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-245">For more information, see the programming guide article on [Interfaces](../interfaces/index.md) and the language reference article on the [interface](../../language-reference/keywords/interface.md) keyword.</span></span>

## <a name="generics"></a><span data-ttu-id="865e8-246">제네릭</span><span class="sxs-lookup"><span data-stu-id="865e8-246">Generics</span></span>

<span data-ttu-id="865e8-247">.NET의 클래스, 구조체, 인터페이스 및 메서드는 저장하거나 사용할 수 있는 개체의 형식을 정의하는 ‘형식 매개 변수’를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-247">Classes, structures, interfaces, and methods in .NET can include *type parameters* that define types of objects that they can store or use.</span></span> <span data-ttu-id="865e8-248">제네릭의 가장 일반적인 예는 컬렉션에 저장할 개체의 형식을 지정할 수 있는 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-248">The most common example of generics is a collection, where you can specify the type of objects to be stored in a collection.</span></span>

<span data-ttu-id="865e8-249">제네릭 클래스를 정의하려면</span><span class="sxs-lookup"><span data-stu-id="865e8-249">To define a generic class:</span></span>

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

<span data-ttu-id="865e8-250">제네릭 클래스의 인스턴스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="865e8-250">To create an instance of a generic class:</span></span>

```csharp
var sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

<span data-ttu-id="865e8-251">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-251">For more information, see:</span></span>

- [<span data-ttu-id="865e8-252">.NET의 제네릭</span><span class="sxs-lookup"><span data-stu-id="865e8-252">Generics in .NET</span></span>](../../../standard/generics/index.md)
- [<span data-ttu-id="865e8-253">제네릭 - C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="865e8-253">Generics - C# Programming Guide</span></span>](../generics/index.md)

## <a name="delegates"></a><span data-ttu-id="865e8-254">대리자</span><span class="sxs-lookup"><span data-stu-id="865e8-254">Delegates</span></span>

<span data-ttu-id="865e8-255">*대리자*는 메서드 시그니처를 정의하는 형식으로, 호환되는 시그니처가 있는 모든 메서드에 대한 참조를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-255">A *delegate* is a type that defines a method signature, and can provide a reference to any method with a compatible signature.</span></span> <span data-ttu-id="865e8-256">대리자를 통해 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-256">You can invoke (or call) the method through the delegate.</span></span> <span data-ttu-id="865e8-257">대리자는 메서드를 다른 메서드에 인수로 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-257">Delegates are used to pass methods as arguments to other methods.</span></span>

> [!NOTE]
> <span data-ttu-id="865e8-258">이벤트 처리기는 대리자를 통해 호출되는 메서드라고 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="865e8-258">Event handlers are nothing more than methods that are invoked through delegates.</span></span> <span data-ttu-id="865e8-259">이벤트를 처리할 때 대리자를 사용하는 방법에 대한 자세한 내용은 [이벤트](../../../standard/events/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-259">For more information about using delegates in event handling, see [Events](../../../standard/events/index.md).</span></span>

<span data-ttu-id="865e8-260">대리자를 만들려면</span><span class="sxs-lookup"><span data-stu-id="865e8-260">To create a delegate:</span></span>

```csharp
public delegate void SampleDelegate(string str);
```

<span data-ttu-id="865e8-261">대리자가 지정한 시그니처와 일치하는 메서드에 대한 참조를 만들려면</span><span class="sxs-lookup"><span data-stu-id="865e8-261">To create a reference to a method that matches the signature specified by the delegate:</span></span>

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void SampleMethod(string message)
    {
        // Add code here.
    }

    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

<span data-ttu-id="865e8-262">자세한 내용은 [대리자](../delegates/index.md)에 관한 프로그래밍 가이드 문서와 [delegate](../../language-reference/builtin-types/reference-types.md) 키워드에 관한 언어 참조 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="865e8-262">For more information, see the programming guide article on [Delegates](../delegates/index.md) and the language reference article on the [delegate](../../language-reference/builtin-types/reference-types.md) keyword.</span></span>

## <a name="see-also"></a><span data-ttu-id="865e8-263">참조</span><span class="sxs-lookup"><span data-stu-id="865e8-263">See also</span></span>

- [<span data-ttu-id="865e8-264">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="865e8-264">C# Programming Guide</span></span>](../index.md)
