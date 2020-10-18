---
title: "'<typename>'은(는) 기본 <type>의 액세스를 해당 어셈블리 범위 밖으로 확장하므로 <basetypename> '<type>'에서 상속할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: 5c019f9d74b11e48aa05a1480b9449fa28488b43
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161844"
---
# <a name="bc30910-typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="bf37f-102">BC30910: ' '은 (는) \<typename> \<type> \<basetypename> 기본의 액세스를 어셈블리 외부에 확장 하므로 ' '에서 상속할 수 없습니다. \<type></span><span class="sxs-lookup"><span data-stu-id="bf37f-102">BC30910: '\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>

<span data-ttu-id="bf37f-103">클래스 또는 인터페이스가 기본 클래스 또는 인터페이스에서 상속 되지만 덜 제한적인 액세스 수준을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf37f-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>

 <span data-ttu-id="bf37f-104">예를 들어 `Public` 인터페이스는 인터페이스에서 상속 `Friend` 하거나 클래스 `Protected` 에서 상속 `Private` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf37f-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="bf37f-105">이는 기본 클래스 또는 인터페이스를 제공 하 여 원하는 수준 이상으로 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf37f-105">This exposes the base class or interface to access beyond the intended level.</span></span>

 <span data-ttu-id="bf37f-106">**오류 ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="bf37f-106">**Error ID:** BC30910</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="bf37f-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="bf37f-107">To correct this error</span></span>

- <span data-ttu-id="bf37f-108">파생 클래스 또는 인터페이스의 액세스 수준을 기본 클래스 또는 인터페이스와 최소한 제한적으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf37f-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>

     <span data-ttu-id="bf37f-109">또는</span><span class="sxs-lookup"><span data-stu-id="bf37f-109">-or-</span></span>

- <span data-ttu-id="bf37f-110">덜 제한적인 액세스 수준을 필요로 하는 경우 `Inherits` 문을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf37f-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="bf37f-111">더 제한 된 기본 클래스 또는 인터페이스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf37f-111">You cannot inherit from a more restricted base class or interface.</span></span>

## <a name="see-also"></a><span data-ttu-id="bf37f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf37f-112">See also</span></span>

- [<span data-ttu-id="bf37f-113">Class 문</span><span class="sxs-lookup"><span data-stu-id="bf37f-113">Class Statement</span></span>](../statements/class-statement.md)
- [<span data-ttu-id="bf37f-114">Interface 문</span><span class="sxs-lookup"><span data-stu-id="bf37f-114">Interface Statement</span></span>](../statements/interface-statement.md)
- [<span data-ttu-id="bf37f-115">Inherits Statement</span><span class="sxs-lookup"><span data-stu-id="bf37f-115">Inherits Statement</span></span>](../statements/inherits-statement.md)
- [<span data-ttu-id="bf37f-116">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="bf37f-116">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
