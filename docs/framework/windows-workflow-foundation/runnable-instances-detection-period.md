---
title: 실행 가능한 인스턴스 검색 기간
ms.date: 03/30/2017
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
ms.openlocfilehash: aefde2726bb2ccc15f9e68009e5e141602b13b10
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245772"
---
# <a name="runnable-instances-detection-period"></a><span data-ttu-id="3b95a-102">실행 가능한 인스턴스 검색 기간</span><span class="sxs-lookup"><span data-stu-id="3b95a-102">Runnable Instances Detection Period</span></span>

<span data-ttu-id="3b95a-103">SQL 워크플로 인스턴스 저장소는 정기적으로 다시 시작되어 지속성 데이터베이스에서 실행 가능하거나 활성화 가능한 인스턴스를 검색하는 내부 태스크를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3b95a-103">The SQL Workflow Instance Store runs an internal task that periodically wakes up and detects runnable or activatable instances in the persistence database.</span></span> <span data-ttu-id="3b95a-104">SQL 워크플로 인스턴스 저장소의 실행 가능한 **인스턴스 검색 기간** 속성은 Sql 워크플로 인스턴스 저장소가 이전 검색 주기 후에 지 속성 데이터베이스에서 실행 가능 하거나 활성화 가능한 워크플로 인스턴스를 검색 하기 위해 검색 작업을 실행 하는 기간을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b95a-104">The **Runnable Instances Detection Period** property of the SQL Workflow Instance Store specifies the time period after which the SQL Workflow Instance Store runs a detection task to detect any runnable or activatable workflow instances in the persistence database after the previous detection cycle.</span></span>  
  
 <span data-ttu-id="3b95a-105">이 속성의 간격을 짧게 설정할수록 워크플로 인스턴스와 연결된 타이머 만료 시간과 인스턴스 이벤트 및 후속 로드 신호 사이의 간격이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="3b95a-105">Setting a shorter interval for this property reduces the time between the expiration of a timer associated with a workflow instance and the signaling of the event and subsequent loading of the instance.</span></span> <span data-ttu-id="3b95a-106">하지만 호스트의 처리 부하가 증가하므로 지속적인 타이머 및/또는 호스트 오류가 거의 없는 시나리오에서는 유용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b95a-106">However, it also increases the processing load on a host and may not be desirable in scenarios where durable timers and/or host failures are rare.</span></span> <span data-ttu-id="3b95a-107">속성 형식은 TimeSpan이고 속성 값은 hh:mm:ss 형식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3b95a-107">The type of the property is TimeSpan and the value of the property follows the format: hh:mm:ss.</span></span> <span data-ttu-id="3b95a-108">이 속성의 최소값은 00:00:01이고</span><span class="sxs-lookup"><span data-stu-id="3b95a-108">The minimum value for this property is 00:00:01.</span></span> <span data-ttu-id="3b95a-109">기본값은 00:00:05입니다.</span><span class="sxs-lookup"><span data-stu-id="3b95a-109">The default value for the property is 00:00:05.</span></span>  
  
 <span data-ttu-id="3b95a-110">실행 가능 하 고 활성화 가능한 워크플로 인스턴스를 검색 하 고 활성화 하는 방법은 [인스턴스 활성화](instance-activation.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3b95a-110">For more information detecting and activating runnable and activatable workflow instances, see [Instance Activation](instance-activation.md).</span></span>
