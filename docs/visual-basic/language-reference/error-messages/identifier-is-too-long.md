---
title: 식별자가 너무 깁니다.
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: 084e3d9306ad84d7e6e36e5fe4bbfc868b8dfac6
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874000"
---
# <a name="identifier-is-too-long"></a><span data-ttu-id="82ef0-102">식별자가 너무 깁니다.</span><span class="sxs-lookup"><span data-stu-id="82ef0-102">Identifier is too long</span></span>

<span data-ttu-id="82ef0-103">모든 프로그래밍 요소의 이름 또는 식별자는 1023 자로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="82ef0-103">The name, or identifier, of every programming element is limited to 1023 characters.</span></span> <span data-ttu-id="82ef0-104">또한 정규화 된 이름은 1023 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="82ef0-104">In addition, a fully qualified name cannot exceed 1023 characters.</span></span> <span data-ttu-id="82ef0-105">즉, 전체 식별자 문자열 ()은 `<namespace>.<...>.<namespace>.<class>.<element>` 멤버 액세스 연산자 () 문자를 포함 하 여 1023 자를 초과할 수 없습니다 `.` .</span><span class="sxs-lookup"><span data-stu-id="82ef0-105">This means that the entire identifier string (`<namespace>.<...>.<namespace>.<class>.<element>`) cannot be more than 1023 characters long, including the member-access operator (`.`) characters.</span></span>  
  
 <span data-ttu-id="82ef0-106">**오류 ID:** BC30033</span><span class="sxs-lookup"><span data-stu-id="82ef0-106">**Error ID:** BC30033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="82ef0-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="82ef0-107">To correct this error</span></span>  
  
- <span data-ttu-id="82ef0-108">식별자의 길이를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="82ef0-108">Reduce the length of the identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82ef0-109">참조</span><span class="sxs-lookup"><span data-stu-id="82ef0-109">See also</span></span>

- [<span data-ttu-id="82ef0-110">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="82ef0-110">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
