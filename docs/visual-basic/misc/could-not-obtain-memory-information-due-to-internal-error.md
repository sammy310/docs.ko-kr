---
description: '자세히 알아보기: 내부 오류로 인해 메모리 정보를 가져올 수 없습니다.'
title: 내부 오류 때문에 메모리 정보를 가져올 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_Memory
ms.assetid: 1ba8f774-5858-438e-914e-99fddc9e5e7e
ms.openlocfilehash: 08e85371f19f1e6e365e201c1a43bd679d7847e6
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463484"
---
# <a name="could-not-obtain-memory-information-due-to-internal-error"></a><span data-ttu-id="f74e6-103">내부 오류 때문에 메모리 정보를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f74e6-103">Could not obtain memory information due to internal error</span></span>

<span data-ttu-id="f74e6-104">`My.Computer.Info` 개체의 메모리 정보 속성 중 하나에 대한 호출이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="f74e6-104">A call to one of the memory-information properties of the `My.Computer.Info` object failed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f74e6-105">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f74e6-105">To correct this error</span></span>  
  
- <span data-ttu-id="f74e6-106">`Try...Catch` 개체의 메모리 정보 속성에 대한 호출 주위에 `My.Computer.Info` 블록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f74e6-106">Add a `Try...Catch` block around the call to the memory-information property of the `My.Computer.Info` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f74e6-107">추가 정보</span><span class="sxs-lookup"><span data-stu-id="f74e6-107">See also</span></span>

- [<span data-ttu-id="f74e6-108">My.Computer.Info</span><span class="sxs-lookup"><span data-stu-id="f74e6-108">My.Computer.Info</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo)
- [<span data-ttu-id="f74e6-109">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="f74e6-109">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
