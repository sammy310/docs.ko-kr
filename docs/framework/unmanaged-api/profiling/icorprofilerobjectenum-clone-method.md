---
title: ICorProfilerObjectEnum::Clone 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum.Clone
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerObjectEnum interface [.NET Framework profiling]
- ICorProfilerObjectEnum::Clone method [.NET Framework profiling]
ms.assetid: b0b2facd-5991-4f4c-932d-c4937f45cef9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 14e8086532eff5dba6883575cc2daf447a32343a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182366"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="46fca-102">ICorProfilerObjectEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="46fca-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="46fca-103">이 복사본에 인터페이스 포인터를 가져옵니다 [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="46fca-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46fca-104">구문</span><span class="sxs-lookup"><span data-stu-id="46fca-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46fca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="46fca-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="46fca-106">[out] 이 복사본을 가리키고 있는 인터페이스 포인터에 대 한 포인터 `ICorProfilerObjectEnum` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="46fca-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="46fca-107">복사본을이 별도로 자체 열거형의 상태를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="46fca-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="46fca-108">그러나이 열거자의 현재 커서 위치와 동일 복사본의 초기 커서 위치가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46fca-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46fca-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="46fca-109">Requirements</span></span>  
 <span data-ttu-id="46fca-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="46fca-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46fca-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46fca-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46fca-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46fca-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="46fca-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="46fca-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="46fca-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="46fca-114">See also</span></span>

- [<span data-ttu-id="46fca-115">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46fca-115">ICorProfilerObjectEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md)
