---
title: ICorProfilerThreadEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Clone method [.NET Framework profiling]
ms.assetid: 5a278bc9-88e2-4c69-b035-9d550dd77081
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0301334621a2e393a59e7cc34f2964450a81213f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074172"
---
# <a name="icorprofilerthreadenumclone-method"></a><span data-ttu-id="e0565-102">ICorProfilerThreadEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="e0565-102">ICorProfilerThreadEnum::Clone Method</span></span>
<span data-ttu-id="e0565-103">이 복사본에 인터페이스 포인터를 가져옵니다 [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e0565-103">Gets an interface pointer to a copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0565-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0565-104">Syntax</span></span>  
  
```  
HRESULT Clone (    [out] ICorProfilerThreadEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0565-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0565-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="e0565-106">[out] 이 복사본을 가리키는 하는 인터페이스 포인터에 대 한 포인터 [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e0565-106">[out] A pointer to the interface pointer, which, in turn, points to the copy of this [ICorProfilerThreadEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md) interface.</span></span> <span data-ttu-id="e0565-107">열거자의 복사본을이 열거자는 별도로 자체 열거형의 상태를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="e0565-107">The copy of the enumerator maintains its own enumeration state separately from this enumerator.</span></span> <span data-ttu-id="e0565-108">그러나 복사본의 초기 커서 위치 열거자의 현재 커서 위치와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e0565-108">However, the initial cursor position of the copy is the same as this current cursor position of the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0565-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0565-109">Requirements</span></span>  
 <span data-ttu-id="e0565-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0565-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0565-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0565-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0565-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0565-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e0565-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="e0565-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0565-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="e0565-114">See also</span></span>

- [<span data-ttu-id="e0565-115">ICorProfilerThreadEnum</span><span class="sxs-lookup"><span data-stu-id="e0565-115">ICorProfilerThreadEnum</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="e0565-116">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0565-116">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
