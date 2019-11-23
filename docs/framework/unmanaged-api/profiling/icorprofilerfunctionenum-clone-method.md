---
title: ICorProfilerFunctionEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Clone
helpviewer_keywords:
- ICorProfilerFunctionEnum::Clone method [.NET Framework profiling]
- Clone method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 0c3d4835-e111-4e82-af6d-53f140b8f2c9
topic_type:
- apiref
ms.openlocfilehash: a212a0499b1091f1c77b52951ecef2cb2cace4df
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447840"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="083ab-102">ICorProfilerFunctionEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="083ab-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="083ab-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="083ab-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="083ab-104">구문</span><span class="sxs-lookup"><span data-stu-id="083ab-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="083ab-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="083ab-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="083ab-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="083ab-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="083ab-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span><span class="sxs-lookup"><span data-stu-id="083ab-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="083ab-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span><span class="sxs-lookup"><span data-stu-id="083ab-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="083ab-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="083ab-109">Requirements</span></span>  
 <span data-ttu-id="083ab-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="083ab-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="083ab-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="083ab-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="083ab-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="083ab-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="083ab-113">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="083ab-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="083ab-114">참조</span><span class="sxs-lookup"><span data-stu-id="083ab-114">See also</span></span>

- [<span data-ttu-id="083ab-115">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="083ab-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="083ab-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="083ab-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
