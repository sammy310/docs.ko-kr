---
title: C#의 컬렉션 반복
description: 반복기를 사용하여 목록 및 배열과 같은 컬렉션을 단계별로 실행하는 방법에 대해 알아봅니다. 반복기는 foreach 문 또는 LINQ 쿼리를 사용하여 클라이언트 코드에서 사용됩니다.
ms.date: 08/14/2018
ms.assetid: c93f6dd4-e72a-4a06-be1c-a98b3255b734
ms.openlocfilehash: 310fff68a242812620357517c212ddd5f053775c
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104257"
---
# <a name="iterators-c"></a><span data-ttu-id="78ecb-104">반복기(C#)</span><span class="sxs-lookup"><span data-stu-id="78ecb-104">Iterators (C#)</span></span>

<span data-ttu-id="78ecb-105">*반복기*는 목록 및 배열과 같은 컬렉션을 단계별로 실행하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-105">An *iterator* can be used to step through collections such as lists and arrays.</span></span>

<span data-ttu-id="78ecb-106">반복기 메서드 또는 `get` 접근자는 컬렉션에 대해 사용자 지정 반복을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-106">An iterator method or `get` accessor performs a custom iteration over a collection.</span></span> <span data-ttu-id="78ecb-107">반복기 메서드는 [yield return](../../language-reference/keywords/yield.md) 문을 사용하여 각 요소를 한 번에 하나씩 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-107">An iterator method uses the [yield return](../../language-reference/keywords/yield.md) statement to return each element one at a time.</span></span> <span data-ttu-id="78ecb-108">`yield return` 문에 도달하면 코드의 현재 위치가 기억됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-108">When a `yield return` statement is reached, the current location in code is remembered.</span></span> <span data-ttu-id="78ecb-109">다음에 반복기 함수가 호출되면 해당 위치에서 실행이 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-109">Execution is restarted from that location the next time the iterator function is called.</span></span>

<span data-ttu-id="78ecb-110">클라이언트 코드에서 [foreach](../../language-reference/keywords/foreach-in.md) 문 또는 LINQ 쿼리를 사용하여 반복기를 이용합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-110">You consume an iterator from client code by using a [foreach](../../language-reference/keywords/foreach-in.md) statement or by using a LINQ query.</span></span>

<span data-ttu-id="78ecb-111">다음 예제에서 `foreach` 루프의 첫 번째 반복은 첫 번째 `yield return` 문에 도달할 때까지 `SomeNumbers` 반복기 메서드에서 실행이 계속되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-111">In the following example, the first iteration of the `foreach` loop causes execution to proceed in the `SomeNumbers` iterator method until the first `yield return` statement is reached.</span></span> <span data-ttu-id="78ecb-112">이 반복은 3 값을 반환하며 반복기 메서드에서 현재 위치는 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-112">This iteration returns a value of 3, and the current location in the iterator method is retained.</span></span> <span data-ttu-id="78ecb-113">루프의 다음 반복에서는 반복기 메서드의 실행이 중지되었던 위치에서 계속되고 `yield return` 문에 도달하면 다시 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-113">On the next iteration of the loop, execution in the iterator method continues from where it left off, again stopping when it reaches a `yield return` statement.</span></span> <span data-ttu-id="78ecb-114">이 반복은 값 5를 반환하며 반복기 메서드에서 현재 위치는 다시 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-114">This iteration returns a value of 5, and the current location in the iterator method is again retained.</span></span> <span data-ttu-id="78ecb-115">루프는 반복기 메서드의 끝에 도달하면 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-115">The loop completes when the end of the iterator method is reached.</span></span>

```csharp
static void Main()
{
    foreach (int number in SomeNumbers())
    {
        Console.Write(number.ToString() + " ");
    }
    // Output: 3 5 8
    Console.ReadKey();
}

public static System.Collections.IEnumerable SomeNumbers()
{
    yield return 3;
    yield return 5;
    yield return 8;
}
```

<span data-ttu-id="78ecb-116">반복기 메서드 또는 `get` 접근자의 반환 형식은 <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> 또는 <xref:System.Collections.Generic.IEnumerator%601>일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-116">The return type of an iterator method or `get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.</span></span>

<span data-ttu-id="78ecb-117">`yield break` 문을 사용하여 반복기를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-117">You can use a `yield break` statement to end the iteration.</span></span>

