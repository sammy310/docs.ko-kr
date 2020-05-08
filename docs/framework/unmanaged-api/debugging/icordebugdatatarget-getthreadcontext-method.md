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
ms.openlocfilehash: 79708aa5a2abcb8d7465f82a8beb918484c193b9
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976553"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="cc767-102">ICorDebugDataTarget::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="cc767-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="cc767-103">지정 된 스레드에 대 한 현재 스레드 컨텍스트를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc767-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc767-104">구문</span><span class="sxs-lookup"><span data-stu-id="cc767-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc767-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc767-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="cc767-106">진행 컨텍스트를 검색할 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="cc767-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="cc767-107">식별자는 운영 체제에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc767-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="cc767-108">진행 읽을 컨텍스트의 부분을 나타내는 플랫폼 종속 플래그의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="cc767-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="cc767-109">[in] `pContext`의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="cc767-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="cc767-110">제한이 스레드 컨텍스트가 저장 될 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="cc767-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc767-111">설명</span><span class="sxs-lookup"><span data-stu-id="cc767-111">Remarks</span></span>  
 <span data-ttu-id="cc767-112">Windows 플랫폼에서은 `pContext` `CONTEXT` [ICorDebugDataTarget:: getplatform](icordebugdatatarget-getplatform-method.md) 메서드로 지정 된 컴퓨터 유형에 적절 한 구조 (winnt.exe에 정의 됨) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc767-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="cc767-113">`contextFlags``CONTEXT` 구조체의 `ContextFlags` 필드와 값이 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc767-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="cc767-114">구조 `CONTEXT` 는 프로세서에만 해당 됩니다. 자세한 내용은 Winnt.sif 파일을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc767-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc767-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cc767-115">Requirements</span></span>  
 <span data-ttu-id="cc767-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc767-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc767-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc767-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc767-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc767-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc767-119">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc767-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc767-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc767-120">See also</span></span>

- [<span data-ttu-id="cc767-121">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc767-121">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="cc767-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cc767-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="cc767-123">디버깅</span><span class="sxs-lookup"><span data-stu-id="cc767-123">Debugging</span></span>](index.md)
