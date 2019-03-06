---
title: ICorDebugModule3::CreateReaderForInMemorySymbols 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule3.CreateReaderForInMemorySymbols
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3::CreateReaderForInMemorySymbols
helpviewer_keywords:
- CreateReaderForInMemorySymbols method, ICorDebugModule3 interface [.NET Framework debugging]
- ICorDebugModule3::CreateReaderForInMemorySymbols method [.NET Framework debugging]
ms.assetid: af317171-d66d-4114-89eb-063554c74940
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f553870399a8f2ddb78e01d27a7f7e5bd32d786b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473996"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="c3945-102">ICorDebugModule3::CreateReaderForInMemorySymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="c3945-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="c3945-103">동적 모듈에 대 한 디버그 기호 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c3945-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3945-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3945-104">Syntax</span></span>  
  
```  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3945-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3945-105">Parameters</span></span>  
 <span data-ttu-id="c3945-106">riid</span><span class="sxs-lookup"><span data-stu-id="c3945-106">riid</span></span>  
 <span data-ttu-id="c3945-107">[in] 반환할 COM 인터페이스의 IID입니다.</span><span class="sxs-lookup"><span data-stu-id="c3945-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="c3945-108">일반적으로 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3945-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="c3945-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="c3945-109">ppObj</span></span>  
 <span data-ttu-id="c3945-110">[out] 반환 되는 인터페이스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c3945-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3945-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="c3945-111">Return Value</span></span>  
 <span data-ttu-id="c3945-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="c3945-112">S_OK</span></span>  
 <span data-ttu-id="c3945-113">판독기를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3945-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="c3945-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="c3945-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="c3945-115">모듈에는 메모리 내 또는 동적 모듈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c3945-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="c3945-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c3945-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="c3945-117">기호는 응용 프로그램에서 지정 되지 않은 또는 아직 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3945-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="c3945-118">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="c3945-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="c3945-119">판독기를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c3945-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3945-120">설명</span><span class="sxs-lookup"><span data-stu-id="c3945-120">Remarks</span></span>  
 <span data-ttu-id="c3945-121">이 메서드가 될 수 있습니다도 메모리 내 (동적이 아닌) 모듈에 대 한 기호 판독기 개체를 만드는 데에 기호를 먼저 사용할 (나타난 합니다 [UpdateModuleSymbols 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) 콜백).</span><span class="sxs-lookup"><span data-stu-id="c3945-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="c3945-122">이 메서드가 호출 될 때마다 새 판독기 인스턴스를 반환 합니다 (같은 [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="c3945-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="c3945-123">디버거에서 결과 캐시 하 고 기본 데이터를 변경한 경우에 새 인스턴스를 요청 해야 하므로 (즉을 [LoadClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 콜백을 수신).</span><span class="sxs-lookup"><span data-stu-id="c3945-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="c3945-124">첫 번째 형식이 로드 될 때까지 동적 모듈에서는 사용할 수 있는 모든 기호를 있지 않은 (표시 된 대로 합니다 [LoadClass 메서드](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) 콜백).</span><span class="sxs-lookup"><span data-stu-id="c3945-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3945-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3945-125">Requirements</span></span>  
 <span data-ttu-id="c3945-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3945-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3945-127">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c3945-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c3945-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c3945-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c3945-129">**.NET framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c3945-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3945-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3945-130">See also</span></span>
- [<span data-ttu-id="c3945-131">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3945-131">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="c3945-132">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3945-132">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="c3945-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3945-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
