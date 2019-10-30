---
title: 'ICorDebugMutableDataTarget:: SetThreadContext 메서드'
ms.date: 03/30/2017
ms.assetid: 8c0d01d5-67e5-4522-9ccf-c8f3a78cb4fd
ms.openlocfilehash: 2c9e508c7a4059fee4e1cce6eb28e6de7b2fff6d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132712"
---
# <a name="icordebugmutabledatatargetsetthreadcontext-method"></a><span data-ttu-id="3d46d-102">ICorDebugMutableDataTarget:: SetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="3d46d-102">ICorDebugMutableDataTarget::SetThreadContext Method</span></span>
<span data-ttu-id="3d46d-103">스레드에 대한 컨텍스트(레지스터 값)를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3d46d-103">Sets the context (register values) for a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d46d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d46d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
   [in] DWORD dwThreadID,  
   [in] ULONG32 contextSize,   [in, size_is(contextSize)] const BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d46d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d46d-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="3d46d-106">[in] 운영 체제에서 정의된 스레드 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d46d-106">[in] The operating system-defined thread identifier.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="3d46d-107">[in] 쓸 `pContext` 버퍼의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3d46d-107">[in] The size of the `pContext` buffer to be written.</span></span>  
  
 `pContext`  
 <span data-ttu-id="3d46d-108">[in] 쓸 바이트에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3d46d-108">[in] A pointer to the bytes to be written.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d46d-109">주의</span><span class="sxs-lookup"><span data-stu-id="3d46d-109">Remarks</span></span>  
 <span data-ttu-id="3d46d-110">`SetThreadContext` 메서드는 운영 체제에서 정의된 `dwThreadID` 인수로 지정된 스레드에 대한 현재 컨텍스트를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="3d46d-110">The `SetThreadContext` method updates the current context for the thread specified by the operating system-defined `dwThreadID` argument.</span></span> <span data-ttu-id="3d46d-111">컨텍스트 레코드의 형식은 [ICorDebugDataTarget:: getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드로 표시 되는 플랫폼에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d46d-111">The format of the context record is determined by the platform indicated by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="3d46d-112">Windows에서는 [컨텍스트](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="3d46d-112">On Windows, this is a [CONTEXT](/windows/win32/api/winnt/ns-winnt-arm64_nt_context) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d46d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d46d-113">Requirements</span></span>  
 <span data-ttu-id="3d46d-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d46d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d46d-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d46d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d46d-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d46d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d46d-117">**.NET Framework 버전:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d46d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d46d-118">참조</span><span class="sxs-lookup"><span data-stu-id="3d46d-118">See also</span></span>

- [<span data-ttu-id="3d46d-119">ICorDebugMutableDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d46d-119">ICorDebugMutableDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-interface.md)
- [<span data-ttu-id="3d46d-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d46d-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
