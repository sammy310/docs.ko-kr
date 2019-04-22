---
title: "'<membername>'은(는) <typename> '<containertype>'을(를) 통해 '<containertypename>' 형식을 프로젝트 외부로 노출할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: 16f579a05236ba8977a071cb08068be8e98799f8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818346"
---
# <a name="membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="1c4c4-102">'\<membername >' 형식을 노출할 수 없습니다 '\<typename >'를 통해 프로젝트 외부 \<containertype > '\<containertypename >'</span><span class="sxs-lookup"><span data-stu-id="1c4c4-102">'\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>
<span data-ttu-id="1c4c4-103">변수, 프로시저 매개 변수 또는 함수 반환 해당 컨테이너 외부에 노출 됩니다 있지만 컨테이너 외부 하지 노출 해야 하는 형식으로 선언 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-103">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>  
  
 <span data-ttu-id="1c4c4-104">다음 기본 코드를이 오류를 생성 하는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-104">The following skeleton code shows a situation that generates this error.</span></span>  
  
```  
Private Class privateClass  
End Class  
Public Class mainClass  
    Public exposedVar As New privateClass  
End Class  
```  
  
 <span data-ttu-id="1c4c4-105">선언 된 형식을 `Protected`, `Friend`를 `Protected Friend`, 또는 `Private` 해당 선언 컨텍스트 외부 액세스가 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-105">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="1c4c4-106">사용 하 여 데이터와 덜 제한적인된 액세스를 사용 하 여 변수 형식을 벗어나는이 목적입니다.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-106">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="1c4c4-107">앞의 기본 코드에서 `exposedVar` 은 `Public` 노출 및 `privateClass` 액세스할 수 없어야 하는 코드를 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-107">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>  
  
 <span data-ttu-id="1c4c4-108">**오류 ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="1c4c4-108">**Error ID:** BC30909</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1c4c4-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1c4c4-109">To correct this error</span></span>  
  
-   <span data-ttu-id="1c4c4-110">변수, 프로시저 매개 변수 또는 함수에 대 한 액세스 수준을 변경 하는 최소 제한적으로 해당 데이터 형식의 액세스 수준을 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="1c4c4-110">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4c4-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="1c4c4-111">See also</span></span>

- [<span data-ttu-id="1c4c4-112">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="1c4c4-112">Access levels in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
