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
ms.openlocfilehash: a2a54c32c0713b4b69d8f2a0272687cbe9420610
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494776"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="3925d-102">ICorProfilerObjectEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="3925d-102">ICorProfilerObjectEnum::Clone Method</span></span>
<span data-ttu-id="3925d-103">이 [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) 인터페이스의 복사본에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3925d-103">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3925d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3925d-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3925d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3925d-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3925d-106">제한이 이 인터페이스의 복사본을 가리키는 인터페이스 포인터에 대 한 포인터입니다 `ICorProfilerObjectEnum` .</span><span class="sxs-lookup"><span data-stu-id="3925d-106">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="3925d-107">복사본은이 항목에서 별도로 자체 열거 상태를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="3925d-107">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="3925d-108">그러나 복사본의 초기 커서 위치는이 열거자의 현재 커서 위치와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="3925d-108">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3925d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3925d-109">Requirements</span></span>  
 <span data-ttu-id="3925d-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3925d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3925d-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3925d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3925d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3925d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3925d-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3925d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3925d-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3925d-114">See also</span></span>

- [<span data-ttu-id="3925d-115">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3925d-115">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
