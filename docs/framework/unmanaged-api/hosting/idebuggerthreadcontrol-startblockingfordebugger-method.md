---
title: IDebuggerThreadControl::StartBlockingForDebugger 메서드
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc94c2de1a14842cc017e5c4ef6023154c20f2a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59194034"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="a29e3-102">IDebuggerThreadControl::StartBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="a29e3-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="a29e3-103">디버깅 서비스 시작 모든 스레드를 차단 하려는 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a29e3-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a29e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="a29e3-104">Syntax</span></span>  
  
```  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a29e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a29e3-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="a29e3-106">[in] 사용 하도록 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="a29e3-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a29e3-107">설명</span><span class="sxs-lookup"><span data-stu-id="a29e3-107">Remarks</span></span>  
 <span data-ttu-id="a29e3-108">`StartBlockingForDebugger` 런타임 스레드에서 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a29e3-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a29e3-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a29e3-109">Requirements</span></span>  
 <span data-ttu-id="a29e3-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a29e3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a29e3-111">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a29e3-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a29e3-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a29e3-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a29e3-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="a29e3-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a29e3-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="a29e3-114">See also</span></span>

- [<span data-ttu-id="a29e3-115">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a29e3-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
