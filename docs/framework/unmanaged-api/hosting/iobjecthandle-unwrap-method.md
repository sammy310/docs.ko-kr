---
description: '자세히 알아보기: IObjectHandle:: 래핑 해제 메서드'
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
ms.openlocfilehash: 3f791eaf52abd045d495fe15e868423e464fd27e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728329"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="2abd6-103">IObjectHandle::Unwrap 메서드</span><span class="sxs-lookup"><span data-stu-id="2abd6-103">IObjectHandle::Unwrap Method</span></span>

<span data-ttu-id="2abd6-104">의 래핑을 해제에서 값으로 마샬링하는 개체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2abd6-104">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2abd6-105">구문</span><span class="sxs-lookup"><span data-stu-id="2abd6-105">Syntax</span></span>  
  
```cpp  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2abd6-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2abd6-106">Parameters</span></span>  

 `ppv`  
 <span data-ttu-id="2abd6-107">제한이 래핑을 해제할 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2abd6-107">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2abd6-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2abd6-108">Requirements</span></span>  

 <span data-ttu-id="2abd6-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2abd6-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2abd6-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2abd6-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2abd6-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2abd6-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2abd6-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2abd6-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
