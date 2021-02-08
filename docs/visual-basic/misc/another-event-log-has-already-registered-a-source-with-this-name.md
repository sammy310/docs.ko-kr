---
description: '자세히 알아보기: 다른 이벤트 로그에서 이미이 이름으로 소스를 등록 했습니다.'
title: 다른 이벤트 로그에서 이미 이 이름으로 소스를 등록했습니다.
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: ec6ae0b3ef12452a0135e5bf17dbdd5844c0f478
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787359"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a><span data-ttu-id="6bdb2-103">다른 이벤트 로그에서 이미 이 이름으로 소스를 등록했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bdb2-103">Another event log has already registered a source with this name</span></span>

<span data-ttu-id="6bdb2-104">지정한 소스가 다른 이벤트 로그와 함께 등록되어 있는 이벤트 로그에 항목을 쓰려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6bdb2-104">An attempt was made to write an entry to an event log where the specified source is registered with another event log.</span></span>  
  
 <span data-ttu-id="6bdb2-105">구성 요소가 로그에 항목을 쓰기 전에 <xref:System.Diagnostics.EventLog.Source%2A> 구성 요소 인스턴스의 <xref:System.Diagnostics.EventLog> 속성을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdb2-105">You must set the <xref:System.Diagnostics.EventLog.Source%2A> property of your <xref:System.Diagnostics.EventLog> component instance before your component writes an entry to a log.</span></span> <span data-ttu-id="6bdb2-106">이때 시스템에서 구성 요소가 쓰고 있는 이벤트 로그에 지정한 소스가 등록되어 있는지 확인하고 필요한 경우 <xref:System.Diagnostics.EventLog.CreateEventSource%2A> 를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdb2-106">When this happens, the system checks that the source you specified is registered with the event log to which the component is writing, and calls <xref:System.Diagnostics.EventLog.CreateEventSource%2A> if needed.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6bdb2-107">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="6bdb2-107">To correct this error</span></span>  
  
1. <span data-ttu-id="6bdb2-108">소스와 <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> 또는 <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> 메서드를 사용하는 첫 번째 로그의 연결을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdb2-108">Remove the association of the source with the first log using the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> or the <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> method.</span></span>  
  
2. <span data-ttu-id="6bdb2-109">새 로그에 소스를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdb2-109">Register the source with the new log.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bdb2-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bdb2-110">See also</span></span>

- [<span data-ttu-id="6bdb2-111">내 응용 프로그램 .Log</span><span class="sxs-lookup"><span data-stu-id="6bdb2-111">My.Application.Log</span></span>](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
