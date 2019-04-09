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
ms.openlocfilehash: a340086be042c790ae7bf750759ff80f7c9eaf23
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59122618"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="00419-102">ICorDebugModule3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00419-102">ICorDebugModule3 Interface</span></span>
<span data-ttu-id="00419-103">동적 모듈에 대한 기호 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="00419-103">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00419-104">구문</span><span class="sxs-lookup"><span data-stu-id="00419-104">Syntax</span></span>  
  
```  
interface ICorDebugModule3 : IUnknown  
{  
    HRESULT CreateReaderForInMemorySymbols  
      (  
      [in] REFIID riid,  
      [out][iid_is(riid)] void **  ppObj  
      );  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="00419-105">메서드</span><span class="sxs-lookup"><span data-stu-id="00419-105">Methods</span></span>  
  
|<span data-ttu-id="00419-106">메서드</span><span class="sxs-lookup"><span data-stu-id="00419-106">Method</span></span>|<span data-ttu-id="00419-107">설명</span><span class="sxs-lookup"><span data-stu-id="00419-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="00419-108">ICorDebugModule3::CreateReaderForInMemorySymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="00419-108">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="00419-109">기호 판독기를 만듭니다 (일반적으로 [ISymUnmanagedReader 인터페이스](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) 동적 모듈에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="00419-109">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00419-110">설명</span><span class="sxs-lookup"><span data-stu-id="00419-110">Remarks</span></span>  
 <span data-ttu-id="00419-111">이 인터페이스는 논리적으로 "ICorDebugModule" 및 "ICorDebugModule2" 인터페이스를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="00419-111">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00419-112">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="00419-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00419-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="00419-113">Requirements</span></span>  
 <span data-ttu-id="00419-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="00419-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00419-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00419-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00419-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00419-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00419-117">**.NET framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="00419-117">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="00419-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="00419-118">See also</span></span>

- [<span data-ttu-id="00419-119">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00419-119">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)
- [<span data-ttu-id="00419-120">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00419-120">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)

- [<span data-ttu-id="00419-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="00419-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
