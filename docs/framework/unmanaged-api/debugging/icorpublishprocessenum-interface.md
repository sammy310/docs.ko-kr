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
ms.openlocfilehash: 188ff8feabd704d828256a09aca20f9db2227f2c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790503"
---
# <a name="icorpublishprocessenum-interface"></a><span data-ttu-id="a6f99-102">ICorPublishProcessEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6f99-102">ICorPublishProcessEnum Interface</span></span>
<span data-ttu-id="a6f99-103">[ICorPublishProcess](icorpublishprocess-interface.md) 개체의 컬렉션을 순회 하는 메서드를 제공 하는 [ICorPublishEnum](icorpublishenum-interface.md) 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a6f99-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishProcess](icorpublishprocess-interface.md) objects.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a6f99-104">메서드</span><span class="sxs-lookup"><span data-stu-id="a6f99-104">Methods</span></span>  
  
|<span data-ttu-id="a6f99-105">메서드</span><span class="sxs-lookup"><span data-stu-id="a6f99-105">Method</span></span>|<span data-ttu-id="a6f99-106">설명</span><span class="sxs-lookup"><span data-stu-id="a6f99-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a6f99-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="a6f99-107">Next Method</span></span>](icorpublishprocessenum-next-method.md)|<span data-ttu-id="a6f99-108">현재 위치에서 시작 하 여 컬렉션에서 지정 된 수의 `ICorPublishProcess` 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a6f99-108">Gets the specified number of `ICorPublishProcess` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6f99-109">주의</span><span class="sxs-lookup"><span data-stu-id="a6f99-109">Remarks</span></span>  
 <span data-ttu-id="a6f99-110">`ICorPublishProcessEnum` 인터페이스는 추상 인터페이스인 [ICorPublishEnum](icorpublishenum-interface.md)의 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f99-110">The `ICorPublishProcessEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
 <span data-ttu-id="a6f99-111">[ICorPublish:: enumprocesses](icorpublish-enumprocesses-method.md) 메서드로 `ICorPublishProcessEnum` 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a6f99-111">An `ICorPublishProcessEnum` instance is created by the [ICorPublish::EnumProcesses](icorpublish-enumprocesses-method.md) method.</span></span> <span data-ttu-id="a6f99-112">`ICorPublishProcess` 개체 컬렉션의 순회는 `ICorPublishProcessEnum` 인스턴스가 만들어질 때 지정 된 필터 조건을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f99-112">The traversal of the collection of `ICorPublishProcess` objects is based on the filter criteria given at the time the `ICorPublishProcessEnum` instance was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6f99-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a6f99-113">Requirements</span></span>  
 <span data-ttu-id="a6f99-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a6f99-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6f99-115">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="a6f99-115">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="a6f99-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6f99-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6f99-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f99-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f99-118">참조</span><span class="sxs-lookup"><span data-stu-id="a6f99-118">See also</span></span>

- [<span data-ttu-id="a6f99-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a6f99-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a6f99-120">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="a6f99-120">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
