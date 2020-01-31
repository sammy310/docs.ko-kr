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
ms.openlocfilehash: e70d8ee40e16e37a12f8ed4033d2aa7489f0f25e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863962"
---
# <a name="icorprofilerinfogetcurrentthreadid-method"></a><span data-ttu-id="ca7f2-102">ICorProfilerInfo::GetCurrentThreadID 메서드</span><span class="sxs-lookup"><span data-stu-id="ca7f2-102">ICorProfilerInfo::GetCurrentThreadID Method</span></span>
<span data-ttu-id="ca7f2-103">관리 되는 스레드인 경우 현재 스레드의 ID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-103">Gets the ID of the current thread, if it is a managed thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca7f2-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca7f2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentThreadID(  
    [out] ThreadID *pThreadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca7f2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca7f2-105">Parameters</span></span>  
 `pThreadId`  
 <span data-ttu-id="ca7f2-106">제한이 관리 되는 스레드의 반환 된 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-106">[out] A pointer to the returned ID of the managed thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca7f2-107">주의</span><span class="sxs-lookup"><span data-stu-id="ca7f2-107">Remarks</span></span>  
 <span data-ttu-id="ca7f2-108">현재 스레드가 내부 런타임 스레드나 다른 관리 되지 않는 스레드인 경우 `GetCurrentThreadID`는 HRESULT로 CORPROF_E_NOT_MANAGED_THREAD을 반환 하 고 `pThreadId` 매개 변수의 반환 된 값은 null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-108">If the current thread is an internal runtime thread or other unmanaged thread, `GetCurrentThreadID` returns CORPROF_E_NOT_MANAGED_THREAD as the HRESULT, and the returned value of the `pThreadId` parameter will be null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca7f2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca7f2-109">Requirements</span></span>  
 <span data-ttu-id="ca7f2-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca7f2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca7f2-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ca7f2-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ca7f2-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca7f2-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca7f2-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca7f2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca7f2-114">참조</span><span class="sxs-lookup"><span data-stu-id="ca7f2-114">See also</span></span>

- [<span data-ttu-id="ca7f2-115">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca7f2-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
