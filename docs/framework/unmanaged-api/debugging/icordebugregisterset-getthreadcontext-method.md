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
ms.openlocfilehash: 8137d5477b75b864e223852cf524ac8c5b6c0f2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792086"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="35853-102">ICorDebugRegisterSet::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="35853-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="35853-103">현재 스레드의 컨텍스트를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="35853-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35853-104">구문</span><span class="sxs-lookup"><span data-stu-id="35853-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35853-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="35853-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="35853-106">진행 `context` 배열의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="35853-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="35853-107">[in, out] 현재 플랫폼에 대 한 Win32 `CONTEXT` 구조를 구성 하는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="35853-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="35853-108">주의</span><span class="sxs-lookup"><span data-stu-id="35853-108">Remarks</span></span>  
 <span data-ttu-id="35853-109">스레드가 일시적으로 변경 된 "하이재킹" 상태가 될 수 있으므로 디버거가 Win32 `GetThreadContext` 함수 대신이 함수를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35853-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="35853-110">반환 되는 데이터는 현재 플랫폼에 대 한 Win32 `CONTEXT` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="35853-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="35853-111">리프가 아닌 프레임의 경우 클라이언트는 [ICorDebugRegisterSet:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md)를 사용 하 여 유효한 레지스터를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35853-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35853-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="35853-112">Requirements</span></span>  
 <span data-ttu-id="35853-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="35853-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35853-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35853-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35853-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35853-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35853-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35853-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35853-117">참조</span><span class="sxs-lookup"><span data-stu-id="35853-117">See also</span></span>

- [<span data-ttu-id="35853-118">ICorDebugRegisterSet 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35853-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="35853-119">ICorDebugRegisterSet2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="35853-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
