---
title: 추상 속성 정의 방법 - C# 프로그래밍 가이드
description: C#에서 추상 속성을 정의하는 방법에 대해 알아봅니다. 추상 속성을 선언하는 것은 클래스가 속성을 지원함을 의미합니다. 파생된 클래스는 접근자를 구현합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- properties [C#], abstract
- abstract properties [C#]
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 672a90eb-47b9-4ae0-9914-af53852fddcb
ms.openlocfilehash: 46941c811b42891b38ab6f0c4a9b428d368cf4a4
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099428"
---
# <a name="how-to-define-abstract-properties-c-programming-guide"></a><span data-ttu-id="aecb4-105">추상 속성 정의 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="aecb4-105">How to define abstract properties (C# Programming Guide)</span></span>

<span data-ttu-id="aecb4-106">다음 예제에서는 [abstract](../../language-reference/keywords/abstract.md) 속성을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-106">The following example shows how to define [abstract](../../language-reference/keywords/abstract.md) properties.</span></span> <span data-ttu-id="aecb4-107">추상 속성 선언은 속성 접근자의 구현을 제공하지 않습니다. 클래스가 속성을 지원하도록 선언하지만 접근자 구현은 파생 클래스에서 처리되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-107">An abstract property declaration does not provide an implementation of the property accessors -- it declares that the class supports properties, but leaves the accessor implementation to derived classes.</span></span> <span data-ttu-id="aecb4-108">다음 예제에서는 기본 클래스에서 상속된 추상 속성을 구현하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-108">The following example demonstrates how to implement the abstract properties inherited from a base class.</span></span>  
  
 <span data-ttu-id="aecb4-109">이 샘플은 개별적으로 컴파일된 파일 3개로 구성되었으며, 결과로 생성된 어셈블리는 다음 컴파일 시 참조됩니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-109">This sample consists of three files, each of which is compiled individually and its resulting assembly is referenced by the next compilation:</span></span>  
  
- <span data-ttu-id="aecb4-110">abstractshape.cs: 추상 `Area` 속성이 포함된 `Shape` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-110">abstractshape.cs: the `Shape` class that contains an abstract `Area` property.</span></span>  
  
- <span data-ttu-id="aecb4-111">shapes.cs: `Shape` 클래스의 서브클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-111">shapes.cs: The subclasses of the `Shape` class.</span></span>  
  
- <span data-ttu-id="aecb4-112">shapetest.cs: 일부 `Shape` 파생 개체의 영역을 표시할 테스트 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-112">shapetest.cs: A test program to display the areas of some `Shape`-derived objects.</span></span>  
  
 <span data-ttu-id="aecb4-113">예제를 컴파일하려면 다음 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-113">To compile the example, use the following command:</span></span>  
  
 `csc abstractshape.cs shapes.cs shapetest.cs`  
  
 <span data-ttu-id="aecb4-114">그러면 shapetest.exe 실행 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-114">This will create the executable file shapetest.exe.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aecb4-115">예제</span><span class="sxs-lookup"><span data-stu-id="aecb4-115">Example</span></span>  

 <span data-ttu-id="aecb4-116">이 파일에서는 `double` 형식의 `Area` 속성을 포함하는 `Shape` 클래스를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-116">This file declares the `Shape` class that contains the `Area` property of the type `double`.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#1)]  
  
- <span data-ttu-id="aecb4-117">속성의 한정자는 속성 선언 자체에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-117">Modifiers on the property are placed on the property declaration itself.</span></span> <span data-ttu-id="aecb4-118">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="aecb4-118">For example:</span></span>  
  
    ```csharp  
    public abstract double Area  
    ```  
  
- <span data-ttu-id="aecb4-119">추상 속성(이 예제의 `Area`)을 선언할 때는 단순히 사용할 수 있는 속성 접근자를 나타내고 구현하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-119">When declaring an abstract property (such as `Area` in this example), you simply indicate what property accessors are available, but do not implement them.</span></span> <span data-ttu-id="aecb4-120">이 예제에서는 [get](../../language-reference/keywords/get.md) 접근자만 사용할 수 있으므로 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-120">In this example, only a [get](../../language-reference/keywords/get.md) accessor is available, so the property is read-only.</span></span>  
  
## <a name="example"></a><span data-ttu-id="aecb4-121">예제</span><span class="sxs-lookup"><span data-stu-id="aecb4-121">Example</span></span>  

 <span data-ttu-id="aecb4-122">다음 코드에서는 `Shape`의 세 가지 서브클래스와 이러한 서브클래스에서 `Area` 속성을 재정의하여 고유한 구현을 제공하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-122">The following code shows three subclasses of `Shape` and how they override the `Area` property to provide their own implementation.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#2)]  
  
## <a name="example"></a><span data-ttu-id="aecb4-123">예제</span><span class="sxs-lookup"><span data-stu-id="aecb4-123">Example</span></span>  

 <span data-ttu-id="aecb4-124">다음 코드에서는 많은 `Shape` 파생 개체를 만들고 해당 영역을 출력하는 테스트 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aecb4-124">The following code shows a test program that creates a number of `Shape`-derived objects and prints out their areas.</span></span>  
  
 [!code-csharp[csProgGuideInheritance#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#3)]  
  
## <a name="see-also"></a><span data-ttu-id="aecb4-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aecb4-125">See also</span></span>

- [<span data-ttu-id="aecb4-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="aecb4-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="aecb4-127">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="aecb4-127">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="aecb4-128">추상/봉인된 클래스 및 클래스 멤버</span><span class="sxs-lookup"><span data-stu-id="aecb4-128">Abstract and Sealed Classes and Class Members</span></span>](./abstract-and-sealed-classes-and-class-members.md)
- [<span data-ttu-id="aecb4-129">속성</span><span class="sxs-lookup"><span data-stu-id="aecb4-129">Properties</span></span>](./properties.md)
