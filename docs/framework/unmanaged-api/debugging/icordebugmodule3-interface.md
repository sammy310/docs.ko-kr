---
title: ICorDebugModule3 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugModule3
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule3
helpviewer_keywords:
- ICorDebugModule3 interface [.NET Framework debugging]
ms.assetid: 0b69f945-263a-4e11-8512-89d27f6ea296
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37041764ad37221ea80cefa12adfb214287d8248
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764009"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="e36d0-102">ICorDebugModule3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e36d0-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="e36d0-103">동적 모듈에 대한 기호 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e36d0-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e36d0-104">구문</span><span class="sxs-lookup"><span data-stu-id="e36d0-104">Syntax</span></span>  
  
```cpp  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e36d0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e36d0-105">Methods</span></span>  
  
|<span data-ttu-id="e36d0-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e36d0-106">Method</span></span>|<span data-ttu-id="e36d0-107">설명</span><span class="sxs-lookup"><span data-stu-id="e36d0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e36d0-108">ICorDebugModule3::CreateReaderForInMemorySymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="e36d0-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="e36d0-109">기호 판독기를 만듭니다 (일반적으로 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) 동적 모듈에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36d0-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e36d0-110">설명</span><span class="sxs-lookup"><span data-stu-id="e36d0-110">Remarks</span></span>  
 <span data-ttu-id="e36d0-111">이 인터페이스는 논리적으로 "ICorDebugModule" 및 "ICorDebugModule2" 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e36d0-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e36d0-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e36d0-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e36d0-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e36d0-113">Requirements</span></span>  
 <span data-ttu-id="e36d0-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e36d0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e36d0-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e36d0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e36d0-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e36d0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e36d0-117">**.NET framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e36d0-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e36d0-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="e36d0-118">See also</span></span>

- [<span data-ttu-id="e36d0-119">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e36d0-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="e36d0-120">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e36d0-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="e36d0-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e36d0-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
