---
title: "'<constructorname>'의 기본 클래스 '<baseclassname>'에 있는 '<derivedclassname>'이(가) obsolete로 표시되어 있으므로 이 'Sub New'의 첫 번째 문은 'MyBase.New' 또는 'MyClass.New'에 대한 명시적 호출이어야 합니다. '<errormessage>'"
ms.date: 07/20/2015
f1_keywords:
- vbc30920
- bc30920
helpviewer_keywords:
- BC30920
ms.assetid: e47dc755-4294-4368-b813-2177b7677957
ms.openlocfilehash: 4918ac2e11dfaf682b1c00275f30c171bf241fe3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874116"
---
# <a name="first-statement-of-this-sub-new-must-be-an-explicit-call-to-mybasenew-or-myclassnew-because-the-constructorname-in-the-base-class-baseclassname-of-derivedclassname-is-marked-obsolete-errormessage"></a><span data-ttu-id="f0a06-102">'\<constructorname>'의 기본 클래스 '\<baseclassname>'에 있는 '\<derivedclassname>'이(가) obsolete로 표시되어 있으므로 이 'Sub New'의 첫 번째 문은 'MyBase.New' 또는 'MyClass.New'에 대한 명시적 호출이어야 합니다. '\<errormessage>'</span><span class="sxs-lookup"><span data-stu-id="f0a06-102">First statement of this 'Sub New' must be an explicit call to 'MyBase.New' or 'MyClass.New' because the '\<constructorname>' in the base class '\<baseclassname>' of '\<derivedclassname>' is marked obsolete: '\<errormessage>'</span></span>

<span data-ttu-id="f0a06-103">클래스 생성자는 기본 클래스 생성자를 명시적으로 호출하지 않으며, 암시적 기본 클래스 생성자가 <xref:System.ObsoleteAttribute> 특성 및 지시문으로 표시되어 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a06-103">A class constructor does not explicitly call a base class constructor, and the implicit base class constructor is marked with the <xref:System.ObsoleteAttribute> attribute and the directive to treat it as an error.</span></span>  
  
 <span data-ttu-id="f0a06-104">파생 클래스 생성자가 기본 클래스 생성자를 호출 하지 않는 경우 Visual Basic는 매개 변수가 없는 기본 클래스 생성자에 대 한 암시적 호출을 생성 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a06-104">When a derived class constructor does not call a base class constructor, Visual Basic attempts to generate an implicit call to a parameterless base class constructor.</span></span> <span data-ttu-id="f0a06-105">인수 없이 호출 될 수 있는 기본 클래스에 액세스할 수 있는 생성자가 없는 경우 Visual Basic는 암시적 호출을 생성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a06-105">If there is no accessible constructor in the base class that can be called without arguments, Visual Basic cannot generate an implicit call.</span></span> <span data-ttu-id="f0a06-106">이 경우 필요한 생성자는 특성으로 표시 <xref:System.ObsoleteAttribute> 되므로 Visual Basic 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a06-106">In this case, the required constructor is marked with the <xref:System.ObsoleteAttribute> attribute, so Visual Basic cannot call it.</span></span>  
  
 <span data-ttu-id="f0a06-107">프로그래밍 요소에 <xref:System.ObsoleteAttribute> 를 적용하여 더 이상 사용하지 않는 요소로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a06-107">You can mark any programming element as being no longer in use by applying <xref:System.ObsoleteAttribute> to it.</span></span> <span data-ttu-id="f0a06-108">이렇게 하면 특성의 <xref:System.ObsoleteAttribute.IsError%2A> 속성을 `True` 또는 `False`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0a06-108">If you do this, you can set the attribute's <xref:System.ObsoleteAttribute.IsError%2A> property to either `True` or `False`.</span></span> <span data-ttu-id="f0a06-109">`True`로 설정하면 컴파일러가 요소를 사용하려는 시도를 오류로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a06-109">If you set it to `True`, the compiler treats an attempt to use the element as an error.</span></span> <span data-ttu-id="f0a06-110">`False`로 설정하거나 기본값인 `False`로 두면 컴파일러가 요소를 사용하려는 시도가 있을 경우 경고를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="f0a06-110">If you set it to `False`, or let it default to `False`, the compiler issues a warning if there is an attempt to use the element.</span></span>  
  
 <span data-ttu-id="f0a06-111">**오류 ID:** BC30920</span><span class="sxs-lookup"><span data-stu-id="f0a06-111">**Error ID:** BC30920</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f0a06-112">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f0a06-112">To correct this error</span></span>  
  
1. <span data-ttu-id="f0a06-113">따옴표 붙은 오류 메시지를 검사하고 적절한 조치를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a06-113">Examine the quoted error message and take appropriate action.</span></span>  
  
2. <span data-ttu-id="f0a06-114">`MyBase.New()` 또는 `MyClass.New()` 에 대한 호출을 파생 클래스에 `Sub New` 의 첫 번째 문으로 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f0a06-114">Include a call to `MyBase.New()` or `MyClass.New()` as the first statement of the `Sub New` in the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0a06-115">참조</span><span class="sxs-lookup"><span data-stu-id="f0a06-115">See also</span></span>

- [<span data-ttu-id="f0a06-116">특성 개요</span><span class="sxs-lookup"><span data-stu-id="f0a06-116">Attributes overview</span></span>](../../programming-guide/concepts/attributes/index.md)
