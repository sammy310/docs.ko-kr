---
description: '자세히 알아보기: ICorPublishEnum:: Skip 메서드'
title: ICorPublishEnum::Skip 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
ms.openlocfilehash: f0124681c8051a5c05c1caf3edd06c697da486e5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794603"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="71cd5-103">ICorPublishEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="71cd5-103">ICorPublishEnum::Skip Method</span></span>

<span data-ttu-id="71cd5-104">지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="71cd5-104">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71cd5-105">구문</span><span class="sxs-lookup"><span data-stu-id="71cd5-105">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71cd5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71cd5-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="71cd5-107">진행 커서를 앞으로 이동 하는 기준이 되는 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="71cd5-107">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71cd5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="71cd5-108">Requirements</span></span>  

 <span data-ttu-id="71cd5-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71cd5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71cd5-110">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="71cd5-110">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="71cd5-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="71cd5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="71cd5-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71cd5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71cd5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71cd5-113">See also</span></span>

- [<span data-ttu-id="71cd5-114">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="71cd5-114">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
