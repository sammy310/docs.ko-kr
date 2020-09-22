---
title: 메서드(multiline lambda) 내에서 명령문을 사용할 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbc30024
- bc30024
helpviewer_keywords:
- BC30024
ms.assetid: 758e7a8f-429b-42c1-9a78-778e5b480e04
ms.openlocfilehash: d5d756f1772b9519613e163119b88a3057d36cf3
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870619"
---
# <a name="statement-is-not-valid-inside-a-methodmultiline-lambda"></a><span data-ttu-id="ea01d-102">메서드 내부에는 문을 사용할 수 없습니다./multiline lambda</span><span class="sxs-lookup"><span data-stu-id="ea01d-102">Statement is not valid inside a method/multiline lambda</span></span>

<span data-ttu-id="ea01d-103">`Sub`, `Function` , 속성 `Get` 또는 속성 프로시저 내에서 문을 사용할 수 없습니다 `Set` .</span><span class="sxs-lookup"><span data-stu-id="ea01d-103">The statement is not valid within a `Sub`, `Function`, property `Get`, or property `Set` procedure.</span></span> <span data-ttu-id="ea01d-104">일부 문은 모듈 또는 클래스 수준에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea01d-104">Some statements can be placed at the module or class level.</span></span> <span data-ttu-id="ea01d-105">등의 다른 항목은 `Option Strict` 네임 스페이스 수준에 있어야 하 고 다른 모든 선언 앞에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea01d-105">Others, such as `Option Strict`, must be at namespace level and precede all other declarations.</span></span>  
  
 <span data-ttu-id="ea01d-106">**오류 ID:** BC30024</span><span class="sxs-lookup"><span data-stu-id="ea01d-106">**Error ID:** BC30024</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ea01d-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="ea01d-107">To correct this error</span></span>  
  
- <span data-ttu-id="ea01d-108">프로시저에서 문을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea01d-108">Remove the statement from the procedure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea01d-109">참조</span><span class="sxs-lookup"><span data-stu-id="ea01d-109">See also</span></span>

- [<span data-ttu-id="ea01d-110">Sub 문</span><span class="sxs-lookup"><span data-stu-id="ea01d-110">Sub Statement</span></span>](../statements/sub-statement.md)
- [<span data-ttu-id="ea01d-111">Function 문</span><span class="sxs-lookup"><span data-stu-id="ea01d-111">Function Statement</span></span>](../statements/function-statement.md)
- [<span data-ttu-id="ea01d-112">Get 문</span><span class="sxs-lookup"><span data-stu-id="ea01d-112">Get Statement</span></span>](../statements/get-statement.md)
- [<span data-ttu-id="ea01d-113">Set 문</span><span class="sxs-lookup"><span data-stu-id="ea01d-113">Set Statement</span></span>](../statements/set-statement.md)
