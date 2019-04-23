---
title: ICorProfilerInfo7::ReadInMemorySymbols
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo7.ReadInMemorySymbols
api_location:
- CorProf.idl
- CorProf.h
- CorGuids.lib
api_type:
- COM
ms.assetid: 1745a0b9-8332-4777-a670-b549bff3b901
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 662863ec69e464dafe893552f1d81755313acc75
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153324"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="95025-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="95025-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="95025-103">[[!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="95025-103">[Supported in the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)] and later versions]</span></span>  
  
 <span data-ttu-id="95025-104">메모리 내 기호 스트림에서 바이트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="95025-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95025-105">구문</span><span class="sxs-lookup"><span data-stu-id="95025-105">Syntax</span></span>  
  
```  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95025-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95025-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="95025-107">[in] 메모리 스트림이 포함 된 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="95025-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="95025-108">[in] 바이트 읽기를 시작 하는 메모리 내 스트림 내의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="95025-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="95025-109">[out] 데이터를 복사할 대상 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="95025-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="95025-110">버퍼 있어야 `countSymbolBytes` 사용 가능한 공간입니다.</span><span class="sxs-lookup"><span data-stu-id="95025-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="95025-111">[in] 복사할 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="95025-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="95025-112">[out] 메서드는 반환 될 때 실제 읽은 바이트 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="95025-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="95025-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="95025-113">Return Value</span></span>  
 <span data-ttu-id="95025-114">`S_OK`에서 읽을 바이트 수를 0이 아닌 경우.</span><span class="sxs-lookup"><span data-stu-id="95025-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="95025-115">`CORPROF_E_MODULE_IS_DYNAMIC`를 사용 하 여 모듈을 만든 경우 <xref:System.Reflection.Emit>합니다.</span><span class="sxs-lookup"><span data-stu-id="95025-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95025-116">설명</span><span class="sxs-lookup"><span data-stu-id="95025-116">Remarks</span></span>  
 <span data-ttu-id="95025-117">합니다 `ReadInMemorySymbols` 메서드 판독 하 려 `countSymbolBytes` 오프셋에서 시작 하는 데이터의 `symbolsReadOffset` 메모리 스트림 내에서.</span><span class="sxs-lookup"><span data-stu-id="95025-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="95025-118">데이터를 복사할 `pSymbolBytes`, 것으로 예상 되는 `countSymbolBytes` 사용 가능한 공간입니다.</span><span class="sxs-lookup"><span data-stu-id="95025-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="95025-119">`pCountSymbolsBytesRead` 실제 읽은 작은 일 수 있는 바이트 수가 포함 보다 `countSymbolBytes` 스트림의 맨 끝에 도달한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="95025-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95025-120">현재 구현에서는 Reflection.Emit을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95025-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="95025-121">메서드가 반환 하는 경우 모듈을 Reflection.Emit을 사용 하 여 만든, `CORPROF_E_MODULE_IS_DYNAMIC`합니다.</span><span class="sxs-lookup"><span data-stu-id="95025-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95025-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95025-122">Requirements</span></span>  
 <span data-ttu-id="95025-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="95025-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95025-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="95025-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="95025-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95025-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95025-126">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95025-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95025-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="95025-127">See also</span></span>

- [<span data-ttu-id="95025-128">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="95025-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
