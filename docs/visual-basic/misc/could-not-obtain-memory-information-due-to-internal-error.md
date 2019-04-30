---
title: 내부 오류 때문에 메모리 정보를 가져올 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_Memory
ms.assetid: 1ba8f774-5858-438e-914e-99fddc9e5e7e
ms.openlocfilehash: a8d1f3799de11596b9eed9df39e143587e283b55
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61970523"
---
# <a name="could-not-obtain-memory-information-due-to-internal-error"></a><span data-ttu-id="f2008-102">내부 오류 때문에 메모리 정보를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2008-102">Could not obtain memory information due to internal error</span></span>
<span data-ttu-id="f2008-103">`My.Computer.Info` 개체의 메모리 정보 속성 중 하나에 대한 호출이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="f2008-103">A call to one of the memory-information properties of the `My.Computer.Info` object failed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f2008-104">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="f2008-104">To correct this error</span></span>  
  
- <span data-ttu-id="f2008-105">`Try...Catch` 개체의 메모리 정보 속성에 대한 호출 주위에 `My.Computer.Info` 블록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f2008-105">Add a `Try...Catch` block around the call to the memory-information property of the `My.Computer.Info` object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2008-106">참고자료</span><span class="sxs-lookup"><span data-stu-id="f2008-106">See also</span></span>

- [<span data-ttu-id="f2008-107">My.Computer.Info</span><span class="sxs-lookup"><span data-stu-id="f2008-107">My.Computer.Info</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo)
- [<span data-ttu-id="f2008-108">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="f2008-108">Try...Catch...Finally Statement</span></span>](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
