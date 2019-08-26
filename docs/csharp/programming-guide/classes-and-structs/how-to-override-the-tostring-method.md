---
title: '방법: ToString 메서드 재정의 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- ToString method, overriding in C#
- inheritance [C#], overriding OnPaint and ToString
ms.assetid: 8016db69-1f19-420c-8e17-98e8bebb7749
ms.openlocfilehash: a2cf05dc6b288ffdaf1a20cf594231f48046a724
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69596751"
---
# <a name="how-to-override-the-tostring-method-c-programming-guide"></a><span data-ttu-id="7d704-102">방법: ToString 메서드 재정의(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7d704-102">How to: Override the ToString Method (C# Programming Guide)</span></span>

<span data-ttu-id="7d704-103">C#의 모든 클래스 또는 구조체는 <xref:System.Object> 클래스를 암시적으로 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-103">Every class or struct in C# implicitly inherits the <xref:System.Object> class.</span></span> <span data-ttu-id="7d704-104">따라서 C#의 모든 개체는 해당 개체의 문자열 표현을 반환하는 <xref:System.Object.ToString%2A> 메서드를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-104">Therefore, every object in C# gets the <xref:System.Object.ToString%2A> method, which returns a string representation of that object.</span></span> <span data-ttu-id="7d704-105">예를 들어 `int` 형식의 모든 변수에는 해당 내용을 문자열로 반환할 수 있도록 하는 `ToString` 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-105">For example, all variables of type `int` have a `ToString` method, which enables them to return their contents as a string:</span></span>  
  
 [!code-csharp[csProgGuideInheritance#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#37)]  
  
 <span data-ttu-id="7d704-106">사용자 지정 클래스 또는 구조체를 만들 때 해당 형식에 대한 정보를 클라이언트 코드에 제공하려면 <xref:System.Object.ToString%2A> 메서드를 재정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-106">When you create a custom class or struct, you should override the <xref:System.Object.ToString%2A> method in order to provide information about your type to client code.</span></span>  
  
 <span data-ttu-id="7d704-107">`ToString` 메서드와 함께 형식 문자열 및 다른 형식의 사용자 지정 서식을 사용하는 방법에 대한 자세한 내용은 [형식 서식 지정](../../../standard/base-types/formatting-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7d704-107">For information about how to use format strings and other types of custom formatting with the `ToString` method, see [Formatting Types](../../../standard/base-types/formatting-types.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7d704-108">이 메서드를 통해 제공할 정보를 결정하는 경우 신뢰할 수 없는 코드에서 클래스 또는 구조체가 사용될지 여부를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-108">When you decide what information to provide through this method, consider whether your class or struct will ever be used by untrusted code.</span></span> <span data-ttu-id="7d704-109">악성 코드에서 악용될 수 있는 정보를 제공하지 않으면 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-109">Be careful to ensure that you do not provide any information that could be exploited by malicious code.</span></span>  
  
<span data-ttu-id="7d704-110">클래스 또는 구조체에서 `ToString` 메서드를 재정의하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-110">To override the `ToString` method in your class or struct:</span></span>
  
1. <span data-ttu-id="7d704-111">다음 한정자 및 반환 형식으로 `ToString` 메서드를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-111">Declare a `ToString` method with the following modifiers and return type:</span></span>  
  
    ```csharp  
    public override string ToString(){}  
    ```  
  
2. <span data-ttu-id="7d704-112">문자열을 반환하도록 메서드를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-112">Implement the method so that it returns a string.</span></span>  
  
     <span data-ttu-id="7d704-113">다음 예제에서는 클래스의 특정 인스턴스와 관련된 데이터뿐 아니라 클래스의 이름을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-113">The following example returns the name of the class in addition to the data specific to a particular instance of the class.</span></span>  
  
     [!code-csharp[csProgGuideInheritance#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#36)]  
  
     <span data-ttu-id="7d704-114">다음 코드 예제와 같이 `ToString` 메서드를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7d704-114">You can test the `ToString` method as shown in the following code example:</span></span>  
  
     [!code-csharp[csProgGuideInheritance#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#38)]  
  
## <a name="see-also"></a><span data-ttu-id="7d704-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7d704-115">See also</span></span>

- <xref:System.IFormattable>
- [<span data-ttu-id="7d704-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7d704-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7d704-117">클래스 및 구조체</span><span class="sxs-lookup"><span data-stu-id="7d704-117">Classes and Structs</span></span>](./index.md)
- [<span data-ttu-id="7d704-118">문자열</span><span class="sxs-lookup"><span data-stu-id="7d704-118">Strings</span></span>](../strings/index.md)
- [<span data-ttu-id="7d704-119">string</span><span class="sxs-lookup"><span data-stu-id="7d704-119">string</span></span>](../../language-reference/keywords/string.md)
- [<span data-ttu-id="7d704-120">override</span><span class="sxs-lookup"><span data-stu-id="7d704-120">override</span></span>](../../language-reference/keywords/override.md)
- [<span data-ttu-id="7d704-121">virtual</span><span class="sxs-lookup"><span data-stu-id="7d704-121">virtual</span></span>](../../language-reference/keywords/virtual.md)
- [<span data-ttu-id="7d704-122">형식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="7d704-122">Formatting Types</span></span>](../../../standard/base-types/formatting-types.md)