> [!NOTE]
> <span data-ttu-id="78ecb-118">단순 반복기 예제를 제외한 이 항목의 모든 예제에 대해 `System.Collections` 및 `System.Collections.Generic` 네임스페이스에 대한 [using](../../language-reference/keywords/using-directive.md) 지시문을 포함하세요.</span><span class="sxs-lookup"><span data-stu-id="78ecb-118">For all examples in this topic except the Simple Iterator example, include [using](../../language-reference/keywords/using-directive.md) directives for the `System.Collections` and `System.Collections.Generic` namespaces.</span></span>

## <a name="simple-iterator"></a><span data-ttu-id="78ecb-119">단순 반복기</span><span class="sxs-lookup"><span data-stu-id="78ecb-119">Simple Iterator</span></span>

<span data-ttu-id="78ecb-120">다음 예제에는 [for](../../language-reference/keywords/for.md) 루프 내에 단일 `yield return` 문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-120">The following example has a single `yield return` statement that is inside a [for](../../language-reference/keywords/for.md) loop.</span></span> <span data-ttu-id="78ecb-121">`Main`에서 `foreach` 문 본문을 반복할 때마다 다음 `yield return` 문으로 진행하는 반복기 함수에 대한 호출이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-121">In `Main`, each iteration of the `foreach` statement body creates a call to the iterator function, which proceeds to the next `yield return` statement.</span></span>

```csharp
static void Main()
{
    foreach (int number in EvenSequence(5, 18))
    {
        Console.Write(number.ToString() + " ");
    }
    // Output: 6 8 10 12 14 16 18
    Console.ReadKey();
}

public static System.Collections.Generic.IEnumerable<int>
    EvenSequence(int firstNumber, int lastNumber)
{
    // Yield even numbers in the range.
    for (int number = firstNumber; number <= lastNumber; number++)
    {
        if (number % 2 == 0)
        {
            yield return number;
        }
    }
}
```

## <a name="creating-a-collection-class"></a><span data-ttu-id="78ecb-122">컬렉션 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="78ecb-122">Creating a Collection Class</span></span>

<span data-ttu-id="78ecb-123">다음 예제에서 `DaysOfTheWeek` 클래스는 <xref:System.Collections.IEnumerable> 인터페이스를 구현하며, <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-123">In the following example, the `DaysOfTheWeek` class implements the <xref:System.Collections.IEnumerable> interface, which requires a <xref:System.Collections.IEnumerable.GetEnumerator%2A> method.</span></span> <span data-ttu-id="78ecb-124">컴파일러는 `GetEnumerator` 메서드를 암시적으로 호출하며, <xref:System.Collections.IEnumerator>가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-124">The compiler implicitly calls the `GetEnumerator` method, which returns an <xref:System.Collections.IEnumerator>.</span></span>

<span data-ttu-id="78ecb-125">`GetEnumerator` 메서드는 `yield return` 문을 사용하여 각 문자열을 한 번에 하나씩 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-125">The `GetEnumerator` method returns each string one at a time by using the `yield return` statement.</span></span>

```csharp
static void Main()
{
    DaysOfTheWeek days = new DaysOfTheWeek();

    foreach (string day in days)
    {
        Console.Write(day + " ");
    }
    // Output: Sun Mon Tue Wed Thu Fri Sat
    Console.ReadKey();
}

public class DaysOfTheWeek : IEnumerable
{
    private string[] days = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };

    public IEnumerator GetEnumerator()
    {
        for (int index = 0; index < days.Length; index++)
        {
            // Yield each day of the week.
            yield return days[index];
        }
    }
}
```

<span data-ttu-id="78ecb-126">다음 예제에서는 동물 컬렉션을 포함하는 `Zoo` 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-126">The following example creates a `Zoo` class that contains a collection of animals.</span></span>

<span data-ttu-id="78ecb-127">클래스 인스턴스(`theZoo`)를 참조하는 `foreach` 문은 `GetEnumerator` 메서드를 암시적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-127">The `foreach` statement that refers to the class instance (`theZoo`) implicitly calls the `GetEnumerator` method.</span></span> <span data-ttu-id="78ecb-128">`Birds` 및 `Mammals` 속성을 참조하는 `foreach` 문은 `AnimalsForType` 명명된 반복기 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-128">The `foreach` statements that refer to the `Birds` and `Mammals` properties use the `AnimalsForType` named iterator method.</span></span>

