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
ms.openlocfilehash: 604ecb2122cce6e24f0e5168fa286a523d8bb4f7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495075"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="7808c-102">ICorProfilerModuleEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="7808c-102">ICorProfilerModuleEnum::GetCount Method</span></span>
<span data-ttu-id="7808c-103">애플리케이션에 로드된 관리되는 모듈 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7808c-103">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7808c-104">구문</span><span class="sxs-lookup"><span data-stu-id="7808c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7808c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7808c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="7808c-106">제한이 컬렉션의 런타임 모듈 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7808c-106">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7808c-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7808c-107">Requirements</span></span>  
 <span data-ttu-id="7808c-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7808c-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7808c-109">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7808c-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7808c-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7808c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7808c-111">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7808c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7808c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7808c-112">See also</span></span>

- [<span data-ttu-id="7808c-113">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7808c-113">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="7808c-114">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7808c-114">Profiling Interfaces</span></span>](profiling-interfaces.md)
