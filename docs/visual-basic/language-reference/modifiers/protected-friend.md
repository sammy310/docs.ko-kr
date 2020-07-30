---
title: Protected Friend
ms.date: 05/10/2018
f1_keywords:
- vb.ProtectedFriend
helpviewer_keywords:
- Protected Friend keyword [Visual Basic]
- Protected Friend keyword [Visual Basic], syntax
ms.openlocfilehash: 27fc993ca0b94d406261d5e6275de8cd619eb6a8
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303454"
---
# <a name="protected-friend-visual-basic"></a><span data-ttu-id="6776a-102">보호 된 Friend (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6776a-102">Protected Friend (Visual Basic)</span></span>

<span data-ttu-id="6776a-103">`Protected Friend` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="6776a-103">The `Protected Friend` keyword combination is a member access modifier.</span></span> <span data-ttu-id="6776a-104">선언 된 요소에 대 한 [Friend](friend.md) 액세스와 [보호 된](protected.md) 액세스를 모두 권한을 부여, 동일한 어셈블리, 자체 클래스 및 파생 클래스의 어디에서 나 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6776a-104">It confers both [Friend](friend.md) access and [Protected](protected.md) access on the declared elements, so they are accessible from anywhere in the same assembly, from their own class, and from derived classes.</span></span> <span data-ttu-id="6776a-105">클래스의 멤버만 지정할 수 있습니다. 구조체 `Protected Friend` `Protected Friend` 는 상속 될 수 없으므로 구조체의 멤버에는 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6776a-105">You can specify `Protected Friend` only on members of classes; you cannot apply `Protected Friend` to members of a structure because structures cannot be inherited.</span></span>

> [!NOTE]
> <span data-ttu-id="6776a-106">Visual Studio에서 F1 도움말을 선택 하 여 `protected friend` [보호](protected.md) 또는 [friend](friend.md)에 대 한 도움말을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6776a-106">In Visual Studio, selecting F1 help on `protected friend` provides help for either [protected](protected.md) or [friend](friend.md).</span></span> <span data-ttu-id="6776a-107">IDE는 복합 단어가 아니라 커서에서 단일 토큰을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6776a-107">The IDE picks the single token under the cursor rather than the compound word.</span></span>

## <a name="rules"></a><span data-ttu-id="6776a-108">규칙</span><span class="sxs-lookup"><span data-stu-id="6776a-108">Rules</span></span>

<span data-ttu-id="6776a-109">**선언 컨텍스트.**</span><span class="sxs-lookup"><span data-stu-id="6776a-109">**Declaration Context.**</span></span> <span data-ttu-id="6776a-110">`Protected Friend`는 클래스 수준 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6776a-110">You can use `Protected Friend` only at the class level.</span></span> <span data-ttu-id="6776a-111">즉, 요소에 대 한 선언 컨텍스트는 `Protected` 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6776a-111">This means the declaration context for a `Protected` element must be a class, and cannot be a source file, namespace, interface, module, structure, or procedure.</span></span>

## <a name="see-also"></a><span data-ttu-id="6776a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6776a-112">See also</span></span>

- [<span data-ttu-id="6776a-113">공용</span><span class="sxs-lookup"><span data-stu-id="6776a-113">Public</span></span>](public.md)
- [<span data-ttu-id="6776a-114">보호</span><span class="sxs-lookup"><span data-stu-id="6776a-114">Protected</span></span>](protected.md)
- [<span data-ttu-id="6776a-115">Friend</span><span class="sxs-lookup"><span data-stu-id="6776a-115">Friend</span></span>](friend.md)
- [<span data-ttu-id="6776a-116">프라이빗</span><span class="sxs-lookup"><span data-stu-id="6776a-116">Private</span></span>](private.md)
- [<span data-ttu-id="6776a-117">개인 보호</span><span class="sxs-lookup"><span data-stu-id="6776a-117">Private Protected</span></span>](./private-protected.md)
- [<span data-ttu-id="6776a-118">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="6776a-118">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
- [<span data-ttu-id="6776a-119">절차</span><span class="sxs-lookup"><span data-stu-id="6776a-119">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
- [<span data-ttu-id="6776a-120">구조체</span><span class="sxs-lookup"><span data-stu-id="6776a-120">Structures</span></span>](../../programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="6776a-121">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="6776a-121">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
