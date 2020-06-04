---
title: "'Module' 문은 파일이나 네임스페이스 수준에서만 사용할 수 있습니다."
ms.date: 07/20/2015
f1_keywords:
- bc30617
- vbc30617
helpviewer_keywords:
- BC30617
ms.assetid: 5e9de8e5-d26b-4fb2-9e28-814413fe9cef
ms.openlocfilehash: d01c30571fc34e142300ac8706c56d5e99175fcf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84397209"
---
# <a name="module-statements-can-occur-only-at-file-or-namespace-level"></a><span data-ttu-id="8bf2b-102">'Module' 문은 파일이나 네임스페이스 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bf2b-102">'Module' statements can occur only at file or namespace level</span></span>
<span data-ttu-id="8bf2b-103">`Module`문은 소스 파일의 맨 위에 `Option` 및 `Imports` 문, 전역 특성 및 네임 스페이스 선언 바로 뒤에, 다른 모든 선언 앞에 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf2b-103">`Module` statements must appear at the top of your source file immediately after `Option` and `Imports` statements, global attributes, and namespace declarations, but before all other declarations.</span></span>  
  
 <span data-ttu-id="8bf2b-104">**오류 ID:** BC30617</span><span class="sxs-lookup"><span data-stu-id="8bf2b-104">**Error ID:** BC30617</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8bf2b-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="8bf2b-105">To correct this error</span></span>  
  
- <span data-ttu-id="8bf2b-106">`Module` 문을 네임스페이스 선언 또는 원본 파일의 맨 위로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8bf2b-106">Move the `Module` statement to the top of your namespace declaration or source file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bf2b-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bf2b-107">See also</span></span>

- [<span data-ttu-id="8bf2b-108">Module 문</span><span class="sxs-lookup"><span data-stu-id="8bf2b-108">Module Statement</span></span>](../statements/module-statement.md)
