---
title: ToString 메서드 재정의 방법 - C# 프로그래밍 가이드
description: C#에서 ToString 메서드를 재정의하는 방법에 대해 알아봅니다. 모든 클래스 또는 구조체는 Object를 상속하고 해당 개체의 문자열 표현을 반환하는 ToString을 가져옵니다.
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.topic: how-to
ms.custom: contperfq2
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: de56ea10ea15f497f9375c2449acbae1d0c8978a
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099265"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="7e824-104">ToString 메서드 재정의 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7e824-104">How to override the ToString method (C# Programming Guide)</span></span>

<span data-ttu-id="7e824-105">C#의 모든 클래스 또는 구조체는 <xref:System.Object> 클래스를 암시적으로 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-105">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="7e824-106">따라서 C#의 모든 개체는 해당 개체의 문자열 표현을 반환하는 <xref:System.Object.ToString%2A> 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-106">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="7e824-107">예를 들어 `int` 형식의 모든 변수에는 해당 내용을 문자열로 반환할 수 있도록 하는 `ToString` 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-107">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 <span data-ttu-id="7e824-108">사용자 지정 클래스 또는 구조체를 만들 때 해당 형식에 대한 정보를 클라이언트 코드에 제공하려면 <xref:System.Object.ToString%2A> 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-108">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="7e824-109">`ToString` 메서드와 함께 형식 문자열 및 다른 형식의 사용자 지정 서식을 사용하는 방법에 대한 자세한 내용은 [형식 서식 지정](../../../standard/base-types/formatting-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7e824-109">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7e824-110">이 메서드를 통해 제공할 정보를 결정하는 경우 신뢰할 수 없는 코드에서 클래스 또는 구조체가 사용될지 여부를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-110">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="7e824-111">악성 코드에서 악용될 수 있는 정보를 제공하지 않으면 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-111">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
<span data-ttu-id="7e824-112">클래스 또는 구조체에서 `ToString` 메서드를 재정의하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-112">To override the `ToString` method in your class or struct:</span></span>
  
1. <span data-ttu-id="7e824-113">다음 한정자 및 반환 형식으로 `ToString` 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-113">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. <span data-ttu-id="7e824-114">문자열을 반환하도록 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-114">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="7e824-115">다음 예제에서는 클래스의 특정 인스턴스와 관련된 데이터뿐 아니라 클래스의 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-115">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     <span data-ttu-id="7e824-116">다음 코드 예제와 같이 `ToString` 메서드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e824-116">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="7e824-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7e824-117">See also</span></span>

- <xref:System.IFormattable>
- [<span data-ttu-id="7e824-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7e824-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7e824-119">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="7e824-119">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="7e824-120">문자열</span><span class="sxs-lookup"><span data-stu-id="7e824-120">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="7e824-121">string</span><span class="sxs-lookup"><span data-stu-id="7e824-121">string</span></span>](../../language-reference/builtin-types/reference-types.md)
- [<span data-ttu-id="7e824-122">override</span><span class="sxs-lookup"><span data-stu-id="7e824-122">override</span></span>](../../language-reference/keywords/override.md)
- [<span data-ttu-id="7e824-123">virtual</span><span class="sxs-lookup"><span data-stu-id="7e824-123">virtual</span></span>](../../language-reference/keywords/virtual.md)
- [<span data-ttu-id="7e824-124">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="7e824-124">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
