---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionCLRCatcherFound 메서드'
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
ms.openlocfilehash: 37027a00e488eed5681b1d99ada6332d59e6a632
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706307"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="eff76-103">ICorProfilerCallback::ExceptionCLRCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="eff76-103">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>

<span data-ttu-id="eff76-104">`catch`예외에 대 한 블록이 CLR (공용 언어 런타임) 내에서 발견 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eff76-104">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="eff76-105">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eff76-105">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eff76-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="eff76-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="eff76-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eff76-107">Requirements</span></span>  

 <span data-ttu-id="eff76-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eff76-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eff76-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eff76-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eff76-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eff76-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eff76-111">**.NET Framework 버전:** 1.0</span><span class="sxs-lookup"><span data-stu-id="eff76-111">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff76-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eff76-112">See also</span></span>

- [<span data-ttu-id="eff76-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eff76-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="eff76-114">ExceptionCLRCatcherExecute 메서드</span><span class="sxs-lookup"><span data-stu-id="eff76-114">ExceptionCLRCatcherExecute Method</span></span>](icorprofilercallback-exceptionclrcatcherexecute-method.md)
