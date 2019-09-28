---
title: 형식 매개 변수는 한정자로 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc32098
- bc32098
helpviewer_keywords:
- BC32098
ms.assetid: bab05325-dde8-4621-a5f6-368b5b7b2d76
ms.openlocfilehash: 88b5f365c47b98964d9f5a0d22a941d85dcfb95f
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592142"
---
# <a name="type-parameters-cannot-be-used-as-qualifiers"></a><span data-ttu-id="b7c8d-102">형식 매개 변수는 한정자로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c8d-102">Type parameters cannot be used as qualifiers</span></span>
<span data-ttu-id="b7c8d-103">프로그래밍 요소는 형식 매개 변수를 포함 하는 한정 문자열을 사용 하 여 정규화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7c8d-103">A programming element is qualified with a qualification string that includes a type parameter.</span></span>  
  
 <span data-ttu-id="b7c8d-104">형식 매개 변수는 제네릭 형식이 생성 될 때 제공 되는 형식에 대 한 요구 사항을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7c8d-104">A type parameter represents a requirement for a type that is to be supplied when the generic type is constructed.</span></span> <span data-ttu-id="b7c8d-105">특정 정의 된 형식을 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c8d-105">It does not represent a specific defined type.</span></span> <span data-ttu-id="b7c8d-106">정규화 문자열에는 컴파일 시간에 정의 된 요소만 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c8d-106">A qualification string must include only elements that are defined at compile time.</span></span>  
  
 <span data-ttu-id="b7c8d-107">다음 문은 이 오류를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7c8d-107">The following statements can generate this error.</span></span>  
  
```vb  
Public Function checkText(Of c As System.Windows.Forms.Control)(  
    ByVal badText As String) As Boolean  
  
    Dim saveText As c.Text  
    ' Insert code to look for badText within saveText.  
End Function  
```  
  
 <span data-ttu-id="b7c8d-108">**오류 ID:** BC32098</span><span class="sxs-lookup"><span data-stu-id="b7c8d-108">**Error ID:** BC32098</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b7c8d-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="b7c8d-109">To correct this error</span></span>  
  
1. <span data-ttu-id="b7c8d-110">정규화 문자열에서 형식 매개 변수를 제거 하거나 정의 된 형식으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b7c8d-110">Remove the type parameter from the qualification string, or replace it with a defined type.</span></span>  
  
2. <span data-ttu-id="b7c8d-111">정규화 된 프로그래밍 요소를 찾기 위해 생성 된 형식을 사용 해야 하는 경우에는 추가 프로그램 논리를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7c8d-111">If you need to use a constructed type to locate the programming element being qualified, you must use additional program logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7c8d-112">참조</span><span class="sxs-lookup"><span data-stu-id="b7c8d-112">See also</span></span>

- [<span data-ttu-id="b7c8d-113">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="b7c8d-113">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [<span data-ttu-id="b7c8d-114">Generic Types in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b7c8d-114">Generic Types in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [<span data-ttu-id="b7c8d-115">형식 목록</span><span class="sxs-lookup"><span data-stu-id="b7c8d-115">Type List</span></span>](../../../visual-basic/language-reference/statements/type-list.md)
