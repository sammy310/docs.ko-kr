---
title: "'Module' 문은 파일이나 네임스페이스 수준에서만 사용할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: fc3c102dbfe7c55e66093421bc11379d48ba000d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64592092"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="17efc-102">'Module' 문은 파일이나 네임스페이스 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17efc-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="17efc-103">`Module` 문을 소스 파일의 맨 위에 있는 나타나야 직후 `Option` 및 `Imports` 문, 전역 특성 및 네임 스페이스 선언을 다른 모든 선언 앞입니다.</span><span class="sxs-lookup"><span data-stu-id="17efc-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="17efc-104">**오류 ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="17efc-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="17efc-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="17efc-105">To correct this error</span></span>  
  
- <span data-ttu-id="17efc-106">`Module` 문을 네임스페이스 선언 또는 원본 파일의 맨 위로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="17efc-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17efc-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="17efc-107">See also</span></span>

- [<span data-ttu-id="17efc-108">Module 문</span><span class="sxs-lookup"><span data-stu-id="17efc-108">Module Statement</span></span>](../../../visual-basic/language-reference/statements/module-statement.md)
