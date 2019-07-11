---
title: ICorDebugThread4::HadUnhandledException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9bbc3379ff9523564f4eae7da96fca2247601fcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765162"
---
# <a name="icordebugthread4hadunhandledexception-method"></a><span data-ttu-id="f011d-102">ICorDebugThread4::HadUnhandledException 메서드</span><span class="sxs-lookup"><span data-stu-id="f011d-102">ICorDebugThread4::HadUnhandledException Method</span></span>
<span data-ttu-id="f011d-103">스레드 처리 되지 않은 예외가 한 적이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f011d-103">Indicates whether the thread has ever had an unhandled exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f011d-104">구문</span><span class="sxs-lookup"><span data-stu-id="f011d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f011d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f011d-105">Parameters</span></span>  
 `ppBlockingObjectEnum`  
 <span data-ttu-id="f011d-106">[out] 순서가 지정 된 열거형의 주소에 대 한 포인터 [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="f011d-106">[out] A pointer to the address of an ordered enumeration of [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structures.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f011d-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="f011d-107">Return Value</span></span>  
 <span data-ttu-id="f011d-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f011d-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f011d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f011d-109">HRESULT</span></span>|<span data-ttu-id="f011d-110">설명</span><span class="sxs-lookup"><span data-stu-id="f011d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f011d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="f011d-111">S_OK</span></span>|<span data-ttu-id="f011d-112">스레드에는 생성 된 후 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f011d-112">The thread has had an unhandled exception since its creation.</span></span>|  
|<span data-ttu-id="f011d-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="f011d-113">S_FALSE</span></span>|<span data-ttu-id="f011d-114">스레드의 처리 되지 않은 예외가 적입니다.</span><span class="sxs-lookup"><span data-stu-id="f011d-114">The thread has never had an unhandled exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f011d-115">설명</span><span class="sxs-lookup"><span data-stu-id="f011d-115">Remarks</span></span>  
 <span data-ttu-id="f011d-116">이 메서드는 스레드에서 처리 되지 않은 예외가 한 적이 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f011d-116">This method indicates whether the thread has ever had an unhandled exception.</span></span> <span data-ttu-id="f011d-117">처리 되지 않은 예외가 콜백이 트리거될 때 또는 네이티브 JIT 연결 시작 되 면이 메서드는 항상 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f011d-117">By the time the unhandled exception callback is triggered or native JIT-attach is initiated, this method is guaranteed to return S_OK.</span></span> <span data-ttu-id="f011d-118">그러나 보장이 합니다 [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) 메서드는 처리 되지 않은 예외를 반환 하는 경우 프로세스 하지 아직 계속 된 처리 되지 않은 예외 콜백을 받은 후 또는 시는; 네이티브 JIT 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f011d-118">There is no guarantee that the [ICorDebugThread.GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) method will return the unhandled exception; however, it will if the process has not yet been continued after getting the unhandled exception callback or upon native JIT-attach.</span></span> <span data-ttu-id="f011d-119">또한 가능성이 없지만 예외가 트리거되는 네이티브 JIT 연결 시 사용 하 여 스레드를 둘 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f011d-119">Furthermore, it is possible (although unlikely) to have more than one thread with an unhandled exception at the time native JIT-attach is triggered.</span></span> <span data-ttu-id="f011d-120">이러한 경우 JIT 연결을 트리거한 예외 확인할 방법은 없으며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f011d-120">In such a case there is no way to determine which exception triggered the JIT-attach.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f011d-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f011d-121">Requirements</span></span>  
 <span data-ttu-id="f011d-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f011d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f011d-123">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f011d-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f011d-124">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f011d-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f011d-125">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f011d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f011d-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="f011d-126">See also</span></span>

- [<span data-ttu-id="f011d-127">ICorDebugThread4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f011d-127">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="f011d-128">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f011d-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="f011d-129">디버깅</span><span class="sxs-lookup"><span data-stu-id="f011d-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
