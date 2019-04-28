---
title: ICorThreadpool::CorDeleteTimer 메서드
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorDeleteTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeleteTimer
helpviewer_keywords:
- ICorThreadpool::CorDeleteTimer method [.NET Framework hosting]
- CorDeleteTimer method [.NET Framework hosting]
ms.assetid: 74847c35-7ca1-466a-b750-b25e7b03d100
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 098c23dd0ddff4342aa4cefbaa4e149ed95a1cb3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700074"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="a82f8-102">ICorThreadpool::CorDeleteTimer 메서드</span><span class="sxs-lookup"><span data-stu-id="a82f8-102">ICorThreadpool::CorDeleteTimer Method</span></span>
<span data-ttu-id="a82f8-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a82f8-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a82f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="a82f8-104">Syntax</span></span>  
  
```  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a82f8-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a82f8-105">Requirements</span></span>  
 <span data-ttu-id="a82f8-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a82f8-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a82f8-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a82f8-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a82f8-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a82f8-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a82f8-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a82f8-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a82f8-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="a82f8-110">See also</span></span>

- [<span data-ttu-id="a82f8-111">ICorThreadpool 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a82f8-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
