---
title: ICorDebugDataTarget::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2db073f6bde3ded27f8e1aa41bfcb87e764745f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174969"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="e5c3d-102">ICorDebugDataTarget::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="e5c3d-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="e5c3d-103">지정 된 스레드에 대 한 현재 스레드 컨텍스트를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e5c3d-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5c3d-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5c3d-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5c3d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5c3d-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="e5c3d-106">[in] 해당 컨텍스트를 검색할는 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c3d-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="e5c3d-107">식별자는 운영 체제에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5c3d-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="e5c3d-108">[in] 컨텍스트의 부분 읽어들여야 함을 나타내는 플랫폼에 종속 된 플래그의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c3d-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="e5c3d-109">[in] `pContext`의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c3d-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="e5c3d-110">[out] 스레드 컨텍스트를 저장할 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="e5c3d-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e5c3d-111">설명</span><span class="sxs-lookup"><span data-stu-id="e5c3d-111">Remarks</span></span>  
 <span data-ttu-id="e5c3d-112">Windows 플랫폼에서 `pContext` 이어야 합니다는 `CONTEXT` 구조 (WinNT.h에 정의 됨)으로 지정 된 컴퓨터 종류에 적합 합니다 [icordebugdatatarget:: Getplatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e5c3d-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="e5c3d-113">`contextFlags` 으로 동일한 값이 있어야 합니다 `ContextFlags` 필드는 `CONTEXT` 구조.</span><span class="sxs-lookup"><span data-stu-id="e5c3d-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="e5c3d-114">`CONTEXT` 구조체가 프로세서별 대 한 자세한 내용은 WinNT.h 파일을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5c3d-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5c3d-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5c3d-115">Requirements</span></span>  
 <span data-ttu-id="e5c3d-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e5c3d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5c3d-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e5c3d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e5c3d-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e5c3d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e5c3d-119">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5c3d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5c3d-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="e5c3d-120">See also</span></span>

- [<span data-ttu-id="e5c3d-121">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5c3d-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="e5c3d-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5c3d-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="e5c3d-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="e5c3d-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
