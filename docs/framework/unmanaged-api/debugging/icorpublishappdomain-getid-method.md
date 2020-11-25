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
ms.openlocfilehash: ab331145a8147e8830cb9b158a1975bc748c7cce
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716865"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="efb79-102">ICorPublishAppDomain::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="efb79-102">ICorPublishAppDomain::GetID Method</span></span>

<span data-ttu-id="efb79-103">이 [ICorPublishAppDomain](icorpublishappdomain-interface.md)에 대 한 고유 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="efb79-103">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efb79-104">구문</span><span class="sxs-lookup"><span data-stu-id="efb79-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="efb79-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="efb79-105">Parameters</span></span>  

 `puId`  
 <span data-ttu-id="efb79-106">제한이 응용 프로그램 도메인의 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="efb79-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="efb79-107">설명</span><span class="sxs-lookup"><span data-stu-id="efb79-107">Remarks</span></span>  

 <span data-ttu-id="efb79-108">식별자는 포함 하는 프로세스의 범위 에서만 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb79-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efb79-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="efb79-109">Requirements</span></span>  

 <span data-ttu-id="efb79-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb79-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efb79-111">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="efb79-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="efb79-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efb79-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efb79-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efb79-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efb79-114">참조</span><span class="sxs-lookup"><span data-stu-id="efb79-114">See also</span></span>

- [<span data-ttu-id="efb79-115">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="efb79-115">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
