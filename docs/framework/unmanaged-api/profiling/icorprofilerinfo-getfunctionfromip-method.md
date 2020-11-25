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
ms.openlocfilehash: 4a7e21ae60253c741b57674212e0ecabdd844d2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722563"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="58c51-102">ICorProfilerInfo::GetFunctionFromIP 메서드</span><span class="sxs-lookup"><span data-stu-id="58c51-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>

<span data-ttu-id="58c51-103">관리 되는 코드 명령 포인터를에 매핑합니다 `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="58c51-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c51-104">구문</span><span class="sxs-lookup"><span data-stu-id="58c51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58c51-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="58c51-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="58c51-106">\[in] 관리 코드의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="58c51-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="58c51-107">\[out] 반환 된 함수 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="58c51-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="58c51-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58c51-108">Requirements</span></span>  

 <span data-ttu-id="58c51-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58c51-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c51-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58c51-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58c51-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58c51-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58c51-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c51-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c51-113">참조</span><span class="sxs-lookup"><span data-stu-id="58c51-113">See also</span></span>

- [<span data-ttu-id="58c51-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="58c51-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
