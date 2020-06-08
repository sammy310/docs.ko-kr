---
title: ICorProfilerInfo::GetFunctionFromIP 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
ms.openlocfilehash: 339c5db1610a3cf087085ce19fc663436d9c4ec1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498312"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="45823-102">ICorProfilerInfo::GetFunctionFromIP 메서드</span><span class="sxs-lookup"><span data-stu-id="45823-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="45823-103">관리 되는 코드 명령 포인터를에 매핑합니다 `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="45823-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45823-104">구문</span><span class="sxs-lookup"><span data-stu-id="45823-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45823-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="45823-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="45823-106">\[in] 관리 코드의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="45823-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="45823-107">\[out] 반환 된 함수 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="45823-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="45823-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="45823-108">Requirements</span></span>  
 <span data-ttu-id="45823-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="45823-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45823-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="45823-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="45823-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45823-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45823-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45823-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45823-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="45823-113">See also</span></span>

- [<span data-ttu-id="45823-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="45823-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
