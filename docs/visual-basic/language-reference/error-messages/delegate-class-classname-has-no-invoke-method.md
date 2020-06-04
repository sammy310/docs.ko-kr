---
title: "'<classname>' 대리자 클래스에는 Invoke 메서드가 없으므로 이러한 형식의 식은 프로시저 호출의 대상일 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30220
- bc30220
helpviewer_keywords:
- BC30220
ms.assetid: 6be0d61c-f2f9-4f9b-ab90-8871a0d7206d
ms.openlocfilehash: 27be97ba2930791bcb9012c824bc418a0089b037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409714"
---
# <a name="delegate-class-classname-has-no-invoke-method-so-an-expression-of-this-type-cannot-be-the-target-of-a-method-call"></a><span data-ttu-id="80a1b-102">'\<classname>' 대리자 클래스에는 Invoke 메서드가 없으므로 이러한 형식의 식은 프로시저 호출의 대상일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="80a1b-102">Delegate class '\<classname>' has no Invoke method, so an expression of this type cannot be the target of a method call</span></span>
<span data-ttu-id="80a1b-103">대리자 `Invoke` `Invoke` 클래스에서가 구현 되지 않았기 때문에 대리자를 통한 호출이 실패 했습니다.</span><span class="sxs-lookup"><span data-stu-id="80a1b-103">A call to `Invoke` through a delegate has failed because `Invoke` is not implemented on the delegate class.</span></span>  
  
 <span data-ttu-id="80a1b-104">**오류 ID:** BC30220</span><span class="sxs-lookup"><span data-stu-id="80a1b-104">**Error ID:** BC30220</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="80a1b-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="80a1b-105">To correct this error</span></span>  
  
1. <span data-ttu-id="80a1b-106">문을 사용 하 여 대리자 클래스의 인스턴스를 만들고 `Dim` 프로시저가 연산자를 사용 하 여 대리자 인스턴스에 할당 되었는지 확인 `AddressOf` 합니다.</span><span class="sxs-lookup"><span data-stu-id="80a1b-106">Ensure that an instance of the delegate class has been created with a `Dim` statement and that a procedure has been assigned to the delegate instance with the `AddressOf` operator.</span></span>  
  
2. <span data-ttu-id="80a1b-107">대리자 클래스를 구현 하는 코드를 찾고 프로시저를 구현 하는지 확인 합니다 `Invoke` .</span><span class="sxs-lookup"><span data-stu-id="80a1b-107">Locate the code that implements the delegate class and make sure it implements the `Invoke` procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a1b-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="80a1b-108">See also</span></span>

- [<span data-ttu-id="80a1b-109">대리자</span><span class="sxs-lookup"><span data-stu-id="80a1b-109">Delegates</span></span>](../../programming-guide/language-features/delegates/index.md)
- [<span data-ttu-id="80a1b-110">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="80a1b-110">Delegate Statement</span></span>](../statements/delegate-statement.md)
- [<span data-ttu-id="80a1b-111">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="80a1b-111">AddressOf Operator</span></span>](../operators/addressof-operator.md)
- [<span data-ttu-id="80a1b-112">Dim 문</span><span class="sxs-lookup"><span data-stu-id="80a1b-112">Dim Statement</span></span>](../statements/dim-statement.md)
