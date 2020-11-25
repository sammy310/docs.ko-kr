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
ms.openlocfilehash: 90bcf4f37631e0246e58cc14bfcd331d981e4713
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731724"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="97be4-102">ComCallUnmarshal Coclass</span><span class="sxs-lookup"><span data-stu-id="97be4-102">ComCallUnmarshal Coclass</span></span>

<span data-ttu-id="97be4-103">인터페이스 포인터의 마샬링을 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="97be4-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97be4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97be4-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="97be4-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="97be4-105">Interfaces</span></span>  
  
|<span data-ttu-id="97be4-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="97be4-106">Interface</span></span>|<span data-ttu-id="97be4-107">설명</span><span class="sxs-lookup"><span data-stu-id="97be4-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="97be4-108">클라이언트 프로세스에서 프록시를 만들고, 초기화 하 고, 관리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="97be4-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="97be4-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="97be4-109">Requirements</span></span>  

 <span data-ttu-id="97be4-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97be4-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97be4-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="97be4-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="97be4-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97be4-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97be4-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97be4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97be4-114">참조</span><span class="sxs-lookup"><span data-stu-id="97be4-114">See also</span></span>

- [<span data-ttu-id="97be4-115">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="97be4-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
