---
description: '자세히 알아보기: ICorPublishEnum:: GetCount 메서드'
title: ICorPublishEnum::GetCount 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::GetCount
helpviewer_keywords:
- GetCount method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::GetCount method [.NET Framework debugging]
ms.assetid: d228f684-2be3-4029-93ae-31fe02213c1f
topic_type:
- apiref
ms.openlocfilehash: 99e831ae366604e2ae7494bf80fb2e7f25532582
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721621"
---
# <a name="icorpublishenumgetcount-method"></a><span data-ttu-id="2a548-103">ICorPublishEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="2a548-103">ICorPublishEnum::GetCount Method</span></span>

<span data-ttu-id="2a548-104">열거형의 항목 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2a548-104">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a548-105">구문</span><span class="sxs-lookup"><span data-stu-id="2a548-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG   *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a548-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2a548-106">Parameters</span></span>  

 `pcelt`  
 <span data-ttu-id="2a548-107">제한이 열거형의 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2a548-107">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a548-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a548-108">Requirements</span></span>  

 <span data-ttu-id="2a548-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a548-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a548-110">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="2a548-110">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2a548-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2a548-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2a548-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a548-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a548-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a548-113">See also</span></span>

- [<span data-ttu-id="2a548-114">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a548-114">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
