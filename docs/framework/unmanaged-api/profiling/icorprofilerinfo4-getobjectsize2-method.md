---
title: ICorProfilerInfo4::GetObjectSize2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetObjectSize2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type:
- apiref
ms.openlocfilehash: fdfba34f35e40b2a50dbc4edc5b6b6c45f17194f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442876"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="659da-102">ICorProfilerInfo4::GetObjectSize2 메서드</span><span class="sxs-lookup"><span data-stu-id="659da-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="659da-103">지정 된 개체의 크기를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="659da-103">Returns the size of a specified object.</span></span> <span data-ttu-id="659da-104">`ULONG`표현할 수 있는 것 보다 큰 개체의 크기를 보고 하 여 [ICorProfilerInfo:: GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) 메서드를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="659da-104">Replaces the [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="659da-105">구문</span><span class="sxs-lookup"><span data-stu-id="659da-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="659da-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="659da-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="659da-107">진행 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="659da-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="659da-108">제한이 개체의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="659da-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="659da-109">주의</span><span class="sxs-lookup"><span data-stu-id="659da-109">Remarks</span></span>  
 <span data-ttu-id="659da-110">동일한 유형의 개체 마다 크기가 같은 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="659da-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="659da-111">그러나 배열 또는 문자열과 같은 일부 형식에는 각 개체에 대해 다른 크기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="659da-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="659da-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="659da-112">Requirements</span></span>  
 <span data-ttu-id="659da-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="659da-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="659da-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="659da-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="659da-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="659da-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="659da-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="659da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="659da-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="659da-117">See also</span></span>

- [<span data-ttu-id="659da-118">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="659da-118">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
