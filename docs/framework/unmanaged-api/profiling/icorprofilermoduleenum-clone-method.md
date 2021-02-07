---
description: '자세히 알아보기: ICorProfilerModuleEnum:: Clone 메서드'
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
ms.openlocfilehash: 0d2a235def6d3b16d661e51979742426ebe1942f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736939"
---
# <a name="icorprofilermoduleenumclone-method"></a><span data-ttu-id="d6c23-103">ICorProfilerModuleEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="d6c23-103">ICorProfilerModuleEnum::Clone Method</span></span>

<span data-ttu-id="d6c23-104">이 [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) 인터페이스의 복사본에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d6c23-104">Gets an interface pointer to a copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c23-105">구문</span><span class="sxs-lookup"><span data-stu-id="d6c23-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6c23-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d6c23-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="d6c23-107">제한이 차례로이 [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) 인터페이스의 복사본을 가리키는 인터페이스 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c23-107">[out] A pointer to the interface pointer that in turn points to the copy of this [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) interface.</span></span> <span data-ttu-id="d6c23-108">열거자의 복사본은이 열거자와 별도로 고유한 열거형 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c23-108">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="d6c23-109">그러나 복사본의 초기 커서 위치는이 열거자의 현재 커서 위치와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c23-109">However, the copy's initial cursor position is the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6c23-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6c23-110">Requirements</span></span>  

 <span data-ttu-id="d6c23-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d6c23-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6c23-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d6c23-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d6c23-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6c23-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6c23-114">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6c23-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c23-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6c23-115">See also</span></span>

- [<span data-ttu-id="d6c23-116">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6c23-116">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="d6c23-117">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d6c23-117">Profiling Interfaces</span></span>](profiling-interfaces.md)
