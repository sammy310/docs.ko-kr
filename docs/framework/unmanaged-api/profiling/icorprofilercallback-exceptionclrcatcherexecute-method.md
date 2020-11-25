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
ms.openlocfilehash: 1a9e377ba98c0c2302e341149bd5acb46c24051a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699991"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="bc1c6-102">ICorProfilerCallback::ExceptionCLRCatcherExecute 메서드</span><span class="sxs-lookup"><span data-stu-id="bc1c6-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>

<span data-ttu-id="bc1c6-103">`catch`예외에 대 한 블록이 CLR (공용 언어 런타임) 내에서 실행 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="bc1c6-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc1c6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bc1c6-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="bc1c6-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc1c6-106">Requirements</span></span>  

 <span data-ttu-id="bc1c6-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc1c6-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc1c6-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bc1c6-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bc1c6-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bc1c6-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bc1c6-110">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="bc1c6-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc1c6-111">참조</span><span class="sxs-lookup"><span data-stu-id="bc1c6-111">See also</span></span>

- [<span data-ttu-id="bc1c6-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bc1c6-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="bc1c6-113">ExceptionCLRCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="bc1c6-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
