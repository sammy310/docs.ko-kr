---
title: ICorProfilerModuleEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::GetCount
helpviewer_keywords:
- ICorProfilerModuleEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: f0a4a5e0-4689-474b-b0f4-37ca0639c918
topic_type:
- apiref
ms.openlocfilehash: 9aaf1a282435e3f52b2c2d8f3d17254b877e61cc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442775"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="4976f-102">ICorProfilerModuleEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="4976f-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="4976f-103">애플리케이션에 로드된 관리되는 모듈 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4976f-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4976f-104">구문</span><span class="sxs-lookup"><span data-stu-id="4976f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4976f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4976f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4976f-106">[out] The number of runtime modules in the collection.</span><span class="sxs-lookup"><span data-stu-id="4976f-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4976f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4976f-107">Requirements</span></span>  
 <span data-ttu-id="4976f-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4976f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4976f-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4976f-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4976f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4976f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4976f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4976f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4976f-112">참조</span><span class="sxs-lookup"><span data-stu-id="4976f-112">See also</span></span>

- [<span data-ttu-id="4976f-113">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4976f-113">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="4976f-114">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4976f-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