```csharp
static void Main()
{
    Zoo theZoo = new Zoo();

    theZoo.AddMammal("Whale");
    theZoo.AddMammal("Rhinoceros");
    theZoo.AddBird("Penguin");
    theZoo.AddBird("Warbler");

    foreach (string name in theZoo)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Whale Rhinoceros Penguin Warbler

    foreach (string name in theZoo.Birds)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Penguin Warbler

    foreach (string name in theZoo.Mammals)
    {
        Console.Write(name + " ");
    }
    Console.WriteLine();
    // Output: Whale Rhinoceros

    Console.ReadKey();
}

public class Zoo : IEnumerable
{
    // Private members.
    private List<Animal> animals = new List<Animal>();

    // Public methods.
    public void AddMammal(string name)
    {
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Mammal });
    }

    public void AddBird(string name)
    {
        animals.Add(new Animal { Name = name, Type = Animal.TypeEnum.Bird });
    }

    public IEnumerator GetEnumerator()
    {
        foreach (Animal theAnimal in animals)
        {
            yield return theAnimal.Name;
        }
    }

    // Public members.
    public IEnumerable Mammals
    {
        get { return AnimalsForType(Animal.TypeEnum.Mammal); }
    }

    public IEnumerable Birds
    {
        get { return AnimalsForType(Animal.TypeEnum.Bird); }
    }

    // Private methods.
    private IEnumerable AnimalsForType(Animal.TypeEnum type)
    {
        foreach (Animal theAnimal in animals)
        {
            if (theAnimal.Type == type)
            {
                yield return theAnimal.Name;
            }
        }
    }

    // Private class.
    private class Animal
    {
        public enum TypeEnum { Bird, Mammal }

        public string Name { get; set; }
        public TypeEnum Type { get; set; }
    }
}
```

## <a name="using-iterators-with-a-generic-list"></a><span data-ttu-id="78ecb-129">제네릭 목록과 함께 반복기 사용</span><span class="sxs-lookup"><span data-stu-id="78ecb-129">Using Iterators with a Generic List</span></span>

<span data-ttu-id="78ecb-130">다음 예제에서 <xref:System.Collections.Generic.Stack%601> 제네릭 클래스는 <xref:System.Collections.Generic.IEnumerable%601> 제네릭 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-130">In the following example, the <xref:System.Collections.Generic.Stack%601> generic class implements the <xref:System.Collections.Generic.IEnumerable%601> generic interface.</span></span> <span data-ttu-id="78ecb-131"><xref:System.Collections.Generic.Stack%601.Push%2A> 메서드는 `T` 형식의 배열에 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-131">The <xref:System.Collections.Generic.Stack%601.Push%2A> method assigns values to an array of type `T`.</span></span> <span data-ttu-id="78ecb-132"><xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 메서드는 `yield return` 문을 사용하여 배열 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-132">The <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method returns the array values by using the `yield return` statement.</span></span>

<span data-ttu-id="78ecb-133">제네릭 <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> 메서드뿐 아니라 제네릭이 아닌 <xref:System.Collections.IEnumerable.GetEnumerator%2A> 메서드도 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-133">In addition to the generic <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> method, the non-generic <xref:System.Collections.IEnumerable.GetEnumerator%2A> method must also be implemented.</span></span> <span data-ttu-id="78ecb-134"><xref:System.Collections.Generic.IEnumerable%601>이 <xref:System.Collections.IEnumerable>에서 상속하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-134">This is because <xref:System.Collections.Generic.IEnumerable%601> inherits from <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="78ecb-135">제네릭이 아닌 구현은 제네릭 구현을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-135">The non-generic implementation defers to the generic implementation.</span></span>

<span data-ttu-id="78ecb-136">예제에서는 명명된 반복기를 사용하여 동일한 데이터 컬렉션을 반복하는 다양한 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-136">The example uses named iterators to support various ways of iterating through the same collection of data.</span></span> <span data-ttu-id="78ecb-137">이러한 명명된 반복기는 `TopToBottom` 및 `BottomToTop` 속성과 `TopN` 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-137">These named iterators are the `TopToBottom` and `BottomToTop` properties, and the `TopN` method.</span></span>

<span data-ttu-id="78ecb-138">`BottomToTop` 속성은 `get` 접근자에서 반복기를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-138">The `BottomToTop` property uses an iterator in a `get` accessor.</span></span>

