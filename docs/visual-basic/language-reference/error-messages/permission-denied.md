---
title: 사용 권한이 거부됨
ms.date: 07/20/2015
f1_keywords:
- vbrID70
ms.assetid: 71f46756-f522-4814-aab4-492bf9924245
ms.openlocfilehash: bf95a7a0c6cb80bc02434eab7a86d07cb6855ee2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84387142"
---
# <a name="permission-denied-visual-basic"></a><span data-ttu-id="be43f-102">사용 권한이 거부되었습니다(Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="be43f-102">Permission denied (Visual Basic)</span></span>
<span data-ttu-id="be43f-103">쓰기 방지 된 디스크에 쓰거나 잠긴 파일에 액세스 하려고 한 경우</span><span class="sxs-lookup"><span data-stu-id="be43f-103">An attempt was made to write to a write-protected disk or to access a locked file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="be43f-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="be43f-104">To correct this error</span></span>  
  
1. <span data-ttu-id="be43f-105">쓰기 보호 된 파일을 열려면 파일의 쓰기 방지 특성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="be43f-105">To open a write-protected file, change the write-protection attribute of the file.</span></span>  
  
2. <span data-ttu-id="be43f-106">다른 프로세스에서 파일을 잠그지 않았는지 확인 하 고 다른 프로세스에서 파일을 놓을 때까지 파일을 열 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="be43f-106">Make sure that another process has not locked the file, and wait to open the file until the other process releases it.</span></span>  
  
3. <span data-ttu-id="be43f-107">레지스트리에 액세스 하려면 사용자 권한이이 유형의 레지스트리 액세스를 포함 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="be43f-107">To access the registry, check that your user permissions include this type of registry access.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be43f-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be43f-108">See also</span></span>

- [<span data-ttu-id="be43f-109">오류 유형</span><span class="sxs-lookup"><span data-stu-id="be43f-109">Error Types</span></span>](../../programming-guide/language-features/error-types.md)
