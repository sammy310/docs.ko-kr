---
title: ICorProfilerInfo::GetThreadContext 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetThreadContext
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetThreadContext
helpviewer_keywords:
- ICorProfilerInfo::GetThreadContext method [.NET Framework profiling]
- GetThreadContext method, ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: 79446216-4b8b-484c-8fe3-e87dbf9df2fd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b8afe10563d61e3ddab93e8d1b57eee4b6765c7
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766838"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="6a3c7-102">ICorProfilerInfo::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="6a3c7-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="6a3c7-103">현재 스레드와 연결 된 지정 된 컨텍스트 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3c7-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a3c7-104">구문</span><span class="sxs-lookup"><span data-stu-id="6a3c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a3c7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6a3c7-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="6a3c7-106">[in] 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6a3c7-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="6a3c7-107">[out] 현재 스레드와 연결 된 지정 된 컨텍스트 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6a3c7-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="6a3c7-108">스레드에 현재 연결 된 컨텍스트가 없는 경우이 함수는 CORPROF_E_DATAINCOMPLETE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3c7-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6a3c7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a3c7-109">Requirements</span></span>  
 <span data-ttu-id="6a3c7-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a3c7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a3c7-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6a3c7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6a3c7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6a3c7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6a3c7-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a3c7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a3c7-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a3c7-114">See also</span></span>

- [<span data-ttu-id="6a3c7-115">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6a3c7-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
