---
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
ms.openlocfilehash: ea66474e809b3813faceef79a69dd8a639a72a3b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502797"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="8ee9d-102">ICorProfilerInfo4::GetFunctionFromIP2 메서드</span><span class="sxs-lookup"><span data-stu-id="8ee9d-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="8ee9d-103">관리 되는 코드 명령 포인터를 함수의 JIT 다시 컴파일된 버전에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9d-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ee9d-104">구문</span><span class="sxs-lookup"><span data-stu-id="8ee9d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ee9d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ee9d-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="8ee9d-106">진행 관리 코드의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9d-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="8ee9d-107">제한이 함수 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9d-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="8ee9d-108">제한이 함수의 JIT 다시 컴파일된 버전 id입니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9d-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ee9d-109">설명</span><span class="sxs-lookup"><span data-stu-id="8ee9d-109">Remarks</span></span>  
 <span data-ttu-id="8ee9d-110">`GetFunctionFromIP2`는 지정 된 `GetFunctionFromIP` IP 주소를 포함 하는 함수의 함수 ID 대신 JIT 다시 컴파일된 ID를 가져오는 점을 제외 하 고와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9d-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8ee9d-111">`GetFunctionFromIP2`는 가비지 수집을 트리거할 수 있지만 `GetFunctionFromIP` 는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee9d-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="8ee9d-112">자세한 내용은 [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8ee9d-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ee9d-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ee9d-113">Requirements</span></span>  
 <span data-ttu-id="8ee9d-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ee9d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ee9d-115">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8ee9d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8ee9d-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ee9d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ee9d-117">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ee9d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee9d-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ee9d-118">See also</span></span>

- [<span data-ttu-id="8ee9d-119">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ee9d-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