```csharp
static void Main()
{
    Stack<int> theStack = new Stack<int>();

    //  Add items to the stack.
    for (int number = 0; number <= 9; number++)
    {
        theStack.Push(number);
    }

    // Retrieve items from the stack.
    // foreach is allowed because theStack implements IEnumerable<int>.
    foreach (int number in theStack)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3 2 1 0

    // foreach is allowed, because theStack.TopToBottom returns IEnumerable(Of Integer).
    foreach (int number in theStack.TopToBottom)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3 2 1 0

    foreach (int number in theStack.BottomToTop)
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 0 1 2 3 4 5 6 7 8 9

    foreach (int number in theStack.TopN(7))
    {
        Console.Write("{0} ", number);
    }
    Console.WriteLine();
    // Output: 9 8 7 6 5 4 3

    Console.ReadKey();
}

public class Stack<T> : IEnumerable<T>
{
    private T[] values = new T[100];
    private int top = 0;

    public void Push(T t)
    {
        values[top] = t;
        top++;
    }
    public T Pop()
    {
        top--;
        return values[top];
    }

    // This method implements the GetEnumerator method. It allows
    // an instance of the class to be used in a foreach statement.
    public IEnumerator<T> GetEnumerator()
    {
        for (int index = top - 1; index >= 0; index--)
        {
            yield return values[index];
        }
    }

    IEnumerator IEnumerable.GetEnumerator()
    {
        return GetEnumerator();
    }

    public IEnumerable<T> TopToBottom
    {
        get { return this; }
    }

    public IEnumerable<T> BottomToTop
    {
        get
        {
            for (int index = 0; index <= top - 1; index++)
            {
                yield return values[index];
            }
        }
    }

    public IEnumerable<T> TopN(int itemsFromTop)
    {
        // Return less than itemsFromTop if necessary.
        int startIndex = itemsFromTop >= top ? 0 : top - itemsFromTop;

        for (int index = top - 1; index >= startIndex; index--)
        {
            yield return values[index];
        }
    }

}
```

## <a name="syntax-information"></a><span data-ttu-id="78ecb-139">구문 정보</span><span class="sxs-lookup"><span data-stu-id="78ecb-139">Syntax Information</span></span>

<span data-ttu-id="78ecb-140">반복기는 메서드 또는 `get` 접근자로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-140">An iterator can occur as a method or `get` accessor.</span></span> <span data-ttu-id="78ecb-141">이벤트, 인스턴스 생성자, 정적 생성자 또는 정적 종료자에서는 반복기가 발생할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-141">An iterator cannot occur in an event, instance constructor, static constructor, or static finalizer.</span></span>

<span data-ttu-id="78ecb-142">반복기에서 반환된 `IEnumerable<T>`의 형식 인수에 대한 `yield return` 문의 식 형식에는 암시적 변환이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-142">An implicit conversion must exist from the expression type in the `yield return` statement to the type argument for the `IEnumerable<T>` returned by the iterator.</span></span>

<span data-ttu-id="78ecb-143">C#에서 반복기 메서드는 `in`, `ref` 또는 `out` 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-143">In C#, an iterator method cannot have any `in`, `ref`, or `out` parameters.</span></span>

<span data-ttu-id="78ecb-144">C#에서 `yield`는 예약어가 아니며 `return` 또는 `break` 키워드 앞에서 사용되는 경우에만 특별한 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-144">In C#, `yield` is not a reserved word and has special meaning only when it is used before a `return` or `break` keyword.</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="78ecb-145">기술 구현</span><span class="sxs-lookup"><span data-stu-id="78ecb-145">Technical Implementation</span></span>

<span data-ttu-id="78ecb-146">반복기를 메서드로 작성하는 경우에도 컴파일러는 실제로 상태 시스템인 중첩 클래스로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-146">Although you write an iterator as a method, the compiler translates it into a nested class that is, in effect, a state machine.</span></span> <span data-ttu-id="78ecb-147">이 클래스는 클라이언트 코드의 `foreach` 루프가 계속되는 한 반복기의 위치를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-147">This class keeps track of the position of the iterator as long the `foreach` loop in the client code continues.</span></span>

<span data-ttu-id="78ecb-148">컴파일러의 용도를 확인하려면 Ildasm.exe 도구를 사용하여 반복기 메서드에 대해 생성되는 Microsoft Intermediate Language 코드를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-148">To see what the compiler does, you can use the Ildasm.exe tool to view the Microsoft intermediate language code that's generated for an iterator method.</span></span>

<span data-ttu-id="78ecb-149">[class](../../language-reference/keywords/class.md) 또는 [struct](../../language-reference/builtin-types/struct.md)에 대해 반복기를 만드는 경우 전체 <xref:System.Collections.IEnumerator> 인터페이스를 구현할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-149">When you create an iterator for a [class](../../language-reference/keywords/class.md) or [struct](../../language-reference/builtin-types/struct.md), you don't have to implement the whole <xref:System.Collections.IEnumerator> interface.</span></span> <span data-ttu-id="78ecb-150">컴파일러는 반복기를 검색할 경우 <xref:System.Collections.IEnumerator> 또는 <xref:System.Collections.Generic.IEnumerator%601> 인터페이스의 `Current`, `MoveNext` 및 `Dispose` 메서드를 자동으로 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-150">When the compiler detects the iterator, it automatically generates the `Current`, `MoveNext`, and `Dispose` methods of the <xref:System.Collections.IEnumerator> or <xref:System.Collections.Generic.IEnumerator%601> interface.</span></span>

