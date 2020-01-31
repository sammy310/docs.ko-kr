---
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
ms.openlocfilehash: bd62fb38352022f69c45d2a5921973cfbec1c6e4
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790600"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="04f8f-102">ICorPublishEnum::Skip 메서드</span><span class="sxs-lookup"><span data-stu-id="04f8f-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="04f8f-103">지정 된 항목 수 만큼 열거에서 커서를 앞으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="04f8f-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04f8f-104">구문</span><span class="sxs-lookup"><span data-stu-id="04f8f-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="04f8f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="04f8f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="04f8f-106">진행 커서를 앞으로 이동 하는 기준이 되는 항목의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="04f8f-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04f8f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="04f8f-107">Requirements</span></span>  
 <span data-ttu-id="04f8f-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="04f8f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04f8f-109">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="04f8f-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="04f8f-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="04f8f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="04f8f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04f8f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04f8f-112">참조</span><span class="sxs-lookup"><span data-stu-id="04f8f-112">See also</span></span>

- [<span data-ttu-id="04f8f-113">ICorPublishEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="04f8f-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
