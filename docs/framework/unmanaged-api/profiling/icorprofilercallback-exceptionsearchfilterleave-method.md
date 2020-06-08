---
title: ICorProfilerCallback::ExceptionSearchFilterLeave 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionSearchFilterLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionSearchFilterLeave method [.NET Framework profiling]
- ExceptionSearchFilterLeave method [.NET Framework profiling]
ms.assetid: c28a2a82-dd11-4385-843f-b509fb61753b
topic_type:
- apiref
ms.openlocfilehash: fbece20701fbde5551e025b4f116f9873abf444d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500210"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="2cdfb-102">ICorProfilerCallback::ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="2cdfb-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="2cdfb-103">사용자 필터의 실행이 완료 되었음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="2cdfb-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cdfb-104">구문</span><span class="sxs-lookup"><span data-stu-id="2cdfb-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="2cdfb-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2cdfb-105">Requirements</span></span>  
 <span data-ttu-id="2cdfb-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cdfb-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cdfb-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2cdfb-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2cdfb-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cdfb-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cdfb-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cdfb-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cdfb-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cdfb-110">See also</span></span>

- [<span data-ttu-id="2cdfb-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2cdfb-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="2cdfb-112">ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="2cdfb-112">ExceptionSearchFilterEnter Method</span></span>](icorprofilercallback-exceptionsearchfilterenter-method.md)
