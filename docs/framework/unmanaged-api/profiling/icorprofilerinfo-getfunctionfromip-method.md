---
description: '자세히 알아보기: ICorProfilerInfo:: GetFunctionFromIP 메서드'
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
ms.openlocfilehash: 1acea6943e74e65e4359c7da590d3888736dbd6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647598"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="068b5-103">ICorProfilerInfo::GetFunctionFromIP 메서드</span><span class="sxs-lookup"><span data-stu-id="068b5-103">ICorProfilerInfo::GetFunctionFromIP Method</span></span>

<span data-ttu-id="068b5-104">관리 되는 코드 명령 포인터를에 매핑합니다 `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="068b5-104">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="068b5-105">구문</span><span class="sxs-lookup"><span data-stu-id="068b5-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="068b5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="068b5-106">Parameters</span></span>

- `ip`

  <span data-ttu-id="068b5-107">\[in] 관리 코드의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="068b5-107">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="068b5-108">\[out] 반환 된 함수 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="068b5-108">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="068b5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="068b5-109">Requirements</span></span>  

 <span data-ttu-id="068b5-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="068b5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="068b5-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="068b5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="068b5-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="068b5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="068b5-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="068b5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="068b5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="068b5-114">See also</span></span>

- [<span data-ttu-id="068b5-115">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="068b5-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
