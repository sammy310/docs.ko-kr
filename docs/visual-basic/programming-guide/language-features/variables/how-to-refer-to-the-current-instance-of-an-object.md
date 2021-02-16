---
description: '자세히 알아보기: 방법: 개체의 현재 인스턴스 참조 (Visual Basic)'
title: '방법: 개체의 현재 인스턴스 참조'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], object
- objects [Visual Basic], referring to current instance
- instances [Visual Basic], referring to current
- current instance
- object variables [Visual Basic]
ms.assetid: 7f9b2c77-03cd-428f-adc2-b18070226e7c
ms.openlocfilehash: 84a52c9d0a8b1f588630b31d022490f37595850d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100481742"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="bd143-103">방법: 개체의 현재 인스턴스 참조(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bd143-103">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>

<span data-ttu-id="bd143-104">개체의 *현재 인스턴스* 는 코드가 현재 실행 중인 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="bd143-104">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="bd143-105">키워드를 사용 하 여 `Me` 현재 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd143-105">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="bd143-106">현재 인스턴스를 참조 하려면</span><span class="sxs-lookup"><span data-stu-id="bd143-106">To refer to the current instance</span></span>  
  
- <span data-ttu-id="bd143-107">`Me`일반적으로 개체 변수 이름을 사용 하는 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd143-107">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```vb  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="bd143-108">`Me`는 개체 변수 처럼 동작 하지만이를 선언 하거나 할당할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd143-108">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="bd143-109">`Me` 항상 현재 인스턴스를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd143-109">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd143-110">추가 정보</span><span class="sxs-lookup"><span data-stu-id="bd143-110">See also</span></span>

- [<span data-ttu-id="bd143-111">개체 변수</span><span class="sxs-lookup"><span data-stu-id="bd143-111">Object Variables</span></span>](object-variables.md)
- [<span data-ttu-id="bd143-112">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="bd143-112">Object Variable Assignment</span></span>](object-variable-assignment.md)
- [<span data-ttu-id="bd143-113">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="bd143-113">Me, My, MyBase, and MyClass</span></span>](../../program-structure/me-my-mybase-and-myclass.md)
