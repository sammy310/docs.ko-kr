---
description: "자세한 정보: BC30910: ' '은 <typename> <type> <basetypename> <type> 어셈블리 외부의 기본 액세스를 확장 하므로 ' '에서 상속할 수 없습니다."
title: "'<typename>'은(는) 기본 <type>의 액세스를 해당 어셈블리 범위 밖으로 확장하므로 <basetypename> '<type>'에서 상속할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 332bfcbe9345f03605d6e1d6ded4a3e931ed491f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99641098"
---
# <a name="bc30910-typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="80dfa-103">BC30910: ' '은 (는) \<typename> \<type> \<basetypename> 기본의 액세스를 어셈블리 외부에 확장 하므로 ' '에서 상속할 수 없습니다. \<type></span><span class="sxs-lookup"><span data-stu-id="80dfa-103">BC30910: '\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>

<span data-ttu-id="80dfa-104">클래스 또는 인터페이스가 기본 클래스 또는 인터페이스에서 상속 되지만 덜 제한적인 액세스 수준을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="80dfa-104">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>

 <span data-ttu-id="80dfa-105">예를 들어 `Public` 인터페이스는 인터페이스에서 상속 `Friend` 하거나 클래스 `Protected` 에서 상속 `Private` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="80dfa-105">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="80dfa-106">이는 기본 클래스 또는 인터페이스를 제공 하 여 원하는 수준 이상으로 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="80dfa-106">This exposes the base class or interface to access beyond the intended level.</span></span>

 <span data-ttu-id="80dfa-107">**오류 ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="80dfa-107">**Error ID:** BC30910</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="80dfa-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="80dfa-108">To correct this error</span></span>

- <span data-ttu-id="80dfa-109">파생 클래스 또는 인터페이스의 액세스 수준을 기본 클래스 또는 인터페이스와 최소한 제한적으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="80dfa-109">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>

     <span data-ttu-id="80dfa-110">또는</span><span class="sxs-lookup"><span data-stu-id="80dfa-110">-or-</span></span>

- <span data-ttu-id="80dfa-111">덜 제한적인 액세스 수준을 필요로 하는 경우 `Inherits` 문을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="80dfa-111">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="80dfa-112">더 제한 된 기본 클래스 또는 인터페이스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80dfa-112">You cannot inherit from a more restricted base class or interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="80dfa-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80dfa-113">See also</span></span>

- [<span data-ttu-id="80dfa-114">Class 문</span><span class="sxs-lookup"><span data-stu-id="80dfa-114">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="80dfa-115">Interface 문</span><span class="sxs-lookup"><span data-stu-id="80dfa-115">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="80dfa-116">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="80dfa-116">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="80dfa-117">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="80dfa-117">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
