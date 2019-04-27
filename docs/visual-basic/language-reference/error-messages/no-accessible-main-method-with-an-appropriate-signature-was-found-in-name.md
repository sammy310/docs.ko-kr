---
title: "'<name>'에 적절한 시그니처가 있는 액세스 가능한 'Main' 메서드가 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: f5053bddf4b9ba791ad6d0733e1dd89c4ded91bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918270"
---
# <a name="no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="35d71-102">적절 한 시그니처가 있는 액세스 가능한 'Main' 메서드가 없습니다에서 찾을 수 '\<이름 >'</span><span class="sxs-lookup"><span data-stu-id="35d71-102">No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>
<span data-ttu-id="35d71-103">명령줄 응용 프로그램에 있어야는 `Sub Main` 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="35d71-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="35d71-104">`Main` 로 선언 되어야 합니다 `Public Shared` 또는 클래스에서 정의 된 경우 `Public` 모듈에 정의 된 경우.</span><span class="sxs-lookup"><span data-stu-id="35d71-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="35d71-105">**오류 ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="35d71-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="35d71-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="35d71-106">To correct this error</span></span>  
  
-   <span data-ttu-id="35d71-107">정의 `Public Sub Main` 프로젝트에 대 한 절차입니다.</span><span class="sxs-lookup"><span data-stu-id="35d71-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="35d71-108">로 선언 `Shared` 클래스 내에서 정의 하는 경우에 합니다.</span><span class="sxs-lookup"><span data-stu-id="35d71-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d71-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="35d71-109">See also</span></span>

- [<span data-ttu-id="35d71-110">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="35d71-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="35d71-111">절차</span><span class="sxs-lookup"><span data-stu-id="35d71-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
