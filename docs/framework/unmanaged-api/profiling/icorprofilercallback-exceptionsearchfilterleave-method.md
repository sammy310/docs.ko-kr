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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e89b76f7a246277737123e180c20874940437506
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124646"
---
# <a name="icorprofilercallbackexceptionsearchfilterleave-method"></a><span data-ttu-id="231cc-102">ICorProfilerCallback::ExceptionSearchFilterLeave 메서드</span><span class="sxs-lookup"><span data-stu-id="231cc-102">ICorProfilerCallback::ExceptionSearchFilterLeave Method</span></span>
<span data-ttu-id="231cc-103">사용자 필터를 방금 실행을 마친 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="231cc-103">Notifies the profiler that a user filter has just finished executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="231cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="231cc-104">Syntax</span></span>  
  
```  
HRESULT ExceptionSearchFilterLeave();  
```  
  
## <a name="requirements"></a><span data-ttu-id="231cc-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="231cc-105">Requirements</span></span>  
 <span data-ttu-id="231cc-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="231cc-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="231cc-107">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="231cc-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="231cc-108">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="231cc-108">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="231cc-109">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="231cc-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="231cc-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="231cc-110">See also</span></span>

- [<span data-ttu-id="231cc-111">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="231cc-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="231cc-112">ExceptionSearchFilterEnter 메서드</span><span class="sxs-lookup"><span data-stu-id="231cc-112">ExceptionSearchFilterEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)
