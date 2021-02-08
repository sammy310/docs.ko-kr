---
description: '자세히 알아보기: BC30033: 식별자가 너무 깁니다.'
title: 식별자가 너무 깁니다.
ms.date: 07/20/2015
f1_keywords:
- bc30033
- vbc30033
helpviewer_keywords:
- BC30033
ms.assetid: 3d07f6d0-9a2f-49ca-94e8-1e354932e855
ms.openlocfilehash: f2439c4bfc53f906fdc277b0de1faac0941c8808
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796095"
---
# <a name="bc30033-identifier-is-too-long"></a><span data-ttu-id="05f20-103">BC30033: 식별자가 너무 깁니다.</span><span class="sxs-lookup"><span data-stu-id="05f20-103">BC30033: Identifier is too long</span></span>

<span data-ttu-id="05f20-104">모든 프로그래밍 요소의 이름 또는 식별자는 1023 자로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05f20-104">The name, or identifier, of every programming element is limited to 1023 characters.</span></span> <span data-ttu-id="05f20-105">또한 정규화 된 이름은 1023 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="05f20-105">In addition, a fully qualified name cannot exceed 1023 characters.</span></span> <span data-ttu-id="05f20-106">즉, 전체 식별자 문자열 ()은 `<namespace>.<...>.<namespace>.<class>.<element>` 멤버 액세스 연산자 () 문자를 포함 하 여 1023 자를 초과할 수 없습니다 `.` .</span><span class="sxs-lookup"><span data-stu-id="05f20-106">This means that the entire identifier string (`<namespace>.<...>.<namespace>.<class>.<element>`) cannot be more than 1023 characters long, including the member-access operator (`.`) characters.</span></span>

 <span data-ttu-id="05f20-107">**오류 ID:** BC30033</span><span class="sxs-lookup"><span data-stu-id="05f20-107">**Error ID:** BC30033</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="05f20-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="05f20-108">To correct this error</span></span>

- <span data-ttu-id="05f20-109">식별자의 길이를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="05f20-109">Reduce the length of the identifier.</span></span>

## <a name="see-also"></a><span data-ttu-id="05f20-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05f20-110">See also</span></span>

- [<span data-ttu-id="05f20-111">Declared Element Names</span><span class="sxs-lookup"><span data-stu-id="05f20-111">Declared Element Names</span></span>](../../programming-guide/language-features/declared-elements/declared-element-names.md)
