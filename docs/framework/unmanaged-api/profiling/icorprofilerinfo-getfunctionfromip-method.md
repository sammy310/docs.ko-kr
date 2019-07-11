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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a9f6e63a1f24043ac502d139f735cada599df4f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780674"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="12161-102">ICorProfilerInfo::GetFunctionFromIP 메서드</span><span class="sxs-lookup"><span data-stu-id="12161-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="12161-103">에 대 한 관리 되는 코드 명령 포인터를 매핑하는 `FunctionID`합니다.</span><span class="sxs-lookup"><span data-stu-id="12161-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12161-104">구문</span><span class="sxs-lookup"><span data-stu-id="12161-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12161-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12161-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="12161-106">[in] 관리 코드에서 명령 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="12161-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="12161-107">[out] 반환 된 함수 id입니다.</span><span class="sxs-lookup"><span data-stu-id="12161-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12161-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12161-108">Requirements</span></span>  
 <span data-ttu-id="12161-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="12161-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12161-110">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12161-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12161-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12161-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12161-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12161-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12161-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="12161-113">See also</span></span>

- [<span data-ttu-id="12161-114">ICorProfilerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="12161-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
