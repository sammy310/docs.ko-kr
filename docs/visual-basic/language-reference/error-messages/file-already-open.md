---
title: 파일이 이미 열려 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: e565dbd6352a8f76290f3f58d62e2e14a18ef45f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58823508"
---
# <a name="file-already-open"></a><span data-ttu-id="0f585-102">파일이 이미 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f585-102">File already open</span></span>
<span data-ttu-id="0f585-103">다른 것 보다 먼저 파일을 닫아야 때로는 `FileOpen` 또는 다른 작업이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0f585-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="0f585-104">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="0f585-104">Among the possible causes of this error are:</span></span>  
  
-   <span data-ttu-id="0f585-105">순차적 출력 모드 `FileOpen` 이미 열려 있는 파일에 대 한 작업 실행</span><span class="sxs-lookup"><span data-stu-id="0f585-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
-   <span data-ttu-id="0f585-106">문이 열려 있는 파일을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="0f585-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0f585-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="0f585-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="0f585-108">문을 실행 하기 전에 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="0f585-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f585-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="0f585-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
