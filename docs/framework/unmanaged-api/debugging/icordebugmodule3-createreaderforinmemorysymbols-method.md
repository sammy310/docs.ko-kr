---
description: '자세히 알아보기: ICorDebugModule3:: CreateReaderForInMemorySymbols 메서드'
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
ms.openlocfilehash: af037cc891e83f53fd94bad290f40286ed665e6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790778"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="84cfc-103">ICorDebugModule3::CreateReaderForInMemorySymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="84cfc-103">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>

<span data-ttu-id="84cfc-104">동적 모듈에 대 한 디버그 기호 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="84cfc-104">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84cfc-105">구문</span><span class="sxs-lookup"><span data-stu-id="84cfc-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="84cfc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="84cfc-106">Parameters</span></span>  

 <span data-ttu-id="84cfc-107">riid</span><span class="sxs-lookup"><span data-stu-id="84cfc-107">riid</span></span>  
 <span data-ttu-id="84cfc-108">진행 반환할 COM 인터페이스의 IID입니다.</span><span class="sxs-lookup"><span data-stu-id="84cfc-108">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="84cfc-109">일반적으로이 인터페이스는 [ISymUnmanagedReader 인터페이스](../diagnostics/isymunmanagedreader-interface.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="84cfc-109">Typically, this is an [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="84cfc-110">ppObj</span><span class="sxs-lookup"><span data-stu-id="84cfc-110">ppObj</span></span>  
 <span data-ttu-id="84cfc-111">제한이 반환 된 인터페이스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="84cfc-111">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="84cfc-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="84cfc-112">Return Value</span></span>  

 <span data-ttu-id="84cfc-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="84cfc-113">S_OK</span></span>  
 <span data-ttu-id="84cfc-114">판독기를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="84cfc-114">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="84cfc-115">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="84cfc-115">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="84cfc-116">모듈이 메모리 내 또는 동적 모듈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="84cfc-116">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="84cfc-117">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="84cfc-117">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="84cfc-118">응용 프로그램에서 기호를 제공 하지 않았거나 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84cfc-118">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="84cfc-119">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="84cfc-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="84cfc-120">판독기를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84cfc-120">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84cfc-121">설명</span><span class="sxs-lookup"><span data-stu-id="84cfc-121">Remarks</span></span>  

 <span data-ttu-id="84cfc-122">이 메서드를 사용 하 여 메모리 내 (동적이 아닌) 모듈에 대 한 기호 판독기 개체를 만들 수도 있습니다. 단, 기호를 처음 사용할 수 있는 경우에만 ( [UpdateModuleSymbols 메서드](icordebugmanagedcallback-updatemodulesymbols-method.md) 콜백에서 표시).</span><span class="sxs-lookup"><span data-stu-id="84cfc-122">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="84cfc-123">이 메서드는 호출 될 때마다 새 판독기 인스턴스를 반환 합니다 (예 [: Ccomptrbase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="84cfc-123">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="84cfc-124">따라서 디버거는 기본 데이터가 변경 되었을 수 있는 경우 (즉, [LoadClass 메서드](icordebugmanagedcallback-loadclass-method.md) 콜백이 수신 될 때)에만 결과를 캐시 하 고 새 인스턴스를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84cfc-124">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="84cfc-125">동적 모듈에는 첫 번째 형식이 로드 될 때까지 사용할 수 있는 기호가 없습니다 ( [LoadClass 메서드](icordebugmanagedcallback-loadclass-method.md) 콜백에 표시 됨).</span><span class="sxs-lookup"><span data-stu-id="84cfc-125">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84cfc-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="84cfc-126">Requirements</span></span>  

 <span data-ttu-id="84cfc-127">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84cfc-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84cfc-128">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84cfc-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84cfc-129">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84cfc-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84cfc-130">**.NET Framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="84cfc-130">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84cfc-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="84cfc-131">See also</span></span>

- [<span data-ttu-id="84cfc-132">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84cfc-132">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="84cfc-133">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84cfc-133">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="84cfc-134">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="84cfc-134">Debugging Interfaces</span></span>](debugging-interfaces.md)
