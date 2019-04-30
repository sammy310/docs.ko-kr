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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5186df61eb82b29fcfa9776408498b748068e122
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993484"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="ea8e4-102">ICorPublishProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea8e4-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="ea8e4-103">서브 클래스는 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) 의 컬렉션을 이동 하는 메서드를 제공 하는 인터페이스 [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e4-103">A subclass of the [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ea8e4-104">메서드</span><span class="sxs-lookup"><span data-stu-id="ea8e4-104">Methods</span></span>  
  
|<span data-ttu-id="ea8e4-105">메서드</span><span class="sxs-lookup"><span data-stu-id="ea8e4-105">Method</span></span>|<span data-ttu-id="ea8e4-106">설명</span><span class="sxs-lookup"><span data-stu-id="ea8e4-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ea8e4-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="ea8e4-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-next-method.md)|<span data-ttu-id="ea8e4-108">지정 된 수를 가져옵니다 `ICorPublishProcess` 현재 위치부터 컬렉션의 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="ea8e4-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ea8e4-109">설명</span><span class="sxs-lookup"><span data-stu-id="ea8e4-109">Remarks</span></span>  
 <span data-ttu-id="ea8e4-110">합니다 `ICorPublishProcessEnum` 추상 인터페이스의 메서드를 구현 하는 인터페이스 [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e4-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="ea8e4-111">`ICorPublishProcessEnum` 하 여 인스턴스가 생성 되는 [icorpublish:: Enumprocesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="ea8e4-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](../../../../docs/framework/unmanaged-api/debugging/icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="ea8e4-112">컬렉션의 순회 `ICorPublishProcess` 개체는 시간에 지정 된 필터 조건에 따라는 `ICorPublishProcessEnum` 인스턴스를 만든 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea8e4-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea8e4-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ea8e4-113">Requirements</span></span>  
 <span data-ttu-id="ea8e4-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ea8e4-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea8e4-115">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="ea8e4-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ea8e4-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ea8e4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ea8e4-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea8e4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea8e4-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="ea8e4-118">See also</span></span>

- [<span data-ttu-id="ea8e4-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ea8e4-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="ea8e4-120">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="ea8e4-120">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
