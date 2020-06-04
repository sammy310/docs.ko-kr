---
title: "'<membername>'은(는) 상속된 인터페이스 '<interfacename1>' 및 '<interfacename2>'에서 모호합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: f242db9e02a1983e731dce280be0e8f8a8b12712
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397274"
---
# <a name="membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a><span data-ttu-id="d5a3a-102">'\<membername>'은(는) 상속된 인터페이스 '\<interfacename1>' 및 '\<interfacename2>'에서 모호합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a3a-102">'\<membername>' is ambiguous across the inherited interfaces '\<interfacename1>' and '\<interfacename2>'</span></span>
<span data-ttu-id="d5a3a-103">인터페이스는 여러 인터페이스에서 이름이 같은 멤버를 두 개 이상 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5a3a-103">The interface inherits two or more members with the same name from multiple interfaces.</span></span>  
  
 <span data-ttu-id="d5a3a-104">**오류 ID:** BC30685</span><span class="sxs-lookup"><span data-stu-id="d5a3a-104">**Error ID:** BC30685</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d5a3a-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d5a3a-105">To correct this error</span></span>  
  
- <span data-ttu-id="d5a3a-106">사용 하려는 기본 인터페이스로 값을 캐스팅 합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="d5a3a-106">Cast the value to the base interface that you want to use; for example:</span></span>  
  
    ```vb  
    Interface Left  
        Sub MySub()  
    End Interface  
  
    Interface Right  
        Sub MySub()  
    End Interface  
  
    Interface LeftRight  
        Inherits Left, Right  
    End Interface  
  
    Module test  
        Sub Main()  
            Dim x As LeftRight  
            ' x.MySub()  'x is ambiguous.  
            CType(x, Left).MySub() ' Cast to base type.  
            CType(x, Right).MySub() ' Call the other base type.  
        End Sub  
    End Module  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d5a3a-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5a3a-107">See also</span></span>

- [<span data-ttu-id="d5a3a-108">인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5a3a-108">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
