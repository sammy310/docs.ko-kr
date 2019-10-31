---
title: ICorDebugManagedCallback::DebuggerError 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
ms.openlocfilehash: c03be2405e1ab0287a2921b6e2e293862c67a193
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137368"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="0a154-102">ICorDebugManagedCallback::DebuggerError 메서드</span><span class="sxs-lookup"><span data-stu-id="0a154-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="0a154-103">CLR (공용 언어 런타임)에서 이벤트를 처리 하려고 시도 하는 동안 오류가 발생 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="0a154-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a154-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a154-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a154-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a154-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="0a154-106">진행 이벤트가 발생 한 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0a154-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="0a154-107">진행 이벤트 처리기에서 반환 된 HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="0a154-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="0a154-108">진행 CLR 오류를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="0a154-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a154-109">주의</span><span class="sxs-lookup"><span data-stu-id="0a154-109">Remarks</span></span>  
 <span data-ttu-id="0a154-110">오류 특성에 따라 프로세스를 통과 모드로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a154-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="0a154-111">`DebugError` 콜백은 오류로 인해 디버깅 서비스를 사용할 수 없도록 설정 했으므로 디버거가 사용자에 게 오류 메시지를 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a154-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="0a154-112">[ICorDebugProcess:: GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) 는 호출 해도 안전 하지만 [ICorDebug:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)를 비롯 한 다른 모든 메서드는 호출 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a154-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="0a154-113">디버거는 프로세스를 종료 하는 운영 체제 기능을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a154-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a154-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a154-114">Requirements</span></span>  
 <span data-ttu-id="0a154-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a154-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a154-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a154-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a154-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a154-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a154-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a154-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a154-119">참조</span><span class="sxs-lookup"><span data-stu-id="0a154-119">See also</span></span>

- [<span data-ttu-id="0a154-120">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a154-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
