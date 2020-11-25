---
title: ICorProfilerInfo::GetCurrentThreadID 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCurrentThreadID
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCurrentThreadID
helpviewer_keywords:
- GetCurrentThreadID method, ICorProfilerInfo interface [.NET Framework profiling]
- ICorProfilerInfo::GetCurrentThreadID method [.NET Framework profiling]
ms.assetid: 39bbdb30-6a7a-4202-8da3-67ae9a0ab3a8
topic_type:
- apiref
ms.openlocfilehash: 18298c4c726d7d850e67afbf82ca77b7511d8917
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722595"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="03d8b-102">ICorProfilerInfo::GetCurrentThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="03d8b-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>

<span data-ttu-id="03d8b-103">관리 되는 스레드인 경우 현재 스레드의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="03d8b-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03d8b-104">구문</span><span class="sxs-lookup"><span data-stu-id="03d8b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03d8b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="03d8b-105">Parameters</span></span>  

 `pThreadId`  
 <span data-ttu-id="03d8b-106">제한이 관리 되는 스레드의 반환 된 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="03d8b-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03d8b-107">설명</span><span class="sxs-lookup"><span data-stu-id="03d8b-107">Remarks</span></span>  

 <span data-ttu-id="03d8b-108">현재 스레드가 내부 런타임 스레드나 다른 관리 되지 않는 스레드인 경우 `GetCurrentThreadID` CORPROF_E_NOT_MANAGED_THREAD를 HRESULT로 반환 하 고 매개 변수의 반환 된 값은 `pThreadId` null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03d8b-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03d8b-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="03d8b-109">Requirements</span></span>  

 <span data-ttu-id="03d8b-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03d8b-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03d8b-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="03d8b-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="03d8b-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="03d8b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="03d8b-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03d8b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d8b-114">참조</span><span class="sxs-lookup"><span data-stu-id="03d8b-114">See also</span></span>

- [<span data-ttu-id="03d8b-115">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="03d8b-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
