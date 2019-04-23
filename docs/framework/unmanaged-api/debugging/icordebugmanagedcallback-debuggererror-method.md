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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd7909b94343b1fb83836f5c369ddc1993f049d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59191176"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="d028f-102">ICorDebugManagedCallback::DebuggerError 메서드</span><span class="sxs-lookup"><span data-stu-id="d028f-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="d028f-103">CLR (공용 언어 런타임)의 이벤트를 처리 하는 동안 오류가 발생 했습니다는 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="d028f-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d028f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d028f-104">Syntax</span></span>  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d028f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d028f-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="d028f-106">[in] 이벤트가 발생 한 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d028f-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="d028f-107">[in] 이벤트 처리기에서 반환 된 HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d028f-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="d028f-108">[in] CLR 오류를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="d028f-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d028f-109">설명</span><span class="sxs-lookup"><span data-stu-id="d028f-109">Remarks</span></span>  
 <span data-ttu-id="d028f-110">프로세스 오류의 성격에 따라 통과 모드로 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d028f-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="d028f-111">`DebugError` 콜백 있도록 오류 메시지를 사용할 수 있는 사용자에 게 디버깅 서비스가 오류로 인해 비활성화 되었습니다.는 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d028f-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="d028f-112">[Icordebugprocess:: Getid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) 호출을 포함 한 다른 모든 메서드를 안전한 [icordebug:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)를 호출 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d028f-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="d028f-113">디버거는 프로세스 종료에 대 한 운영 체제 기능을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d028f-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d028f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d028f-114">Requirements</span></span>  
 <span data-ttu-id="d028f-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d028f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d028f-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d028f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d028f-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d028f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d028f-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d028f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d028f-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="d028f-119">See also</span></span>

- [<span data-ttu-id="d028f-120">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d028f-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
