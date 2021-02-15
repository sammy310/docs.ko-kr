---
description: '자세한 정보: 내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.'
title: 내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
ms.openlocfilehash: d274a08728b084b21309862de69e2fded5c164da
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100463496"
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a><span data-ttu-id="08668-103">내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08668-103">Could not obtain full operation system name due to internal error</span></span>

<span data-ttu-id="08668-104">내부 오류로 인해 전체 작업 시스템 이름을 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08668-104">Could not obtain full operation system name due to internal error.</span></span> <span data-ttu-id="08668-105">이는 현재 컴퓨터에 존재하지 않는 WMI에 의해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08668-105">This might be caused by WMI not existing on the current machine.</span></span>  
  
 <span data-ttu-id="08668-106">`My.Computer.Info.OSFullName` 속성 호출이 실패했습니다.</span><span class="sxs-lookup"><span data-stu-id="08668-106">A call to the `My.Computer.Info.OSFullName` property failed.</span></span> <span data-ttu-id="08668-107">현재 컴퓨터에 WMI(Windows Management Instrumentation)가 설치되지 않아서 이 오류가 발생했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08668-107">A possible cause for this failure is if Windows Management Instrumentation (WMI) is not installed on the current computer.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="08668-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="08668-108">To correct this error</span></span>  
  
1. <span data-ttu-id="08668-109">`Try...Catch` 속성을 호출하는 주변에 `My.Computer.Info.OSFullName` 블록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="08668-109">Add a `Try...Catch` block around the call to the `My.Computer.Info.OSFullName` property.</span></span>  
  
2. <span data-ttu-id="08668-110">WMI 및 설치 방법에 대 한 자세한 내용을 보려면로 이동 하 여 "WMI(Windows Management Instrumentation) Core"를 검색 하십시오.</span><span class="sxs-lookup"><span data-stu-id="08668-110">For more information about WMI and how to install it, go to  and search for "Windows Management Instrumentation Core".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08668-111">추가 정보</span><span class="sxs-lookup"><span data-stu-id="08668-111">See also</span></span>

- [<span data-ttu-id="08668-112">My.computer. Svfullname</span><span class="sxs-lookup"><span data-stu-id="08668-112">My.Computer.Info.OSFullName</span></span>](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)
- [<span data-ttu-id="08668-113">.NET의 예외 처리 및 Throw</span><span class="sxs-lookup"><span data-stu-id="08668-113">Handling and throwing exceptions in .NET</span></span>](../../standard/exceptions/index.md)
- [<span data-ttu-id="08668-114">Try...Catch...Finally 문</span><span class="sxs-lookup"><span data-stu-id="08668-114">Try...Catch...Finally Statement</span></span>](../language-reference/statements/try-catch-finally-statement.md)
