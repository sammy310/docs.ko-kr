---
description: '자세히 알아보기: ICorProfilerCallback2:: FinalizeableObjectQueued 메서드'
title: ICorProfilerCallback2::FinalizeableObjectQueued 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.FinalizeableObjectQueued
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::FinalizeableObjectQueued
helpviewer_keywords:
- FinalizeableObjectQueued method [.NET Framework profiling]
- ICorProfilerCallback2::FinalizeableObjectQueued method [.NET Framework profiling]
ms.assetid: 92d76893-683c-475d-9996-5bff03cdb10f
topic_type:
- apiref
ms.openlocfilehash: 62424ea60f72cee2328a143e4e50acd7af33e221
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647911"
---
# <a name="icorprofilercallback2finalizeableobjectqueued-method"></a><span data-ttu-id="ceba7-103">ICorProfilerCallback2::FinalizeableObjectQueued 메서드</span><span class="sxs-lookup"><span data-stu-id="ceba7-103">ICorProfilerCallback2::FinalizeableObjectQueued Method</span></span>

<span data-ttu-id="ceba7-104">종료자를 사용 하는 개체가 해당 메서드를 실행 하기 위해 종료자 스레드에 대기 되었음을 코드 프로파일러에 알립니다 `Finalize` .</span><span class="sxs-lookup"><span data-stu-id="ceba7-104">Notifies the code profiler that an object with a finalizer has been queued to the finalizer thread for execution of its `Finalize` method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ceba7-105">구문</span><span class="sxs-lookup"><span data-stu-id="ceba7-105">Syntax</span></span>  
  
```cpp  
HRESULT FinalizeableObjectQueued(  
    [in] DWORD finalizerFlags,  
    [in] ObjectID objectID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ceba7-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ceba7-106">Parameters</span></span>  

 `finalizerFlags`  
 <span data-ttu-id="ceba7-107">진행 종료자의 여러 측면을 설명 하는 [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ceba7-107">[in] A value of the [COR_PRF_FINALIZER_FLAGS](cor-prf-finalizer-flags-enumeration.md) enumeration that describes aspects of the finalizer.</span></span>  
  
 `objectID`  
 <span data-ttu-id="ceba7-108">진행 큐에 대기 된 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ceba7-108">[in] The ID of the object that has been queued.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ceba7-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ceba7-109">Requirements</span></span>  

 <span data-ttu-id="ceba7-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ceba7-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ceba7-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ceba7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ceba7-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ceba7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ceba7-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ceba7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ceba7-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ceba7-114">See also</span></span>

- [<span data-ttu-id="ceba7-115">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ceba7-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ceba7-116">ICorProfilerCallback2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ceba7-116">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
