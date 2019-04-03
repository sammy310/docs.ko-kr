---
title: "'AddressOf' 피연산자에는 괄호 없이 메서드 이름을 사용해야 합니다."
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: af1ce858108785fa4dac6352c9e80531e86fbb23
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813966"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a><span data-ttu-id="c4051-102">'AddressOf' 피연산자에는 괄호 없이 메서드 이름을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4051-102">'AddressOf' operand must be the name of a method (without parentheses)</span></span>
<span data-ttu-id="c4051-103">`AddressOf` 연산자는 특정 프로시저를 참조하는 프로시저 대리자 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4051-103">The `AddressOf` operator creates a procedure delegate instance that references a specific procedure.</span></span> <span data-ttu-id="c4051-104">구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c4051-104">The syntax is as follows.</span></span>  
  
 <span data-ttu-id="c4051-105">`AddressOf` `procedurename`</span><span class="sxs-lookup"><span data-stu-id="c4051-105">`AddressOf` `procedurename`</span></span>  
  
 <span data-ttu-id="c4051-106">인수 다음에 괄호를 삽입 `AddressOf`에 불필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4051-106">You inserted parentheses around the argument following `AddressOf`, where none are needed.</span></span>  
  
 <span data-ttu-id="c4051-107">**오류 ID:** BC30577</span><span class="sxs-lookup"><span data-stu-id="c4051-107">**Error ID:** BC30577</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c4051-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="c4051-108">To correct this error</span></span>  
  
1.  <span data-ttu-id="c4051-109">인수 다음에 괄호를 제거 `AddressOf`합니다.</span><span class="sxs-lookup"><span data-stu-id="c4051-109">Remove the parentheses around the argument following `AddressOf`.</span></span>  
  
2.  <span data-ttu-id="c4051-110">인수는 메서드 이름 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c4051-110">Make sure the argument is a method name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4051-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="c4051-111">See also</span></span>

- [<span data-ttu-id="c4051-112">AddressOf 연산자</span><span class="sxs-lookup"><span data-stu-id="c4051-112">AddressOf Operator</span></span>](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [<span data-ttu-id="c4051-113">대리자</span><span class="sxs-lookup"><span data-stu-id="c4051-113">Delegates</span></span>](../../../visual-basic/programming-guide/language-features/delegates/index.md)
