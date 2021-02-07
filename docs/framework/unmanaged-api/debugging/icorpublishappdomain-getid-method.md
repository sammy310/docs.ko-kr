---
description: '자세히 알아보기: ICorPublishAppDomain:: GetID 메서드'
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
ms.openlocfilehash: b3de19c053b5fcce2af5e0036ee6174b01700aac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721842"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="cb9c2-103">ICorPublishAppDomain::GetID 메서드</span><span class="sxs-lookup"><span data-stu-id="cb9c2-103">ICorPublishAppDomain::GetID Method</span></span>

<span data-ttu-id="cb9c2-104">이 [ICorPublishAppDomain](icorpublishappdomain-interface.md)에 대 한 고유 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="cb9c2-104">Gets the unique identifier for this [ICorPublishAppDomain](icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb9c2-105">구문</span><span class="sxs-lookup"><span data-stu-id="cb9c2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb9c2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cb9c2-106">Parameters</span></span>  

 `puId`  
 <span data-ttu-id="cb9c2-107">제한이 응용 프로그램 도메인의 식별자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="cb9c2-107">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cb9c2-108">설명</span><span class="sxs-lookup"><span data-stu-id="cb9c2-108">Remarks</span></span>  

 <span data-ttu-id="cb9c2-109">식별자는 포함 하는 프로세스의 범위 에서만 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb9c2-109">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb9c2-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cb9c2-110">Requirements</span></span>  

 <span data-ttu-id="cb9c2-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cb9c2-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb9c2-112">**헤더:** CorPub .idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="cb9c2-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cb9c2-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb9c2-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb9c2-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb9c2-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb9c2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb9c2-115">See also</span></span>

- [<span data-ttu-id="cb9c2-116">ICorPublishAppDomain 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cb9c2-116">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)
