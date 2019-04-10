---
title: ICorProfilerFunctionEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a5061750489c74e0385f2ce020c88518604b3167
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169288"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="7835d-102">ICorProfilerFunctionEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="7835d-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="7835d-103">응용 프로그램에서 로드했거나 프로파일러에서 강제로 로드한 함수 개수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7835d-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7835d-104">구문</span><span class="sxs-lookup"><span data-stu-id="7835d-104">Syntax</span></span>  
  
```  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7835d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7835d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7835d-106">[out] 로드 된 함수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7835d-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7835d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7835d-107">Requirements</span></span>  
 <span data-ttu-id="7835d-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7835d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7835d-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7835d-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7835d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7835d-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="7835d-111">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="7835d-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7835d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="7835d-112">See also</span></span>

- [<span data-ttu-id="7835d-113">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7835d-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="7835d-114">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7835d-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
