---
description: "자세한 정보: BC30685: ' ' <membername> 이 (가) 상속 된 인터페이스 ' <interfacename1> ' 및 ' '에서 모호 합니다. <interfacename2>"
title: "'<membername>'은(는) 상속된 인터페이스 '<interfacename1>' 및 '<interfacename2>'에서 모호합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30685
- bc30685
helpviewer_keywords:
- BC30685
ms.assetid: 756add7a-23d5-4b4f-a48d-8297d6459c73
ms.openlocfilehash: cb8d5da2f95cca5a1668a19dbc1ec313732882ad
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471034"
---
# <a name="bc30685-membername-is-ambiguous-across-the-inherited-interfaces-interfacename1-and-interfacename2"></a><span data-ttu-id="522be-103">BC30685: ' '은 (는) \<membername> 상속 된 인터페이스 ' \<interfacename1> ' 및 ' \<interfacename2> '에서 모호 합니다.</span><span class="sxs-lookup"><span data-stu-id="522be-103">BC30685: '\<membername>' is ambiguous across the inherited interfaces '\<interfacename1>' and '\<interfacename2>'</span></span>

<span data-ttu-id="522be-104">인터페이스는 여러 인터페이스에서 이름이 같은 멤버를 두 개 이상 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="522be-104">The interface inherits two or more members with the same name from multiple interfaces.</span></span>

 <span data-ttu-id="522be-105">**오류 ID:** BC30685</span><span class="sxs-lookup"><span data-stu-id="522be-105">**Error ID:** BC30685</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="522be-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="522be-106">To correct this error</span></span>

- <span data-ttu-id="522be-107">사용 하려는 기본 인터페이스로 값을 캐스팅 합니다. 예를 들어:</span><span class="sxs-lookup"><span data-stu-id="522be-107">Cast the value to the base interface that you want to use; for example:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="522be-108">추가 정보</span><span class="sxs-lookup"><span data-stu-id="522be-108">See also</span></span>

- [<span data-ttu-id="522be-109">인터페이스</span><span class="sxs-lookup"><span data-stu-id="522be-109">Interfaces</span></span>](../../programming-guide/language-features/interfaces/index.md)
