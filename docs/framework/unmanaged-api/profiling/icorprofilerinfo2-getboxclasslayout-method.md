---
title: ICorProfilerInfo2::GetBoxClassLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
ms.openlocfilehash: ff39a688132112e88438bc192d7c1ab61f169400
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727161"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="ab92d-102">ICorProfilerInfo2::GetBoxClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="ab92d-102">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>

<span data-ttu-id="ab92d-103">Boxing 될 때 지정 된 값 형식이 있는 위치에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ab92d-103">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab92d-104">구문</span><span class="sxs-lookup"><span data-stu-id="ab92d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ab92d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ab92d-105">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="ab92d-106">진행 Boxing 된 값 형식을 설명 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ab92d-106">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="ab92d-107">제한이 Boxed 개체 ID 포인터에 상대적인 값 형식의 오프셋 인 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="ab92d-107">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab92d-108">설명</span><span class="sxs-lookup"><span data-stu-id="ab92d-108">Remarks</span></span>  

 <span data-ttu-id="ab92d-109">`pBufferOffset`값은 상자 내 값 형식의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="ab92d-109">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="ab92d-110">`pBufferOffset`가 boxed 개체에 적용 된 후에는 값 형식의 클래스 레이아웃을 사용 하 여 개체의 값을 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab92d-110">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab92d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ab92d-111">Requirements</span></span>  

 <span data-ttu-id="ab92d-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ab92d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab92d-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ab92d-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ab92d-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab92d-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ab92d-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab92d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab92d-116">참조</span><span class="sxs-lookup"><span data-stu-id="ab92d-116">See also</span></span>

- [<span data-ttu-id="ab92d-117">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab92d-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="ab92d-118">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ab92d-118">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
