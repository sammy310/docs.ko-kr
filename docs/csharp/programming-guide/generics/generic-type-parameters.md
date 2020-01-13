---
title: 제네릭 형식 매개 변수 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 8412980d35989c445d2e0a44c0b9f35e6087bb8d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75712184"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="fbd00-102">제네릭 형식 매개 변수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="fbd00-102">Generic type parameters (C# Programming Guide)</span></span>

<span data-ttu-id="fbd00-103">제네릭 형식 또는 메서드 정의에서 형식 매개 변수는 클라이언트가 제네릭 형식의 인스턴스를 만들 때 지정하는 특정 형식에 대한 자리 표시자입니다.</span><span class="sxs-lookup"><span data-stu-id="fbd00-103">In a generic type or method definition, a type parameter is a placeholder for a specific type that a client specifies when they create an instance of the generic type.</span></span> <span data-ttu-id="fbd00-104">[제네릭 소개](./index.md)에 나열된 `GenericList<T>`와 같은 제네릭 클래스는 실제로 형식이 아니고 형식에 대한 청사진과 같으므로 있는 그대로 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd00-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](./index.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="fbd00-105">`GenericList<T>`를 사용하려면, 클라이언트 코드에서 꺾쇠 괄호 안에 형식 인수를 지정하여 생성된 형식을 선언하고 인스턴스화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd00-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="fbd00-106">이 특정 클래스의 형식 인수는 컴파일러에서 인식하는 모든 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd00-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="fbd00-107">만들 수 있는 생성된 형식 인스턴스의 수에는 제한이 없고, 각 인스턴스에서는 다음과 같이 서로 다른 형식 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd00-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
<span data-ttu-id="fbd00-108">`GenericList<T>`의 각 인스턴스에서 클래스에 있는 모든 `T`는 런타임에 형식 인수로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbd00-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class is substituted at run time with the type argument.</span></span> <span data-ttu-id="fbd00-109">이러한 대체를 통해 단일 클래스 정의를 사용하여 세 개의 형식이 안전한 효율적인 개체를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd00-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="fbd00-110">CLR에서 이러한 대체를 수행하는 방식에 대한 자세한 내용은 [런타임의 제네릭](./generics-in-the-run-time.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbd00-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](./generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="fbd00-111">형식 매개 변수 명명 지침</span><span class="sxs-lookup"><span data-stu-id="fbd00-111">Type parameter naming guidelines</span></span>  
  
- <span data-ttu-id="fbd00-112">**필수적** 단일 문자 이름으로도 자체 설명이 가능하여 설명적인 이름을 굳이 사용할 필요가 없는 경우가 아니면 제네릭 형식 매개 변수 이름을 설명적인 이름으로 지정하세요.</span><span class="sxs-lookup"><span data-stu-id="fbd00-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- <span data-ttu-id="fbd00-113">**선택적** 단일 문자 형식 매개 변수를 사용하는 형식에는 형식 매개 변수 이름으로 T를 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="fbd00-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- <span data-ttu-id="fbd00-114">**필수적** 설명적인 형식 매개 변수 이름 앞에 “T”를 붙이세요.</span><span class="sxs-lookup"><span data-stu-id="fbd00-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- <span data-ttu-id="fbd00-115">**선택적** 매개 변수 이름 안에 형식 매개 변수에 적용되는 제약 조건을 나타내 보세요.</span><span class="sxs-lookup"><span data-stu-id="fbd00-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="fbd00-116">예를 들어 `ISession`으로 제한되는 매개 변수의 이름은 `TSession`이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd00-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>

<span data-ttu-id="fbd00-117">코드 분석 규칙 [CA1715](/visualstudio/code-quality/ca1715)를 사용하여 형식 매개 변수의 이름이 적절하게 지정되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd00-117">The code analysis rule [CA1715](/visualstudio/code-quality/ca1715) can be used to ensure that type parameters are named appropriately.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="fbd00-118">참조</span><span class="sxs-lookup"><span data-stu-id="fbd00-118">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="fbd00-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="fbd00-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="fbd00-120">제네릭</span><span class="sxs-lookup"><span data-stu-id="fbd00-120">Generics</span></span>](./index.md)
- [<span data-ttu-id="fbd00-121">C++ 템플릿과 C# 제네릭의 차이점</span><span class="sxs-lookup"><span data-stu-id="fbd00-121">Differences Between C++ Templates and C# Generics</span></span>](./differences-between-cpp-templates-and-csharp-generics.md)
