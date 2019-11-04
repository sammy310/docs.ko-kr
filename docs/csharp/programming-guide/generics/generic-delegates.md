---
title: 제네릭 대리자 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], delegates
- delegates [C#], generic
ms.assetid: bdea509c-44c1-4309-aaa9-15c7aee009df
ms.openlocfilehash: 3c6f29ead76f2e835d78a15d782e1aaca28942c8
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423270"
---
# <a name="generic-delegates-c-programming-guide"></a><span data-ttu-id="54f37-102">제네릭 대리자(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="54f37-102">Generic Delegates (C# Programming Guide)</span></span>
<span data-ttu-id="54f37-103">[대리자](../../language-reference/builtin-types/reference-types.md)는 자체 형식 매개 변수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f37-103">A [delegate](../../language-reference/builtin-types/reference-types.md) can define its own type parameters.</span></span> <span data-ttu-id="54f37-104">제네릭 대리자를 참조하는 코드는 다음 예제와 같이 제네릭 클래스를 인스턴스화하거나 제네릭 메서드를 호출하는 것과 같은 방법으로 형식 인수를 지정하여 폐쇄형 생성 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f37-104">Code that references the generic delegate can specify the type argument to create a closed constructed type, just like when instantiating a generic class or calling a generic method, as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#36)]  
  
 <span data-ttu-id="54f37-105">C# 버전 2.0에는 메서드 그룹 변환이라는 새로운 기능이 있습니다. 이 기능은 제네릭 대리자 형식은 물론 구체적인 대리자 형식에도 적용되며, 이 기능을 사용하여 위 코드 줄을 다음과 같이 간단한 구문으로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f37-105">C# version 2.0 has a new feature called method group conversion, which applies to concrete as well as generic delegate types, and enables you to write the previous line with this simplified syntax:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#37)]  
  
 <span data-ttu-id="54f37-106">제네릭 클래스 내에 정의된 대리자는 클래스 메서드와 같은 방식으로 제네릭 클래스 형식 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54f37-106">Delegates defined within a generic class can use the generic class type parameters in the same way that class methods do.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#38)]  
  
 <span data-ttu-id="54f37-107">대리자를 참조하는 코드는 포함 클래스의 형식 인수를 다음과 같이 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="54f37-107">Code that references the delegate must specify the type argument of the containing class, as follows:</span></span>  
  
 [!code-csharp[csProgGuideGenerics#39](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#39)]  
  
 <span data-ttu-id="54f37-108">제네릭 대리자는 sender 인수를 강력하게 형식화할 수 있고 더 이상 sender 인수와 <xref:System.Object> 간에 캐스팅하지 않아도 되기 때문에 일반적인 디자인 패턴을 기반으로 하는 이벤트를 정의할 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="54f37-108">Generic delegates are especially useful in defining events based on the typical design pattern because the sender argument can be strongly typed and no longer has to be cast to and from <xref:System.Object>.</span></span>  
  
 [!code-csharp[csProgGuideGenerics#40](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#40)]  
  
## <a name="see-also"></a><span data-ttu-id="54f37-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54f37-109">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="54f37-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="54f37-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="54f37-111">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="54f37-111">Introduction to Generics</span></span>](./index.md)
- [<span data-ttu-id="54f37-112">제네릭 메서드</span><span class="sxs-lookup"><span data-stu-id="54f37-112">Generic Methods</span></span>](./generic-methods.md)
- [<span data-ttu-id="54f37-113">제네릭 클래스</span><span class="sxs-lookup"><span data-stu-id="54f37-113">Generic Classes</span></span>](./generic-classes.md)
- [<span data-ttu-id="54f37-114">제네릭 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54f37-114">Generic Interfaces</span></span>](./generic-interfaces.md)
- [<span data-ttu-id="54f37-115">대리자</span><span class="sxs-lookup"><span data-stu-id="54f37-115">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="54f37-116">제네릭</span><span class="sxs-lookup"><span data-stu-id="54f37-116">Generics</span></span>](../../../standard/generics/index.md)
