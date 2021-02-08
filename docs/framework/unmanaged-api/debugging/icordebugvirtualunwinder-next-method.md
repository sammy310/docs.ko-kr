---
description: '자세히 알아보기: ICorDebugVirtualUnwinder:: Next 메서드'
title: ICorDebugVirtualUnwinder::Next 메서드
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
ms.openlocfilehash: b509e8e4fb24c66764999e67ba7e36299ce7f570
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790518"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="fb230-103">ICorDebugVirtualUnwinder::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="fb230-103">ICorDebugVirtualUnwinder::Next Method</span></span>

<span data-ttu-id="fb230-104">호출자의 컨텍스트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="fb230-104">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb230-105">구문</span><span class="sxs-lookup"><span data-stu-id="fb230-105">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="fb230-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fb230-106">Parameters</span></span>  

 <span data-ttu-id="fb230-107">없음</span><span class="sxs-lookup"><span data-stu-id="fb230-107">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fb230-108">Return Value</span><span class="sxs-lookup"><span data-stu-id="fb230-108">Return Value</span></span>  

 <span data-ttu-id="fb230-109">해제가 성공적으로 발생한 경우 `S_OK`이고, 더 이상 프레임이 없어 해제를 완료할 수 없는 경우 `CORDBG_S_AT_END_OF_STACK`입니다.</span><span class="sxs-lookup"><span data-stu-id="fb230-109">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="fb230-110">실패 HRESULT가 반환되면 ICorDebug API에서 `CORDBG_E_DATA_TARGET_ERROR`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb230-110">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb230-111">설명</span><span class="sxs-lookup"><span data-stu-id="fb230-111">Remarks</span></span>  

 <span data-ttu-id="fb230-112">궁극적으로 `Next` 호출에서 실패 HRESULT 또는 `CORDBG_S_AT_END_OF_STACK`이 반환되도록 스택 워크에서 정방향 진행 중인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb230-112">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="fb230-113">`S_OK`무기한 반환 하면 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb230-113">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fb230-114">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb230-114">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb230-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fb230-115">Requirements</span></span>  

 <span data-ttu-id="fb230-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fb230-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb230-117">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fb230-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fb230-118">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb230-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb230-119">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb230-119">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb230-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb230-120">See also</span></span>

- [<span data-ttu-id="fb230-121">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb230-121">ICorDebugMemoryBuffer Interface</span></span>](icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="fb230-122">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fb230-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
