---
title: 리플렉션(C#)
ms.date: 07/20/2015
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
ms.openlocfilehash: a56fb24b63e4d80dbb67b079466b67cd11672023
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711670"
---
# <a name="reflection-c"></a><span data-ttu-id="0eac0-102">리플렉션(C#)</span><span class="sxs-lookup"><span data-stu-id="0eac0-102">Reflection (C#)</span></span>

<span data-ttu-id="0eac0-103">리플렉션은 어셈블리, 모듈 및 형식을 설명하는 개체(<xref:System.Type> 형식)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-103">Reflection provides objects (of type <xref:System.Type>) that describe assemblies, modules, and types.</span></span> <span data-ttu-id="0eac0-104">리플렉션을 사용하면 동적으로 형식 인스턴스를 만들거나, 형식을 기존 개체에 바인딩하거나, 기존 개체에서 형식을 가져와 해당 메서드를 호출하거나, 필드 및 속성에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-104">You can use reflection to dynamically create an instance of a type, bind the type to an existing object, or get the type from an existing object and invoke its methods or access its fields and properties.</span></span> <span data-ttu-id="0eac0-105">코드에서 특성을 사용하는 경우 리플렉션은 특성에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-105">If you are using attributes in your code, reflection enables you to access them.</span></span> <span data-ttu-id="0eac0-106">자세한 내용은 [특성](../../../standard/attributes/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eac0-106">For more information, see [Attributes](../../../standard/attributes/index.md).</span></span>

<span data-ttu-id="0eac0-107">다음은 <xref:System.Object.GetType> 메서드(`Object` 기본 클래스의 모든 형식에 상속됨)를 사용하여 변수 형식을 가져오는 간단한 리플렉션 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-107">Here's a simple example of reflection using the <xref:System.Object.GetType> method - inherited by all types from the `Object` base class - to obtain the type of a variable:</span></span>

> [!NOTE]
> <span data-ttu-id="0eac0-108">`using System;` 및 `using System.Reflection;`을 *.cs* 파일의 맨 위에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-108">Make sure you add `using System;` and `using System.Reflection;` at the top of your *.cs* file.</span></span>

```csharp
// Using GetType to obtain type information:
int i = 42;
Type type = i.GetType();
Console.WriteLine(type);
```

<span data-ttu-id="0eac0-109">출력은 `System.Int32`입니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-109">The output is: `System.Int32`.</span></span>

<span data-ttu-id="0eac0-110">다음 예제에서는 리플렉션을 사용하여 로드된 어셈블리의 전체 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-110">The following example uses reflection to obtain the full name of the loaded assembly.</span></span>

```csharp
// Using Reflection to get information of an Assembly:
Assembly info = typeof(int).Assembly;
Console.WriteLine(info);
```

<span data-ttu-id="0eac0-111">출력은 `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`입니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-111">The output is: `System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e`.</span></span>

> [!NOTE]
> <span data-ttu-id="0eac0-112">C# 키워드 `protected` 및 `internal`은 IL에서 아무런 의미가 없으며 리플렉션 API에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-112">The C# keywords `protected` and `internal` have no meaning in IL and are not used in the reflection APIs.</span></span> <span data-ttu-id="0eac0-113">IL의 해당 용어는 *Family* 및 *Assembly*입니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-113">The corresponding terms in IL are *Family* and *Assembly*.</span></span> <span data-ttu-id="0eac0-114">리플렉션을 사용하는 `internal` 메서드를 식별하려면 <xref:System.Reflection.MethodBase.IsAssembly%2A> 속성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-114">To identify an `internal` method using reflection, use the <xref:System.Reflection.MethodBase.IsAssembly%2A> property.</span></span> <span data-ttu-id="0eac0-115">`protected internal` 메서드를 식별하려면 <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-115">To identify a `protected internal` method, use the <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>.</span></span>

## <a name="reflection-overview"></a><span data-ttu-id="0eac0-116">리플렉션 개요</span><span class="sxs-lookup"><span data-stu-id="0eac0-116">Reflection overview</span></span>

<span data-ttu-id="0eac0-117">리플렉션은 다음과 같은 상황에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-117">Reflection is useful in the following situations:</span></span>

- <span data-ttu-id="0eac0-118">프로그램 메타데이터의 특성에 액세스해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="0eac0-118">When you have to access attributes in your program's metadata.</span></span> <span data-ttu-id="0eac0-119">자세한 내용은 [특성에 저장된 정보 검색](../../../standard/attributes/retrieving-information-stored-in-attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eac0-119">For more information, see [Retrieving Information Stored in Attributes](../../../standard/attributes/retrieving-information-stored-in-attributes.md).</span></span>
- <span data-ttu-id="0eac0-120">어셈블리에서 형식을 검사하고 인스턴스화하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="0eac0-120">For examining and instantiating types in an assembly.</span></span>
- <span data-ttu-id="0eac0-121">런타임에 새 형식을 빌드하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="0eac0-121">For building new types at runtime.</span></span> <span data-ttu-id="0eac0-122"><xref:System.Reflection.Emit>의 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0eac0-122">Use classes in <xref:System.Reflection.Emit>.</span></span>
- <span data-ttu-id="0eac0-123">런타임에 바인딩을 수행하고 런타임에 생성된 형식의 메서드에 액세스하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="0eac0-123">For performing late binding, accessing methods on types created at run time.</span></span> <span data-ttu-id="0eac0-124">[동적으로 형식 로드 및 사용](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md) 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0eac0-124">See the topic [Dynamically Loading and Using Types](../../../framework/reflection-and-codedom/dynamically-loading-and-using-types.md).</span></span>

## <a name="related-sections"></a><span data-ttu-id="0eac0-125">관련 단원</span><span class="sxs-lookup"><span data-stu-id="0eac0-125">Related sections</span></span>

<span data-ttu-id="0eac0-126">추가 정보</span><span class="sxs-lookup"><span data-stu-id="0eac0-126">For more information:</span></span>

- [<span data-ttu-id="0eac0-127">리플렉션</span><span class="sxs-lookup"><span data-stu-id="0eac0-127">Reflection</span></span>](../../../framework/reflection-and-codedom/reflection.md)
- [<span data-ttu-id="0eac0-128">형식 정보 보기</span><span class="sxs-lookup"><span data-stu-id="0eac0-128">Viewing Type Information</span></span>](../../../framework/reflection-and-codedom/viewing-type-information.md)
- [<span data-ttu-id="0eac0-129">리플렉션 및 제네릭 형식</span><span class="sxs-lookup"><span data-stu-id="0eac0-129">Reflection and Generic Types</span></span>](../../../framework/reflection-and-codedom/reflection-and-generic-types.md)
- <xref:System.Reflection.Emit>
- [<span data-ttu-id="0eac0-130">특성에 저장된 정보 검색</span><span class="sxs-lookup"><span data-stu-id="0eac0-130">Retrieving Information Stored in Attributes</span></span>](../../../standard/attributes/retrieving-information-stored-in-attributes.md)

## <a name="see-also"></a><span data-ttu-id="0eac0-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0eac0-131">See also</span></span>

- [<span data-ttu-id="0eac0-132">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0eac0-132">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0eac0-133">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="0eac0-133">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
