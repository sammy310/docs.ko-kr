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
ms.openlocfilehash: a543e5119a3ad5580fb67c31dc0e59ab62eab571
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866494"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="7efa0-102">ICorProfilerCallback::ExceptionCLRCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="7efa0-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="7efa0-103">예외에 대 한 `catch` 블록을 CLR (공용 언어 런타임) 내에서 찾을 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7efa0-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="7efa0-104">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7efa0-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7efa0-105">구문</span><span class="sxs-lookup"><span data-stu-id="7efa0-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="7efa0-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7efa0-106">Requirements</span></span>  
 <span data-ttu-id="7efa0-107">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7efa0-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7efa0-108">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7efa0-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7efa0-109">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7efa0-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7efa0-110">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="7efa0-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7efa0-111">참조</span><span class="sxs-lookup"><span data-stu-id="7efa0-111">See also</span></span>

- [<span data-ttu-id="7efa0-112">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7efa0-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7efa0-113">ExceptionCLRCatcherExecute 메서드</span><span class="sxs-lookup"><span data-stu-id="7efa0-113">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)
