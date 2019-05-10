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
ms.openlocfilehash: 70955cd55dfb91d4111e59ae58bfe409a4470433
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64663537"
---
# <a name="how-to-refer-to-the-current-instance-of-an-object-visual-basic"></a><span data-ttu-id="cc083-102">방법: 개체 (Visual Basic)의 현재 인스턴스 참조</span><span class="sxs-lookup"><span data-stu-id="cc083-102">How to: Refer to the Current Instance of an Object (Visual Basic)</span></span>
<span data-ttu-id="cc083-103">합니다 *현재 인스턴스* 는 코드가 현재 실행 중인 개체의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc083-103">The *current instance* of an object is the instance in which the code is currently executing.</span></span>  
  
 <span data-ttu-id="cc083-104">사용할는 `Me` 키워드를 현재 인스턴스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc083-104">You use the `Me` keyword to refer to the current instance.</span></span>  
  
### <a name="to-refer-to-the-current-instance"></a><span data-ttu-id="cc083-105">현재 인스턴스를 가리키도록</span><span class="sxs-lookup"><span data-stu-id="cc083-105">To refer to the current instance</span></span>  
  
- <span data-ttu-id="cc083-106">사용 된 `Me` 키워드 위치는 일반적으로 사용 하는 개체 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cc083-106">Use the `Me` keyword where you would normally use the name of an object variable.</span></span>  
  
    ```  
    Me.ForeColor = System.Drawing.Color.Crimson  
    Me.Close()  
    ```  
  
     <span data-ttu-id="cc083-107">하지만 `Me` 개체 처럼 변수를 선언할 수 없거나 값을 할당할 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc083-107">Although `Me` behaves like an object variable, you cannot declare it or assign anything to it.</span></span> <span data-ttu-id="cc083-108">`Me` 항상 현재 인스턴스를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="cc083-108">`Me` always refers to the current instance.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc083-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="cc083-109">See also</span></span>

- [<span data-ttu-id="cc083-110">개체 변수</span><span class="sxs-lookup"><span data-stu-id="cc083-110">Object Variables</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [<span data-ttu-id="cc083-111">개체 변수 할당</span><span class="sxs-lookup"><span data-stu-id="cc083-111">Object Variable Assignment</span></span>](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [<span data-ttu-id="cc083-112">Me, My, MyBase 및 MyClass</span><span class="sxs-lookup"><span data-stu-id="cc083-112">Me, My, MyBase, and MyClass</span></span>](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
