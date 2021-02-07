---
description: '자세히 알아보기: ICorProfilerInfo4:: GetFunctionFromIP2 메서드'
title: ICorProfilerInfo4::GetFunctionFromIP2 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
ms.openlocfilehash: f6abda7c9e7d4abcc0f0b256d6a7785cea205d7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686806"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="febed-103">ICorProfilerInfo4::GetFunctionFromIP2 메서드</span><span class="sxs-lookup"><span data-stu-id="febed-103">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>

<span data-ttu-id="febed-104">관리 되는 코드 명령 포인터를 함수의 JIT 다시 컴파일된 버전에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="febed-104">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="febed-105">구문</span><span class="sxs-lookup"><span data-stu-id="febed-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="febed-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="febed-106">Parameters</span></span>  

 `ip`  
 <span data-ttu-id="febed-107">진행 관리 코드의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="febed-107">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="febed-108">제한이 함수 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="febed-108">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="febed-109">제한이 함수의 JIT 다시 컴파일된 버전 id입니다.</span><span class="sxs-lookup"><span data-stu-id="febed-109">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="febed-110">설명</span><span class="sxs-lookup"><span data-stu-id="febed-110">Remarks</span></span>  

 <span data-ttu-id="febed-111">`GetFunctionFromIP2` 는 지정 된 `GetFunctionFromIP` IP 주소를 포함 하는 함수의 함수 ID 대신 JIT 다시 컴파일된 ID를 가져오는 점을 제외 하 고와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="febed-111">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="febed-112">`GetFunctionFromIP2` 는 가비지 수집을 트리거할 수 있지만 `GetFunctionFromIP` 는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="febed-112">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="febed-113">자세한 내용은 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="febed-113">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="febed-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="febed-114">Requirements</span></span>  

 <span data-ttu-id="febed-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="febed-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="febed-116">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="febed-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="febed-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="febed-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="febed-118">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="febed-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="febed-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="febed-119">See also</span></span>

- [<span data-ttu-id="febed-120">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="febed-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
