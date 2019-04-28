---
title: '방법: 개체 (Visual Basic)의 현재 인스턴스 참조'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 3c44748798d5ed554fc9fbded9c3a4d981a66d2f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769033"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="86d13-102">방법: 개체 (Visual Basic)의 현재 인스턴스 참조</span><span class="sxs-lookup"><span data-stu-id="86d13-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="86d13-103">합니다 *현재 인스턴스* 는 코드가 현재 실행 중인 개체의 합니다.</span><span class="sxs-lookup"><span data-stu-id="86d13-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="86d13-104">사용할는 `Me` 키워드를 현재 인스턴스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86d13-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="86d13-105">현재 인스턴스를 가리키도록</span><span class="sxs-lookup"><span data-stu-id="86d13-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="86d13-106">사용 된 `Me` 키워드 위치는 일반적으로 사용 하는 개체 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="86d13-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="86d13-107">하지만 `Me` 개체 처럼 변수를 선언할 수 없거나 값을 할당할 합니다.</span><span class="sxs-lookup"><span data-stu-id="86d13-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="86d13-108">`Me` 항상 현재 인스턴스를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="86d13-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d13-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="86d13-109">See also</span></span>

- [<span data-ttu-id="86d13-110">개체 변수</span><span class="sxs-lookup"><span data-stu-id="86d13-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="86d13-111">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="86d13-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="86d13-112">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="86d13-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
