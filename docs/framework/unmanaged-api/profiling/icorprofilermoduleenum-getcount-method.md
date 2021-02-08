---
description: '자세히 알아보기: ICorProfilerModuleEnum:: GetCount 메서드'
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
ms.openlocfilehash: efdd812795002c25aaeb7634e7a4f4e4287553e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781391"
---
# <a name="icorprofilermoduleenumgetcount-method"></a><span data-ttu-id="17e62-103">ICorProfilerModuleEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="17e62-103">ICorProfilerModuleEnum::GetCount Method</span></span>

<span data-ttu-id="17e62-104">애플리케이션에 로드된 관리되는 모듈 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="17e62-104">Gets the number of managed modules that were loaded into the application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17e62-105">구문</span><span class="sxs-lookup"><span data-stu-id="17e62-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17e62-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="17e62-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="17e62-107">제한이 컬렉션의 런타임 모듈 수입니다.</span><span class="sxs-lookup"><span data-stu-id="17e62-107">[out] The number of runtime modules in the collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17e62-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="17e62-108">Requirements</span></span>  

 <span data-ttu-id="17e62-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="17e62-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17e62-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="17e62-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="17e62-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17e62-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17e62-112">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17e62-112">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17e62-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="17e62-113">See also</span></span>

- [<span data-ttu-id="17e62-114">ICorProfilerModuleEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="17e62-114">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="17e62-115">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="17e62-115">Profiling Interfaces</span></span>](profiling-interfaces.md)
