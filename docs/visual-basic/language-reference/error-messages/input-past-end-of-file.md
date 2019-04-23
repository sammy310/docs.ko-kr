---
title: 입력(값)이 파일의 끝을 넘습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 5da14c7a28ecdcd023fc6439cb6ed64444c1183b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768555"
---
# <a name="input-past-end-of-file"></a><span data-ttu-id="3dfa5-102">입력(값)이 파일의 끝을 넘습니다.</span><span class="sxs-lookup"><span data-stu-id="3dfa5-102">Input past end of file</span></span>
<span data-ttu-id="3dfa5-103">중 하나는 `Input` 문에서 비어 있는 파일 또는 모든 데이터 사용 또는 사용에서 읽고는 `EOF` 함수 파일을 사용 하 여 이진 액세스를 위해 열렸습니다.</span><span class="sxs-lookup"><span data-stu-id="3dfa5-103">Either an `Input` statement is reading from a file that is empty or one in which all the data is used, or you used the `EOF` function with a file opened for binary access.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="3dfa5-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="3dfa5-104">To correct this error</span></span>  
  
1. <span data-ttu-id="3dfa5-105">사용 된 `EOF` 직전 함수를 `Input` 문을 파일의 끝을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3dfa5-105">Use the `EOF` function immediately before the `Input` statement to detect the end of the file.</span></span>  
  
2. <span data-ttu-id="3dfa5-106">파일을 이진 액세스에 대 한 열을 사용 하 여 `Seek` 고 `Loc`입니다.</span><span class="sxs-lookup"><span data-stu-id="3dfa5-106">If the file is opened for binary access, use `Seek` and `Loc`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3dfa5-107">참고자료</span><span class="sxs-lookup"><span data-stu-id="3dfa5-107">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
