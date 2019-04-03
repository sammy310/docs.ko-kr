---
title: "'<name>' 생성자는 자신을 호출할 수 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
ms.openlocfilehash: ef20f74055a07071ef9634973c6852ac58c3143c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824722"
---
# <a name="constructor-name-cannot-call-itself"></a><span data-ttu-id="bbb68-102">생성자 '\<이름 >' 자신을 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb68-102">Constructor '\<name>' cannot call itself</span></span>
<span data-ttu-id="bbb68-103">`Sub New` 클래스 또는 구조체에서 프로시저가 자신을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb68-103">A `Sub New` procedure in a class or structure calls itself.</span></span>  
  
 <span data-ttu-id="bbb68-104">생성자의 목적은 클래스의 인스턴스를 초기화 하는 것 또는 첫 번째 경우 구조체를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb68-104">The purpose of a constructor is to initialize an instance of a class or structure when it is first created.</span></span> <span data-ttu-id="bbb68-105">클래스 또는 구조체는 다른 매개 변수 목록을 모두 제공 된 몇 가지 생성자에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbb68-105">A class or structure can have several constructors, provided they all have different parameter lists.</span></span> <span data-ttu-id="bbb68-106">생성자는 자체 외에도 해당 기능을 수행 하는 다른 생성자를 호출 하도록 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bbb68-106">A constructor is permitted to call another constructor to perform its functionality in addition to its own.</span></span> <span data-ttu-id="bbb68-107">자신을 호출 하는 생성자에 대 한 의미가 없습니다 있고 실제로 결과가 무한 재귀가 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb68-107">But it is meaningless for a constructor to call itself, and in fact it would result in infinite recursion if permitted.</span></span>  
  
 <span data-ttu-id="bbb68-108">**오류 ID:** BC30298</span><span class="sxs-lookup"><span data-stu-id="bbb68-108">**Error ID:** BC30298</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="bbb68-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="bbb68-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="bbb68-110">호출할 생성자의 매개 변수 목록을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb68-110">Check the parameter list of the constructor being called.</span></span> <span data-ttu-id="bbb68-111">호출을 수행 하는 생성자에서 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb68-111">It should be different from that of the constructor making the call.</span></span>  
  
2.  <span data-ttu-id="bbb68-112">다른 생성자를 호출 하지 않을 경우 제거 된 `Sub New` 전적으로 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bbb68-112">If you do not intend to call a different constructor, remove the `Sub New` call entirely.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbb68-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="bbb68-113">See also</span></span>

- [<span data-ttu-id="bbb68-114">개체 수명: 개체가 만들어지고 제거 하는 방법</span><span class="sxs-lookup"><span data-stu-id="bbb68-114">Object Lifetime: How Objects Are Created and Destroyed</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
