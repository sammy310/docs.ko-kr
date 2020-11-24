---
title: ICorDebugThread2::InterceptCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugThread2.InterceptCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread2::InterceptCurrentException
helpviewer_keywords:
- InterceptCurrentException method [.NET Framework debugging]
- ICorDebugThread2::InterceptCurrentException method [.NET Framework debugging]
ms.assetid: 536d2357-1b97-49e0-a10c-c860aed74e6e
topic_type:
- apiref
ms.openlocfilehash: 96e3a90bcb7700915bfd3618d7bae40c0ff64a75
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678599"
---
# <a name="icordebugthread2interceptcurrentexception-method"></a><span data-ttu-id="6c900-102">ICorDebugThread2::InterceptCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="6c900-102">ICorDebugThread2::InterceptCurrentException Method</span></span>

<span data-ttu-id="6c900-103">디버거가이 스레드의 현재 예외를 가로챌 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c900-103">Allows a debugger to intercept the current exception on this thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c900-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c900-104">Syntax</span></span>  
  
```cpp  
HRESULT InterceptCurrentException (  
    [in] ICorDebugFrame  *pFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c900-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c900-105">Parameters</span></span>  

 `pFrame`  
 <span data-ttu-id="6c900-106">진행 활성 스택 프레임을 나타내는 ICorDebugFrame에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c900-106">[in] A pointer to an ICorDebugFrame that represents the active stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c900-107">설명</span><span class="sxs-lookup"><span data-stu-id="6c900-107">Remarks</span></span>  

 <span data-ttu-id="6c900-108">`InterceptCurrentException`메서드는 예외 콜백 ([ICorDebugManagedCallback:: Exception](icordebugmanagedcallback-exception-method.md) 또는 [ICorDebugManagedCallback2:: exception](icordebugmanagedcallback2-exception-method.md))과 연결 된 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md)호출 사이에서 호출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c900-108">The `InterceptCurrentException` method can be called between an exception callback ([ICorDebugManagedCallback::Exception](icordebugmanagedcallback-exception-method.md) or [ICorDebugManagedCallback2::Exception](icordebugmanagedcallback2-exception-method.md)) and the associated call to [ICorDebugController::Continue](icordebugcontroller-continue-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c900-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c900-109">Requirements</span></span>  

 <span data-ttu-id="6c900-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c900-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c900-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6c900-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6c900-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c900-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c900-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c900-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
