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
ms.openlocfilehash: 0631afe149c7a179a6cda4b5e491ad28653ddee9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59111919"
---
# <a name="icorprofilerinfogetthreadinfo-method"></a><span data-ttu-id="2026b-102">ICorProfilerInfo::GetThreadInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="2026b-102">ICorProfilerInfo::GetThreadInfo Method</span></span>
<span data-ttu-id="2026b-103">지정 된 스레드에 대 한 현재 Win32 스레드 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2026b-103">Gets the current Win32 thread identity for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2026b-104">구문</span><span class="sxs-lookup"><span data-stu-id="2026b-104">Syntax</span></span>  
  
```  
HRESULT GetThreadInfo(  
    [in]  ThreadID threadId,  
    [out] DWORD    *pdwWin32ThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2026b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2026b-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="2026b-106">[in] Id입니다. 현재 Win32 가져올 스레드의 ID</span><span class="sxs-lookup"><span data-stu-id="2026b-106">[in] The ID of the thread for which to get the current Win32 ID.</span></span>  
  
 `pdwWin32ThreadId`  
 <span data-ttu-id="2026b-107">[out] 에 대 한 포인터는 지정한 스레드의 현재 Win32 스레드 id입니다.</span><span class="sxs-lookup"><span data-stu-id="2026b-107">[out] A pointer to the specified thread's current Win32 thread ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2026b-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2026b-108">Requirements</span></span>  
 <span data-ttu-id="2026b-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="2026b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2026b-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2026b-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2026b-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2026b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2026b-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2026b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2026b-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="2026b-113">See also</span></span>

- [<span data-ttu-id="2026b-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2026b-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
