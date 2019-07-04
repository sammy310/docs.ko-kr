---
title: ':: 연산자 - C# 참조'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ::_CSharpKeyword
helpviewer_keywords:
- ':: operator [C#]'
- 'namespaces [C#], :: operator'
- namespace alias qualifier operator (::) [C#]
ms.assetid: 698b5a73-85cf-4e0e-9e8e-6496887f8527
ms.openlocfilehash: c494e8dbb18f44ce5520b21800a21d3feb03da59
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025065"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="cb9aa-102">:: 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="cb9aa-102">:: operator (C# reference)</span></span>

<span data-ttu-id="cb9aa-103">네임스페이스 별칭 한정자(`::`)는 식별자를 조회하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb9aa-103">The namespace alias qualifier (`::`) is used to look up identifiers.</span></span> <span data-ttu-id="cb9aa-104">다음 예제와 같이 항상 두 식별자 사이에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb9aa-104">It is always positioned between two identifiers, as in this example:</span></span>

[!code-csharp[csRefOperators#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#27)]

<span data-ttu-id="cb9aa-105">`::` 연산자는 *using 별칭 지시문*과 함께 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb9aa-105">The `::` operator can also be used with a *using alias directive*:</span></span>

```csharp
// using Col=System.Collections.Generic;
var numbers = new Col::List<int> { 1, 2, 3 };
```

## <a name="remarks"></a><span data-ttu-id="cb9aa-106">설명</span><span class="sxs-lookup"><span data-stu-id="cb9aa-106">Remarks</span></span>

<span data-ttu-id="cb9aa-107">네임스페이스 별칭 한정자는 `global`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb9aa-107">The namespace alias qualifier can be `global`.</span></span> <span data-ttu-id="cb9aa-108">별칭이 지정된 네임스페이스가 아니라 전역 네임스페이스에서 조회를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9aa-108">This invokes a lookup in the global namespace, rather than an aliased namespace.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="cb9aa-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="cb9aa-109">For more information</span></span>

<span data-ttu-id="cb9aa-110">`::` 연산자를 사용하는 방법의 예는 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb9aa-110">For an example of how to use the `::` operator, see the following section:</span></span>

- [<span data-ttu-id="cb9aa-111">방법: 전역 네임스페이스 별칭 사용</span><span class="sxs-lookup"><span data-stu-id="cb9aa-111">How to: Use the Global Namespace Alias</span></span>](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)

## <a name="c-language-specification"></a><span data-ttu-id="cb9aa-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="cb9aa-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="cb9aa-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb9aa-113">See also</span></span>

- [<span data-ttu-id="cb9aa-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="cb9aa-114">C# reference</span></span>](../index.md)
- [<span data-ttu-id="cb9aa-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="cb9aa-115">C# operators</span></span>](index.md)
- [<span data-ttu-id="cb9aa-116">. 연산자</span><span class="sxs-lookup"><span data-stu-id="cb9aa-116">. operator</span></span>](member-access-operators.md#member-access-operator-)
- [<span data-ttu-id="cb9aa-117">extern alias</span><span class="sxs-lookup"><span data-stu-id="cb9aa-117">extern alias</span></span>](../keywords/extern-alias.md)
