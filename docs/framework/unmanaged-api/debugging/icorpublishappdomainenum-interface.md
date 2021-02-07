---
description: '자세히 알아보기: ICorPublishAppDomainEnum 인터페이스'
title: ICorPublishAppDomainEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomainEnum
helpviewer_keywords:
- ICorPublishAppDomainEnum interface [.NET Framework debugging]
ms.assetid: bb798c56-042e-475d-a245-b6fac36d0c07
topic_type:
- apiref
ms.openlocfilehash: 4e84af576103a792308fd44f903f2ae4daa5d736
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721790"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="e6021-103">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6021-103">ICorPublishAppDomainEnum Interface</span></span>

<span data-ttu-id="e6021-104">프로세스 내에 현재 존재 하는 [ICorPublishAppDomain](icorpublishappdomain-interface.md) 개체의 컬렉션을 순회 하는 메서드를 제공 하는 [ICorPublishEnum](icorpublishenum-interface.md) 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6021-104">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e6021-105">메서드</span><span class="sxs-lookup"><span data-stu-id="e6021-105">Methods</span></span>  
  
|<span data-ttu-id="e6021-106">메서드</span><span class="sxs-lookup"><span data-stu-id="e6021-106">Method</span></span>|<span data-ttu-id="e6021-107">설명</span><span class="sxs-lookup"><span data-stu-id="e6021-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e6021-108">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="e6021-108">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="e6021-109">`ICorPublishAppDomain`현재 위치에서 시작 하 여 컬렉션에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e6021-109">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e6021-110">설명</span><span class="sxs-lookup"><span data-stu-id="e6021-110">Remarks</span></span>  

 <span data-ttu-id="e6021-111">`ICorPublishAppDomainEnum`인터페이스는 추상 인터페이스인 [ICorPublishEnum](icorpublishenum-interface.md)의 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6021-111">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6021-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e6021-112">Requirements</span></span>  

 <span data-ttu-id="e6021-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6021-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6021-114">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="e6021-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="e6021-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6021-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6021-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6021-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6021-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e6021-117">See also</span></span>

- [<span data-ttu-id="e6021-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e6021-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="e6021-119">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="e6021-119">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
