---
title: partial 메서드 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- partialmethod_CSharpKeyword
helpviewer_keywords:
- partial methods [C#]
ms.assetid: 43f40242-17e0-4452-8573-090503ad3137
ms.openlocfilehash: 14bcd3329b6ca8e46f6c180c97174a561108d143
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633355"
---
# <a name="partial-method-c-reference"></a><span data-ttu-id="dadb0-102">partial 메서드(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="dadb0-102">partial method (C# Reference)</span></span>

<span data-ttu-id="dadb0-103">부분 메서드는 부분 형식의 한 부분에서 해당 시그니처가 정의되고 형식의 다른 부분에서 해당 구현이 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="dadb0-103">A partial method has its signature defined in one part of a partial type, and its implementation defined in another part of the type.</span></span> <span data-ttu-id="dadb0-104">클래스 디자이너는 부분 메서드를 통해 개발자가 구현 여부를 결정할 수 있는 이벤트 처리기와 유사한 메서드 후크를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dadb0-104">Partial methods enable class designers to provide method hooks, similar to event handlers, that developers may decide to implement or not.</span></span> <span data-ttu-id="dadb0-105">개발자가 구현을 제공하지 않을 경우 컴파일러는 컴파일 시간에 시그니처를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="dadb0-105">If the developer does not supply an implementation, the compiler removes the signature at compile time.</span></span> <span data-ttu-id="dadb0-106">부분 메서드에는 다음 조건이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dadb0-106">The following conditions apply to partial methods:</span></span>

- <span data-ttu-id="dadb0-107">부분 형식의 두 부분에 있는 시그니처가 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dadb0-107">Signatures in both parts of the partial type must match.</span></span>

- <span data-ttu-id="dadb0-108">이 메서드는 void를 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dadb0-108">The method must return void.</span></span>

- <span data-ttu-id="dadb0-109">어떠한 액세스 한정자도 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dadb0-109">No access modifiers are allowed.</span></span> <span data-ttu-id="dadb0-110">부분 메서드는 암시적으로 private입니다.</span><span class="sxs-lookup"><span data-stu-id="dadb0-110">Partial methods are implicitly private.</span></span>

<span data-ttu-id="dadb0-111">다음 예제에서는 partial 클래스의 두 부분에서 정의된 부분 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="dadb0-111">The following example shows a partial method defined in two parts of a partial class:</span></span>

[!code-csharp[csrefKeywordsContextual#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#9)]

<span data-ttu-id="dadb0-112">자세한 내용은 참조 [Partial 클래스 및 메서드](../../programming-guide/classes-and-structs/partial-classes-and-methods.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="dadb0-112">For more information, see [Partial Classes and Methods](../../programming-guide/classes-and-structs/partial-classes-and-methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dadb0-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dadb0-113">See also</span></span>

- [<span data-ttu-id="dadb0-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="dadb0-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dadb0-115">partial 형식</span><span class="sxs-lookup"><span data-stu-id="dadb0-115">partial type</span></span>](partial-type.md)
