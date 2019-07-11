---
title: ICorDebugProcess::ClearCurrentException 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ad7dd3ae0e547933fdf7d579116dccc62ae579c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766153"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="5da7a-102">ICorDebugProcess::ClearCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="5da7a-102">ICorDebugProcess::ClearCurrentException Method</span></span>
<span data-ttu-id="5da7a-103">지정 된 스레드에서 현재 관리 되지 않는 예외를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5da7a-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5da7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="5da7a-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5da7a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5da7a-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="5da7a-106">[in] 현재 관리 되지 않는 예외를 지울 수 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5da7a-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5da7a-107">설명</span><span class="sxs-lookup"><span data-stu-id="5da7a-107">Remarks</span></span>  
 <span data-ttu-id="5da7a-108">이 메서드를 호출 하기 전에 [icordebugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) 경우 스레드가 디버기는 무시 해야 하는 관리 되지 않는 예외를 보고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="5da7a-108">Call this method before calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="5da7a-109">처리 중인 대역 (IB) 및 지정 된 스레드에서 대역의 (OOB) 이벤트를 모두 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5da7a-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="5da7a-110">모든 OOB 중단점 및 단일 단계 예외를 자동으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="5da7a-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="5da7a-111">사용 하 여 [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) 를 가로채는 현재 스레드에서 예외를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5da7a-111">Use [ICorDebugThread2::InterceptCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5da7a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5da7a-112">Requirements</span></span>  
 <span data-ttu-id="5da7a-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5da7a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5da7a-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5da7a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5da7a-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5da7a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5da7a-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5da7a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
