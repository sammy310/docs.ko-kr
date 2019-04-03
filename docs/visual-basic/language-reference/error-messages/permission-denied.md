---
title: 사용 권한이 거부되었습니다(Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: d904ee48ee187d073647b6e09af57264c8c318f6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813953"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="06eab-102">사용 권한이 거부되었습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="06eab-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="06eab-103">쓰기 금지 되어 디스크에 쓸 수 또는 잠긴된 파일에 액세스 하도록 시도 했습니다.</span><span class="sxs-lookup"><span data-stu-id="06eab-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="06eab-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="06eab-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="06eab-105">쓰기 암호로 보호 된 파일을 열려면 파일의 쓰기 금지 특성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="06eab-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2.  <span data-ttu-id="06eab-106">다른 프로세스에 파일을 잠그지 있는지 확인 하 고 다른 프로세스에서 해제 될 때까지 파일을 열 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="06eab-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3.  <span data-ttu-id="06eab-107">레지스트리에 액세스 하려면 사용자 권한에 포함이 유형의 레지스트리 액세스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06eab-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06eab-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="06eab-108">See also</span></span>

- [<span data-ttu-id="06eab-109">오류 형식</span><span class="sxs-lookup"><span data-stu-id="06eab-109">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
