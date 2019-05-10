---
title: ICorPublishEnum 인터페이스
ms.date: 03/30/2017
api_name:
- ICorPublishEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum
helpviewer_keywords:
- ICorPublishEnum interface [.NET Framework debugging]
ms.assetid: 76a136b5-e444-417a-8ade-f1596d597dc7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5509dd07bbb6c812a7ea2797c46002aaa161c46
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619960"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="62909-102">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62909-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="62909-103">프로세스 및 응용 프로그램 도메인에 대 한 정보를 게시에 사용 되는 열거자에 대 한 추상 기본 인터페이스로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="62909-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62909-104">메서드</span><span class="sxs-lookup"><span data-stu-id="62909-104">Methods</span></span>  
  
|<span data-ttu-id="62909-105">메서드</span><span class="sxs-lookup"><span data-stu-id="62909-105">Method</span></span>|<span data-ttu-id="62909-106">설명</span><span class="sxs-lookup"><span data-stu-id="62909-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62909-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="62909-107">Clone Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-clone-method.md)|<span data-ttu-id="62909-108">이 복사본을 만들고 `ICorPublishEnum` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="62909-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="62909-109">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="62909-109">GetCount Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-getcount-method.md)|<span data-ttu-id="62909-110">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="62909-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="62909-111">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="62909-111">Reset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-reset-method.md)|<span data-ttu-id="62909-112">열거형의 시작 부분에 커서를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="62909-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="62909-113">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="62909-113">Skip Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-skip-method.md)|<span data-ttu-id="62909-114">열거형에서 항목의 지정된 된 수 만큼 앞으로 커서를 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="62909-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62909-115">설명</span><span class="sxs-lookup"><span data-stu-id="62909-115">Remarks</span></span>  
 <span data-ttu-id="62909-116">파생 되는 다음 열거자 `ICorPublishEnum`:</span><span class="sxs-lookup"><span data-stu-id="62909-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="62909-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="62909-117">ICorPublishAppDomainEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="62909-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="62909-118">ICorPublishProcessEnum</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="62909-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62909-119">Requirements</span></span>  
 <span data-ttu-id="62909-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="62909-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62909-121">**헤더:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="62909-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="62909-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62909-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62909-123">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62909-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62909-124">참고자료</span><span class="sxs-lookup"><span data-stu-id="62909-124">See also</span></span>

- [<span data-ttu-id="62909-125">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="62909-125">CorpubPublish Coclass</span></span>](../../../../docs/framework/unmanaged-api/debugging/corpubpublish-coclass.md)
- [<span data-ttu-id="62909-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62909-126">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
