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
ms.openlocfilehash: 53c01d2db44f4d0adf1ba5b9cc225ab49581aa5d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868345"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="59294-102">ICorProfilerInfo7::ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="59294-102">ICorProfilerInfo7::ReadInMemorySymbols</span></span>
<span data-ttu-id="59294-103">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="59294-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="59294-104">메모리 내 기호 스트림에서 바이트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="59294-104">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59294-105">구문</span><span class="sxs-lookup"><span data-stu-id="59294-105">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59294-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59294-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="59294-107">진행 메모리 내 스트림을 포함 하는 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="59294-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="59294-108">진행 바이트 읽기를 시작할 메모리 내 스트림 내의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="59294-108">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="59294-109">제한이 데이터가 복사 될 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59294-109">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="59294-110">버퍼에 사용 가능한 공간이 `countSymbolBytes` 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59294-110">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="59294-111">진행 복사할 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="59294-111">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="59294-112">제한이 메서드가 반환 될 때 읽은 실제 바이트 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="59294-112">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="59294-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="59294-113">Return Value</span></span>  
 <span data-ttu-id="59294-114">0이 아닌 바이트 수를 읽은 경우 `S_OK`합니다.</span><span class="sxs-lookup"><span data-stu-id="59294-114">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="59294-115"><xref:System.Reflection.Emit>를 사용 하 여 모듈을 만든 경우 `CORPROF_E_MODULE_IS_DYNAMIC`합니다.</span><span class="sxs-lookup"><span data-stu-id="59294-115">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59294-116">주의</span><span class="sxs-lookup"><span data-stu-id="59294-116">Remarks</span></span>  
 <span data-ttu-id="59294-117">`ReadInMemorySymbols` 메서드는 메모리 내 스트림 내의 오프셋 `symbolsReadOffset`에서 시작 하는 데이터 `countSymbolBytes`를 읽으려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="59294-117">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="59294-118">데이터는 `pSymbolBytes`에 복사 됩니다 .이는 사용 가능한 공간 `countSymbolBytes` 있는 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59294-118">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="59294-119">`pCountSymbolsBytesRead`는 읽은 실제 바이트 수를 포함 하며 스트림의 끝에 도달 하는 경우 `countSymbolBytes` 보다 적을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59294-119">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59294-120">현재 구현에서는 리플렉션 내보내기를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59294-120">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="59294-121">리플렉션을 사용 하 여 모듈을 만든 경우이 메서드는 `CORPROF_E_MODULE_IS_DYNAMIC`를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="59294-121">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59294-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59294-122">Requirements</span></span>  
 <span data-ttu-id="59294-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59294-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59294-124">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="59294-124">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="59294-125">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="59294-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="59294-126">**.NET Framework 버전:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="59294-126">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59294-127">참조</span><span class="sxs-lookup"><span data-stu-id="59294-127">See also</span></span>

- [<span data-ttu-id="59294-128">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59294-128">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
