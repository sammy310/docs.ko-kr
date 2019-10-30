---
title: ITypeName::GetAssemblyName 메서드
ms.date: 03/30/2017
api_name:
- ITypeName.GetAssemblyName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetAssemblyName
helpviewer_keywords:
- ITypeName::GetAssemblyName method [.NET Framework hosting]
- GetAssemblyName method [.NET Framework hosting]
ms.assetid: 97801d99-f5f1-4a30-882f-959827093fac
topic_type:
- apiref
ms.openlocfilehash: de89f20842ab505e40ee0e9795774a92a7d5f1a9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102665"
---
# <a name="itypenamegetassemblyname-method"></a><span data-ttu-id="c996c-102">ITypeName::GetAssemblyName 메서드</span><span class="sxs-lookup"><span data-stu-id="c996c-102">ITypeName::GetAssemblyName Method</span></span>
<span data-ttu-id="c996c-103">이 메서드는 .NET Framework 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c996c-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c996c-104">구문</span><span class="sxs-lookup"><span data-stu-id="c996c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyName (  
    [out, retval] BSTR* rgbszAssemblyNames  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c996c-105">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c996c-105">Requirements</span></span>  
 <span data-ttu-id="c996c-106">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c996c-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c996c-107">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="c996c-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c996c-108">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c996c-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c996c-109">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c996c-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c996c-110">참조</span><span class="sxs-lookup"><span data-stu-id="c996c-110">See also</span></span>

- [<span data-ttu-id="c996c-111">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c996c-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
