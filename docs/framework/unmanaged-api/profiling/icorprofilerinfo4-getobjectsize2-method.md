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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15829e08a755b91ff91ca939b92a5a87bd377e8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000677"
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a><span data-ttu-id="fd079-102">ICorProfilerInfo4::GetObjectSize2 메서드</span><span class="sxs-lookup"><span data-stu-id="fd079-102">ICorProfilerInfo4::GetObjectSize2 Method</span></span>
<span data-ttu-id="fd079-103">지정된 된 개체의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fd079-103">Returns the size of a specified object.</span></span> <span data-ttu-id="fd079-104">대체는 [icorprofilerinfo:: Getobjectsize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) 에서 표현할 수 있는 보다 큰 개체의 크기를 보고 하 여 메서드를 `ULONG`입니다.</span><span class="sxs-lookup"><span data-stu-id="fd079-104">Replaces the [ICorProfilerInfo::GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) method by reporting sizes of objects that are larger than what can be expressed in a `ULONG`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd079-105">구문</span><span class="sxs-lookup"><span data-stu-id="fd079-105">Syntax</span></span>  
  
```  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd079-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd079-106">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="fd079-107">[in] 개체의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fd079-107">[in] The ID of the object.</span></span>  
  
 `pcSize`  
 <span data-ttu-id="fd079-108">[out] 개체의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fd079-108">[out] A pointer to the object's size, in bytes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd079-109">설명</span><span class="sxs-lookup"><span data-stu-id="fd079-109">Remarks</span></span>  
 <span data-ttu-id="fd079-110">동일한 유형의 다른 개체에는 동일한 크기가 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="fd079-110">Different objects of the same types often have the same size.</span></span> <span data-ttu-id="fd079-111">그러나 배열 또는 문자열 같은 일부 유형의 경우에 각 개체에 대해 다른 크기가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd079-111">However, some types, such as arrays or strings, may have a different size for each object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd079-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd079-112">Requirements</span></span>  
 <span data-ttu-id="fd079-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd079-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd079-114">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd079-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd079-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd079-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd079-116">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd079-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd079-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="fd079-117">See also</span></span>

- [<span data-ttu-id="fd079-118">ICorProfilerInfo4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd079-118">ICorProfilerInfo4 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
