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
ms.openlocfilehash: 0ff088731514b2da0d8b1fa51ef48d8b71d16528
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842233"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="a00a5-102">IObjectHandle::Unwrap 메서드</span><span class="sxs-lookup"><span data-stu-id="a00a5-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="a00a5-103">의 래핑을 해제에서 값으로 마샬링하는 개체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a00a5-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a00a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="a00a5-104">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a00a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a00a5-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="a00a5-106">제한이 래핑을 해제할 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a00a5-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a00a5-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a00a5-107">Requirements</span></span>  
 <span data-ttu-id="a00a5-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a00a5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a00a5-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="a00a5-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a00a5-110">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a00a5-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a00a5-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a00a5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
