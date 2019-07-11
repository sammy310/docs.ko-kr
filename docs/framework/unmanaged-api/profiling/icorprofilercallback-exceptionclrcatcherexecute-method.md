---
title: ICorProfilerCallback::ExceptionCLRCatcherExecute 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a17776b38d7e16b39f966e0d83d50a7d004d4c3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776063"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="1055d-102">ICorProfilerCallback::ExceptionCLRCatcherExecute 메서드</span><span class="sxs-lookup"><span data-stu-id="1055d-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="1055d-103">될 때 호출을 `catch` 차단 예외는 CLR (공용 언어 런타임) 자체 내에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1055d-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="1055d-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1055d-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1055d-105">구문</span><span class="sxs-lookup"><span data-stu-id="1055d-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="1055d-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1055d-106">Requirements</span></span>  
 <span data-ttu-id="1055d-107">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1055d-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1055d-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1055d-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1055d-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1055d-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1055d-110">**.NET framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="1055d-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1055d-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="1055d-111">See also</span></span>

- [<span data-ttu-id="1055d-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1055d-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="1055d-113">ExceptionCLRCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="1055d-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
