---
title: ICorPublishProcessEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublishProcessEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcessEnum
helpviewer_keywords:
- ICorPublishProcessEnum interface [.NET Framework debugging]
ms.assetid: aac8fcf9-ac09-437c-bd5c-2fda14ae1007
topic_type:
- apiref
ms.openlocfilehash: 3a7267548a957d403cfe02aa3d800a410c14b82a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103426"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="10c2b-102">ICorPublishProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10c2b-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="10c2b-103">[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 개체의 컬렉션을 순회 하는 메서드를 제공 하는 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="10c2b-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="10c2b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="10c2b-104">Methods</span></span>  
  
|<span data-ttu-id="10c2b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="10c2b-105">Method</span></span>|<span data-ttu-id="10c2b-106">설명</span><span class="sxs-lookup"><span data-stu-id="10c2b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="10c2b-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="10c2b-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="10c2b-108">현재 위치에서 시작 하 여 컬렉션에서 지정 된 수의 `ICorPublishProcess` 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="10c2b-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10c2b-109">주의</span><span class="sxs-lookup"><span data-stu-id="10c2b-109">Remarks</span></span>  
 <span data-ttu-id="10c2b-110">`ICorPublishProcessEnum` 인터페이스는 추상 인터페이스인 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)의 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="10c2b-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="10c2b-111">[ICorPublish:: enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) 메서드로 `ICorPublishProcessEnum` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10c2b-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="10c2b-112">`ICorPublishProcess` 개체 컬렉션의 순회는 `ICorPublishProcessEnum` 인스턴스가 만들어질 때 지정 된 필터 조건을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="10c2b-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10c2b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="10c2b-113">Requirements</span></span>  
 <span data-ttu-id="10c2b-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10c2b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10c2b-115">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="10c2b-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="10c2b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10c2b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10c2b-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10c2b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10c2b-118">참조</span><span class="sxs-lookup"><span data-stu-id="10c2b-118">See also</span></span>

- [<span data-ttu-id="10c2b-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="10c2b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="10c2b-120">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="10c2b-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
