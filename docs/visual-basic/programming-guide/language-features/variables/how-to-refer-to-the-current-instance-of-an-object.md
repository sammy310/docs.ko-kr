---
title: '방법: 개체의 현재 인스턴스 (Visual Basic)를 참조 하세요.'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 6c216dbc59bcad7a9f24bb01f856c3d29c288dbb
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005660"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="f8f6e-102">방법: 개체의 현재 인스턴스 (Visual Basic)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f8f6e-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="f8f6e-103">개체의 *현재 인스턴스* 는 코드가 현재 실행 중인 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="f8f6e-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="f8f6e-104">@No__t-0 키워드를 사용 하 여 현재 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f6e-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="f8f6e-105">현재 인스턴스를 참조 하려면</span><span class="sxs-lookup"><span data-stu-id="f8f6e-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="f8f6e-106">일반적으로 개체 변수 이름을 사용 하는 `Me` 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f6e-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="f8f6e-107">@No__t-0은 개체 변수 처럼 동작 하지만이를 선언 하거나 할당할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f8f6e-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="f8f6e-108">`Me`은 항상 현재 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8f6e-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8f6e-109">참조</span><span class="sxs-lookup"><span data-stu-id="f8f6e-109">See also</span></span>

- [<span data-ttu-id="f8f6e-110">개체 변수</span><span class="sxs-lookup"><span data-stu-id="f8f6e-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="f8f6e-111">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="f8f6e-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="f8f6e-112">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="f8f6e-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
