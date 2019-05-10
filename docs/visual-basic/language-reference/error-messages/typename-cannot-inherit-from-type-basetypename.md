---
title: "'<typename>'은(는) 기본 <type>의 액세스를 해당 어셈블리 범위 밖으로 확장하므로 <basetypename> '<type>'에서 상속할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords:
- BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
ms.openlocfilehash: e21eea20d953e64e91522074c25f037451145bf8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64664203"
---
# <a name="typename-cannot-inherit-from-type-basetypename-because-it-expands-the-access-of-the-base-type-outside-the-assembly"></a><span data-ttu-id="33335-102">'\<typename >'에서 상속할 수 없습니다 \<유형 > '\<basetypename >' 기본에 대 한 액세스를 확장 하므로 \<유형 > 어셈블리 외부에서</span><span class="sxs-lookup"><span data-stu-id="33335-102">'\<typename>' cannot inherit from \<type> '\<basetypename>' because it expands the access of the base \<type> outside the assembly</span></span>
<span data-ttu-id="33335-103">기본 클래스에서 상속 하는 클래스 또는 인터페이스 또는 인터페이스의 하지만 덜 제한적인 액세스 수준이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33335-103">A class or interface inherits from a base class or interface but has a less restrictive access level.</span></span>  
  
 <span data-ttu-id="33335-104">예를 들어,를 `Public` 인터페이스에서 상속 되는 `Friend` 인터페이스 또는 `Protected` 클래스에서 상속을 `Private` 클래스.</span><span class="sxs-lookup"><span data-stu-id="33335-104">For example, a `Public` interface inherits from a `Friend` interface, or a `Protected` class inherits from a `Private` class.</span></span> <span data-ttu-id="33335-105">이 기본 클래스 또는 인터페이스 의도 한 수준 이상의 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="33335-105">This exposes the base class or interface to access beyond the intended level.</span></span>  
  
 <span data-ttu-id="33335-106">**오류 ID:** BC30910</span><span class="sxs-lookup"><span data-stu-id="33335-106">**Error ID:** BC30910</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="33335-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="33335-107">To correct this error</span></span>  
  
- <span data-ttu-id="33335-108">파생된 클래스 또는 적어도 제한적으로 기본 클래스 또는 인터페이스의 인터페이스의 액세스 수준을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="33335-108">Change the access level of the derived class or interface to be at least as restrictive as that of the base class or interface.</span></span>  
  
     <span data-ttu-id="33335-109">또는</span><span class="sxs-lookup"><span data-stu-id="33335-109">-or-</span></span>  
  
- <span data-ttu-id="33335-110">덜 제한적인 액세스 수준에 필요한 경우 제거 된 `Inherits` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="33335-110">If you require the less restrictive access level, remove the `Inherits` statement.</span></span> <span data-ttu-id="33335-111">좀 더 제한 된 기본 클래스 또는 인터페이스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33335-111">You cannot inherit from a more restricted base class or interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33335-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="33335-112">See also</span></span>

- [<span data-ttu-id="33335-113">Class 문</span><span class="sxs-lookup"><span data-stu-id="33335-113">Class Statement</span></span>](../../../visual-basic/language-reference/statements/class-statement.md)
- [<span data-ttu-id="33335-114">Interface 문</span><span class="sxs-lookup"><span data-stu-id="33335-114">Interface Statement</span></span>](../../../visual-basic/language-reference/statements/interface-statement.md)
- [<span data-ttu-id="33335-115">Inherits 문</span><span class="sxs-lookup"><span data-stu-id="33335-115">Inherits Statement</span></span>](../../../visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="33335-116">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="33335-116">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
