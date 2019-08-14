---
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 05f25d8fb61a16f41a82a987529017db6a687740
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973993"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="81c5e-102">ICorProfilerInfo10:: IsFrozenObject 메서드</span><span class="sxs-lookup"><span data-stu-id="81c5e-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>
  
 <span data-ttu-id="81c5e-103">ObjectID가 지정 된 경우 개체가 읽기 전용 세그먼트에 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81c5e-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="81c5e-104">구문</span><span class="sxs-lookup"><span data-stu-id="81c5e-104">Syntax</span></span>  
  
```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```  
  
#### <a name="parameters"></a><span data-ttu-id="81c5e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="81c5e-105">Parameters</span></span>  
 
 `objectId` \
 <span data-ttu-id="81c5e-106">진행 검사할 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="81c5e-106">[in] The object to examine.</span></span>

 `pbFrozen` \
 <span data-ttu-id="81c5e-107">제한이 개체가 `BOOL` 읽기 전용 세그먼트에 있는지 여부를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="81c5e-107">[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="81c5e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="81c5e-108">Requirements</span></span>  
 <span data-ttu-id="81c5e-109">**플랫폼** [.Net Core 지원 운영 체제](../../../core/windows-prerequisites.md#net-core-supported-operating-systems)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81c5e-109">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="81c5e-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81c5e-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81c5e-111">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81c5e-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81c5e-112">**.Net 버전:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81c5e-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="81c5e-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="81c5e-113">See also</span></span>
- [<span data-ttu-id="81c5e-114">ICorProfilerInfo10 인터페이스</span><span class="sxs-lookup"><span data-stu-id="81c5e-114">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

