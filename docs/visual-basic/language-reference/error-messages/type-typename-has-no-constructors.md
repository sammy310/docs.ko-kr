---
title: "'<typename>' 형식에 생성자가 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 249bcb7020f26c7c43d560e91ef7a34e4dc64470
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161181"
---
# <a name="bc30251-type-typename-has-no-constructors"></a><span data-ttu-id="46364-102">BC30251: ' \<typename> ' 형식에 생성자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46364-102">BC30251: Type '\<typename>' has no constructors</span></span>

<span data-ttu-id="46364-103">형식이 `Sub New()` 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46364-103">A type does not support a call to `Sub New()`.</span></span> <span data-ttu-id="46364-104">컴파일러 또는 이진 파일이 손상되었기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46364-104">One possible cause is a corrupted compiler or binary file.</span></span>

 <span data-ttu-id="46364-105">**오류 ID:** BC30251</span><span class="sxs-lookup"><span data-stu-id="46364-105">**Error ID:** BC30251</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="46364-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="46364-106">To correct this error</span></span>

1. <span data-ttu-id="46364-107">형식이 다른 프로젝트 또는 참조되는 파일에 있으면 해당 프로젝트나 파일을 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="46364-107">If the type is in a different project or in a referenced file, reinstall the project or file.</span></span>

2. <span data-ttu-id="46364-108">형식이 같은 프로젝트에 있으면 해당 형식이 포함된 어셈블리를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="46364-108">If the type is in the same project, recompile the assembly containing the type.</span></span>

3. <span data-ttu-id="46364-109">오류가 다시 발생 하면 Visual Basic 컴파일러를 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="46364-109">If the error recurs, reinstall the Visual Basic compiler.</span></span>

4. <span data-ttu-id="46364-110">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="46364-110">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="46364-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="46364-111">See also</span></span>

- [<span data-ttu-id="46364-112">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="46364-112">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="46364-113">의견 보내기</span><span class="sxs-lookup"><span data-stu-id="46364-113">Talk to Us</span></span>](/visualstudio/ide/feedback-options)
