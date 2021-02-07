---
description: '자세히 알아보기: ICorDebugDataTarget:: GetThreadContext 메서드'
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
ms.openlocfilehash: cf40579aa0a495af4e5e775334d177ca6f3da86f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710636"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="5a076-103">ICorDebugDataTarget::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="5a076-103">ICorDebugDataTarget::GetThreadContext Method</span></span>

<span data-ttu-id="5a076-104">지정 된 스레드에 대 한 현재 스레드 컨텍스트를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a076-104">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a076-105">구문</span><span class="sxs-lookup"><span data-stu-id="5a076-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a076-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5a076-106">Parameters</span></span>  

 `dwThreadID`  
 <span data-ttu-id="5a076-107">진행 컨텍스트를 검색할 스레드의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5a076-107">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="5a076-108">식별자는 운영 체제에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a076-108">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="5a076-109">진행 읽을 컨텍스트의 부분을 나타내는 플랫폼 종속 플래그의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="5a076-109">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="5a076-110">[in] `pContext`의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="5a076-110">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="5a076-111">제한이 스레드 컨텍스트가 저장 될 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="5a076-111">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a076-112">설명</span><span class="sxs-lookup"><span data-stu-id="5a076-112">Remarks</span></span>  

 <span data-ttu-id="5a076-113">Windows 플랫폼에서은 `pContext` `CONTEXT` [ICorDebugDataTarget:: getplatform](icordebugdatatarget-getplatform-method.md) 메서드로 지정 된 컴퓨터 유형에 적절 한 구조 (winnt.exe에 정의 됨) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a076-113">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="5a076-114">`contextFlags` 구조체의 필드와 값이 같아야 합니다 `ContextFlags` `CONTEXT` .</span><span class="sxs-lookup"><span data-stu-id="5a076-114">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="5a076-115">`CONTEXT`구조는 프로세서 마다 다릅니다. 자세한 내용은 winnt.exe 파일을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a076-115">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a076-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a076-116">Requirements</span></span>  

 <span data-ttu-id="5a076-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a076-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a076-118">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5a076-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5a076-119">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a076-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a076-120">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a076-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a076-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a076-121">See also</span></span>

- [<span data-ttu-id="5a076-122">ICorDebugDataTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a076-122">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="5a076-123">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a076-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="5a076-124">디버깅</span><span class="sxs-lookup"><span data-stu-id="5a076-124">Debugging</span></span>](index.md)
