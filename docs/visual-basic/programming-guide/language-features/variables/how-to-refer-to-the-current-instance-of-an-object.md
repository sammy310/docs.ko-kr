---
title: '방법: 개체의 현재 인스턴스 참조'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 64d21fe4aaf6fd34bf880373a7ab3067fb67820e
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91077061"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="508b0-102">방법: 개체의 현재 인스턴스 참조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="508b0-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>

<span data-ttu-id="508b0-103">개체의 *현재 인스턴스* 는 코드가 현재 실행 중인 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="508b0-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="508b0-104">키워드를 사용 하 여 `Me` 현재 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="508b0-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="508b0-105">현재 인스턴스를 참조 하려면</span><span class="sxs-lookup"><span data-stu-id="508b0-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="508b0-106">`Me`일반적으로 개체 변수 이름을 사용 하는 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="508b0-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="508b0-107">`Me`는 개체 변수 처럼 동작 하지만이를 선언 하거나 할당할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="508b0-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="508b0-108">`Me` 항상 현재 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="508b0-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="508b0-109">참조</span><span class="sxs-lookup"><span data-stu-id="508b0-109">See also</span></span>

- [<span data-ttu-id="508b0-110">개체 변수</span><span class="sxs-lookup"><span data-stu-id="508b0-110">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="508b0-111">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="508b0-111">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="508b0-112">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="508b0-112">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
