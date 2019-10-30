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
ms.openlocfilehash: 38f3140a181deae1a86569bfc2eb7cf3cd7d1991
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131925"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="9e93f-102">ComCallUnmarshal Coclass</span><span class="sxs-lookup"><span data-stu-id="9e93f-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="9e93f-103">인터페이스 포인터의 마샬링을 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e93f-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e93f-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e93f-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="9e93f-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e93f-105">Interfaces</span></span>  
  
|<span data-ttu-id="9e93f-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e93f-106">Interface</span></span>|<span data-ttu-id="9e93f-107">설명</span><span class="sxs-lookup"><span data-stu-id="9e93f-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="9e93f-108">클라이언트 프로세스에서 프록시를 만들고, 초기화 하 고, 관리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e93f-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9e93f-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e93f-109">Requirements</span></span>  
 <span data-ttu-id="9e93f-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e93f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e93f-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9e93f-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="9e93f-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e93f-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e93f-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e93f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e93f-114">참조</span><span class="sxs-lookup"><span data-stu-id="9e93f-114">See also</span></span>

- [<span data-ttu-id="9e93f-115">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="9e93f-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
