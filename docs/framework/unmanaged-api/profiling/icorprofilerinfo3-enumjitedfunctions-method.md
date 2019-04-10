---
title: ICorProfilerInfo3::EnumJITedFunctions 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.EnumJITedFunctions Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::EnumJITedFunctions
helpviewer_keywords:
- ICorProfilerInfo3::EnumJITedFunctions method [.NET Framework profiling]
- EnumJITedFunctions method [.NET Framework profiling]
ms.assetid: e2847a36-f460-45e2-9b6c-b33b008f40d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7525d107fec7229d9b86eee63bde2aaf2d701b1b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190303"
---
# <a name="icorprofilerinfo3enumjitedfunctions-method"></a><span data-ttu-id="b1c33-102">ICorProfilerInfo3::EnumJITedFunctions 메서드</span><span class="sxs-lookup"><span data-stu-id="b1c33-102">ICorProfilerInfo3::EnumJITedFunctions Method</span></span>
<span data-ttu-id="b1c33-103">이전에 JIT 컴파일된 모든 함수에 대 한 열거자를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1c33-103">Returns an enumerator for all functions that were previously JIT-compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c33-104">구문</span><span class="sxs-lookup"><span data-stu-id="b1c33-104">Syntax</span></span>  
  
```  
HRESULT EnumJITedFunctions([out] ICorProfilerFunctionEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1c33-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b1c33-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="b1c33-106">[out] 에 대 한 포인터를 [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) 열거자입니다.</span><span class="sxs-lookup"><span data-stu-id="b1c33-106">[out] A pointer to the [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) enumerator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1c33-107">설명</span><span class="sxs-lookup"><span data-stu-id="b1c33-107">Remarks</span></span>  
 <span data-ttu-id="b1c33-108">이 메서드를 사용 하 여 겹치면 `JITCompilation` 와 같이 콜백 합니다 [icorprofilercallback:: Jitcompilationstarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b1c33-108">This method may overlap with `JITCompilation` callbacks such as the [ICorProfilerCallback::JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) method.</span></span> <span data-ttu-id="b1c33-109">이 메서드에서 반환 되는 열거자에서 Ngen.exe로 생성 된 네이티브 이미지에서 로드 된 함수를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1c33-109">The enumerator returned by this method does not include functions that are loaded from native images generated with Ngen.exe.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b1c33-110">반환된 된 열거형의 값 "0"만 포함 된 `COR_PRF_FUNCTION::reJitId` 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="b1c33-110">The returned enumeration includes only "0" for the value of the `COR_PRF_FUNCTION::reJitId` field.</span></span>  <span data-ttu-id="b1c33-111">유효 해야 하는 경우 `COR_PRF_FUNCTION::reJitId` 값을 사용 합니다 [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="b1c33-111">If you require valid `COR_PRF_FUNCTION::reJitId` values, use the [ICorProfilerInfo4::EnumJITedFunctions2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-enumjitedfunctions2-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1c33-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1c33-112">Requirements</span></span>  
 <span data-ttu-id="b1c33-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1c33-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1c33-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1c33-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1c33-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1c33-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b1c33-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b1c33-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1c33-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1c33-117">See also</span></span>

- [<span data-ttu-id="b1c33-118">ICorProfilerInfo3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1c33-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b1c33-119">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1c33-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b1c33-120">프로파일링</span><span class="sxs-lookup"><span data-stu-id="b1c33-120">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
