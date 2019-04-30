---
title: Protected Friend (Visual Basic)
ms.date: 05/10/2018
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 331c63dc290d4096e8158f265ee869b47743a273
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053888"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="05824-102">Protected Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="05824-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="05824-103">`Protected Friend` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="05824-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="05824-104">둘 다를 부여 하 [Friend](friend.md) 액세스 하 고 [보호 된](protected.md) 자체 클래스 및 파생된 클래스에서 동일한 어셈블리에서 임의의 위치에서 액세스할 수 있도록 선언된 된 요소에 대 한 액세스.</span><span class="sxs-lookup"><span data-stu-id="05824-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="05824-105">지정할 수 있습니다 `Protected Friend` 클래스의 멤버에만 적용할 수 없습니다 `Protected Friend` 구조체의 멤버에 구조체를 상속할 수 없습니다 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="05824-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="05824-106">Visual Studio에서에서 F1 도움말을 선택 하 `protected friend` 에 대 한 도움말을 제공 [보호](protected.md) 하거나 [friend](friend.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="05824-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="05824-107">IDE 복합 단어를 사용 하지 않고 커서 아래에 있는 단일 토큰을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="05824-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="05824-108">규칙</span><span class="sxs-lookup"><span data-stu-id="05824-108">Rules</span></span>

- <span data-ttu-id="05824-109">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="05824-109">**Declaration Context.**</span></span> <span data-ttu-id="05824-110">사용할 수 있습니다 `Protected Friend` 클래스 수준에만 합니다.</span><span class="sxs-lookup"><span data-stu-id="05824-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="05824-111">즉, 선언 컨텍스트는 `Protected` 요소 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05824-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span> 

## <a name="see-also"></a><span data-ttu-id="05824-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="05824-112">See also</span></span>

- [<span data-ttu-id="05824-113">공용</span><span class="sxs-lookup"><span data-stu-id="05824-113">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)
- [<span data-ttu-id="05824-114">보호됨</span><span class="sxs-lookup"><span data-stu-id="05824-114">Protected</span></span>](../../../visual-basic/language-reference/modifiers/protected.md)
- [<span data-ttu-id="05824-115">Friend</span><span class="sxs-lookup"><span data-stu-id="05824-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="05824-116">전용</span><span class="sxs-lookup"><span data-stu-id="05824-116">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="05824-117">Private Protected</span><span class="sxs-lookup"><span data-stu-id="05824-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="05824-118">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="05824-118">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="05824-119">절차</span><span class="sxs-lookup"><span data-stu-id="05824-119">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="05824-120">구조체</span><span class="sxs-lookup"><span data-stu-id="05824-120">Structures</span></span>](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="05824-121">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="05824-121">Objects and Classes</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
