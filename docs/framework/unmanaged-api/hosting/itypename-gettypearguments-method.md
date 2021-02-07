---
description: '자세히 알아보기: ITypeName:: GetTypeArguments 메서드'
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
ms.openlocfilehash: b88ffcfb856905bf891ebeafa1e6dbeda2563aaf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753663"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="7400e-103">ITypeName::GetTypeArguments 메서드</span><span class="sxs-lookup"><span data-stu-id="7400e-103">ITypeName::GetTypeArguments Method</span></span>

<span data-ttu-id="7400e-104">이 메서드는 .NET Framework 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7400e-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7400e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7400e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="7400e-106">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7400e-106">Requirements</span></span>  

 <span data-ttu-id="7400e-107">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7400e-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7400e-108">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="7400e-108">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7400e-109">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7400e-109">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7400e-110">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7400e-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7400e-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7400e-111">See also</span></span>

- [<span data-ttu-id="7400e-112">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7400e-112">Hosting Interfaces</span></span>](hosting-interfaces.md)
