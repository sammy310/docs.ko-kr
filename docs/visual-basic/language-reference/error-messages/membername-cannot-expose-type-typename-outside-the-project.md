---
title: "'<membername>'은(는) <typename> '<containertype>'을(를) 통해 '<containertypename>' 형식을 프로젝트 외부로 노출할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 729a9f385d94412469d318cb804d216827eeb0fd
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397287"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="ce0a7-102">'\<membername>'은(는) \<typename> '\<containertype>'을(를) 통해 '\<containertypename>' 형식을 프로젝트 외부로 노출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="ce0a7-103">변수, 프로시저 매개 변수 또는 함수 반환은 해당 컨테이너 외부에 노출 되지만 컨테이너 외부에 노출 되지 않아야 하는 형식으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="ce0a7-104">다음 기본 코드는이 오류를 생성 하는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```vb  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="ce0a7-105">,, 또는로 선언 된 형식은 `Protected` `Friend` `Protected Friend` `Private` 선언 컨텍스트 외부에서 제한 된 액세스를 제공 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="ce0a7-106">제한 된 액세스 권한이 있는 변수의 데이터 형식으로 사용 하면 이러한 목적이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="ce0a7-107">위의 기본 코드에서는 이며 `exposedVar` `Public` 에 액세스할 수 없는 `privateClass` 코드에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="ce0a7-108">**오류 ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="ce0a7-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ce0a7-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ce0a7-109">To correct this error</span></span>  
  
- <span data-ttu-id="ce0a7-110">변수, 프로시저 매개 변수 또는 함수 반환의 액세스 수준을 해당 데이터 형식의 액세스 수준 보다 최소한 제한적으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0a7-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce0a7-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce0a7-111">See also</span></span>

- [<span data-ttu-id="ce0a7-112">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="ce0a7-112">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
