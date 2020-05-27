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
ms.openlocfilehash: e059cdddef7926c1359a83bc562146203724aa60
ms.sourcegitcommit: e5772b3ddcc114c80b4c9767ffdb3f6c7fad8f05
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/26/2020
ms.locfileid: "83842117"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="aea84-102">ITypeName::GetTypeArguments 메서드</span><span class="sxs-lookup"><span data-stu-id="aea84-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="aea84-103">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aea84-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aea84-104">구문</span><span class="sxs-lookup"><span data-stu-id="aea84-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="aea84-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aea84-105">Requirements</span></span>  
 <span data-ttu-id="aea84-106">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aea84-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aea84-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="aea84-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aea84-108">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aea84-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aea84-109">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aea84-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea84-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aea84-110">See also</span></span>

- [<span data-ttu-id="aea84-111">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aea84-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
