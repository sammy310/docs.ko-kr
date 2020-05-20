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
ms.openlocfilehash: acbc37d0f49af21c60ff6989932c5d341673512b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421178"
---
# <a name="icorpublishenum-interface"></a><span data-ttu-id="5a465-102">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a465-102">ICorPublishEnum Interface</span></span>
<span data-ttu-id="5a465-103">프로세스 및 응용 프로그램 도메인에 대 한 정보를 게시 하는 데 사용 되는 열거자에 대 한 추상 기본 인터페이스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a465-103">Serves as the abstract base interface for the enumerators that are used in the publishing of information about processes and application domains.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5a465-104">메서드</span><span class="sxs-lookup"><span data-stu-id="5a465-104">Methods</span></span>  
  
|<span data-ttu-id="5a465-105">메서드</span><span class="sxs-lookup"><span data-stu-id="5a465-105">Method</span></span>|<span data-ttu-id="5a465-106">설명</span><span class="sxs-lookup"><span data-stu-id="5a465-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5a465-107">Clone 메서드</span><span class="sxs-lookup"><span data-stu-id="5a465-107">Clone Method</span></span>](icorpublishenum-clone-method.md)|<span data-ttu-id="5a465-108">이 `ICorPublishEnum` 개체의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5a465-108">Creates a copy of this `ICorPublishEnum` object.</span></span>|  
|[<span data-ttu-id="5a465-109">GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="5a465-109">GetCount Method</span></span>](icorpublishenum-getcount-method.md)|<span data-ttu-id="5a465-110">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5a465-110">Gets the number of items in the enumeration.</span></span>|  
|[<span data-ttu-id="5a465-111">Reset 메서드</span><span class="sxs-lookup"><span data-stu-id="5a465-111">Reset Method</span></span>](icorpublishenum-reset-method.md)|<span data-ttu-id="5a465-112">커서를 열거형의 시작 부분으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a465-112">Moves the cursor of to the beginning of the enumeration.</span></span>|  
|[<span data-ttu-id="5a465-113">Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="5a465-113">Skip Method</span></span>](icorpublishenum-skip-method.md)|<span data-ttu-id="5a465-114">지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a465-114">Moves the cursor forward in the enumeration by the specified number of items.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a465-115">설명</span><span class="sxs-lookup"><span data-stu-id="5a465-115">Remarks</span></span>  
 <span data-ttu-id="5a465-116">다음 열거자는에서 파생 됩니다 `ICorPublishEnum` .</span><span class="sxs-lookup"><span data-stu-id="5a465-116">The following enumerators derive from `ICorPublishEnum`:</span></span>  
  
- [<span data-ttu-id="5a465-117">ICorPublishAppDomainEnum</span><span class="sxs-lookup"><span data-stu-id="5a465-117">ICorPublishAppDomainEnum</span></span>](icorpublishappdomainenum-interface.md)  
  
- [<span data-ttu-id="5a465-118">ICorPublishProcessEnum</span><span class="sxs-lookup"><span data-stu-id="5a465-118">ICorPublishProcessEnum</span></span>](icorpublishprocessenum-interface.md)  
  
## <a name="requirements"></a><span data-ttu-id="5a465-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5a465-119">Requirements</span></span>  
 <span data-ttu-id="5a465-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5a465-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a465-121">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="5a465-121">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5a465-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a465-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a465-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a465-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a465-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5a465-124">See also</span></span>

- [<span data-ttu-id="5a465-125">CorpubPublish Coclass</span><span class="sxs-lookup"><span data-stu-id="5a465-125">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
- [<span data-ttu-id="5a465-126">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5a465-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
