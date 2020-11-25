---
title: ICorDebugBoxValue 인터페이스
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
ms.openlocfilehash: 6d58ae048382a78c422703d5c6caeb3bbc739849
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723170"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="adcac-102">ICorDebugBoxValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="adcac-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="adcac-103">Boxed 값 클래스 개체를 나타내는 "ICorDebugHeapValue"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="adcac-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="adcac-104">메서드</span><span class="sxs-lookup"><span data-stu-id="adcac-104">Methods</span></span>  
  
|<span data-ttu-id="adcac-105">메서드</span><span class="sxs-lookup"><span data-stu-id="adcac-105">Method</span></span>|<span data-ttu-id="adcac-106">설명</span><span class="sxs-lookup"><span data-stu-id="adcac-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="adcac-107">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="adcac-107">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="adcac-108">Boxed "ICorDebugObjectValue" 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="adcac-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="adcac-109">설명</span><span class="sxs-lookup"><span data-stu-id="adcac-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="adcac-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="adcac-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="adcac-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="adcac-111">Requirements</span></span>  

 <span data-ttu-id="adcac-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="adcac-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="adcac-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="adcac-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="adcac-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="adcac-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="adcac-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="adcac-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adcac-116">참조</span><span class="sxs-lookup"><span data-stu-id="adcac-116">See also</span></span>

- [<span data-ttu-id="adcac-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="adcac-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
