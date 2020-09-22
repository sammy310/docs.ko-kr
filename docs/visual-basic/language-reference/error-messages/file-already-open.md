---
title: 파일이 이미 열려 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 97f9e13e6802e793f7c7baf1f03ec51205eb6d42
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874173"
---
# <a name="file-already-open"></a><span data-ttu-id="633c4-102">파일이 이미 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="633c4-102">File already open</span></span>

<span data-ttu-id="633c4-103">경우에 따라 다른 작업을 수행 하거나 다른 작업을 수행 하기 전에 파일을 닫아야 합니다 `FileOpen` .</span><span class="sxs-lookup"><span data-stu-id="633c4-103">Sometimes a file must be closed before another `FileOpen` or other operation can occur.</span></span> <span data-ttu-id="633c4-104">이 오류의 가능한 원인:</span><span class="sxs-lookup"><span data-stu-id="633c4-104">Among the possible causes of this error are:</span></span>  
  
- <span data-ttu-id="633c4-105">`FileOpen`이미 열려 있는 파일에 대해 순차적 출력 모드 작업이 실행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="633c4-105">A sequential output mode `FileOpen` operation was executed for a file that is already open</span></span>  
  
- <span data-ttu-id="633c4-106">문이 열려 있는 파일을 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="633c4-106">A statement refers to an open file.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="633c4-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="633c4-107">To correct this error</span></span>  
  
1. <span data-ttu-id="633c4-108">문을 실행 하기 전에 파일을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="633c4-108">Close the file before executing the statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="633c4-109">참조</span><span class="sxs-lookup"><span data-stu-id="633c4-109">See also</span></span>

- <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
