---
description: '자세히 알아보기: ICorProfilerInfo7:: ReadInMemorySymbols'
title: 'ICorProfilerInfo7:: ReadInMemorySymbols'
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
ms.openlocfilehash: 7f1a88d823e7cdfcc89aa140681f61cfbe3f63ec
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736988"
---
# <a name="icorprofilerinfo7readinmemorysymbols"></a><span data-ttu-id="04e93-103">ICorProfilerInfo7:: ReadInMemorySymbols</span><span class="sxs-lookup"><span data-stu-id="04e93-103">ICorProfilerInfo7::ReadInMemorySymbols</span></span>

<span data-ttu-id="04e93-104">[.NET Framework 4.6.1 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="04e93-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="04e93-105">메모리 내 기호 스트림에서 바이트를 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-105">Reads bytes from an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04e93-106">구문</span><span class="sxs-lookup"><span data-stu-id="04e93-106">Syntax</span></span>  
  
```cpp  
HRESULT ReadInMemorySymbols(  
        [in] ModuleID moduleId,  
        [in] DWORD symbolsReadOffset,  
        [out] BYTE* pSymbolBytes,  
        [in] DWORD countSymbolBytes,  
        [out] DWORD* pCountSymbolBytesRead  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04e93-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04e93-107">Parameters</span></span>  

 `moduleId`  
 <span data-ttu-id="04e93-108">진행 메모리 내 스트림을 포함 하는 모듈의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-108">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 `symbolsReadOffset`  
 <span data-ttu-id="04e93-109">진행 바이트 읽기를 시작할 메모리 내 스트림 내의 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-109">[in] The offset within the in-memory stream at which to start reading bytes.</span></span>  
  
 `pSymbolBytes`  
 <span data-ttu-id="04e93-110">제한이 데이터가 복사 될 버퍼에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-110">[out] A pointer to the buffer to which the data will be copied.</span></span> <span data-ttu-id="04e93-111">버퍼에 `countSymbolBytes` 사용 가능한 공간이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-111">The buffer should have `countSymbolBytes` of space available.</span></span>  
  
 `countSymbolBytes`  
 <span data-ttu-id="04e93-112">진행 복사할 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-112">[in] The number of bytes to copy.</span></span>  
  
 `pCountSymbolBytesRead`  
 <span data-ttu-id="04e93-113">제한이 메서드가 반환 될 때 읽은 실제 바이트 수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-113">[out] When the method returns, contains the actual number of bytes read.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="04e93-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="04e93-114">Return Value</span></span>  

 <span data-ttu-id="04e93-115">`S_OK`0이 아닌 바이트 수를 읽은 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-115">`S_OK`, if a non-zero number of bytes were read.</span></span>  
  
 <span data-ttu-id="04e93-116">`CORPROF_E_MODULE_IS_DYNAMIC`를 사용 하 여 모듈을 만든 경우 <xref:System.Reflection.Emit> 입니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-116">`CORPROF_E_MODULE_IS_DYNAMIC`, if the module was created using <xref:System.Reflection.Emit>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04e93-117">설명</span><span class="sxs-lookup"><span data-stu-id="04e93-117">Remarks</span></span>  

 <span data-ttu-id="04e93-118">`ReadInMemorySymbols`메서드는 `countSymbolBytes` `symbolsReadOffset` 메모리 내 스트림 내의 오프셋에서 시작 하는 데이터를 읽으려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-118">The `ReadInMemorySymbols` method attempts to read `countSymbolBytes` of data starting at offset      `symbolsReadOffset` within the in-memory stream.</span></span> <span data-ttu-id="04e93-119">데이터가에 복사 됩니다 `pSymbolBytes` .이는 `countSymbolBytes` 사용 가능한 공간이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-119">The data is copied to `pSymbolBytes`, which is expected to have `countSymbolBytes` of space available.</span></span>     <span data-ttu-id="04e93-120">`pCountSymbolsBytesRead` 읽은 실제 바이트 수를 포함 합니다. 스트림의 끝에 도달 하는 경우 보다 적을 수 있습니다 `countSymbolBytes` .</span><span class="sxs-lookup"><span data-stu-id="04e93-120">`pCountSymbolsBytesRead` contains the actual number of bytes read, which may be less than `countSymbolBytes` if the end of the stream is reached.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04e93-121">현재 구현에서는 리플렉션 내보내기를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04e93-121">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="04e93-122">리플렉션을 사용 하 여 모듈을 만든 경우이 메서드는를 반환 합니다 `CORPROF_E_MODULE_IS_DYNAMIC` .</span><span class="sxs-lookup"><span data-stu-id="04e93-122">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04e93-123">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04e93-123">Requirements</span></span>  

 <span data-ttu-id="04e93-124">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04e93-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04e93-125">**헤더:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="04e93-125">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="04e93-126">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04e93-126">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04e93-127">**.NET Framework 버전:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04e93-127">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04e93-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04e93-128">See also</span></span>

- [<span data-ttu-id="04e93-129">ICorProfilerInfo7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04e93-129">ICorProfilerInfo7 Interface</span></span>](icorprofilerinfo7-interface.md)
