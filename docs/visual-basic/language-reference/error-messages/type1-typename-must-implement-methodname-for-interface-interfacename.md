---
title: <type1>'<typename>'은 '<interfacename>' 인터페이스에 대한 '<methodname>'을 구현해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: c387b0225375f4675042bef593b23a084305b4fd
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591589"
---
# <a name="type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="8715c-102">\<type1 > ' \<typename > '은 ' \<methodname > ' 인터페이스에 ' \<interfacename > ' 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8715c-102">\<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>
<span data-ttu-id="8715c-103">클래스 또는 구조체는 인터페이스를 구현 하지만 인터페이스에 의해 정의 된 프로시저를 구현 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8715c-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="8715c-104">인터페이스의 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8715c-104">Every member of the interface must be implemented.</span></span>  
  
 <span data-ttu-id="8715c-105">**오류 ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="8715c-105">**Error ID:** BC30149</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8715c-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8715c-106">To correct this error</span></span>  
  
1. <span data-ttu-id="8715c-107">인터페이스에 정의 된 것과 동일한 이름 및 서명을 사용 하 여 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="8715c-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="8715c-108">@No__t-0 또는 `End Sub` 문을 적어도 하나 이상 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8715c-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="8715c-109">@No__t-1 또는 `Sub` 문의 끝에 `Implements` 절을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8715c-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="8715c-110">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8715c-110">For example:</span></span>  
  
    ```vb  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="8715c-111">참조</span><span class="sxs-lookup"><span data-stu-id="8715c-111">See also</span></span>

- [<span data-ttu-id="8715c-112">Implements 문</span><span class="sxs-lookup"><span data-stu-id="8715c-112">Implements Statement</span></span>](../../../visual-basic/language-reference/statements/implements-statement.md)
- [<span data-ttu-id="8715c-113">인터페이스</span><span class="sxs-lookup"><span data-stu-id="8715c-113">Interfaces</span></span>](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
