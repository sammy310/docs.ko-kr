---
description: '자세히 알아보기: ICorProfilerInfo2:: GetBoxClassLayout 메서드'
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
ms.openlocfilehash: 0bc9ccc80da8bcc89cfe73eaa240310c01e6ca8f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760515"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a><span data-ttu-id="8d5fe-103">ICorProfilerInfo2::GetBoxClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="8d5fe-103">ICorProfilerInfo2::GetBoxClassLayout Method</span></span>

<span data-ttu-id="8d5fe-104">Boxing 될 때 지정 된 값 형식이 있는 위치에 대 한 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8d5fe-104">Gets information about where the specified value type is located when it is boxed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d5fe-105">구문</span><span class="sxs-lookup"><span data-stu-id="8d5fe-105">Syntax</span></span>  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d5fe-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8d5fe-106">Parameters</span></span>  

 `classId`  
 <span data-ttu-id="8d5fe-107">진행 Boxing 된 값 형식을 설명 하는 클래스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5fe-107">[in] The ID of the class that describes the value type that is boxed.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="8d5fe-108">제한이 Boxed 개체 ID 포인터에 상대적인 값 형식의 오프셋 인 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5fe-108">[out] An integer that is the offset, relative to the boxed object ID pointer, of the value type.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d5fe-109">설명</span><span class="sxs-lookup"><span data-stu-id="8d5fe-109">Remarks</span></span>  

 <span data-ttu-id="8d5fe-110">`pBufferOffset`값은 상자 내 값 형식의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8d5fe-110">The `pBufferOffset` value is the location of the value type within a box.</span></span> <span data-ttu-id="8d5fe-111">`pBufferOffset`가 boxed 개체에 적용 된 후에는 값 형식의 클래스 레이아웃을 사용 하 여 개체의 값을 해석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d5fe-111">After `pBufferOffset` is applied to a boxed object, the value type's class layout can be used to interpret the object's value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d5fe-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d5fe-112">Requirements</span></span>  

 <span data-ttu-id="8d5fe-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d5fe-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d5fe-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8d5fe-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8d5fe-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d5fe-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d5fe-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d5fe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d5fe-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d5fe-117">See also</span></span>

- [<span data-ttu-id="8d5fe-118">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d5fe-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="8d5fe-119">ICorProfilerInfo2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d5fe-119">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
