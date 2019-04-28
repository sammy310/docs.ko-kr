---
title: ICorProfilerCallback::ExceptionCLRCatcherFound 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 59225677671388b4ed31f7fa440b6e502b604c63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597650"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="f51b8-102">ICorProfilerCallback::ExceptionCLRCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="f51b8-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="f51b8-103">될 때 호출을 `catch` 예외는 CLR (공용 언어 런타임) 자체 내에서 차단 합니다.</span><span class="sxs-lookup"><span data-stu-id="f51b8-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="f51b8-104">이 메서드는.NET Framework 버전 2.0에서에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f51b8-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f51b8-105">구문</span><span class="sxs-lookup"><span data-stu-id="f51b8-105">Syntax</span></span>  
  
```  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="f51b8-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f51b8-106">Requirements</span></span>  
 <span data-ttu-id="f51b8-107">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f51b8-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f51b8-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f51b8-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f51b8-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f51b8-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f51b8-110">**.NET framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="f51b8-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f51b8-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="f51b8-111">See also</span></span>

- [<span data-ttu-id="f51b8-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f51b8-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="f51b8-113">ExceptionCLRCatcherExecute 메서드</span><span class="sxs-lookup"><span data-stu-id="f51b8-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
