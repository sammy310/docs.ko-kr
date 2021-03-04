---
description: "자세한 정보: BC30251: ' ' 형식 <typename> 에 생성자가 없습니다."
title: "'<typename>' 형식에 생성자가 없습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30251
- vbc30251
helpviewer_keywords:
- BC30251
ms.assetid: aff3e1df-abe6-4bc0-9abc-a1e70514c561
ms.openlocfilehash: 3961ba557ad2afd9c94f071b6615573419d7325b
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106581"
---
# <a name="bc30251-type-typename-has-no-constructors"></a><span data-ttu-id="1dfb2-103">BC30251: ' \<typename> ' 형식에 생성자가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1dfb2-103">BC30251: Type '\<typename>' has no constructors</span></span>

<span data-ttu-id="1dfb2-104">형식이 `Sub New()` 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1dfb2-104">A type does not support a call to `Sub New()`.</span></span> <span data-ttu-id="1dfb2-105">컴파일러 또는 이진 파일이 손상되었기 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dfb2-105">One possible cause is a corrupted compiler or binary file.</span></span>

 <span data-ttu-id="1dfb2-106">**오류 ID:** BC30251</span><span class="sxs-lookup"><span data-stu-id="1dfb2-106">**Error ID:** BC30251</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="1dfb2-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1dfb2-107">To correct this error</span></span>

1. <span data-ttu-id="1dfb2-108">형식이 다른 프로젝트 또는 참조되는 파일에 있으면 해당 프로젝트나 파일을 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="1dfb2-108">If the type is in a different project or in a referenced file, reinstall the project or file.</span></span>

2. <span data-ttu-id="1dfb2-109">형식이 같은 프로젝트에 있으면 해당 형식이 포함된 어셈블리를 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="1dfb2-109">If the type is in the same project, recompile the assembly containing the type.</span></span>

3. <span data-ttu-id="1dfb2-110">오류가 다시 발생 하면 Visual Basic 컴파일러를 다시 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dfb2-110">If the error recurs, reinstall the Visual Basic compiler.</span></span>

4. <span data-ttu-id="1dfb2-111">오류가 계속 발생하면 해당 상황에 대한 정보를 수집하여 Microsoft 기술 지원 서비스에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="1dfb2-111">If the error persists, gather information about the circumstances and notify Microsoft Product Support Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dfb2-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1dfb2-112">See also</span></span>

- [<span data-ttu-id="1dfb2-113">개체 및 클래스</span><span class="sxs-lookup"><span data-stu-id="1dfb2-113">Objects and Classes</span></span>](../../programming-guide/language-features/objects-and-classes/index.md)
- [<span data-ttu-id="1dfb2-114">Visual Studio 피드백 옵션</span><span class="sxs-lookup"><span data-stu-id="1dfb2-114">Visual Studio feedback options</span></span>](/visualstudio/ide/feedback-options)
