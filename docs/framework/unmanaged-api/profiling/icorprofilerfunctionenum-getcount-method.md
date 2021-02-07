---
description: '자세히 알아보기: ICorProfilerFunctionEnum:: GetCount 메서드'
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
ms.openlocfilehash: a3eccfa31676636aff7379b4080bcb85a268df6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737625"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="21a83-103">ICorProfilerFunctionEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="21a83-103">ICorProfilerFunctionEnum::GetCount Method</span></span>

<span data-ttu-id="21a83-104">애플리케이션에서 로드했거나 프로파일러에서 강제로 로드한 함수 개수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="21a83-104">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21a83-105">구문</span><span class="sxs-lookup"><span data-stu-id="21a83-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21a83-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="21a83-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="21a83-107">제한이 로드 된 함수 수입니다.</span><span class="sxs-lookup"><span data-stu-id="21a83-107">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21a83-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="21a83-108">Requirements</span></span>  

 <span data-ttu-id="21a83-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="21a83-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21a83-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="21a83-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="21a83-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21a83-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21a83-112">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21a83-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21a83-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21a83-113">See also</span></span>

- [<span data-ttu-id="21a83-114">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21a83-114">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="21a83-115">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="21a83-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
