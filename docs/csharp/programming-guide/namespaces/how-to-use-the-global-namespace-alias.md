---
title: '방법: 전역 네임스페이스 별칭 사용 - C# 프로그래밍 가이드'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: b163981d3cf6d56ab953757931b0b386a47263ff
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796284"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a><span data-ttu-id="cb7c9-102">방법: 전역 네임스페이스 별칭 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="cb7c9-102">How to: Use the Global Namespace Alias (C# Programming Guide)</span></span>
<span data-ttu-id="cb7c9-103">전역 [네임스페이스](../../../csharp/language-reference/keywords/namespace.md)의 멤버에 액세스하는 기능은 멤버가 동일한 이름의 다른 엔터티에 의해 숨겨질 수 있는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-103">The ability to access a member in the global [namespace](../../../csharp/language-reference/keywords/namespace.md) is useful when the member might be hidden by another entity of the same name.</span></span>  
  
 <span data-ttu-id="cb7c9-104">예를 들어 다음 코드에서 `Console`은 <xref:System> 네임스페이스의 `Console` 형식 대신 `TestApp.Console`로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-104">For example, in the following code, `Console` resolves to `TestApp.Console` instead of to the `Console` type in the <xref:System> namespace.</span></span>  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 <span data-ttu-id="cb7c9-105">`System.Console`을 사용하면 `System` 네임스페이스가 `TestApp.System` 클래스에 의해 숨겨지기 때문에 여전히 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-105">Using `System.Console` still results in an error because the `System` namespace is hidden by the class `TestApp.System`:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 <span data-ttu-id="cb7c9-106">그러나 다음과 같이 `global::System.Console`을 사용하여 이 오류를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-106">However, you can work around this error by using `global::System.Console`, like this:</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 <span data-ttu-id="cb7c9-107">왼쪽 식별자가 `global`이면 오른쪽 식별자 검색이 전역 네임스페이스에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-107">When the left identifier is `global`, the search for the right identifier starts at the global namespace.</span></span> <span data-ttu-id="cb7c9-108">예를 들어 다음 선언에서는 `TestApp`을 전역 공간의 멤버로 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-108">For example, the following declaration is referencing `TestApp` as a member of the global space.</span></span>  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 <span data-ttu-id="cb7c9-109">물론, `System`이라는 고유한 네임스페이스를 만드는 것은 권장되지 않으며, 이러한 작업이 수행된 코드를 발견할 가능성은 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-109">Obviously, creating your own namespaces called `System` is not recommended, and it is unlikely you will encounter any code in which this has happened.</span></span> <span data-ttu-id="cb7c9-110">그러나 대규모 프로젝트에서는 어떤 형태로든 네임스페이스 중복이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-110">However, in larger projects, it is a very real possibility that namespace duplication may occur in one form or another.</span></span> <span data-ttu-id="cb7c9-111">이러한 상황에서 전역 네임스페이스 한정자는 루트 네임스페이스를 지정할 수 있도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7c9-111">In these situations, the global namespace qualifier is your guarantee that you can specify the root namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7c9-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb7c9-112">See also</span></span>

- [<span data-ttu-id="cb7c9-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="cb7c9-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="cb7c9-114">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="cb7c9-114">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)
- [<span data-ttu-id="cb7c9-115">:: 연산자</span><span class="sxs-lookup"><span data-stu-id="cb7c9-115">:: Operator</span></span>](../../../csharp/language-reference/operators/namespace-alias-qualifier.md)
- [<span data-ttu-id="cb7c9-116">extern</span><span class="sxs-lookup"><span data-stu-id="cb7c9-116">extern</span></span>](../../../csharp/language-reference/keywords/extern.md)
