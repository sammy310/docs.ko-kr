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
ms.openlocfilehash: 1e0cb52a6b9f03209256e5398415b4ec632fb5e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705509"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="2550e-102">IDebuggerThreadControl::StartBlockingForDebugger 메서드</span><span class="sxs-lookup"><span data-stu-id="2550e-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>

<span data-ttu-id="2550e-103">디버깅 서비스가 모든 스레드를 차단 하기 시작 했음을 호스트에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2550e-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2550e-104">구문</span><span class="sxs-lookup"><span data-stu-id="2550e-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2550e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2550e-105">Parameters</span></span>  

 `dwUnused`  
 <span data-ttu-id="2550e-106">진행 나중에 사용 하도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2550e-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2550e-107">설명</span><span class="sxs-lookup"><span data-stu-id="2550e-107">Remarks</span></span>  

 <span data-ttu-id="2550e-108">`StartBlockingForDebugger`메서드는 런타임 스레드에서 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2550e-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2550e-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2550e-109">Requirements</span></span>  

 <span data-ttu-id="2550e-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2550e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2550e-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2550e-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2550e-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2550e-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2550e-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2550e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2550e-114">참조</span><span class="sxs-lookup"><span data-stu-id="2550e-114">See also</span></span>

- [<span data-ttu-id="2550e-115">IDebuggerThreadControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2550e-115">IDebuggerThreadControl Interface</span></span>](idebuggerthreadcontrol-interface.md)
