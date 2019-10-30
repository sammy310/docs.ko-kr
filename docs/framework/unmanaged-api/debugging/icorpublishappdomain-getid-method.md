---
title: ICorPublishAppDomain::GetID 메서드
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
ms.openlocfilehash: 33a72d9aea09f808d42d1a17a7ec5640d20d7c79
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140379"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="272f1-102">ICorPublishAppDomain::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="272f1-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="272f1-103">이 [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)에 대 한 고유 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="272f1-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="272f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="272f1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="272f1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="272f1-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="272f1-106">제한이 응용 프로그램 도메인의 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="272f1-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="272f1-107">주의</span><span class="sxs-lookup"><span data-stu-id="272f1-107">Remarks</span></span>  
 <span data-ttu-id="272f1-108">식별자는 포함 하는 프로세스의 범위 에서만 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="272f1-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="272f1-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="272f1-109">Requirements</span></span>  
 <span data-ttu-id="272f1-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="272f1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="272f1-111">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="272f1-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="272f1-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="272f1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="272f1-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="272f1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="272f1-114">참조</span><span class="sxs-lookup"><span data-stu-id="272f1-114">See also</span></span>

- [<span data-ttu-id="272f1-115">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="272f1-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
