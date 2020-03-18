---
title: 개체 및 컬렉션 이니셜라이저 - C# 프로그래밍 가이드
ms.date: 12/19/2018
helpviewer_keywords:
- object initializers [C#]
- collection initializers [C#]
ms.assetid: c58f3db5-d7d4-4651-bd2d-5a3a97357f61
ms.openlocfilehash: ae8741e2f29db0a470ad8d3b121375fbdeaff0d9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79170197"
---
# <a name="object-and-collection-initializers-c-programming-guide"></a><span data-ttu-id="5b824-102">개체 및 컬렉션 이니셜라이저(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="5b824-102">Object and Collection Initializers (C# Programming Guide)</span></span>

<span data-ttu-id="5b824-103">C#을 사용하면 개체 또는 컬렉션을 인스턴스화하고 단일 명령문에서 멤버 할당을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-103">C# lets you instantiate an object or collection and perform member assignments in a single statement.</span></span>

## <a name="object-initializers"></a><span data-ttu-id="5b824-104">개체 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="5b824-104">Object initializers</span></span>

<span data-ttu-id="5b824-105">개체 이니셜라이저를 사용하면 명시적으로 생성자를 호출한 다음 할당문 줄을 추가하지 않고도 생성 시 개체의 모든 액세스 가능한 필드나 속성에 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-105">Object initializers let you assign values to any accessible fields or properties of an object at creation time without having to invoke a constructor followed by lines of assignment statements.</span></span> <span data-ttu-id="5b824-106">개체 이니셜라이저 구문을 사용하면 생성자의 인수를 지정하거나 인수(및 괄호 구문)를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-106">The object initializer syntax enables you to specify arguments for a constructor or omit the arguments (and parentheses syntax).</span></span>  <span data-ttu-id="5b824-107">다음 예제에서는 명명된 형식인 `Cat`로 개체 이니셜라이저를 사용하는 방법과 매개 변수가 없는 생성자를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-107">The following example shows how to use an object initializer with a named type, `Cat` and how to invoke the parameterless constructor.</span></span> <span data-ttu-id="5b824-108">`Cat` 클래스의 자동 구현된 속성 사용을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-108">Note the use of auto-implemented properties in the `Cat` class.</span></span> <span data-ttu-id="5b824-109">자세한 내용은 [자동으로 구현된 속성](auto-implemented-properties.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b824-109">For more information, see [Auto-Implemented Properties](auto-implemented-properties.md).</span></span>  
  
[!code-csharp[ObjectInitializer1](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#CatDeclaration)]  
[!code-csharp[ObjectInitializer1a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ObjectPropertyInitialization)]  

<span data-ttu-id="5b824-110">개체 이니셜라이저 구문을 사용하여 인스턴스를 만들 수 있으며, 만들고 나면 새로 만든 개체와 할당된 해당 속성이 할당의 변수에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-110">The object initializers syntax allows you to create an instance, and after that it assigns the newly created object, with its assigned properties, to the variable in the assignment.</span></span>

<span data-ttu-id="5b824-111">C# 6부터 객체 이니셜라이저는 필드 및 속성을 할당하는 것 외에 인덱서를 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-111">Starting with C# 6, object initializers can set indexers, in addition to assigning fields and properties.</span></span> <span data-ttu-id="5b824-112">기본적인 `Matrix` 클래스를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-112">Consider this basic `Matrix` class:</span></span>

[!code-csharp[ObjectInitializer2](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixDeclaration)]  

<span data-ttu-id="5b824-113">다음 코드를 사용하여 matrix라는 ID를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-113">You could initialize the identity matrix with the following code:</span></span>

[!code-csharp[ObjectInitializer2a](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#MatrixInitialization)]  

<span data-ttu-id="5b824-114">액세스 가능한 setter가 포함된 액세스 가능한 인덱서는 인수의 개수나 형식에 관계없이 객체 이니셜라이저에서 식 중 하나로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-114">Any accessible indexer that contains an accessible setter can be used as one of the expressions in an object initializer, regardless of the number or types of arguments.</span></span> <span data-ttu-id="5b824-115">인덱스 인수는 할당의 왼쪽에 있으며, 값은 식의 오른쪽에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-115">The index arguments form the left side of the assignment, and the value is the right side of the expression.</span></span>  <span data-ttu-id="5b824-116">예를 들어 `IndexersExample`에 적절한 인덱서가 있는 경우 이 모든 것이 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-116">For example, these are all valid if `IndexersExample` has the appropriate indexers:</span></span>

```csharp
var thing = new IndexersExample {
    name = "object one",
    [1] = '1',
    [2] = '4',
    [3] = '9',
    Size = Math.PI,
    ['C',4] = "Middle C"
}
```

<span data-ttu-id="5b824-117">이전 코드를 컴파일하려면 `IndexersExample` 형식에 다음 멤버가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-117">For the preceding code to compile, the `IndexersExample` type must have the following members:</span></span>

```csharp
public string name;
public double Size { set { ... }; }
public char this[int i] { set { ... }; }
public string this[char c, int i] {  set { ... }; }
```

## <a name="object-initializers-with-anonymous-types"></a><span data-ttu-id="5b824-118">익명 형식의 개체 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="5b824-118">Object Initializers with anonymous types</span></span>

<span data-ttu-id="5b824-119">개체 이니셜라이저는 모든 컨텍스트에서 사용할 수 있지만 특히 LINQ 쿼리 식에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-119">Although object initializers can be used in any context, they are especially useful in LINQ query expressions.</span></span> <span data-ttu-id="5b824-120">쿼리 식은 [무명 형식](./anonymous-types.md)을 자주 사용합니다. 이 형식은 다음 선언에 표시된 바와 같이 개체 이니셜라이저를 사용하는 경우에만 초기화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-120">Query expressions make frequent use of [anonymous types](./anonymous-types.md), which can only be initialized by using an object initializer, as shown in the following declaration.</span></span>  

```csharp
var pet = new { Age = 10, Name = "Fluffy" };  
```

<span data-ttu-id="5b824-121">무명 형식을 사용하면 LINQ 쿼리 식의 `select` 절에서 원래 시퀀스의 개체를 값과 모양이 원본과 다를 수 있는 개체로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-121">Anonymous types enable the `select` clause in a LINQ query expression to transform objects of the original sequence into objects whose value and shape may differ from the original.</span></span> <span data-ttu-id="5b824-122">이 기능은 각 개체의 일부 정보만 시퀀스에 저장하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-122">This is useful if you want to store only a part of the information from each object in a sequence.</span></span> <span data-ttu-id="5b824-123">다음 예제에서 제품 개체(`p`)는 많은 필드와 메서드를 포함하며, 제품 이름과 단위 가격이 들어 있는 개체 시퀀스만 만들려 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-123">In the following example, assume that a product object (`p`) contains many fields and methods, and that you are only interested in creating a sequence of objects that contain the product name and the unit price.</span></span>  
  
[!code-csharp[ObjectInitializer3](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#AnonymousUse)]  

<span data-ttu-id="5b824-124">이 쿼리를 실행하면 다음 예제와 같이 `productInfos` 문에서 액세스할 수 있는 개체 시퀀스가 `foreach` 변수에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-124">When this query is executed, the `productInfos` variable will contain a sequence of objects that can be accessed in a `foreach` statement as shown in this example:</span></span>  

```csharp
foreach(var p in productInfos){...}  
```

<span data-ttu-id="5b824-125">새 익명 형식의 각 개체에는 원래 개체의 속성이나 필드와 동일한 이름을 받는 두 개의 public 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-125">Each object in the new anonymous type has two public properties that receive the same names as the properties or fields in the original object.</span></span> <span data-ttu-id="5b824-126">익명 형식을 만들 때 필드 이름을 바꿀 수도 있습니다. 다음 예제에서는 `UnitPrice` 필드의 이름을 `Price`로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-126">You can also rename a field when you are creating an anonymous type; the following example renames the `UnitPrice` field to `Price`.</span></span>  

```csharp
select new {p.ProductName, Price = p.UnitPrice};  
```

## <a name="collection-initializers"></a><span data-ttu-id="5b824-127">컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="5b824-127">Collection initializers</span></span>

<span data-ttu-id="5b824-128">컬렉션 이니셜라이저를 사용하면 <xref:System.Collections.IEnumerable>을 구현하고 적절한 시그니처가 있는 `Add`를 인스턴스 메서드 또는 확장 메서드로 포함하는 컬렉션 형식을 초기화할 때 하나 이상의 요소 이니셜라이저를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-128">Collection initializers let you specify one or more element initializers when you initialize a collection type that implements <xref:System.Collections.IEnumerable> and has `Add` with the appropriate signature as an instance method or an extension method.</span></span> <span data-ttu-id="5b824-129">요소 이니셜라이저는 단순한 값, 식 또는 개체 이니셜라이저일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-129">The element initializers can be a simple value, an expression, or an object initializer.</span></span> <span data-ttu-id="5b824-130">컬렉션 이니셜라이저를 사용하면 호출을 여러 번 지정할 필요가 없습니다. 컴파일러가 호출을 자동으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-130">By using a collection initializer, you do not have to specify multiple calls; the compiler adds the calls automatically.</span></span>  
  
<span data-ttu-id="5b824-131">다음 예제에서는 두 개의 단순한 컬렉션 이니셜라이저를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-131">The following example shows two simple collection initializers:</span></span>  

```csharp
List<int> digits = new List<int> { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };  
List<int> digits2 = new List<int> { 0 + 1, 12 % 3, MakeInt() };  
```

<span data-ttu-id="5b824-132">다음 컬렉션 이니셜라이저는 개체 이니셜라이저를 사용하여 앞의 예제에서 정의된 `Cat` 클래스의 개체를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-132">The following collection initializer uses object initializers to initialize objects of the `Cat` class defined in a previous example.</span></span> <span data-ttu-id="5b824-133">개별 개체 이니셜라이저는 괄호로 묶이고 쉼표로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-133">Note that the individual object initializers are enclosed in braces and separated by commas.</span></span>  
  
[!code-csharp[ListInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitializer)]  
  
<span data-ttu-id="5b824-134">컬렉션의 [ 메서드에서 허용하는 경우 ](../../language-reference/keywords/null.md)null`Add`을 컬렉션 이니셜라이저의 요소로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-134">You can specify [null](../../language-reference/keywords/null.md) as an element in a collection initializer if the collection's `Add` method allows it.</span></span>  
  
[!code-csharp[ListInitializerNull](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#ListInitialerWithNull)]  
  
 <span data-ttu-id="5b824-135">컬렉션이 읽기/쓰기 인덱싱을 지원하는 경우 인덱싱된 요소를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-135">You can specify indexed elements if the collection supports read / write indexing.</span></span>
  
[!code-csharp[DictionaryInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryIndexerInitializer)]  

<span data-ttu-id="5b824-136">이전 샘플에서는 <xref:System.Collections.Generic.Dictionary%602.Item(%600)>을 호출하여 값을 설정하는 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-136">The preceding sample generates code that calls the <xref:System.Collections.Generic.Dictionary%602.Item(%600)> to set the values.</span></span> <span data-ttu-id="5b824-137">C# 6 이전에는 다음 구문을 사용하여 사전 및 다른 연관 컨테이너를 초기화할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-137">Before C# 6, you could initialize dictionaries and other associative containers using the following syntax.</span></span> <span data-ttu-id="5b824-138">괄호와 할당이 있는 인덱서 구문 대신 여러 값이 있는 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-138">Notice that instead of indexer syntax, with parentheses and an assignment, it uses an object with multiple values:</span></span>

[!code-csharp[DictionaryAddInitializer](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#DictionaryAddInitializer)]  

<span data-ttu-id="5b824-139">이 이니셜라이저 예제에서는 <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)>를 호출하여 사전에 세 가지 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-139">This initializer example calls <xref:System.Collections.Generic.Dictionary%602.Add(%600,%601)> to add the three items into the dictionary.</span></span> <span data-ttu-id="5b824-140">연관 컬렉션을 초기화하는 이러한 두 가지 방법은 컴파일러가 생성하는 메서드 호출 때문에 약간 다르게 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-140">These two different ways to initialize associative collections have slightly different behavior because of the method calls the compiler generates.</span></span> <span data-ttu-id="5b824-141">두 가지 방법 모두 `Dictionary` 클래스와 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-141">Both variants work with the `Dictionary` class.</span></span> <span data-ttu-id="5b824-142">다른 형식은 공용 API에 따라 어느 한 쪽만 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-142">Other types may only support one or the other based on their public API.</span></span>

## <a name="examples"></a><span data-ttu-id="5b824-143">예</span><span class="sxs-lookup"><span data-stu-id="5b824-143">Examples</span></span>

<span data-ttu-id="5b824-144">다음 예제에서는 개체 및 컬렉션 이니셜라이저의 개념을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-144">The following example combines the concepts of object and collection initializers.</span></span>

[!code-csharp[InitializerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullExample)]  

<span data-ttu-id="5b824-145">다음 예제에서는 <xref:System.Collections.IEnumerable>을 구현하고 여러 매개 변수가 있는 `Add` 메서드를 포함하는 개체를 보여줍니다. 이는 `Add` 메서드의 시그니처에 해당하는 목록의 항목당 여러 요소가 있는 컬렉션 이니셜라이저를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-145">The following example shows an object that implements <xref:System.Collections.IEnumerable> and contains an `Add` method with multiple parameters, It uses a collection initializer with multiple elements per item in the list that correspond to the signature of the `Add` method.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullListExample)]  

<span data-ttu-id="5b824-146">다음 예제에 표시된 것처럼 `Add` 메서드는 `params` 키워드를 사용하여 가변적인 인수 개수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-146">`Add` methods can use the `params` keyword to take a variable number of arguments, as shown in the following example.</span></span> <span data-ttu-id="5b824-147">이 예제에서는 인덱스를 사용하여 컬렉션을 초기화하기 위한 인덱서의 사용자 지정 구현도 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="5b824-147">This example also demonstrates the custom implementation of an indexer to initialize a collection using indexes.</span></span>

[!code-csharp[InitializerListExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/BasicObjectInitializers.cs#FullDictionaryInitializer)]  

## <a name="see-also"></a><span data-ttu-id="5b824-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5b824-148">See also</span></span>

- [<span data-ttu-id="5b824-149">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="5b824-149">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5b824-150">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="5b824-150">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="5b824-151">익명 형식</span><span class="sxs-lookup"><span data-stu-id="5b824-151">Anonymous Types</span></span>](anonymous-types.md)
