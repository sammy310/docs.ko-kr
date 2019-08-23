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
ms.openlocfilehash: 95b463b23c230d620d746e48da49d75238ef2cb7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69955367"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="b3242-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="b3242-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="b3242-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="b3242-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="b3242-104">메모리 내 기호 스트림에서 바이트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3242-105">구문</span><span class="sxs-lookup"><span data-stu-id="b3242-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3242-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b3242-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="b3242-107">진행 메모리 내 스트림을 포함 하는 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="b3242-108">진행 바이트 읽기를 시작할 메모리 내 스트림 내의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="b3242-109">제한이 데이터가 복사 될 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="b3242-110">버퍼 `countSymbolBytes` 에 사용 가능한 공간이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="b3242-111">진행 복사할 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="b3242-112">제한이 메서드가 반환 될 때 읽은 실제 바이트 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3242-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="b3242-113">Return Value</span></span>  
 <span data-ttu-id="b3242-114">`S_OK`0이 아닌 바이트 수를 읽은 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="b3242-115">`CORPROF_E_MODULE_IS_DYNAMIC`를 사용 하 여 <xref:System.Reflection.Emit>모듈을 만든 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b3242-116">설명</span><span class="sxs-lookup"><span data-stu-id="b3242-116">Remarks</span></span>  
 <span data-ttu-id="b3242-117">메서드 `ReadInMemorySymbols` 는 메모리 내 스트림 `countSymbolBytes` 내의 오프셋 `symbolsReadOffset` 에서 시작 하는 데이터를 읽으려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="b3242-118">데이터가에 `pSymbolBytes`복사 됩니다 .이는 사용 가능한 공간이 있어야 `countSymbolBytes` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="b3242-119">`pCountSymbolsBytesRead`읽은 실제 바이트 수를 포함 합니다. 스트림의 끝에 도달 하 `countSymbolBytes` 는 경우 보다 적을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b3242-120">현재 구현에서는 리플렉션 내보내기를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="b3242-121">리플렉션을 사용 하 여 모듈을 만든 경우이 메서드는를 반환 `CORPROF_E_MODULE_IS_DYNAMIC`합니다.</span><span class="sxs-lookup"><span data-stu-id="b3242-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3242-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3242-122">Requirements</span></span>  
 <span data-ttu-id="b3242-123">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3242-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3242-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3242-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3242-125">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3242-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3242-126">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3242-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3242-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="b3242-127">See also</span></span>

- [<span data-ttu-id="b3242-128">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3242-128">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)
