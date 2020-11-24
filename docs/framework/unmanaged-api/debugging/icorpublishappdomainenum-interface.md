---
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
ms.openlocfilehash: 5b5a901bef779948467cfcc3d71a1fcd057c1aeb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693712"
---
# <a name="icorpublishappdomainenum-interface"></a><span data-ttu-id="257ca-102">ICorPublishAppDomainEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="257ca-102">ICorPublishAppDomainEnum Interface</span></span>

<span data-ttu-id="257ca-103">프로세스 내에 현재 존재 하는 [ICorPublishAppDomain](icorpublishappdomain-interface.md) 개체의 컬렉션을 순회 하는 메서드를 제공 하는 [ICorPublishEnum](icorpublishenum-interface.md) 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="257ca-103">A subclass of the [ICorPublishEnum](icorpublishenum-interface.md) interface that provides methods to traverse a collection of [ICorPublishAppDomain](icorpublishappdomain-interface.md) objects that currently exist within a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="257ca-104">메서드</span><span class="sxs-lookup"><span data-stu-id="257ca-104">Methods</span></span>  
  
|<span data-ttu-id="257ca-105">메서드</span><span class="sxs-lookup"><span data-stu-id="257ca-105">Method</span></span>|<span data-ttu-id="257ca-106">설명</span><span class="sxs-lookup"><span data-stu-id="257ca-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="257ca-107">Next 메서드</span><span class="sxs-lookup"><span data-stu-id="257ca-107">Next Method</span></span>](icorpublishappdomainenum-next-method.md)|<span data-ttu-id="257ca-108">`ICorPublishAppDomain`현재 위치에서 시작 하 여 컬렉션에서 지정 된 수의 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="257ca-108">Gets the specified number of `ICorPublishAppDomain` instances from the collection, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="257ca-109">설명</span><span class="sxs-lookup"><span data-stu-id="257ca-109">Remarks</span></span>  

 <span data-ttu-id="257ca-110">`ICorPublishAppDomainEnum`인터페이스는 추상 인터페이스인 [ICorPublishEnum](icorpublishenum-interface.md)의 메서드를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="257ca-110">The `ICorPublishAppDomainEnum` interface implements the methods of the abstract interface, [ICorPublishEnum](icorpublishenum-interface.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="257ca-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="257ca-111">Requirements</span></span>  

 <span data-ttu-id="257ca-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="257ca-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="257ca-113">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="257ca-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="257ca-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="257ca-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="257ca-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="257ca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="257ca-116">참조</span><span class="sxs-lookup"><span data-stu-id="257ca-116">See also</span></span>

- [<span data-ttu-id="257ca-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="257ca-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="257ca-118">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="257ca-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
