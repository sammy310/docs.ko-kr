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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3e30cc8ff320c1a4a9a69fb2a07427ef4c8a4149
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485371"
---
# <a name="icorprofilerfunctionenumclone-method"></a><span data-ttu-id="eec9c-102">ICorProfilerFunctionEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="eec9c-102">ICorProfilerFunctionEnum::Clone Method</span></span>
<span data-ttu-id="eec9c-103">이 복사본에 인터페이스 포인터를 가져옵니다 [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="eec9c-103">Gets an interface pointer to a copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eec9c-104">구문</span><span class="sxs-lookup"><span data-stu-id="eec9c-104">Syntax</span></span>  
  
```  
HRESULT Clone([out] ICorProfilerFunctionEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eec9c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="eec9c-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="eec9c-106">[out] 이 복사본을 가리키는 하는 인터페이스 포인터에 대 한 포인터 [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="eec9c-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerFunctionEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md) interface.</span></span> <span data-ttu-id="eec9c-107">열거자의 복사본을이 열거자는 별도로 자체 열거형의 상태를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="eec9c-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="eec9c-108">그러나 복사본의 초기 커서 위치는이 열거자의 현재 커서 위치와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="eec9c-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eec9c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="eec9c-109">Requirements</span></span>  
 <span data-ttu-id="eec9c-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eec9c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eec9c-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eec9c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eec9c-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eec9c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eec9c-113">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eec9c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eec9c-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="eec9c-114">See also</span></span>
- [<span data-ttu-id="eec9c-115">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eec9c-115">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="eec9c-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="eec9c-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
