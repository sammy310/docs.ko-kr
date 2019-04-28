---
title: IObjectHandle::Unwrap 메서드
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4c18607d5373b415228846350a3dd0637ade1b45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917594"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="015c7-102">IObjectHandle::Unwrap 메서드</span><span class="sxs-lookup"><span data-stu-id="015c7-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="015c7-103">간접 참조의 값으로 마샬링된 개체를 래핑 해제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="015c7-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="015c7-104">구문</span><span class="sxs-lookup"><span data-stu-id="015c7-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="015c7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="015c7-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="015c7-106">[out] 래핑 해제할 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="015c7-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="015c7-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="015c7-107">Requirements</span></span>  
 <span data-ttu-id="015c7-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="015c7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="015c7-109">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="015c7-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="015c7-110">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="015c7-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="015c7-111">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="015c7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
