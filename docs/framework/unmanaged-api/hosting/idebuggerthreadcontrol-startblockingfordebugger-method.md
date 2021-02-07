---
description: '자세히 알아보기: IDebuggerThreadControl:: StartBlockingForDebugger 메서드'
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
ms.openlocfilehash: 3e19817c4adbefd1dd70be047656b3fea261c389
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709678"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="539b1-103">IDebuggerThreadControl::StartBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="539b1-103">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>

<span data-ttu-id="539b1-104">디버깅 서비스가 모든 스레드를 차단 하기 시작 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="539b1-104">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="539b1-105">구문</span><span class="sxs-lookup"><span data-stu-id="539b1-105">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="539b1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="539b1-106">Parameters</span></span>  

 `dwUnused`  
 <span data-ttu-id="539b1-107">진행 나중에 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="539b1-107">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="539b1-108">설명</span><span class="sxs-lookup"><span data-stu-id="539b1-108">Remarks</span></span>  

 <span data-ttu-id="539b1-109">`StartBlockingForDebugger`메서드는 런타임 스레드에서 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="539b1-109">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="539b1-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="539b1-110">Requirements</span></span>  

 <span data-ttu-id="539b1-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="539b1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="539b1-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="539b1-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="539b1-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="539b1-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="539b1-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="539b1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="539b1-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="539b1-115">See also</span></span>

- [<span data-ttu-id="539b1-116">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="539b1-116">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
