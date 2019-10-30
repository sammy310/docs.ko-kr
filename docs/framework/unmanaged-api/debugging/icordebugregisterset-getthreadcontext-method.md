---
title: ICorDebugRegisterSet::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
ms.openlocfilehash: db4f9bc6277015055cbcdb509628f2862a71dbc4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127161"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="09cc5-102">ICorDebugRegisterSet::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="09cc5-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="09cc5-103">현재 스레드의 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="09cc5-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09cc5-104">구문</span><span class="sxs-lookup"><span data-stu-id="09cc5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09cc5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09cc5-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="09cc5-106">진행 `context` 배열의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="09cc5-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="09cc5-107">[in, out] 현재 플랫폼에 대 한 Win32 `CONTEXT` 구조를 구성 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="09cc5-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09cc5-108">주의</span><span class="sxs-lookup"><span data-stu-id="09cc5-108">Remarks</span></span>  
 <span data-ttu-id="09cc5-109">스레드가 일시적으로 변경 된 "하이재킹" 상태가 될 수 있으므로 디버거가 Win32 `GetThreadContext` 함수 대신이 함수를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09cc5-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="09cc5-110">반환 되는 데이터는 현재 플랫폼에 대 한 Win32 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="09cc5-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="09cc5-111">리프가 아닌 프레임의 경우 클라이언트는 [ICorDebugRegisterSet:: GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md)를 사용 하 여 유효한 레지스터를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09cc5-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09cc5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09cc5-112">Requirements</span></span>  
 <span data-ttu-id="09cc5-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09cc5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09cc5-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="09cc5-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="09cc5-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09cc5-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09cc5-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09cc5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09cc5-117">참조</span><span class="sxs-lookup"><span data-stu-id="09cc5-117">See also</span></span>

- [<span data-ttu-id="09cc5-118">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09cc5-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="09cc5-119">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09cc5-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
