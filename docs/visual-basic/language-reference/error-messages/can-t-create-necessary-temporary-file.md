---
title: 필요한 임시 파일을 만들 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID322
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
ms.openlocfilehash: 658c2ab1dc210bf472646bce529ae5ffd7f67bc5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59310228"
---
# <a name="cant-create-necessary-temporary-file"></a><span data-ttu-id="874b1-102">필요한 임시 파일을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="874b1-102">Can't create necessary temporary file</span></span>
<span data-ttu-id="874b1-103">드라이브가 꽉 TEMP 환경 변수로 지정 된 디렉터리를 포함 하는 또는 TEMP 환경 변수는 유효 하지 않거나 읽기 전용 드라이브 또는 디렉터리를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="874b1-103">Either the drive is full that contains the directory specified by the TEMP environment variable, or the TEMP environment variable specifies an invalid or read-only drive or directory.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="874b1-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="874b1-104">To correct this error</span></span>  
  
1. <span data-ttu-id="874b1-105">전체 경우 드라이브에서 파일을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="874b1-105">Delete files from the drive, if full.</span></span>  
  
2. <span data-ttu-id="874b1-106">TEMP 환경 변수에서 다른 드라이브를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="874b1-106">Specify a different drive in the TEMP environment variable.</span></span>  
  
3. <span data-ttu-id="874b1-107">TEMP 환경 변수에 대해 올바른 드라이브를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="874b1-107">Specify a valid drive for the TEMP environment variable.</span></span>  
  
4. <span data-ttu-id="874b1-108">현재 지정 된 드라이브 또는 디렉터리에서 읽기 전용으로 제한을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="874b1-108">Remove the read-only restriction from the currently specified drive or directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="874b1-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="874b1-109">See also</span></span>

- [<span data-ttu-id="874b1-110">오류 형식</span><span class="sxs-lookup"><span data-stu-id="874b1-110">Error Types</span></span>](../../../visual-basic/programming-guide/language-features/error-types.md)
