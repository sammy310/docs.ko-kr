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
ms.openlocfilehash: b21b8ad10c76b2e9eaad773315122c3635845a78
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760251"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="d0f53-103">ICorProfilerInfo::GetFunctionFromIP 메서드</span><span class="sxs-lookup"><span data-stu-id="d0f53-103">ICorProfilerInfo::GetFunctionFromIP Method</span></span>

<span data-ttu-id="d0f53-104">관리 되는 코드 명령 포인터를에 매핑합니다 `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="d0f53-104">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0f53-105">구문</span><span class="sxs-lookup"><span data-stu-id="d0f53-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0f53-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d0f53-106">Parameters</span></span>

<span data-ttu-id="d0f53-107">`ip` 진행 관리 코드의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f53-107">`ip` [in] The instruction pointer in managed code.</span></span>

<span data-ttu-id="d0f53-108">`pFunctionId` 제한이 반환 된 함수 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d0f53-108">`pFunctionId` [out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="d0f53-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d0f53-109">Requirements</span></span>  

 <span data-ttu-id="d0f53-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d0f53-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0f53-111">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0f53-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0f53-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0f53-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0f53-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0f53-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f53-114">참조</span><span class="sxs-lookup"><span data-stu-id="d0f53-114">See also</span></span>

- [<span data-ttu-id="d0f53-115">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d0f53-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
