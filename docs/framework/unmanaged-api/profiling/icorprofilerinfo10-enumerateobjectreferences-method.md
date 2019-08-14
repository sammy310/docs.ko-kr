---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 4b13659f7c9909e9795caee1eace8da8092c5b9a
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974033"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="8e6aa-102">ICorProfilerInfo10:: EnumerateObjectReferences 메서드</span><span class="sxs-lookup"><span data-stu-id="8e6aa-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>
  
 <span data-ttu-id="8e6aa-103">ObjectID, callback 및 clientData가 지정 된 경우 각 개체 참조를 열거 합니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="8e6aa-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="8e6aa-104">구문</span><span class="sxs-lookup"><span data-stu-id="8e6aa-104">Syntax</span></span>  
  
```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e6aa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8e6aa-105">Parameters</span></span>  

 `objectId` \
 <span data-ttu-id="8e6aa-106">진행 참조를 열거할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6aa-106">[in] The object to enumerate references on.</span></span>

 `callback` \
 <span data-ttu-id="8e6aa-107">진행 개체에 대 한 참조를 사용 하 여 호출 되는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="8e6aa-107">[in] The function that will be called with the references for the object.</span></span>

 `clientData` \
 <span data-ttu-id="8e6aa-108">진행 프로파일러에서 `callback` 함수에 전달할 데이터를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6aa-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="8e6aa-109">설명</span><span class="sxs-lookup"><span data-stu-id="8e6aa-109">Remarks</span></span>  
 <span data-ttu-id="8e6aa-110">메서드 `EnumerateObjectReferences` 는 참조를 저장 하는 배열을 미리 할당 하는 대신 프로파일러의 요청 시 참조를 [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)한다는 점을 제외 하 고는와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e6aa-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>  

## <a name="requirements"></a><span data-ttu-id="8e6aa-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8e6aa-111">Requirements</span></span>  
 <span data-ttu-id="8e6aa-112">**플랫폼** [.Net Core 지원 운영 체제](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e6aa-112">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="8e6aa-113">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e6aa-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e6aa-114">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e6aa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e6aa-115">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8e6aa-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8e6aa-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="8e6aa-116">See also</span></span>
- [<span data-ttu-id="8e6aa-117">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8e6aa-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

