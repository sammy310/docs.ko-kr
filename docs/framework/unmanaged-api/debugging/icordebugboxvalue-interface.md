---
description: '자세히 알아보기: ICorDebugBoxValue 인터페이스'
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
ms.openlocfilehash: 86a985d3cbb8330efdef1d6636f91b64c3f78bc6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711936"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="7a4fd-103">ICorDebugBoxValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a4fd-103">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="7a4fd-104">Boxed 값 클래스 개체를 나타내는 "ICorDebugHeapValue"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="7a4fd-104">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7a4fd-105">메서드</span><span class="sxs-lookup"><span data-stu-id="7a4fd-105">Methods</span></span>  
  
|<span data-ttu-id="7a4fd-106">메서드</span><span class="sxs-lookup"><span data-stu-id="7a4fd-106">Method</span></span>|<span data-ttu-id="7a4fd-107">설명</span><span class="sxs-lookup"><span data-stu-id="7a4fd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7a4fd-108">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="7a4fd-108">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="7a4fd-109">Boxed "ICorDebugObjectValue" 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="7a4fd-109">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a4fd-110">설명</span><span class="sxs-lookup"><span data-stu-id="7a4fd-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7a4fd-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a4fd-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a4fd-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a4fd-112">Requirements</span></span>  

 <span data-ttu-id="7a4fd-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a4fd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a4fd-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a4fd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a4fd-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a4fd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a4fd-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a4fd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a4fd-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a4fd-117">See also</span></span>

- [<span data-ttu-id="7a4fd-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7a4fd-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
