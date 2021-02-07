---
description: '자세히 알아보기: ICorProfilerInfo:: GetThreadContext 메서드'
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
ms.openlocfilehash: b2970da90250819cc68eee55b70188d4830113a6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687274"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="fb6cb-103">ICorProfilerInfo::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="fb6cb-103">ICorProfilerInfo::GetThreadContext Method</span></span>

<span data-ttu-id="fb6cb-104">지정 된 스레드와 현재 연결 된 컨텍스트 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fb6cb-104">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb6cb-105">구문</span><span class="sxs-lookup"><span data-stu-id="fb6cb-105">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb6cb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb6cb-106">Parameters</span></span>  

 `threadId`  
 <span data-ttu-id="fb6cb-107">진행 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fb6cb-107">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="fb6cb-108">제한이 지정 된 스레드와 현재 연결 된 컨텍스트 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fb6cb-108">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="fb6cb-109">스레드에 현재 연결 된 컨텍스트가 없으면이 함수는 CORPROF_E_DATAINCOMPLETE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb6cb-109">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb6cb-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb6cb-110">Requirements</span></span>  

 <span data-ttu-id="fb6cb-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb6cb-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb6cb-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb6cb-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb6cb-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb6cb-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb6cb-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb6cb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb6cb-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb6cb-115">See also</span></span>

- [<span data-ttu-id="fb6cb-116">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb6cb-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
