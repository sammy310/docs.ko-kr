---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionOSHandlerEnter 메서드'
title: ICorProfilerCallback::ExceptionOSHandlerEnter 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
ms.openlocfilehash: 88dfd062451c63265716e7cf4c04292aa15f91ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657621"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="8a49b-103">ICorProfilerCallback::ExceptionOSHandlerEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="8a49b-103">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>

<span data-ttu-id="8a49b-104">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="8a49b-104">Not implemented.</span></span> <span data-ttu-id="8a49b-105">관리 되지 않는 예외 정보가 필요한 프로파일러는 다른 방법으로이 정보를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a49b-105">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a49b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a49b-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8a49b-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a49b-107">Requirements</span></span>  

 <span data-ttu-id="8a49b-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a49b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a49b-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8a49b-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8a49b-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a49b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a49b-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a49b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a49b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a49b-112">See also</span></span>

- [<span data-ttu-id="8a49b-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a49b-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
