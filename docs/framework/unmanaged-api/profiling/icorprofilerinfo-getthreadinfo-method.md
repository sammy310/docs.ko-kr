---
title: ICorProfilerInfo::GetThreadInfo 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadInfo
helpviewer_keywords:
- ICorProfilerInfo::GetThreadInfo method [.NET Framework profiling]
- GetThreadInfo method [.NET Framework profiling]
ms.assetid: fc994fef-65c9-432a-84cb-66c8141147e7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 405d5ff49ba7bc2e5204f00cf50c30822354e56d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775591"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="e3691-102">ICorProfilerInfo::GetThreadInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="e3691-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="e3691-103">지정 된 스레드에 대 한 현재 Win32 스레드 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3691-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3691-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3691-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3691-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3691-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="e3691-106">[in] Id입니다. 현재 Win32 가져올 스레드의 ID</span><span class="sxs-lookup"><span data-stu-id="e3691-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="e3691-107">[out] 에 대 한 포인터는 지정한 스레드의 현재 Win32 스레드 id입니다.</span><span class="sxs-lookup"><span data-stu-id="e3691-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3691-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3691-108">Requirements</span></span>  
 <span data-ttu-id="e3691-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e3691-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3691-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e3691-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e3691-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3691-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3691-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3691-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3691-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="e3691-113">See also</span></span>

- [<span data-ttu-id="e3691-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3691-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
