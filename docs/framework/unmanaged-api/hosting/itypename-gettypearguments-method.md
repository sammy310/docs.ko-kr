---
title: ITypeName::GetTypeArguments 메서드
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
ms.openlocfilehash: ac835459f88655377d96699e6aea0e877218c8fb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125279"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="2facd-102">ITypeName::GetTypeArguments 메서드</span><span class="sxs-lookup"><span data-stu-id="2facd-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="2facd-103">이 메서드는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="2facd-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2facd-104">구문</span><span class="sxs-lookup"><span data-stu-id="2facd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2facd-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2facd-105">Requirements</span></span>  
 <span data-ttu-id="2facd-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2facd-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2facd-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="2facd-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2facd-108">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2facd-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2facd-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2facd-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2facd-110">참조</span><span class="sxs-lookup"><span data-stu-id="2facd-110">See also</span></span>

- [<span data-ttu-id="2facd-111">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2facd-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
