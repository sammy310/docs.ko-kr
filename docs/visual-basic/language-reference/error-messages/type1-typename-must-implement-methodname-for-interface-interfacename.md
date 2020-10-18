---
title: <type1>'<typename>'은 '<interfacename>' 인터페이스에 대한 '<methodname>'을 구현해야 합니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords:
- BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
ms.openlocfilehash: 68c6f65e6be229cc74458fa56fe3d3aa889c18f7
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161870"
---
# <a name="bc30149-type1typename-must-implement-methodname-for-interface-interfacename"></a><span data-ttu-id="49a71-102">BC30149: \<type1> ' ' \<typename> 은 ' ' \<methodname> 인터페이스에 대해 ' '을 (를) 구현 해야 합니다. \<interfacename></span><span class="sxs-lookup"><span data-stu-id="49a71-102">BC30149: \<type1>'\<typename>' must implement '\<methodname>' for interface '\<interfacename>'</span></span>

<span data-ttu-id="49a71-103">클래스 또는 구조체는 인터페이스를 구현 하지만 인터페이스에 의해 정의 된 프로시저를 구현 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49a71-103">A class or structure claims to implement an interface but does not implement a procedure defined by the interface.</span></span> <span data-ttu-id="49a71-104">인터페이스의 모든 멤버를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a71-104">Every member of the interface must be implemented.</span></span>

 <span data-ttu-id="49a71-105">**오류 ID:** BC30149</span><span class="sxs-lookup"><span data-stu-id="49a71-105">**Error ID:** BC30149</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="49a71-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="49a71-106">To correct this error</span></span>

1. <span data-ttu-id="49a71-107">인터페이스에 정의 된 것과 동일한 이름 및 서명을 사용 하 여 프로시저를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a71-107">Declare a procedure with the same name and signature as defined in the interface.</span></span> <span data-ttu-id="49a71-108">적어도 `End Function` 또는 문을 포함 해야 `End Sub` 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a71-108">Be sure to include at least the `End Function` or `End Sub` statement.</span></span>

2. <span data-ttu-id="49a71-109">`Implements`또는 문의 끝에 절을 추가 `Function` `Sub` 합니다.</span><span class="sxs-lookup"><span data-stu-id="49a71-109">Add an `Implements` clause to the end of the `Function` or `Sub` statement.</span></span> <span data-ttu-id="49a71-110">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="49a71-110">For example:</span></span>

    ```vb
    Public Sub DoSomething() Implements IBaseInterface.DoSomething
    ```

## <a name="see-also"></a><span data-ttu-id="49a71-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="49a71-111">See also</span></span>

- [<span data-ttu-id="49a71-112">Implements 문</span><span class="sxs-lookup"><span data-stu-id="49a71-112">Implements Statement</span></span>](../statements/implements-statement.md)
- [<span data-ttu-id="49a71-113">인터페이스</span><span class="sxs-lookup"><span data-stu-id="49a71-113">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
