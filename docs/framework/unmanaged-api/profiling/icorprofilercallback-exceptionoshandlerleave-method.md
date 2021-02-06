---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionOSHandlerLeave 메서드'
title: ICorProfilerCallback::ExceptionOSHandlerLeave 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerLeave
helpviewer_keywords:
- ExceptionOSHandlerLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerLeave method [.NET Framework profiling]
ms.assetid: 4d164676-0ee9-4f67-a8ea-cb474db09053
topic_type:
- apiref
ms.openlocfilehash: 809f9440510bc0b55c9cae9827757eb61e61b257
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657569"
---
# <a name="icorprofilercallbackexceptionoshandlerleave-method"></a><span data-ttu-id="507cb-103">ICorProfilerCallback::ExceptionOSHandlerLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="507cb-103">ICorProfilerCallback::ExceptionOSHandlerLeave Method</span></span>

<span data-ttu-id="507cb-104">구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-104">Not implemented.</span></span> <span data-ttu-id="507cb-105">관리 되지 않는 예외 정보가 필요한 프로파일러는 다른 방법으로이 정보를 얻어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="507cb-105">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="507cb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="507cb-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerLeave(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="507cb-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="507cb-107">Requirements</span></span>  

 <span data-ttu-id="507cb-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="507cb-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="507cb-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="507cb-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="507cb-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="507cb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="507cb-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="507cb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="507cb-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="507cb-112">See also</span></span>

- [<span data-ttu-id="507cb-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="507cb-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
