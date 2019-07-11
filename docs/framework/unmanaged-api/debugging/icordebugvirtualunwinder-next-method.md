---
title: ICorDebugVirtualUnwinder::Next 메서드
ms.date: 03/30/2017
ms.assetid: 790e0426-e5cd-49fd-a792-f8c8635d72fe
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bd12861b34d577a002fbf0cc8a7962b7bfc35fe1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67775338"
---
# <a name="icordebugvirtualunwindernext-method"></a><span data-ttu-id="1452f-102">ICorDebugVirtualUnwinder::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="1452f-102">ICorDebugVirtualUnwinder::Next Method</span></span>
<span data-ttu-id="1452f-103">호출자의 컨텍스트로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1452f-103">Advances to the caller's context.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1452f-104">구문</span><span class="sxs-lookup"><span data-stu-id="1452f-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="parameters"></a><span data-ttu-id="1452f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1452f-105">Parameters</span></span>  
 <span data-ttu-id="1452f-106">없음</span><span class="sxs-lookup"><span data-stu-id="1452f-106">None.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1452f-107">반환 값</span><span class="sxs-lookup"><span data-stu-id="1452f-107">Return Value</span></span>  
 <span data-ttu-id="1452f-108">해제가 성공적으로 발생한 경우 `S_OK`이고, 더 이상 프레임이 없어 해제를 완료할 수 없는 경우 `CORDBG_S_AT_END_OF_STACK`입니다.</span><span class="sxs-lookup"><span data-stu-id="1452f-108">`S_OK` if the unwind occurred successfully, or `CORDBG_S_AT_END_OF_STACK` if the unwind cannot be completed because there are no more frames.</span></span>  
  
 <span data-ttu-id="1452f-109">실패 HRESULT가 반환되면 ICorDebug API에서 `CORDBG_E_DATA_TARGET_ERROR`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1452f-109">If a failing HRESULT is returned, ICorDebug APIs will return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1452f-110">설명</span><span class="sxs-lookup"><span data-stu-id="1452f-110">Remarks</span></span>  
 <span data-ttu-id="1452f-111">궁극적으로 `Next` 호출에서 실패 HRESULT 또는 `CORDBG_S_AT_END_OF_STACK`이 반환되도록 스택 워크에서 정방향 진행 중인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1452f-111">The stack walker should ensure that it makes forward progress, so that eventually a call to `Next` will return a failing HRESULT or `CORDBG_S_AT_END_OF_STACK`.</span></span> <span data-ttu-id="1452f-112">반환 `S_OK` 무기한 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1452f-112">Returning `S_OK` indefinitely may cause an infinite loop.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1452f-113">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1452f-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1452f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1452f-114">Requirements</span></span>  
 <span data-ttu-id="1452f-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1452f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1452f-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1452f-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1452f-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1452f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1452f-118">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1452f-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1452f-119">참고자료</span><span class="sxs-lookup"><span data-stu-id="1452f-119">See also</span></span>

- [<span data-ttu-id="1452f-120">ICorDebugMemoryBuffer 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1452f-120">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)
- [<span data-ttu-id="1452f-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1452f-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
