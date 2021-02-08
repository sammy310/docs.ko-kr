---
description: '자세히 알아보기: ICorDebugModule3 인터페이스'
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
ms.openlocfilehash: 5b47cffb267ab97de2cd225aca2998962ba66d99
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790765"
---
# <a name="icordebugmodule3-interface"></a><span data-ttu-id="db9e2-103">ICorDebugModule3 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db9e2-103">ICorDebugModule3 Interface</span></span>

<span data-ttu-id="db9e2-104">동적 모듈에 대한 기호 판독기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="db9e2-104">Creates a symbol reader for a dynamic module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db9e2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="db9e2-105">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="db9e2-106">메서드</span><span class="sxs-lookup"><span data-stu-id="db9e2-106">Methods</span></span>  
  
|<span data-ttu-id="db9e2-107">메서드</span><span class="sxs-lookup"><span data-stu-id="db9e2-107">Method</span></span>|<span data-ttu-id="db9e2-108">설명</span><span class="sxs-lookup"><span data-stu-id="db9e2-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db9e2-109">ICorDebugModule3::CreateReaderForInMemorySymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="db9e2-109">ICorDebugModule3::CreateReaderForInMemorySymbols Method</span></span>](icordebugmodule3-createreaderforinmemorysymbols-method.md)|<span data-ttu-id="db9e2-110">동적 모듈에 대 한 기호 판독기 (일반적으로 [ISymUnmanagedReader 인터페이스](../diagnostics/isymunmanagedreader-interface.md))를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="db9e2-110">Creates a symbol reader (typically [ISymUnmanagedReader Interface](../diagnostics/isymunmanagedreader-interface.md)) for a dynamic module.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db9e2-111">설명</span><span class="sxs-lookup"><span data-stu-id="db9e2-111">Remarks</span></span>  

 <span data-ttu-id="db9e2-112">이 인터페이스는 "ICorDebugModule" 및 "ICorDebugModule2" 인터페이스를 논리적으로 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="db9e2-112">This interface logically extends the "ICorDebugModule" and "ICorDebugModule2" interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="db9e2-113">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db9e2-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db9e2-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db9e2-114">Requirements</span></span>  

 <span data-ttu-id="db9e2-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="db9e2-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db9e2-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db9e2-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db9e2-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db9e2-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db9e2-118">**.NET Framework 버전:** 4.5, 4, 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="db9e2-118">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>
  
## <a name="see-also"></a><span data-ttu-id="db9e2-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="db9e2-119">See also</span></span>

- [<span data-ttu-id="db9e2-120">ICorDebugRemoteTarget 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db9e2-120">ICorDebugRemoteTarget Interface</span></span>](icordebugremotetarget-interface.md)
- [<span data-ttu-id="db9e2-121">ICorDebug 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db9e2-121">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="db9e2-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="db9e2-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
