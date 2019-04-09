---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cd6c1dff30bce8857b9fb4092670667109932c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59094087"
---
# <a name="igcthreadcontrolthreadisblockingforsuspension-method"></a><span data-ttu-id="f5408-102">IGCThreadControl::ThreadIsBlockingForSuspension 메서드</span><span class="sxs-lookup"><span data-stu-id="f5408-102">IGCThreadControl::ThreadIsBlockingForSuspension Method</span></span>
<span data-ttu-id="f5408-103">아마도 다른 일시 중단 또는 가비지 컬렉션에 대 한 차단 하 려는 호출 하는 스레드는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f5408-103">Notifies the host that the thread that is making the call is about to block, perhaps for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5408-104">구문</span><span class="sxs-lookup"><span data-stu-id="f5408-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForSuspension ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="f5408-105">설명</span><span class="sxs-lookup"><span data-stu-id="f5408-105">Remarks</span></span>  
 <span data-ttu-id="f5408-106">호스트 내에서 선택할 수는 `ThreadIsBlockingForSuspension` 콜백 스레드를 예약 하기 위한 여부.</span><span class="sxs-lookup"><span data-stu-id="f5408-106">The host may choose within the `ThreadIsBlockingForSuspension` callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5408-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5408-107">Requirements</span></span>  
 <span data-ttu-id="f5408-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f5408-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5408-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f5408-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5408-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="f5408-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="f5408-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f5408-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5408-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="f5408-112">See also</span></span>

- [<span data-ttu-id="f5408-113">IGCThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f5408-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
