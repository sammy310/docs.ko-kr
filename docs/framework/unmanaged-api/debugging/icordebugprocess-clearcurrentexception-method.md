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
ms.openlocfilehash: 0d36390a905561b64b3ca6ca95722f82158450be
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95695220"
---
# <a name="icordebugprocessclearcurrentexception-method"></a><span data-ttu-id="eea60-102">ICorDebugProcess::ClearCurrentException 메서드</span><span class="sxs-lookup"><span data-stu-id="eea60-102">ICorDebugProcess::ClearCurrentException Method</span></span>

<span data-ttu-id="eea60-103">지정 된 스레드에서 현재 관리 되지 않는 예외를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="eea60-103">Clears the current unmanaged exception on the given thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eea60-104">구문</span><span class="sxs-lookup"><span data-stu-id="eea60-104">Syntax</span></span>  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eea60-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eea60-105">Parameters</span></span>  

 `threadID`  
 <span data-ttu-id="eea60-106">진행 현재 관리 되지 않는 예외를 지울 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="eea60-106">[in] The ID of the thread on which the current unmanaged exception will be cleared.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eea60-107">설명</span><span class="sxs-lookup"><span data-stu-id="eea60-107">Remarks</span></span>  

 <span data-ttu-id="eea60-108">스레드가 디버기에서 무시 해야 하는 관리 되지 않는 예외를 보고 한 경우 [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) 를 호출 하기 전에이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="eea60-108">Call this method before calling [ICorDebugController::Continue](icordebugcontroller-continue-method.md) when a thread has reported an unmanaged exception that should be ignored by the debuggee.</span></span> <span data-ttu-id="eea60-109">그러면 지정 된 스레드의 IB (대역 외) 및 OOB (대역 외) 이벤트가 모두 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="eea60-109">This will clear both the outstanding in-band (IB) and out-of-band (OOB) events on the given thread.</span></span> <span data-ttu-id="eea60-110">모든 OOB 중단점과 단일 단계 예외는 자동으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="eea60-110">All OOB breakpoints and single-step exceptions are automatically cleared.</span></span>  
  
 <span data-ttu-id="eea60-111">[ICorDebugThread2:: InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) 를 사용 하 여 스레드에서 현재 관리 되는 예외를 가로챌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eea60-111">Use [ICorDebugThread2::InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) to intercept the current managed exception on a thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eea60-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eea60-112">Requirements</span></span>  

 <span data-ttu-id="eea60-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eea60-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eea60-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eea60-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eea60-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eea60-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eea60-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eea60-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
