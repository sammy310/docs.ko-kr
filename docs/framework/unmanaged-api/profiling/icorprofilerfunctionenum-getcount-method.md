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
ms.openlocfilehash: 8a21f1c0018e99b94a1b9910b6f266bdca84b7fe
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864559"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="25806-102">ICorProfilerFunctionEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="25806-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="25806-103">애플리케이션에서 로드했거나 프로파일러에서 강제로 로드한 함수 개수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="25806-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25806-104">구문</span><span class="sxs-lookup"><span data-stu-id="25806-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25806-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="25806-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="25806-106">제한이 로드 된 함수 수입니다.</span><span class="sxs-lookup"><span data-stu-id="25806-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25806-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="25806-107">Requirements</span></span>  
 <span data-ttu-id="25806-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25806-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25806-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="25806-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="25806-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25806-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25806-111">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25806-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25806-112">참조</span><span class="sxs-lookup"><span data-stu-id="25806-112">See also</span></span>

- [<span data-ttu-id="25806-113">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25806-113">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="25806-114">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="25806-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
