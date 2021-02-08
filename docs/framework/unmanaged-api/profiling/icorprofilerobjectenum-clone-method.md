---
description: '자세히 알아보기: ICorProfilerObjectEnum:: Clone 메서드'
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
ms.openlocfilehash: 59971f6f6e7edab4b4c4f796ee7bea3c4d8b4e91
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798955"
---
# <a name="icorprofilerobjectenumclone-method"></a><span data-ttu-id="802c3-103">ICorProfilerObjectEnum::Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="802c3-103">ICorProfilerObjectEnum::Clone Method</span></span>

<span data-ttu-id="802c3-104">이 [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) 인터페이스의 복사본에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="802c3-104">Gets an interface pointer to a copy of this [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="802c3-105">구문</span><span class="sxs-lookup"><span data-stu-id="802c3-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorProfilerObjectEnum   **ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="802c3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="802c3-106">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="802c3-107">제한이 이 인터페이스의 복사본을 가리키는 인터페이스 포인터에 대 한 포인터입니다 `ICorProfilerObjectEnum` .</span><span class="sxs-lookup"><span data-stu-id="802c3-107">[out] A pointer to the interface pointer that in turn points to the copy of this `ICorProfilerObjectEnum` interface.</span></span> <span data-ttu-id="802c3-108">복사본은이 항목에서 별도로 자체 열거 상태를 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="802c3-108">The copy maintains its own enumeration state separately from this one.</span></span> <span data-ttu-id="802c3-109">그러나 복사본의 초기 커서 위치는이 열거자의 현재 커서 위치와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="802c3-109">However, the copy's initial cursor position will be the same as this enumerator's current cursor position.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="802c3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="802c3-110">Requirements</span></span>  

 <span data-ttu-id="802c3-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="802c3-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="802c3-112">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="802c3-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="802c3-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="802c3-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="802c3-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="802c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="802c3-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="802c3-115">See also</span></span>

- [<span data-ttu-id="802c3-116">ICorProfilerObjectEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="802c3-116">ICorProfilerObjectEnum Interface</span></span>](icorprofilerobjectenum-interface.md)
