---
title: ICorConfiguration::SetGCThreadControl 메서드
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCThreadControl
helpviewer_keywords:
- ICorConfiguration::SetGCThreadControl method [.NET Framework hosting]
- SetGCThreadControl method [.NET Framework hosting]
ms.assetid: 72e38e61-3d56-4ae3-b8f6-0ab7922aaf11
topic_type:
- apiref
ms.openlocfilehash: 7874424150e0f4e1818ad9c72e31fd584e016829
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762398"
---
# <a name="icorconfigurationsetgcthreadcontrol-method"></a><span data-ttu-id="f1a54-102">ICorConfiguration::SetGCThreadControl 메서드</span><span class="sxs-lookup"><span data-stu-id="f1a54-102">ICorConfiguration::SetGCThreadControl Method</span></span>
<span data-ttu-id="f1a54-103">가비지 컬렉션에 대해 차단 되는 런타임 이외의 작업에 대해 스레드를 예약 하는 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1a54-103">Sets the callback interface for scheduling threads for non-runtime tasks that would otherwise be blocked for a garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1a54-104">구문</span><span class="sxs-lookup"><span data-stu-id="f1a54-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCThreadControl (  
    [in] IGCThreadControl* pGCThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f1a54-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f1a54-105">Parameters</span></span>  
 `pGCThreadControl`  
 <span data-ttu-id="f1a54-106">진행 런타임이 아닌 작업에 대 한 스레드 일시 중단을 호스트에 알리는 [Igcthreadcontrol](igcthreadcontrol-interface.md) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f1a54-106">[in] A pointer to an [IGCThreadControl](igcthreadcontrol-interface.md) object that notifies the host about the suspension of threads for non-runtime tasks.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1a54-107">설명</span><span class="sxs-lookup"><span data-stu-id="f1a54-107">Remarks</span></span>  
 <span data-ttu-id="f1a54-108">호스트는 스레드를 다시 예약할 지 여부에 상관 없이 [Igcthreadcontrol:: ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) 콜백 내에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1a54-108">The host may choose within the [IGCThreadControl::ThreadIsBlockingForSuspension](igcthreadcontrol-threadisblockingforsuspension-method.md) callback whether to reschedule a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1a54-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f1a54-109">Requirements</span></span>  
 <span data-ttu-id="f1a54-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f1a54-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1a54-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f1a54-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1a54-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1a54-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1a54-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1a54-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a54-114">참조</span><span class="sxs-lookup"><span data-stu-id="f1a54-114">See also</span></span>

- [<span data-ttu-id="f1a54-115">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f1a54-115">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
