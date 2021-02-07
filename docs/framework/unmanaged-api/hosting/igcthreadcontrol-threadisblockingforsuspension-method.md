---
description: '자세히 알아보기: IGCThreadControl:: ThreadIsBlockingForSuspension 메서드'
title: IGCThreadControl::ThreadIsBlockingForSuspension 메서드
ms.date: 03/30/2017
api_name:
- IGCThreadControl.ThreadIsBlockingForSuspension
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ThreadIsBlockingForSuspension
helpviewer_keywords:
- IGCThreadControl::ThreadIsBlockingForSuspension method [.NET Framework hosting]
- ThreadIsBlockingForSuspension method [.NET Framework hosting]
ms.assetid: ed5b5b58-7db7-46b5-9e2c-278db7159cee
topic_type:
- apiref
ms.openlocfilehash: 13023a75ab1c438abebbeb16fd9fe7c4b95c37ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709206"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="e6f08-103">IGCThreadControl::ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="e6f08-103">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>

<span data-ttu-id="e6f08-104">호출을 수행 하는 스레드가 차단 하려고 함을 호스트에 알립니다 (가비지 수집 또는 기타 일시 중단의 경우).</span><span class="sxs-lookup"><span data-stu-id="e6f08-104">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f08-105">구문</span><span class="sxs-lookup"><span data-stu-id="e6f08-105">Syntax</span></span>  
  
```cpp  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="e6f08-106">설명</span><span class="sxs-lookup"><span data-stu-id="e6f08-106">Remarks</span></span>  

 <span data-ttu-id="e6f08-107">호스트는 스레드를 다시 `ThreadIsBlockingForSuspension` 예약할 지 여부에 관계 없이 콜백 내에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6f08-107">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6f08-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6f08-108">Requirements</span></span>  

 <span data-ttu-id="e6f08-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6f08-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f08-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="e6f08-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6f08-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6f08-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6f08-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6f08-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6f08-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6f08-113">See also</span></span>

- [<span data-ttu-id="e6f08-114">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6f08-114">IGCThreadControl Interface</span></span>](igcthreadcontrol-interface.md)
