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
ms.openlocfilehash: 6596689af6533bb00f41b0d03805b3383ae8c3cc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792947"
---
# <a name="icordebugmodule3createreaderforinmemorysymbols-method"></a><span data-ttu-id="db423-102">ICorDebugModule3::CreateReaderForInMemorySymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="db423-102">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>
<span data-ttu-id="db423-103">동적 모듈에 대 한 디버그 기호 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="db423-103">Creates a debug symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db423-104">구문</span><span class="sxs-lookup"><span data-stu-id="db423-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateReaderForInMemorySymbols (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **    ppObj  
```  
  
## <a name="parameters"></a><span data-ttu-id="db423-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db423-105">Parameters</span></span>  
 <span data-ttu-id="db423-106">riid</span><span class="sxs-lookup"><span data-stu-id="db423-106">riid</span></span>  
 <span data-ttu-id="db423-107">진행 반환할 COM 인터페이스의 IID입니다.</span><span class="sxs-lookup"><span data-stu-id="db423-107">[in] The IID of the COM interface to return.</span></span> <span data-ttu-id="db423-108">일반적으로이 인터페이스는 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="db423-108">Typically, this is an [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md).</span></span>  
  
 <span data-ttu-id="db423-109">ppObj</span><span class="sxs-lookup"><span data-stu-id="db423-109">ppObj</span></span>  
 <span data-ttu-id="db423-110">제한이 반환 된 인터페이스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="db423-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="db423-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="db423-111">Return Value</span></span>  
 <span data-ttu-id="db423-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="db423-112">S_OK</span></span>  
 <span data-ttu-id="db423-113">판독기를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="db423-113">Successfully created the reader.</span></span>  
  
 <span data-ttu-id="db423-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span><span class="sxs-lookup"><span data-stu-id="db423-114">CORDBG_E_MODULE_LOADED_FROM_DISK</span></span>  
 <span data-ttu-id="db423-115">모듈이 메모리 내 또는 동적 모듈이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="db423-115">The module is not an in-memory or dynamic module.</span></span>  
  
 <span data-ttu-id="db423-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span><span class="sxs-lookup"><span data-stu-id="db423-116">CORDBG_E_SYMBOLS_NOT_AVAILABLE</span></span>  
 <span data-ttu-id="db423-117">응용 프로그램에서 기호를 제공 하지 않았거나 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db423-117">Symbols have not been supplied by the application or are not yet available.</span></span>  
  
 <span data-ttu-id="db423-118">E_FAIL(또는 다른 E_ 반환 코드)</span><span class="sxs-lookup"><span data-stu-id="db423-118">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="db423-119">판독기를 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="db423-119">Unable to create the reader.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db423-120">주의</span><span class="sxs-lookup"><span data-stu-id="db423-120">Remarks</span></span>  
 <span data-ttu-id="db423-121">이 메서드를 사용 하 여 메모리 내 (동적이 아닌) 모듈에 대 한 기호 판독기 개체를 만들 수도 있습니다. 단, 기호를 처음 사용할 수 있는 경우에만 ( [UpdateModuleSymbols 메서드](icordebugmanagedcallback-updatemodulesymbols-method.md) 콜백에서 표시).</span><span class="sxs-lookup"><span data-stu-id="db423-121">This method can also be used to create a symbol reader object for in-memory (non-dynamic) modules, but only after the symbols are first available (indicated by the [UpdateModuleSymbols Method](icordebugmanagedcallback-updatemodulesymbols-method.md) callback).</span></span>  
  
 <span data-ttu-id="db423-122">이 메서드는 호출 될 때마다 새 판독기 인스턴스를 반환 합니다 (예 [: Ccomptrbase:: CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span><span class="sxs-lookup"><span data-stu-id="db423-122">This method returns a new reader instance every time it is called (like [CComPtrBase::CoCreateInstance](/cpp/atl/reference/ccomptrbase-class#cocreateinstance)).</span></span> <span data-ttu-id="db423-123">따라서 디버거는 기본 데이터가 변경 되었을 수 있는 경우 (즉, [LoadClass 메서드](icordebugmanagedcallback-loadclass-method.md) 콜백이 수신 될 때)에만 결과를 캐시 하 고 새 인스턴스를 요청 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db423-123">Therefore, the debugger should cache the result and request a new instance only when the underlying data may have changed (that is, when a [LoadClass Method](icordebugmanagedcallback-loadclass-method.md) callback is received).</span></span>  
  
 <span data-ttu-id="db423-124">동적 모듈에는 첫 번째 형식이 로드 될 때까지 사용할 수 있는 기호가 없습니다 ( [LoadClass 메서드](icordebugmanagedcallback-loadclass-method.md) 콜백에 표시 됨).</span><span class="sxs-lookup"><span data-stu-id="db423-124">Dynamic modules do not have any symbols available until the first type has been loaded (as indicated by the [LoadClass Method](icordebugmanagedcallback-loadclass-method.md) callback).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db423-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db423-125">Requirements</span></span>  
 <span data-ttu-id="db423-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db423-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db423-127">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db423-127">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db423-128">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db423-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db423-129">**.NET Framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="db423-129">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db423-130">참조</span><span class="sxs-lookup"><span data-stu-id="db423-130">See also</span></span>

- [<span data-ttu-id="db423-131">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db423-131">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="db423-132">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db423-132">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="db423-133">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db423-133">Debugging Interfaces</span></span>](debugging-interfaces.md)
