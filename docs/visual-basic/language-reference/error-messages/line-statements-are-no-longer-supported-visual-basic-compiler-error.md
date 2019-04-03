---
title: "'Line' 문은 더 이상 지원되지 않습니다(Visual Basic 컴파일러 오류)."
ms.date: 07/20/2015
f1_keywords:
- bc30830
- vbc30830
helpviewer_keywords:
- BC30830
ms.assetid: 4734bc1d-882e-4555-b498-1f1ec0399d16
ms.openlocfilehash: 7616bcdc39ab479049586534fac22f1e2d96a700
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58831841"
---
# <a name="line-statements-are-no-longer-supported-visual-basic-compiler-error"></a><span data-ttu-id="14fdd-102">'Line' 문은 더 이상 지원되지 않습니다(Visual Basic 컴파일러 오류).</span><span class="sxs-lookup"><span data-stu-id="14fdd-102">'Line' statements are no longer supported (Visual Basic Compiler Error)</span></span>
<span data-ttu-id="14fdd-103">줄 문은 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14fdd-103">Line statements are no longer supported.</span></span> <span data-ttu-id="14fdd-104">파일 I/O 기능은 사용할 수 있습니다 `Microsoft.VisualBasic.FileSystem.LineInput` 그래픽 기능으로 제공 되며 `System.Drawing.Graphics.DrawLine`합니다.</span><span class="sxs-lookup"><span data-stu-id="14fdd-104">File I/O functionality is available as `Microsoft.VisualBasic.FileSystem.LineInput` and graphics functionality is available as `System.Drawing.Graphics.DrawLine`.</span></span>  
  
 <span data-ttu-id="14fdd-105">**오류 ID:** BC30830</span><span class="sxs-lookup"><span data-stu-id="14fdd-105">**Error ID:** BC30830</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14fdd-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="14fdd-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="14fdd-107">파일 액세스를 수행 하는 경우 사용 하 여 `Microsoft.VisualBasic.FileSystem.LineInput`입니다.</span><span class="sxs-lookup"><span data-stu-id="14fdd-107">If performing file access, use `Microsoft.VisualBasic.FileSystem.LineInput`.</span></span>  
  
2.  <span data-ttu-id="14fdd-108">그래픽을 수행하는 경우 `System.Drawing.Graphics.Drawline`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="14fdd-108">If performing graphics, use `System.Drawing.Graphics.Drawline`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14fdd-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="14fdd-109">See also</span></span>

- <xref:System.IO>
- <xref:System.Drawing>
- [<span data-ttu-id="14fdd-110">Visual Basic을 사용한 파일 액세스</span><span class="sxs-lookup"><span data-stu-id="14fdd-110">File Access with Visual Basic</span></span>](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)
