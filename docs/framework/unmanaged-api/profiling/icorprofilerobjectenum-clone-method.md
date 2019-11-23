---
title: ICorProfilerObjectEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
ms.openlocfilehash: 99778240afb7e296b93cd87ab91feeca20d02637
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428270"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="f56e8-102">ICorProfilerObjectEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="f56e8-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="f56e8-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="f56e8-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f56e8-104">구문</span><span class="sxs-lookup"><span data-stu-id="f56e8-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f56e8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f56e8-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f56e8-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span><span class="sxs-lookup"><span data-stu-id="f56e8-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="f56e8-107">The copy maintains its own enumeration state separately from this one.</span><span class="sxs-lookup"><span data-stu-id="f56e8-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="f56e8-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span><span class="sxs-lookup"><span data-stu-id="f56e8-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f56e8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f56e8-109">Requirements</span></span>  
 <span data-ttu-id="f56e8-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f56e8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f56e8-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f56e8-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f56e8-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f56e8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f56e8-113">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f56e8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f56e8-114">참조</span><span class="sxs-lookup"><span data-stu-id="f56e8-114">See also</span></span>

- [<span data-ttu-id="f56e8-115">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f56e8-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