<span data-ttu-id="78ecb-151">`foreach` 루프를 연속 반복하거나 `IEnumerator.MoveNext`를 직접 호출하면 다음 반복기 코드 본문이 이전 `yield return` 문 다음에 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-151">On each successive iteration of the `foreach` loop (or the direct call to `IEnumerator.MoveNext`), the next iterator code body resumes after the previous `yield return` statement.</span></span> <span data-ttu-id="78ecb-152">그런 후 반복기 본문의 끝에 도달하거나 `yield break` 문이 나타날 때까지 다음 `yield return` 문을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-152">It then continues to the next `yield return` statement until the end of the iterator body is reached, or until a `yield break` statement is encountered.</span></span>

<span data-ttu-id="78ecb-153">반복기는 <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> 메서드를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-153">Iterators don't support the <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="78ecb-154">처음부터 다시 반복하려면 새 반복기를 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-154">To reiterate from the start, you must obtain a new iterator.</span></span> <span data-ttu-id="78ecb-155">반복기 메서드에 의해 반환된 반복기에서 <xref:System.Collections.IEnumerator.Reset%2A>를 호출하면 <xref:System.NotSupportedException>가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-155">Calling <xref:System.Collections.IEnumerator.Reset%2A> on the iterator returned by an iterator method throws a <xref:System.NotSupportedException>.</span></span>

<span data-ttu-id="78ecb-156">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/classes.md#iterators)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78ecb-156">For additional information, see the [C# Language Specification](~/_csharplang/spec/classes.md#iterators).</span></span>

## <a name="use-of-iterators"></a><span data-ttu-id="78ecb-157">반복기 사용</span><span class="sxs-lookup"><span data-stu-id="78ecb-157">Use of Iterators</span></span>

<span data-ttu-id="78ecb-158">반복기를 사용하면 복잡한 코드를 사용하여 목록 시퀀스를 채워야 하는 경우 `foreach` 루프의 단순성을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-158">Iterators enable you to maintain the simplicity of a `foreach` loop when you need to use complex code to populate a list sequence.</span></span> <span data-ttu-id="78ecb-159">이 기능은 다음을 수행하려는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-159">This can be useful when you want to do the following:</span></span>

- <span data-ttu-id="78ecb-160">첫 번째 `foreach` 루프 반복 후 목록 시퀀스를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-160">Modify the list sequence after the first `foreach` loop iteration.</span></span>

- <span data-ttu-id="78ecb-161">첫 번째 `foreach` 루프 반복 전에 큰 목록이 완전히 로드되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-161">Avoid fully loading a large list before the first iteration of a `foreach` loop.</span></span> <span data-ttu-id="78ecb-162">한 가지 예로 테이블 행을 일괄 로드하는 페이징 페치가 있으며,</span><span class="sxs-lookup"><span data-stu-id="78ecb-162">An example is a paged fetch to load a batch of table rows.</span></span> <span data-ttu-id="78ecb-163">또 다른 예로 .NET에서 반복기를 구현하는 <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-163">Another example is the <xref:System.IO.DirectoryInfo.EnumerateFiles%2A> method, which implements iterators in .NET.</span></span>

- <span data-ttu-id="78ecb-164">반복기에서 목록 작성을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-164">Encapsulate building the list in the iterator.</span></span> <span data-ttu-id="78ecb-165">반복기 메서드에서 목록을 빌드한 후 루프에서 각 결과를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78ecb-165">In the iterator method, you can build the list and then yield each result in a loop.</span></span>

## <a name="see-also"></a><span data-ttu-id="78ecb-166">참조</span><span class="sxs-lookup"><span data-stu-id="78ecb-166">See also</span></span>

- <xref:System.Collections.Generic>
- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="78ecb-167">foreach, in</span><span class="sxs-lookup"><span data-stu-id="78ecb-167">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="78ecb-168">yield</span><span class="sxs-lookup"><span data-stu-id="78ecb-168">yield</span></span>](../../language-reference/keywords/yield.md)
- [<span data-ttu-id="78ecb-169">배열에 foreach 사용</span><span class="sxs-lookup"><span data-stu-id="78ecb-169">Using foreach with Arrays</span></span>](../arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="78ecb-170">제네릭</span><span class="sxs-lookup"><span data-stu-id="78ecb-170">Generics</span></span>](../generics/index.md)
