---
title: 식별자가 너무 깁니다.
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: 52d69bc1681c387fc686f2b4b223336286e82259
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402877"
---
# <a name="identifier-is-too-long"></a><span data-ttu-id="21b15-102">식별자가 너무 깁니다.</span><span class="sxs-lookup"><span data-stu-id="21b15-102">Identifier is too long</span></span>
<span data-ttu-id="21b15-103">모든 프로그래밍 요소의 이름 또는 식별자는 1023 자로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21b15-103">The name, or identifier, of every programming element is limited to 1023 characters.</span></span> <span data-ttu-id="21b15-104">또한 정규화 된 이름은 1023 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="21b15-104">In addition, a fully qualified name cannot exceed 1023 characters.</span></span> <span data-ttu-id="21b15-105">즉, 전체 식별자 문자열 ()은 `<namespace>.<...>.<namespace>.<class>.<element>` 멤버 액세스 연산자 () 문자를 포함 하 여 1023 자를 초과할 수 없습니다 `.` .</span><span class="sxs-lookup"><span data-stu-id="21b15-105">This means that the entire identifier string (`<namespace>.<...>.<namespace>.<class>.<element>`) cannot be more than 1023 characters long, including the member-access operator (`.`) characters.</span></span>  
  
 <span data-ttu-id="21b15-106">**오류 ID:** BC30033</span><span class="sxs-lookup"><span data-stu-id="21b15-106">**Error ID:** BC30033</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="21b15-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="21b15-107">To correct this error</span></span>  
  
- <span data-ttu-id="21b15-108">식별자의 길이를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="21b15-108">Reduce the length of the identifier.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b15-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21b15-109">See also</span></span>

- [<span data-ttu-id="21b15-110">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="21b15-110">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
