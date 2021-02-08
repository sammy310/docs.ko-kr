---
description: "자세히 알아보기: BC30298: ' ' 생성자는 <name> 자신을 호출할 수 없습니다."
title: "'<name>' 생성자는 자신을 호출할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: 486495eb822e3e3008382232091fe3923851f97c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796719"
---
# <a name="bc30298-constructor-name-cannot-call-itself"></a><span data-ttu-id="7dd2f-103">BC30298: ' ' 생성자는 \<name> 자신을 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-103">BC30298: Constructor '\<name>' cannot call itself</span></span>

<span data-ttu-id="7dd2f-104">`Sub New`클래스 또는 구조체의 프로시저는 자신을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-104">A `Sub New` procedure in a class or structure calls itself.</span></span>

 <span data-ttu-id="7dd2f-105">생성자의 목적은 클래스 또는 구조체를 처음 만들 때이 인스턴스를 초기화 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-105">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="7dd2f-106">클래스 또는 구조체에는 여러 개의 생성자가 있을 수 있으며,이 경우 모두 매개 변수 목록이 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-106">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="7dd2f-107">생성자는 다른 생성자를 호출 하 여 자체와 함께 해당 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-107">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="7dd2f-108">그러나 생성자가 자신을 호출 하는 것은 의미가 없으므로 허용 되는 경우 무한 재귀가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-108">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>

 <span data-ttu-id="7dd2f-109">**오류 ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="7dd2f-109">**Error ID:** BC30298</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="7dd2f-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7dd2f-110">To correct this error</span></span>

1. <span data-ttu-id="7dd2f-111">호출 되는 생성자의 매개 변수 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-111">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="7dd2f-112">호출 하는 생성자의 생성자와 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-112">It should be different from that of the constructor making the call.</span></span>

2. <span data-ttu-id="7dd2f-113">다른 생성자를 호출 하지 않으려는 경우 `Sub New` 호출을 완전히 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7dd2f-113">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>

## <a name="see-also"></a><span data-ttu-id="7dd2f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7dd2f-114">See also</span></span>

- [<span data-ttu-id="7dd2f-115">개체 수명: 개체가 만들어지고 제거되는 방법</span><span class="sxs-lookup"><span data-stu-id="7dd2f-115">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
