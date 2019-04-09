---
title: ITypeName::GetNames 메서드
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28076a36880febad20d457ff5a6b290de3d6f173
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121552"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="bde1e-102">ITypeName::GetNames 메서드</span><span class="sxs-lookup"><span data-stu-id="bde1e-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="bde1e-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bde1e-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bde1e-104">구문</span><span class="sxs-lookup"><span data-stu-id="bde1e-104">Syntax</span></span>  
  
```  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="bde1e-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bde1e-105">Requirements</span></span>  
 <span data-ttu-id="bde1e-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bde1e-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bde1e-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bde1e-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bde1e-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="bde1e-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="bde1e-109">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="bde1e-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bde1e-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="bde1e-110">See also</span></span>

- [<span data-ttu-id="bde1e-111">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bde1e-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
