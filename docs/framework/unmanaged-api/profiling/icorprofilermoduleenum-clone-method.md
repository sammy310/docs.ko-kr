---
title: ICorProfilerModuleEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
ms.openlocfilehash: 395340d497294c89c59216ab5f294070690b74a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74444660"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="c3cfe-102">ICorProfilerModuleEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="c3cfe-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="c3cfe-103">이 [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) 인터페이스의 복사본에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c3cfe-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3cfe-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3cfe-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3cfe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3cfe-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="c3cfe-106">제한이 차례로이 [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) 인터페이스의 복사본을 가리키는 인터페이스 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3cfe-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="c3cfe-107">열거자의 복사본은이 열거자와 별도로 고유한 열거형 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3cfe-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="c3cfe-108">그러나 복사본의 초기 커서 위치는이 열거자의 현재 커서 위치와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3cfe-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3cfe-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3cfe-109">Requirements</span></span>  
 <span data-ttu-id="c3cfe-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c3cfe-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3cfe-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c3cfe-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c3cfe-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3cfe-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3cfe-113">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3cfe-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3cfe-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3cfe-114">See also</span></span>

- [<span data-ttu-id="c3cfe-115">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3cfe-115">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="c3cfe-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3cfe-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
