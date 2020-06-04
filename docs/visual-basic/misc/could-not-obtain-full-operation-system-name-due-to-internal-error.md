---
title: 내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: 67e8fb5e906800d28bf15714463b7ff6ae585693
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402280"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="96eed-102">내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96eed-102">Could not obtain full operation system name due to internal error</span></span>
<span data-ttu-id="96eed-103">내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96eed-103">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="96eed-104">이는 현재 컴퓨터에 존재하지 않는 WMI에 의해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96eed-104">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="96eed-105">`My.Computer.Info.OSFullName` 속성 호출이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="96eed-105">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="96eed-106">현재 컴퓨터에 WMI(Windows Management Instrumentation)가 설치되지 않아서 이 오류가 발생했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96eed-106">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="96eed-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="96eed-107">To correct this error</span></span>  
  
1. <span data-ttu-id="96eed-108">`Try...Catch` 속성을 호출하는 주변에 `My.Computer.Info.OSFullName` 블록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96eed-108">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="96eed-109">WMI 및 설치 방법에 대 한 자세한 내용을 보려면로 이동 하 여 "WMI(Windows Management Instrumentation) Core"를 검색 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96eed-109">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96eed-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96eed-110">See also</span></span>

- [<span data-ttu-id="96eed-111">My.computer. Svfullname</span><span class="sxs-lookup"><span data-stu-id="96eed-111">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="96eed-112">.NET의 예외 처리 및 Throw</span><span class="sxs-lookup"><span data-stu-id="96eed-112">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="96eed-113">Try...Catch...Finally 명령문</span><span class="sxs-lookup"><span data-stu-id="96eed-113">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
