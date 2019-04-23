---
title: 구조체 멤버로 선언된 배열은 초기 크기로 선언할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: 5d58b531b670715716e849cd37227bc899195df6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335305"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="da860-102">구조체 멤버로 선언된 배열은 초기 크기로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da860-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="da860-103">구조의 배열 초기 크기를 사용 하 여 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da860-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="da860-104">구조체 요소를 초기화할 수 없습니다 및 배열 크기를 선언 하는 것은 한 가지 형태의 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="da860-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="da860-105">**오류 ID:** BC31043</span><span class="sxs-lookup"><span data-stu-id="da860-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="da860-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="da860-106">To correct this error</span></span>  
  
1. <span data-ttu-id="da860-107">동적 (초기 크기)으로 구조에서 배열을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="da860-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2. <span data-ttu-id="da860-108">사용 하 여 동적 배열 차원을 변경할 수 배열의 특정 크기에 필요한 경우는 [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md) 코드를 실행 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="da860-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="da860-109">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="da860-109">The following example illustrates this.</span></span>  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="da860-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="da860-110">See also</span></span>

- [<span data-ttu-id="da860-111">배열</span><span class="sxs-lookup"><span data-stu-id="da860-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="da860-112">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="da860-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
