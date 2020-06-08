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
ms.openlocfilehash: ccbb051ac30fb25199ce12c16fff74bb0b9944fa
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495088"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="f8286-102">ICorProfilerModuleEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="f8286-102">ICorProfilerModuleEnum::Clone Method</span></span>
<span data-ttu-id="f8286-103">이 [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) 인터페이스의 복사본에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f8286-103">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8286-104">구문</span><span class="sxs-lookup"><span data-stu-id="f8286-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8286-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f8286-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f8286-106">제한이 차례로이 [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) 인터페이스의 복사본을 가리키는 인터페이스 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f8286-106">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="f8286-107">열거자의 복사본은이 열거자와 별도로 고유한 열거형 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8286-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="f8286-108">그러나 복사본의 초기 커서 위치는이 열거자의 현재 커서 위치와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8286-108">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8286-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f8286-109">Requirements</span></span>  
 <span data-ttu-id="f8286-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f8286-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8286-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8286-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8286-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8286-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8286-113">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8286-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8286-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f8286-114">See also</span></span>

- [<span data-ttu-id="f8286-115">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8286-115">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="f8286-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f8286-116">Profiling Interfaces</span></span>](profiling-interfaces.md)
