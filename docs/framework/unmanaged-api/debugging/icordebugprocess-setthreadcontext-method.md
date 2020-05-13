---
title: ICorDebugProcess::SetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
ms.openlocfilehash: c9e403dc8cbb75a1e93c426a9e0b3a2083f1f10e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210464"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="6df17-102">ICorDebugProcess::SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="6df17-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="6df17-103">이 프로세스의 지정 된 스레드에 대 한 컨텍스트를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6df17-104">구문</span><span class="sxs-lookup"><span data-stu-id="6df17-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6df17-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6df17-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="6df17-106">진행 컨텍스트를 설정할 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="6df17-107">[in] `context` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="6df17-108">진행 스레드의 컨텍스트를 설명 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="6df17-109">컨텍스트는 스레드가 실행 되는 프로세서의 아키텍처를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6df17-110">설명</span><span class="sxs-lookup"><span data-stu-id="6df17-110">Remarks</span></span>  
 <span data-ttu-id="6df17-111">`SetThreadContext`스레드가 실제로 해당 컨텍스트가 일시적으로 변경 된 "하이재킹" 상태가 될 수 있으므로 디버거가 Win32 함수 대신이 메서드를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="6df17-112">이 메서드는 스레드가 네이티브 코드에 있는 경우에만 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="6df17-113">관리 코드에서 스레드에 대해 [ICorDebugRegisterSet](icordebugregisterset-interface.md) 를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-113">Use [ICorDebugRegisterSet](icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="6df17-114">OOB (대역 외) 디버그 이벤트 중에는 스레드의 컨텍스트를 수정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="6df17-115">전달 된 데이터는 현재 플랫폼에 대 한 컨텍스트 구조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="6df17-116">이 메서드는 부적절 하 게 사용 되는 경우 런타임을 손상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6df17-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6df17-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6df17-117">Requirements</span></span>  
 <span data-ttu-id="6df17-118">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6df17-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6df17-119">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6df17-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6df17-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6df17-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6df17-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6df17-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
