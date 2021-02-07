---
description: '자세한 정보: GetAppIdAuthority 함수'
title: GetAppIdAuthority 함수
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
ms.openlocfilehash: a0c2a7b754c2b014b189f96fd3c27347571cc0d1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761072"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="dff7c-103">GetAppIdAuthority 함수</span><span class="sxs-lookup"><span data-stu-id="dff7c-103">GetAppIdAuthority Function</span></span>

<span data-ttu-id="dff7c-104">응용 프로그램 id 및 참조에 대 한 키를 관리 하는 [Iappidauthority](iappidauthority-interface.md) 인스턴스에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dff7c-104">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dff7c-105">구문</span><span class="sxs-lookup"><span data-stu-id="dff7c-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="dff7c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dff7c-106">Parameters</span></span>  

 `ppIAppIdAuthority`  
 <span data-ttu-id="dff7c-107">제한이 반환 된 `IAppIdAuthority` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dff7c-107">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dff7c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dff7c-108">Requirements</span></span>  

 <span data-ttu-id="dff7c-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dff7c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dff7c-110">**헤더:** 격리. h</span><span class="sxs-lookup"><span data-stu-id="dff7c-110">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="dff7c-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dff7c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dff7c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dff7c-112">See also</span></span>

- [<span data-ttu-id="dff7c-113">IAppIdAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dff7c-113">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="dff7c-114">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="dff7c-114">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
