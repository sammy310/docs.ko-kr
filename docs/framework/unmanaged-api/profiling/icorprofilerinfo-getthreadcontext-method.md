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
ms.openlocfilehash: f8eff85392d355ea54980ac6b29e3c4cebb1b240
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869598"
---
# <a name="icorprofilerinfogetthreadcontext-method"></a><span data-ttu-id="51ab1-102">ICorProfilerInfo::GetThreadContext 메서드</span><span class="sxs-lookup"><span data-stu-id="51ab1-102">ICorProfilerInfo::GetThreadContext Method</span></span>
<span data-ttu-id="51ab1-103">지정 된 스레드와 현재 연결 된 컨텍스트 id를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="51ab1-103">Gets the context identity currently associated with the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51ab1-104">구문</span><span class="sxs-lookup"><span data-stu-id="51ab1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in]  ThreadID  threadId,  
    [out] ContextID *pContextId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51ab1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="51ab1-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="51ab1-106">진행 스레드의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="51ab1-106">[in] The ID of the thread.</span></span>  
  
 `pContextId`  
 <span data-ttu-id="51ab1-107">제한이 지정 된 스레드와 현재 연결 된 컨텍스트 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="51ab1-107">[out] A pointer to the context ID currently associated with the specified thread.</span></span> <span data-ttu-id="51ab1-108">스레드에 현재 연결 된 컨텍스트가 없으면이 함수는 CORPROF_E_DATAINCOMPLETE을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="51ab1-108">If the thread has no context currently associated with it, this function will return CORPROF_E_DATAINCOMPLETE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51ab1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="51ab1-109">Requirements</span></span>  
 <span data-ttu-id="51ab1-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51ab1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51ab1-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51ab1-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51ab1-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51ab1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51ab1-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51ab1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51ab1-114">참조</span><span class="sxs-lookup"><span data-stu-id="51ab1-114">See also</span></span>

- [<span data-ttu-id="51ab1-115">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="51ab1-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
