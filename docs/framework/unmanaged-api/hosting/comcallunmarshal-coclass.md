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
ms.openlocfilehash: 2f17a88a90905006432ae8c5dc040277124c947b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697292"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="5d276-102">ComCallUnmarshal Coclass</span><span class="sxs-lookup"><span data-stu-id="5d276-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="5d276-103">인터페이스 포인터의 마샬링을 관리에 대 한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d276-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d276-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d276-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="5d276-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d276-105">Interfaces</span></span>  
  
|<span data-ttu-id="5d276-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d276-106">Interface</span></span>|<span data-ttu-id="5d276-107">설명</span><span class="sxs-lookup"><span data-stu-id="5d276-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="5d276-108">만들기, 초기화 및 관리 클라이언트 프로세스에서 프록시에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d276-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d276-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d276-109">Requirements</span></span>  
 <span data-ttu-id="5d276-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5d276-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d276-111">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="5d276-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="5d276-112">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="5d276-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d276-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d276-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d276-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d276-114">See also</span></span>

- [<span data-ttu-id="5d276-115">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="5d276-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
