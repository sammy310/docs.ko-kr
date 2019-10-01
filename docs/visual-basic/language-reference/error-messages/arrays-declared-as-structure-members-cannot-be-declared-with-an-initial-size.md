---
title: 구조체 멤버로 선언된 배열은 초기 크기로 선언할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
ms.openlocfilehash: de9d77aa9ea853b6f044e91878044115588ca77c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701244"
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a><span data-ttu-id="b32eb-102">구조체 멤버로 선언된 배열은 초기 크기로 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b32eb-102">Arrays declared as structure members cannot be declared with an initial size</span></span>
<span data-ttu-id="b32eb-103">구조체의 배열은 초기 크기로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b32eb-103">An array in a structure is declared with an initial size.</span></span> <span data-ttu-id="b32eb-104">구조체 요소를 초기화할 수 없으며 배열 크기를 선언 하는 것은 초기화의 한 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="b32eb-104">You cannot initialize any structure element, and declaring an array size is one form of initialization.</span></span>  
  
 <span data-ttu-id="b32eb-105">**오류 ID:** BC31043</span><span class="sxs-lookup"><span data-stu-id="b32eb-105">**Error ID:** BC31043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b32eb-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b32eb-106">To correct this error</span></span>  
  
1. <span data-ttu-id="b32eb-107">구조체의 배열을 동적 (초기 크기 없음)으로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b32eb-107">Define the array in your structure as dynamic (no initial size).</span></span>  
  
2. <span data-ttu-id="b32eb-108">특정 크기의 배열이 필요한 경우 코드가 실행 중일 때 [ReDim 문으로](../../../visual-basic/language-reference/statements/redim-statement.md) 동적 배열의 크기를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b32eb-108">If you require a certain size of array, you can redimension a dynamic array with a [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md) when your code is running.</span></span> <span data-ttu-id="b32eb-109">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b32eb-109">The following example illustrates this.</span></span>  
  
    ```vb  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b32eb-110">참조</span><span class="sxs-lookup"><span data-stu-id="b32eb-110">See also</span></span>

- [<span data-ttu-id="b32eb-111">배열</span><span class="sxs-lookup"><span data-stu-id="b32eb-111">Arrays</span></span>](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="b32eb-112">방법: 구조 선언</span><span class="sxs-lookup"><span data-stu-id="b32eb-112">How to: Declare a Structure</span></span>](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
