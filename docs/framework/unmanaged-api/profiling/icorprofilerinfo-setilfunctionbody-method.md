---
title: ICorProfilerInfo::SetILFunctionBody 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerInfo::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method [.NET Framework profiling]
ms.assetid: b159c712-00f4-4fc7-a990-40bf9f642e8f
topic_type:
- apiref
ms.openlocfilehash: 296c3973403a5b09332efa24961d7a474d814aab
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863350"
---
# <a name="icorprofilerinfosetilfunctionbody-method"></a><span data-ttu-id="fe729-102">ICorProfilerInfo::SetILFunctionBody 메서드</span><span class="sxs-lookup"><span data-stu-id="fe729-102">ICorProfilerInfo::SetILFunctionBody Method</span></span>
<span data-ttu-id="fe729-103">지정 된 모듈에 있는 지정 된 함수의 본문을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="fe729-103">Replaces the body of the specified function in the specified module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe729-104">구문</span><span class="sxs-lookup"><span data-stu-id="fe729-104">Syntax</span></span>  
  
```cpp  
HRESULT SetILFunctionBody(  
    [in] ModuleID    moduleId,  
    [in] mdMethodDef methodid,  
    [in] LPCBYTE     pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe729-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fe729-105">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="fe729-106">진행 함수가 상주 하는 모듈의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe729-106">[in] The ID of the module in which the function resides.</span></span>  
  
 `methodid`  
 <span data-ttu-id="fe729-107">진행 본문을 바꿀 함수의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="fe729-107">[in] The token of the function for which to replace the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="fe729-108">진행 함수의 새 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="fe729-108">[in] The new header for the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fe729-109">주의</span><span class="sxs-lookup"><span data-stu-id="fe729-109">Remarks</span></span>  
 <span data-ttu-id="fe729-110">`SetILFunctionBody` 메서드는 메타 데이터에 있는 함수의 상대 가상 주소를 대체 하 여 새 함수 본문을 가리키고 필요한 경우 내부 데이터 구조를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe729-110">The `SetILFunctionBody` method replaces the relative virtual address of the function in the metadata so that it points to the new function body, and adjusts any internal data structures as required.</span></span>  
  
 <span data-ttu-id="fe729-111">JIT (just-in-time) 컴파일러에서 컴파일되지 않은 함수 에서만 `SetILFunctionBody` 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fe729-111">The `SetILFunctionBody` method can be called on only those functions that have never been compiled by a just-in-time (JIT) compiler.</span></span>  
  
 <span data-ttu-id="fe729-112">[ICorProfilerInfo:: GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) 메서드를 사용 하 여 버퍼가 호환 되는지 확인 하기 위해 새 메서드에 대 한 공간을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe729-112">Use the [ICorProfilerInfo::GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md) method to allocate space for the new method to ensure that the buffer is compatible.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe729-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe729-113">Requirements</span></span>  
 <span data-ttu-id="fe729-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fe729-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe729-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fe729-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fe729-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe729-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fe729-117">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe729-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe729-118">참조</span><span class="sxs-lookup"><span data-stu-id="fe729-118">See also</span></span>

- [<span data-ttu-id="fe729-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe729-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
