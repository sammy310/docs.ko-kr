---
title: ICorProfilerCallback::ModuleAttachedToAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 791827b9c4b60cb2ee963881bc8e1a6131cd00fb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59139921"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a><span data-ttu-id="ae7a1-102">ICorProfilerCallback::ModuleAttachedToAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="ae7a1-102">ICorProfilerCallback::ModuleAttachedToAssembly Method</span></span>
<span data-ttu-id="ae7a1-103">모듈 부모 어셈블리에 연결 되는 프로파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="ae7a1-103">Notifies the profiler that a module is being attached to its parent assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae7a1-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae7a1-104">Syntax</span></span>  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae7a1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae7a1-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="ae7a1-106">[in] ID는 연결 되는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7a1-106">[in] The ID of the module that is being attached.</span></span>  
  
 `AssemblyId`  
 <span data-ttu-id="ae7a1-107">[in] 모듈을 연결할 부모 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7a1-107">[in] The ID of the parent assembly to which the module is attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae7a1-108">설명</span><span class="sxs-lookup"><span data-stu-id="ae7a1-108">Remarks</span></span>  
 <span data-ttu-id="ae7a1-109">호출 하 여 가져오기 주소 테이블 (IAT)을 통해 모듈을 로드할 수 있습니다 `LoadLibrary`, 또는 메타 데이터 참조를 통해.</span><span class="sxs-lookup"><span data-stu-id="ae7a1-109">A module can be loaded through an import address table (IAT), through a call to `LoadLibrary`, or through a metadata reference.</span></span> <span data-ttu-id="ae7a1-110">결과적으로, 공용 언어 런타임 (CLR) 로더 모듈 거주 하는 어셈블리를 확인 하기 위한 여러 코드 경로 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae7a1-110">As a result, the common language runtime (CLR) loader has multiple code paths for determining the assembly in which a module lives.</span></span> <span data-ttu-id="ae7a1-111">따라서 것이 가능 후 [icorprofilercallback:: Moduleloadfinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) 가 호출 모듈에 어셈블리를 알 수 없습니다 것 이며 수 없는 부모 어셈블리 ID를 가져오는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="ae7a1-111">Therefore, it is possible that after [ICorProfilerCallback::ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) is called, the module does not know what assembly it is in and getting the parent assembly ID is not possible.</span></span> <span data-ttu-id="ae7a1-112">`ModuleAttachedToAssembly` 메서드 모듈은 부모 어셈블리 및 해당 부모 어셈블리 ID를 가져올 수 있습니다를 연결할 때 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae7a1-112">The `ModuleAttachedToAssembly` method is called when the module is attached to its parent assembly and its parent assembly ID can be obtained.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae7a1-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae7a1-113">Requirements</span></span>  
 <span data-ttu-id="ae7a1-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ae7a1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae7a1-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ae7a1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ae7a1-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae7a1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae7a1-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae7a1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae7a1-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae7a1-118">See also</span></span>

- [<span data-ttu-id="ae7a1-119">ICorProfilerCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae7a1-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
