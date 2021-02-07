---
description: '자세히 알아보기: ICorPublishEnum 인터페이스'
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
ms.openlocfilehash: c0d50f67bd61eecbade0b226f2f569ac26712faf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721605"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="c9c4b-103">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9c4b-103">ICorPublishEnum Interface</span></span>

<span data-ttu-id="c9c4b-104">프로세스 및 응용 프로그램 도메인에 대 한 정보를 게시 하는 데 사용 되는 열거자에 대 한 추상 기본 인터페이스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9c4b-104">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c9c4b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="c9c4b-105">Methods</span></span>  
  
|<span data-ttu-id="c9c4b-106">메서드</span><span class="sxs-lookup"><span data-stu-id="c9c4b-106">Method</span></span>|<span data-ttu-id="c9c4b-107">설명</span><span class="sxs-lookup"><span data-stu-id="c9c4b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c9c4b-108">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="c9c4b-108">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="c9c4b-109">이 `ICorPublishEnum` 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9c4b-109">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="c9c4b-110">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="c9c4b-110">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="c9c4b-111">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c9c4b-111">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="c9c4b-112">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="c9c4b-112">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="c9c4b-113">커서를 열거형의 시작 부분으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9c4b-113">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="c9c4b-114">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="c9c4b-114">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="c9c4b-115">지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9c4b-115">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c9c4b-116">설명</span><span class="sxs-lookup"><span data-stu-id="c9c4b-116">Remarks</span></span>  

 <span data-ttu-id="c9c4b-117">다음 열거자는에서 파생 됩니다 `ICorPublishEnum` .</span><span class="sxs-lookup"><span data-stu-id="c9c4b-117">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="c9c4b-118">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="c9c4b-118">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="c9c4b-119">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="c9c4b-119">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="c9c4b-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9c4b-120">Requirements</span></span>  

 <span data-ttu-id="c9c4b-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c9c4b-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9c4b-122">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="c9c4b-122">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c9c4b-123">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c9c4b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9c4b-124">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9c4b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c4b-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9c4b-125">See also</span></span>

- [<span data-ttu-id="c9c4b-126">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="c9c4b-126">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="c9c4b-127">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9c4b-127">Debugging Interfaces</span></span>](debugging-interfaces.md)
