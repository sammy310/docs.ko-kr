---
title: 매개 변수 전달 - C# 프로그래밍 가이드
description: 값 또는 참조로 C#의 매개 변수에 인수를 전달할 수 있습니다. 참조로 전달되는 인수에 대한 변경 내용이 유지됩니다. Ref 또는 out을 사용하여 참조로 전달합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [C#], passing
- passing parameters [C#]
- arguments [C#]
- methods [C#], passing parameters
- C# language, method parameters
ms.assetid: a5c3003f-7441-4710-b8b1-c79de77e0b77
ms.openlocfilehash: 61ec6d31145df5a2aebe805fccdf7614a0ae74f6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91186096"
---
# <a name="passing-parameters-c-programming-guide"></a><span data-ttu-id="719d3-105">매개 변수 전달(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="719d3-105">Passing Parameters (C# Programming Guide)</span></span>

<span data-ttu-id="719d3-106">C#에서는 인수를 값 또는 참조로 매개 변수에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="719d3-106">In C#, arguments can be passed to parameters either by value or by reference.</span></span> <span data-ttu-id="719d3-107">참조로 전달하면 함수 멤버, 메서드, 속성, 인덱서, 연산자 및 생성자가 매개 변수의 값을 변경하고 해당 변경 내용을 호출 환경에서 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="719d3-107">Passing by reference enables function members, methods, properties, indexers, operators, and constructors to change the value of the parameters and have that change persist in the calling environment.</span></span> <span data-ttu-id="719d3-108">값 변경의 목적으로 매개 변수를 참조로 전달하려면 `ref` 또는 `out` 키워드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="719d3-108">To pass a parameter by reference with the intent of changing the value, use the `ref`, or `out` keyword.</span></span> <span data-ttu-id="719d3-109">값을 변경하지 않고 복사 방지 목적으로 참조로 전달하려면 `in` 한정자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="719d3-109">To pass by reference with the intent of avoiding copying but not changing the value, use the `in` modifier.</span></span> <span data-ttu-id="719d3-110">간단히 설명하기 위해 이 항목의 예제에서는 `ref` 키워드만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="719d3-110">For simplicity, only the `ref` keyword is used in the examples in this topic.</span></span> <span data-ttu-id="719d3-111">`in`, `ref` 및 `out` 간의 차이점에 대한 자세한 내용은 [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md) 및 [out](../../language-reference/keywords/out-parameter-modifier.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="719d3-111">For more information about the difference between `in`, `ref`, and `out`, see [in](../../language-reference/keywords/in-parameter-modifier.md), [ref](../../language-reference/keywords/ref.md), and [out](../../language-reference/keywords/out-parameter-modifier.md).</span></span>  
  
 <span data-ttu-id="719d3-112">다음 예제에서는 값 및 참조 매개 변수 간의 차이점을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="719d3-112">The following example illustrates the difference between value and reference parameters.</span></span>  
  
 [!code-csharp[csProgGuideParameters#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideParameters/CS/Parameters.cs#10)]  
  
 <span data-ttu-id="719d3-113">자세한 내용은 다음 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="719d3-113">For more information, see the following topics:</span></span>  
  
- [<span data-ttu-id="719d3-114">값 형식 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="719d3-114">Passing Value-Type Parameters</span></span>](./passing-value-type-parameters.md)  
  
- [<span data-ttu-id="719d3-115">참조 형식 매개 변수 전달</span><span class="sxs-lookup"><span data-stu-id="719d3-115">Passing Reference-Type Parameters</span></span>](./passing-reference-type-parameters.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="719d3-116">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="719d3-116">C# Language Specification</span></span>  

<span data-ttu-id="719d3-117">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [인수 목록](~/_csharplang/spec/expressions.md#argument-lists)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="719d3-117">For more information, see [Argument lists](~/_csharplang/spec/expressions.md#argument-lists) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="719d3-118">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="719d3-118">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="719d3-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="719d3-119">See also</span></span>

- [<span data-ttu-id="719d3-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="719d3-120">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="719d3-121">메서드</span><span class="sxs-lookup"><span data-stu-id="719d3-121">Methods</span></span>](./methods.md)
