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
ms.openlocfilehash: f26fd93d42a709249936815d3c29ae572482f427
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224626"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="318ad-102">ICorProfilerInfo::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="318ad-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="318ad-103">현재 스레드와 연결 된 지정 된 컨텍스트 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="318ad-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="318ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="318ad-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="318ad-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="318ad-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="318ad-106">[in] 스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="318ad-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="318ad-107">[out] 현재 스레드와 연결 된 지정 된 컨텍스트 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="318ad-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="318ad-108">스레드에 현재 연결 된 컨텍스트가 없는 경우이 함수는 CORPROF_E_DATAINCOMPLETE를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="318ad-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="318ad-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="318ad-109">Requirements</span></span>  
 <span data-ttu-id="318ad-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="318ad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="318ad-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="318ad-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="318ad-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="318ad-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="318ad-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="318ad-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="318ad-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="318ad-114">See also</span></span>

- [<span data-ttu-id="318ad-115">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="318ad-115">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
