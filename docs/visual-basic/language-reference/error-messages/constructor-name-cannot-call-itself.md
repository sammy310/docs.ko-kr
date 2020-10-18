---
title: "'<name>' 생성자는 자신을 호출할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: f40319cde8388b17e27cfaec2117ebd519ebd4ff
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160947"
---
# <a name="bc30298-constructor-name-cannot-call-itself"></a><span data-ttu-id="bae5d-102">BC30298: ' ' 생성자는 \<name> 자신을 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bae5d-102">BC30298: Constructor '\<name>' cannot call itself</span></span>

<span data-ttu-id="bae5d-103">`Sub New`클래스 또는 구조체의 프로시저는 자신을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae5d-103">A `Sub New` procedure in a class or structure calls itself.</span></span>

 <span data-ttu-id="bae5d-104">생성자의 목적은 클래스 또는 구조체를 처음 만들 때이 인스턴스를 초기화 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bae5d-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="bae5d-105">클래스 또는 구조체에는 여러 개의 생성자가 있을 수 있으며,이 경우 모두 매개 변수 목록이 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="bae5d-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="bae5d-106">생성자는 다른 생성자를 호출 하 여 자체와 함께 해당 기능을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bae5d-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="bae5d-107">그러나 생성자가 자신을 호출 하는 것은 의미가 없으므로 허용 되는 경우 무한 재귀가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae5d-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>

 <span data-ttu-id="bae5d-108">**오류 ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="bae5d-108">**Error ID:** BC30298</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="bae5d-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="bae5d-109">To correct this error</span></span>

1. <span data-ttu-id="bae5d-110">호출 되는 생성자의 매개 변수 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae5d-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="bae5d-111">호출 하는 생성자의 생성자와 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae5d-111">It should be different from that of the constructor making the call.</span></span>

2. <span data-ttu-id="bae5d-112">다른 생성자를 호출 하지 않으려는 경우 `Sub New` 호출을 완전히 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="bae5d-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>

## <a name="see-also"></a><span data-ttu-id="bae5d-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bae5d-113">See also</span></span>

- [<span data-ttu-id="bae5d-114">개체 수명: 개체가 만들어지고 제거되는 방법</span><span class="sxs-lookup"><span data-stu-id="bae5d-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
