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
ms.openlocfilehash: ef5122d49c428af4faa27f3827a5c60721ef0f74
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435832"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="005ab-102">ICorProfilerCallback::ExceptionCLRCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="005ab-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="005ab-103">예외에 대 한 `catch` 블록을 CLR (공용 언어 런타임) 내에서 찾을 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="005ab-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="005ab-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="005ab-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="005ab-105">구문</span><span class="sxs-lookup"><span data-stu-id="005ab-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="005ab-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="005ab-106">Requirements</span></span>  
 <span data-ttu-id="005ab-107">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="005ab-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="005ab-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="005ab-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="005ab-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="005ab-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="005ab-110">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="005ab-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="005ab-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="005ab-111">See also</span></span>

- [<span data-ttu-id="005ab-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="005ab-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="005ab-113">ExceptionCLRCatcherExecute 메서드</span><span class="sxs-lookup"><span data-stu-id="005ab-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
