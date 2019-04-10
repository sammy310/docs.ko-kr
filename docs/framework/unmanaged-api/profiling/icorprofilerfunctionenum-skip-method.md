---
title: ICorProfilerFunctionEnum::Skip 메서드
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0e334c75afee60591db2b4e1f45cf0ec753ee2e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141653"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="4e113-102">ICorProfilerFunctionEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="4e113-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="4e113-103">지정한 개수의 요소를 건너뛰도록 현재 위치에서 열거자의 커서를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e113-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e113-104">구문</span><span class="sxs-lookup"><span data-stu-id="4e113-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e113-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4e113-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4e113-106">[in] 건너뛸 요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="4e113-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e113-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="4e113-107">Return Value</span></span>  
 <span data-ttu-id="4e113-108">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4e113-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4e113-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e113-109">HRESULT</span></span>|<span data-ttu-id="4e113-110">설명</span><span class="sxs-lookup"><span data-stu-id="4e113-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4e113-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e113-111">S_OK</span></span>|`celt` <span data-ttu-id="4e113-112">요소를 건너뛰었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e113-112">elements were skipped.</span></span>|  
|<span data-ttu-id="4e113-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4e113-113">S_FALSE</span></span>|<span data-ttu-id="4e113-114">미만의 `celt` 요소가 더 이상 있는지를 나타내는 요소를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="4e113-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e113-115">설명</span><span class="sxs-lookup"><span data-stu-id="4e113-115">Remarks</span></span>  
 <span data-ttu-id="4e113-116">이 열거자의이 커서의 새 위치는 (현재 위치) + `celt`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e113-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e113-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4e113-117">Requirements</span></span>  
 <span data-ttu-id="4e113-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e113-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e113-119">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e113-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e113-120">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e113-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4e113-121">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="4e113-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4e113-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="4e113-122">See also</span></span>

- [<span data-ttu-id="4e113-123">ICorProfilerFunctionEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e113-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="4e113-124">프로파일링 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4e113-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
