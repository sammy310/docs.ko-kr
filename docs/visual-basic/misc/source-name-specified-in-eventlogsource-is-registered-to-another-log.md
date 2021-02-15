---
description: '자세히 알아보기: EventLogSource에 지정 된 소스 이름이 EventLogName에 지정 된 것과 다른 로그에 등록 되어 있습니다.'
title: EventLogSource에 지정된 소스 이름이 EventLogName에 지정된 로그가 아닌 로그에 등록되었습니다.
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: d6b9c1265276f94369d37e6ac55604b761fb9bcc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100455459"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a><span data-ttu-id="1a4b6-103">EventLogSource에 지정된 소스 이름이 EventLogName에 지정된 로그가 아닌 로그에 등록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4b6-103">Source name specified in EventLogSource is registered to a log other than that specified in EventLogName</span></span>

<span data-ttu-id="1a4b6-104">`EventLog` 에서 다른 로그에 등록된 소스를 참조하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4b6-104">The `EventLog` is attempting to refer to a source that is registered to a different log.</span></span> <span data-ttu-id="1a4b6-105">이벤트 로그에 항목을 쓰는 경우 <xref:System.Diagnostics.EventLog.Source%2A> 속성을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4b6-105">If you are writing entries to an event log, you must specify the <xref:System.Diagnostics.EventLog.Source%2A> property.</span></span> <span data-ttu-id="1a4b6-106"><xref:System.Diagnostics.EventLog.Source%2A> 속성은 구성 요소를 항목의 유효한 소스로 이벤트 로그에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4b6-106">The <xref:System.Diagnostics.EventLog.Source%2A> property registers your component with the event log as a valid source of entries.</span></span> <span data-ttu-id="1a4b6-107">단일 소스는 한 번에 하나의 이벤트 로그에만 연결되고 항목을 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1a4b6-107">A single source can be associated with (and therefore write entries to) only one event log at a time.</span></span>  
  
 <span data-ttu-id="1a4b6-108">기본적으로 구성 요소를 유효한 소스로 먼저 등록하지 않고 항목을 쓰려고 하면 시스템이 자동으로 <xref:System.Diagnostics.EventLog.Source%2A> 속성의 값을 소스 문자열로 사용하여 이벤트 로그에 소스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4b6-108">By default, if you try to write an entry without first having registered your component as a valid source, the system automatically registers the source with the event log, using the value of the <xref:System.Diagnostics.EventLog.Source%2A> property as the source string.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1a4b6-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="1a4b6-109">To correct this error</span></span>  
  
- <span data-ttu-id="1a4b6-110">소스가 올바른 로그에 등록되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4b6-110">Make sure the source is registered to the correct log.</span></span> <span data-ttu-id="1a4b6-111">이렇게 하려면 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> 메서드 또는 해당 오버로드 중 하나를 사용하여 이벤트 로그에 구성 요소를 고유하게 식별하는 문자열을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="1a4b6-111">To do this, use the <xref:System.Diagnostics.EventLog.CreateEventSource%2A> method or one of its overloads to specify a string that uniquely identifies your component to the event log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a4b6-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="1a4b6-112">See also</span></span>

- <span data-ttu-id="1a4b6-113">[이벤트 로그 관리](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1a4b6-113">[Administering Event Logs](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))</span></span>
- <span data-ttu-id="1a4b6-114">[이벤트 로그 참조](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1a4b6-114">[Event Log References](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))</span></span>
- <span data-ttu-id="1a4b6-115">[방법: 응용 프로그램을 이벤트 로그 항목의 소스로 추가](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1a4b6-115">[How to: Add Your Application as a Source of Event Log Entries](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))</span></span>
- <span data-ttu-id="1a4b6-116">[방법: 이벤트 소스 제거](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="1a4b6-116">[How to: Remove an Event Source](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))</span></span>
