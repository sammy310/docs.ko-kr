---
title: ICorDebugProcess::GetHelperThreadID 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetHelperThreadID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetHelperThreadID
helpviewer_keywords:
- GetHelperThreadID method [.NET Framework debugging]
- ICorDebugProcess::GetHelperThreadID method [.NET Framework debugging]
ms.assetid: 84e1e605-37c1-49a5-8e12-35db85654622
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd5e30d08e667dcd5a8be1f9502462f28290068e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987742"
---
# <a name="icordebugprocessgethelperthreadid-method"></a><span data-ttu-id="c7647-102">ICorDebugProcess::GetHelperThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="c7647-102">ICorDebugProcess::GetHelperThreadID Method</span></span>
<span data-ttu-id="c7647-103">디버거의 내부 도우미 스레드의 운영 체제 (OS) 스레드 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c7647-103">Gets the operating system (OS) thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7647-104">구문</span><span class="sxs-lookup"><span data-stu-id="c7647-104">Syntax</span></span>  
  
```  
HRESULT GetHelperThreadID (  
    [out] DWORD *pThreadID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7647-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c7647-105">Parameters</span></span>  
 `pThreadID`  
 <span data-ttu-id="c7647-106">[out] OS에 대 한 포인터 스레드 디버거의 내부 도우미 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c7647-106">[out] A pointer to the OS thread ID of the debugger's internal helper thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7647-107">설명</span><span class="sxs-lookup"><span data-stu-id="c7647-107">Remarks</span></span>  
 <span data-ttu-id="c7647-108">관리 및 관리 되지 않는 디버그 하는 동안는 디버거의 디버거에 의해 배치 중단점이 적중 될 경우 지정된 된 ID 사용 하 여 스레드가 계속 실행 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7647-108">During managed and unmanaged debugging, it is the debugger's responsibility to ensure that the thread with the specified ID remains running if it hits a breakpoint placed by the debugger.</span></span> <span data-ttu-id="c7647-109">디버거는 사용자 로부터이 스레드를 숨길 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7647-109">A debugger may also wish to hide this thread from the user.</span></span> <span data-ttu-id="c7647-110">도우미 스레드가 아직 프로세스에 있는 경우는 `GetHelperThreadID` 에서 0을 반환 하는 메서드 \*`pThreadID`합니다.</span><span class="sxs-lookup"><span data-stu-id="c7647-110">If no helper thread exists in the process yet, the `GetHelperThreadID` method returns zero in \*`pThreadID`.</span></span>  
  
 <span data-ttu-id="c7647-111">시간이 지남에 따라 변경 될 수 있으므로 도우미 스레드의 스레드 ID를 캐시할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c7647-111">You cannot cache the thread ID of the helper thread, because it may change over time.</span></span> <span data-ttu-id="c7647-112">다시 중지 이벤트가 발생할 때마다 스레드 ID를 쿼리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7647-112">You must re-query the thread ID at every stopping event.</span></span>  
  
 <span data-ttu-id="c7647-113">스레드 ID의 디버거 도우미 스레드에서 수정 될 모든 관리 되지 않는 [icordebugmanagedcallback:: Createthread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) 디버거 도우미 스레드 스레드 ID를 확인 하 고 사용자 로부터 숨길 있으므로 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="c7647-113">The thread ID of the debugger's helper thread will be correct on every unmanaged [ICorDebugManagedCallback::CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) event, thus allowing a debugger to determine the thread ID of its helper thread and hide it from the user.</span></span> <span data-ttu-id="c7647-114">관리 되지 않는 동안 도우미 스레드로 식별 되는 스레드 `ICorDebugManagedCallback::CreateThread` 이벤트는 관리 되는 사용자 코드를 실행 되지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c7647-114">A thread that is identified as a helper thread during an unmanaged `ICorDebugManagedCallback::CreateThread` event will never run managed user code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7647-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c7647-115">Requirements</span></span>  
 <span data-ttu-id="c7647-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7647-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7647-117">**헤더:** CorDebug.idl.</span><span class="sxs-lookup"><span data-stu-id="c7647-117">**Header:** CorDebug.idl.</span></span> <span data-ttu-id="c7647-118">CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7647-118">CorDebug.h</span></span>  
  
 <span data-ttu-id="c7647-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7647-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7647-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7647-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
