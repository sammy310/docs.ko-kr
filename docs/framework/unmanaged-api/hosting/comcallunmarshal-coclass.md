---
title: ComCallUnmarshal Coclass
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fde42e3ecfac81a168920bc152833be7ba72b995
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779089"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="c71ad-102">ComCallUnmarshal Coclass</span><span class="sxs-lookup"><span data-stu-id="c71ad-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="c71ad-103">인터페이스 포인터의 마샬링을 관리에 대 한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71ad-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c71ad-104">구문</span><span class="sxs-lookup"><span data-stu-id="c71ad-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="c71ad-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="c71ad-105">Interfaces</span></span>  
  
|<span data-ttu-id="c71ad-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="c71ad-106">Interface</span></span>|<span data-ttu-id="c71ad-107">설명</span><span class="sxs-lookup"><span data-stu-id="c71ad-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="c71ad-108">만들기, 초기화 및 관리 클라이언트 프로세스에서 프록시에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c71ad-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c71ad-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c71ad-109">Requirements</span></span>  
 <span data-ttu-id="c71ad-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c71ad-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c71ad-111">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="c71ad-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="c71ad-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c71ad-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c71ad-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c71ad-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c71ad-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c71ad-114">See also</span></span>

- [<span data-ttu-id="c71ad-115">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="c71ad-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
