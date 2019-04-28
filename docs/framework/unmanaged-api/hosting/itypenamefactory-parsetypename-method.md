---
title: ITypeNameFactory::ParseTypeName 메서드
ms.date: 03/30/2017
api_name:
- ITypeNameFactory.ParseTypeName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ParseTypeName
helpviewer_keywords:
- ITypeNameFactory::ParseTypeName method [.NET Framework hosting]
- ParseTypeName method [.NET Framework hosting]
ms.assetid: 13c9f063-371c-4911-a5e7-e1e0b88ae382
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbe5f634a5d0580c7e58b03f318da98a0112fa6b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765368"
---
# <a name="itypenamefactoryparsetypename-method"></a><span data-ttu-id="8a4ba-102">ITypeNameFactory::ParseTypeName 메서드</span><span class="sxs-lookup"><span data-stu-id="8a4ba-102">ITypeNameFactory::ParseTypeName Method</span></span>
<span data-ttu-id="8a4ba-103">이 메서드는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a4ba-104">구문</span><span class="sxs-lookup"><span data-stu-id="8a4ba-104">Syntax</span></span>  
  
```  
HRESULT ParseTypeName (  
    [in]  LPCWSTR             szName,  
    [out] DWORD*              pError,  
    [out, retval] ITypeName** ppTypeName  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8a4ba-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a4ba-105">Requirements</span></span>  
 <span data-ttu-id="8a4ba-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8a4ba-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a4ba-107">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a4ba-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a4ba-108">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8a4ba-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a4ba-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a4ba-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a4ba-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="8a4ba-110">See also</span></span>

- [<span data-ttu-id="8a4ba-111">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a4ba-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
