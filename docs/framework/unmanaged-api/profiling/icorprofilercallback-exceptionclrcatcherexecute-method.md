---
description: '자세히 알아보기: ICorProfilerCallback:: ExceptionCLRCatcherExecute 메서드'
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
ms.openlocfilehash: cb6926fdfcc9b5ffef20cc69c71a3bafefd9f6ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657504"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="a5d50-103">ICorProfilerCallback::ExceptionCLRCatcherExecute 메서드</span><span class="sxs-lookup"><span data-stu-id="a5d50-103">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>

<span data-ttu-id="a5d50-104">`catch`예외에 대 한 블록이 CLR (공용 언어 런타임) 내에서 실행 될 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5d50-104">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="a5d50-105">이 메서드는 .NET Framework 버전 2.0에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5d50-105">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5d50-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5d50-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="a5d50-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5d50-107">Requirements</span></span>  

 <span data-ttu-id="a5d50-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5d50-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5d50-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a5d50-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a5d50-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5d50-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5d50-111">**.NET Framework 버전:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="a5d50-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d50-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a5d50-112">See also</span></span>

- [<span data-ttu-id="a5d50-113">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a5d50-113">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="a5d50-114">ExceptionCLRCatcherFound 메서드</span><span class="sxs-lookup"><span data-stu-id="a5d50-114">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
