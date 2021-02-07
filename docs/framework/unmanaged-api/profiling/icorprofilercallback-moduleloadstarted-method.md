---
description: '자세히 알아보기: ICorProfilerCallback:: ModuleLoadStarted 메서드'
title: ICorProfilerCallback::ModuleLoadStarted 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleLoadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleLoadStarted
helpviewer_keywords:
- ModuleLoadStarted method [.NET Framework profiling]
- ICorProfilerCallback::ModuleLoadStarted method [.NET Framework profiling]
ms.assetid: 9cd2fe75-408a-400f-a6b1-9979624a2fe2
topic_type:
- apiref
ms.openlocfilehash: e8d15bece7baf82f69162663da00d331c7904837
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745270"
---
# <a name="icorprofilercallbackmoduleloadstarted-method"></a><span data-ttu-id="38a39-103">ICorProfilerCallback::ModuleLoadStarted 메서드</span><span class="sxs-lookup"><span data-stu-id="38a39-103">ICorProfilerCallback::ModuleLoadStarted Method</span></span>

<span data-ttu-id="38a39-104">모듈이 로드 되 고 있음을 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="38a39-104">Notifies the profiler that a module is being loaded.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a39-105">구문</span><span class="sxs-lookup"><span data-stu-id="38a39-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleLoadStarted(  
    [in] ModuleID moduleId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38a39-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38a39-106">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="38a39-107">진행 로드 되는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="38a39-107">[in] The ID of the module that is being loaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38a39-108">설명</span><span class="sxs-lookup"><span data-stu-id="38a39-108">Remarks</span></span>  

 <span data-ttu-id="38a39-109">`moduleId` [ICorProfilerCallback:: ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) 메서드가 호출 될 때까지 정보 요청에 대 한 값이 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="38a39-109">The value of `moduleId` is not valid for an information request until the [ICorProfilerCallback::ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38a39-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38a39-110">Requirements</span></span>  

 <span data-ttu-id="38a39-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38a39-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a39-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="38a39-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="38a39-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38a39-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38a39-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a39-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a39-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="38a39-115">See also</span></span>

- [<span data-ttu-id="38a39-116">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38a39-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
