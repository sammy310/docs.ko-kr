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
ms.openlocfilehash: 14b152474cd71dc3ff7b59c94b6ec4fa0cd7ce0c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439203"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="4d8ef-102">ICorProfilerInfo::GetFunctionFromIP 메서드</span><span class="sxs-lookup"><span data-stu-id="4d8ef-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="4d8ef-103">관리 코드 명령 포인터를 `FunctionID`에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="4d8ef-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d8ef-104">구문</span><span class="sxs-lookup"><span data-stu-id="4d8ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d8ef-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4d8ef-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="4d8ef-106">진행 관리 코드의 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4d8ef-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="4d8ef-107">제한이 반환 된 함수 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4d8ef-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d8ef-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d8ef-108">Requirements</span></span>  
 <span data-ttu-id="4d8ef-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4d8ef-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d8ef-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4d8ef-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4d8ef-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d8ef-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d8ef-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d8ef-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d8ef-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d8ef-113">See also</span></span>

- [<span data-ttu-id="4d8ef-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4d8ef-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
