---
description: "자세한 정보: BC30737: ' '에서 적절 한 시그니처가 있는 액세스 가능한 ' Main ' 메서드를 찾을 수 없습니다. <name>"
title: "'<name>'에 적절한 시그니처가 있는 액세스 가능한 'Main' 메서드가 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords:
- BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
ms.openlocfilehash: 5ff79c1b7589f6b67492ad640179f7a852a2f381
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483523"
---
# <a name="bc30737-no-accessible-main-method-with-an-appropriate-signature-was-found-in-name"></a><span data-ttu-id="1a8e6-103">BC30737: ' '에서 적절 한 시그니처가 있는 액세스 가능한 ' Main ' 메서드를 찾을 수 없습니다. \<name></span><span class="sxs-lookup"><span data-stu-id="1a8e6-103">BC30737: No accessible 'Main' method with an appropriate signature was found in '\<name>'</span></span>

<span data-ttu-id="1a8e6-104">명령줄 응용 프로그램에는가 정의 되어 있어야 합니다 `Sub Main` .</span><span class="sxs-lookup"><span data-stu-id="1a8e6-104">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="1a8e6-105">`Main` 는 클래스에 정의 된 것 처럼 선언 `Public Shared` 하거나 모듈에 정의 된 것 처럼 선언 해야 합니다 `Public` .</span><span class="sxs-lookup"><span data-stu-id="1a8e6-105">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>

 <span data-ttu-id="1a8e6-106">**오류 ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="1a8e6-106">**Error ID:** BC30737</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1a8e6-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1a8e6-107">To correct this error</span></span>

- <span data-ttu-id="1a8e6-108">`Public Sub Main`프로젝트에 대 한 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8e6-108">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="1a8e6-109">`Shared`클래스 내에서 정의 하는 경우에만이를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a8e6-109">Declare it as `Shared` if and only if you define it inside a class.</span></span>

## <a name="see-also"></a><span data-ttu-id="1a8e6-110">추가 정보</span><span class="sxs-lookup"><span data-stu-id="1a8e6-110">See also</span></span>

- [<span data-ttu-id="1a8e6-111">Visual Basic 프로그램의 구조</span><span class="sxs-lookup"><span data-stu-id="1a8e6-111">Structure of a Visual Basic Program</span></span>](../../programming-guide/program-structure/structure-of-a-visual-basic-program.md)
- [<span data-ttu-id="1a8e6-112">절차</span><span class="sxs-lookup"><span data-stu-id="1a8e6-112">Procedures</span></span>](../../programming-guide/language-features/procedures/index.md)
