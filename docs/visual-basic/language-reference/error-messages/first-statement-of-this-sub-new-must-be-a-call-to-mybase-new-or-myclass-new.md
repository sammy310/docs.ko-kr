---
title: 이 'Sub New'의 첫째 문은 'MyBase.New' 또는 'MyClass.New'에 대한 호출이어야 합니다(매개 변수가 없는 액세스할 수 있는 생성자가 없음).
ms.date: 07/20/2015
f1_keywords:
- bc30148
- vbc30148
helpviewer_keywords:
- BC30148
ms.assetid: 4426e8fc-cb39-4eb8-ba95-503cd32fcc89
ms.openlocfilehash: 2b9d2568fb64e4af72733ad1f3dee58aaee650e5
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402981"
---
# <a name="first-statement-of-this-sub-new-must-be-a-call-to-mybasenew-or-myclassnew-no-accessible-constructor-without-parameters"></a><span data-ttu-id="216f4-102">이 'Sub New'의 첫째 문은 'MyBase.New' 또는 'MyClass.New'에 대한 호출이어야 합니다(매개 변수가 없는 액세스할 수 있는 생성자가 없음).</span><span class="sxs-lookup"><span data-stu-id="216f4-102">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' (No Accessible Constructor Without Parameters)</span></span>
<span data-ttu-id="216f4-103">' '의 기본 클래스 ' '에는 \<basename> \<derivedname> 인수 없이 호출할 수 있는 액세스 가능한 ' sub n e w '가 없으므로이 ' sub n e w '의 첫째 문은 ' mybase.new ' 또는 ' m a s s. n e w '에 대 한 호출 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="216f4-103">First statement of this 'Sub New' must be a call to 'MyBase.New' or 'MyClass.New' because base class '\<basename>' of '\<derivedname>' does not have an accessible 'Sub New' that can be called with no arguments.</span></span>  
  
 <span data-ttu-id="216f4-104">파생 클래스에서 모든 생성자는 기본 클래스 생성자 ()를 호출 해야 합니다 `MyBase.New` .</span><span class="sxs-lookup"><span data-stu-id="216f4-104">In a derived class, every constructor must call a base class constructor (`MyBase.New`).</span></span> <span data-ttu-id="216f4-105">기본 클래스에 파생 클래스에서 액세스할 수 있는 매개 변수가 없는 생성자가 있는 경우를 `MyBase.New` 자동으로 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="216f4-105">If the base class has a constructor with no parameters that is accessible to derived classes, `MyBase.New` can be called automatically.</span></span> <span data-ttu-id="216f4-106">그렇지 않은 경우 기본 클래스 생성자는 매개 변수를 사용 하 여 호출 해야 하며,이 작업은 자동으로 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="216f4-106">If not, a base class constructor must be called with parameters, and this cannot be done automatically.</span></span> <span data-ttu-id="216f4-107">이 경우 모든 파생 클래스 생성자의 첫 번째 문은 기본 클래스에서 매개 변수가 있는 생성자를 호출 하거나 기본 클래스 생성자를 호출 하는 파생 클래스의 다른 생성자를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="216f4-107">In this case, the first statement of every derived class constructor must call a parameterized constructor on the base class, or call another constructor in the derived class that makes a base class constructor call.</span></span>  
  
 <span data-ttu-id="216f4-108">**오류 ID:** BC30148</span><span class="sxs-lookup"><span data-stu-id="216f4-108">**Error ID:** BC30148</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="216f4-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="216f4-109">To correct this error</span></span>  
  
- <span data-ttu-id="216f4-110">`MyBase.New`필요한 매개 변수를 제공 하는를 호출 하거나 이러한 호출을 수행 하는 피어 생성자를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="216f4-110">Either call `MyBase.New` supplying the required parameters, or call a peer constructor that makes such a call.</span></span>  
  
     <span data-ttu-id="216f4-111">예를 들어 기본 클래스에로 선언 된 생성자가 있는 경우 `Public Sub New(ByVal index as Integer)` 파생 클래스 생성자의 첫 번째 문은이 될 수 있습니다 `MyBase.New(100)` .</span><span class="sxs-lookup"><span data-stu-id="216f4-111">For example, if the base class has a constructor that’s declared as `Public Sub New(ByVal index as Integer)`, the first statement in the derived class constructor might be `MyBase.New(100)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="216f4-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="216f4-112">See also</span></span>

- [<span data-ttu-id="216f4-113">상속 기본 사항</span><span class="sxs-lookup"><span data-stu-id="216f4-113">Inheritance Basics</span></span>](../../programming-guide/language-features/objects-and-classes/inheritance-basics.md)
