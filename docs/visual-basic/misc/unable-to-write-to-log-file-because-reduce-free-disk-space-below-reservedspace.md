---
description: '자세한 정보: 로그 파일에 쓰기 때문에 ReservedSpace 값 아래에서 사용 가능한 디스크 공간을 줄일 수 있기 때문에 로그 파일에 쓸 수 없습니다.'
title: 사용 가능한 디스크 공간이 ReservedSpace 값 미만으로 줄어들 수 있기 때문에 로그 파일에 쓸 수 없습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrApplicationLog_ReservedSpaceEncroached
ms.assetid: 95832e70-4ecc-47aa-90c1-f35c4d468151
ms.openlocfilehash: e02fa9527539169da3ea99f89246dafe82646cff
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100456954"
---
# <a name="unable-to-write-to-log-file-because-writing-to-it-would-reduce-free-disk-space-below-reservedspace-value"></a><span data-ttu-id="7a1b9-103">사용 가능한 디스크 공간이 ReservedSpace 값 미만으로 줄어들 수 있기 때문에 로그 파일에 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a1b9-103">Unable to write to log file because writing to it would reduce free disk space below ReservedSpace value</span></span>

<span data-ttu-id="7a1b9-104"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 클래스가 다음 이유로 로그 파일에 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a1b9-104">The <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> class could not write to the log file because:</span></span>  
  
- <span data-ttu-id="7a1b9-105">여유 디스크 공간(바이트)의 용량이 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> 속성의 값보다 작습니다.</span><span class="sxs-lookup"><span data-stu-id="7a1b9-105">The amount of free disk space (in bytes) is less than the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property</span></span>  
  
     <span data-ttu-id="7a1b9-106">—및—</span><span class="sxs-lookup"><span data-stu-id="7a1b9-106">—and—</span></span>  
  
- <span data-ttu-id="7a1b9-107"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 속성의 값이 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>이었습니다.</span><span class="sxs-lookup"><span data-stu-id="7a1b9-107">The value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property was <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.ThrowException>.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7a1b9-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7a1b9-108">To correct this error</span></span>  
  
1. <span data-ttu-id="7a1b9-109"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> 개체가 새 로그를 만들 수 있도록 기존 로그를 보관하고 컴퓨터에서 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1b9-109">Archive the existing logs and remove them from the computer to allow the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener> object to create new logs.</span></span>  
  
2. <span data-ttu-id="7a1b9-110"><xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> 속성의 값을 더 작은 숫자로 변경하여 작은 디스크 공간을 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1b9-110">Change the value of the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A> property to a smaller number to reserve less disk space.</span></span>  
  
3. <span data-ttu-id="7a1b9-111">여유 디스크 공간이 충분하지 않은 경우 경고 없이 메시지를 무시하려면 <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> 속성을 <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> 로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7a1b9-111">Set the <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A> property to <xref:Microsoft.VisualBasic.Logging.DiskSpaceExhaustedOption.DiscardMessages> to discard messages without warning if there is not enough free disk space.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a1b9-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7a1b9-112">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.ReserveDiskSpace%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener.DiskSpaceExhaustedBehavior%2A>
- <xref:Microsoft.VisualBasic.Logging.FileLogTraceListener>
- [<span data-ttu-id="7a1b9-113">내 응용 프로그램 .Log</span><span class="sxs-lookup"><span data-stu-id="7a1b9-113">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
- [<span data-ttu-id="7a1b9-114">DirectoryPath.</span><span class="sxs-lookup"><span data-stu-id="7a1b9-114">My.Application.Info.DirectoryPath</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
