---
title: "'<name>'에 적절한 시그니처가 있는 액세스 가능한 'Main' 메서드가 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 6958e778701066760aa74e3b4d566800b7527b76
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90871482"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="cb127-102">'\<name>'에 적절한 시그니처가 있는 액세스 가능한 'Main' 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb127-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>

<span data-ttu-id="cb127-103">명령줄 응용 프로그램에는가 정의 되어 있어야 합니다 `Sub Main` .</span><span class="sxs-lookup"><span data-stu-id="cb127-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="cb127-104">`Main` 는 클래스에 정의 된 것 처럼 선언 `Public Shared` 하거나 모듈에 정의 된 것 처럼 선언 해야 합니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="cb127-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="cb127-105">**오류 ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="cb127-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cb127-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="cb127-106">To correct this error</span></span>  
  
- <span data-ttu-id="cb127-107">`Public Sub Main`프로젝트에 대 한 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb127-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="cb127-108">`Shared`클래스 내에서 정의 하는 경우에만이를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb127-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb127-109">참조</span><span class="sxs-lookup"><span data-stu-id="cb127-109">See also</span></span>

- [<span data-ttu-id="cb127-110">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="cb127-110">Structure of a Visual Basic Program</span></span>](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="cb127-111">절차</span><span class="sxs-lookup"><span data-stu-id="cb127-111">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
