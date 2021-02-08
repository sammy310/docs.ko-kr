---
description: ICorDebugManagedCallback::D ebuggerError 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 2f73e07711f7d2ce865aab8f90862563e767fd16
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791006"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="86347-103">ICorDebugManagedCallback::DebuggerError 메서드</span><span class="sxs-lookup"><span data-stu-id="86347-103">ICorDebugManagedCallback::DebuggerError Method</span></span>

<span data-ttu-id="86347-104">CLR (공용 언어 런타임)에서 이벤트를 처리 하려고 시도 하는 동안 오류가 발생 했음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="86347-104">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86347-105">구문</span><span class="sxs-lookup"><span data-stu-id="86347-105">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86347-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="86347-106">Parameters</span></span>  

 `pProcess`  
 <span data-ttu-id="86347-107">진행 이벤트가 발생 한 프로세스를 나타내는 "ICorDebugProcess" 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="86347-107">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="86347-108">진행 이벤트 처리기에서 반환 된 HRESULT 값입니다.</span><span class="sxs-lookup"><span data-stu-id="86347-108">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="86347-109">진행 CLR 오류를 지정 하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="86347-109">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86347-110">설명</span><span class="sxs-lookup"><span data-stu-id="86347-110">Remarks</span></span>  

 <span data-ttu-id="86347-111">오류 특성에 따라 프로세스를 통과 모드로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86347-111">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="86347-112">콜백은 오류가 발생 하 여 디버깅 서비스를 사용할 수 없도록 `DebugError` 설정 했으므로 디버거가 사용자에 게 오류 메시지를 사용할 수 있도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86347-112">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="86347-113">[ICorDebugProcess:: GetID](icordebugprocess-getid-method.md) 는 호출 해도 안전 하지만 [ICorDebug:: Terminate](icordebug-terminate-method.md)를 비롯 한 다른 모든 메서드는 호출 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86347-113">[ICorDebugProcess::GetID](icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="86347-114">디버거는 프로세스를 종료 하는 운영 체제 기능을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="86347-114">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86347-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="86347-115">Requirements</span></span>  

 <span data-ttu-id="86347-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86347-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86347-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="86347-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="86347-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86347-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86347-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86347-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86347-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="86347-120">See also</span></span>

- [<span data-ttu-id="86347-121">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86347-121">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
