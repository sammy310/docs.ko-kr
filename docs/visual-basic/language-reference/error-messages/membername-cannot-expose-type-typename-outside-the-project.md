---
description: "자세한 내용은 BC30909: ' '에서 ' ' <membername> <typename> 을 통해 프로젝트 외부에 ' ' 형식을 노출할 수 없습니다 <containertype> . '<containertypename>"
title: "'<membername>'은(는) <typename> '<containertype>'을(를) 통해 '<containertypename>' 형식을 프로젝트 외부로 노출할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30909
- vbc30909
helpviewer_keywords:
- BC30909
ms.assetid: ffa7395d-e182-4087-8ce8-079810fdae54
ms.openlocfilehash: e2cc1d950b646bb787dfe714c39efea78a530129
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795861"
---
# <a name="bc30909-membername-cannot-expose-type-typename-outside-the-project-through-containertype-containertypename"></a><span data-ttu-id="7b780-103">BC30909: ' '는 ' ' \<membername> \<typename> 을 통해 프로젝트 외부의 ' \<containertype> ' 형식을 노출할 수 없습니다. \<containertypename></span><span class="sxs-lookup"><span data-stu-id="7b780-103">BC30909: '\<membername>' cannot expose type '\<typename>' outside the project through \<containertype> '\<containertypename>'</span></span>

<span data-ttu-id="7b780-104">변수, 프로시저 매개 변수 또는 함수 반환은 해당 컨테이너 외부에 노출 되지만 컨테이너 외부에 노출 되지 않아야 하는 형식으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b780-104">A variable, procedure parameter, or function return is exposed outside its container, but it is declared as a type that must not be exposed outside the container.</span></span>

 <span data-ttu-id="7b780-105">다음 기본 코드는이 오류를 생성 하는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b780-105">The following skeleton code shows a situation that generates this error.</span></span>

```vb
Private Class privateClass
End Class
Public Class mainClass
    Public exposedVar As New privateClass
End Class
```

 <span data-ttu-id="7b780-106">,, 또는로 선언 된 형식은 `Protected` `Friend` `Protected Friend` `Private` 선언 컨텍스트 외부에서 제한 된 액세스를 제공 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b780-106">A type that is declared `Protected`, `Friend`, `Protected Friend`, or `Private` is intended to have limited access outside its declaration context.</span></span> <span data-ttu-id="7b780-107">제한 된 액세스 권한이 있는 변수의 데이터 형식으로 사용 하면 이러한 목적이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="7b780-107">Using it as the data type of a variable with less restricted access would defeat this purpose.</span></span> <span data-ttu-id="7b780-108">위의 기본 코드에서는 이며 `exposedVar` `Public` 에 액세스할 수 없는 `privateClass` 코드에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b780-108">In the preceding skeleton code, `exposedVar` is `Public` and would expose `privateClass` to code that should not have access to it.</span></span>

 <span data-ttu-id="7b780-109">**오류 ID:** BC30909</span><span class="sxs-lookup"><span data-stu-id="7b780-109">**Error ID:** BC30909</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7b780-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7b780-110">To correct this error</span></span>

- <span data-ttu-id="7b780-111">변수, 프로시저 매개 변수 또는 함수 반환의 액세스 수준을 해당 데이터 형식의 액세스 수준 보다 최소한 제한적으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b780-111">Change the access level of the variable, procedure parameter, or function return to be at least as restrictive as the access level of its data type.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b780-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b780-112">See also</span></span>

- [<span data-ttu-id="7b780-113">Visual Basic의 액세스 수준</span><span class="sxs-lookup"><span data-stu-id="7b780-113">Access levels in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/access-levels.md)
