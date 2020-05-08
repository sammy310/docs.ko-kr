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
ms.openlocfilehash: bece1be7474c57d38f083e322c2af1b0ba705ee9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894763"
---
# <a name="icordebugboxvalue-interface"></a><span data-ttu-id="a7466-102">ICorDebugBoxValue 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7466-102">ICorDebugBoxValue Interface</span></span>

<span data-ttu-id="a7466-103">Boxed 값 클래스 개체를 나타내는 "ICorDebugHeapValue"의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a7466-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7466-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a7466-104">Methods</span></span>  
  
|<span data-ttu-id="a7466-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a7466-105">Method</span></span>|<span data-ttu-id="a7466-106">설명</span><span class="sxs-lookup"><span data-stu-id="a7466-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7466-107">GetObject 메서드</span><span class="sxs-lookup"><span data-stu-id="a7466-107">GetObject Method</span></span>](icordebugboxvalue-getobject-method.md)|<span data-ttu-id="a7466-108">Boxed "ICorDebugObjectValue" 인스턴스에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a7466-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7466-109">설명</span><span class="sxs-lookup"><span data-stu-id="a7466-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a7466-110">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a7466-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7466-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7466-111">Requirements</span></span>  
 <span data-ttu-id="a7466-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7466-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7466-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7466-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7466-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7466-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7466-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7466-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7466-116">참조</span><span class="sxs-lookup"><span data-stu-id="a7466-116">See also</span></span>

- [<span data-ttu-id="a7466-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7466-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
