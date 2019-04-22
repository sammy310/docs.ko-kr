---
title: 파일이 이미 열려 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 401801c7c9072ce11f9eafdb84f2b377669ae545
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770362"
---
# <a name="file-already-open"></a><span data-ttu-id="80008-102">파일이 이미 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80008-102">File already open</span></span>
<span data-ttu-id="80008-103">다른 것 보다 먼저 파일을 닫아야 때로는 `FileOpen` 또는 다른 작업이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80008-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="80008-104">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="80008-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="80008-105">순차적 출력 모드 `FileOpen` 이미 열려 있는 파일에 대 한 작업 실행</span><span class="sxs-lookup"><span data-stu-id="80008-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="80008-106">문이 열려 있는 파일을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="80008-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="80008-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="80008-107">To correct this error</span></span>  
  
1. <span data-ttu-id="80008-108">문을 실행 하기 전에 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="80008-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80008-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="80008-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
