---
title: ICorProfilerInfo3::EnumModules 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumModules Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumModules
helpviewer_keywords:
- ICorProfilerInfo3::EnumModules method [.NET Framework profiling]
- EnumModules method [.NET Framework profiling]
ms.assetid: 1bf00b42-69da-4019-91b3-bf88026e83fb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73218a5b63ae53ac125d3d807c1a50bdbf0d9c8a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503062"
---
# <a name="icorprofilerinfo3enummodules-method"></a><span data-ttu-id="eabf2-102">ICorProfilerInfo3::EnumModules 메서드</span><span class="sxs-lookup"><span data-stu-id="eabf2-102">ICorProfilerInfo3::EnumModules Method</span></span>
<span data-ttu-id="eabf2-103">응용 프로그램에 로드되는 관리 모듈 컬렉션을 순차적으로 반복하는 메서드를 제공하는 열거자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="eabf2-103">Returns an enumerator that provides methods to sequentially iterate through a collection of managed modules that are loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eabf2-104">구문</span><span class="sxs-lookup"><span data-stu-id="eabf2-104">Syntax</span></span>  
  
```  
HRESULT EnumModules([out] ICorProfilerModuleEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eabf2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eabf2-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="eabf2-106">[out] 에 대 한 포인터를 [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="eabf2-106">[out] A pointer to an [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eabf2-107">설명</span><span class="sxs-lookup"><span data-stu-id="eabf2-107">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eabf2-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eabf2-108">Requirements</span></span>  
 <span data-ttu-id="eabf2-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eabf2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eabf2-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eabf2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eabf2-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eabf2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eabf2-112">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eabf2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eabf2-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="eabf2-113">See also</span></span>
- [<span data-ttu-id="eabf2-114">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eabf2-114">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="eabf2-115">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eabf2-115">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="eabf2-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eabf2-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="eabf2-117">프로파일링</span><span class="sxs-lookup"><span data-stu-id="eabf2-117">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
