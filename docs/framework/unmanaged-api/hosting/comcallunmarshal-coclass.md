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
ms.openlocfilehash: 939acc0ad47021d5fdffe7b7b71ea6a4a1635a6d
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616738"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="4f2b2-102">ComCallUnmarshal Coclass</span><span class="sxs-lookup"><span data-stu-id="4f2b2-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="4f2b2-103">인터페이스 포인터의 마샬링을 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2b2-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f2b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="4f2b2-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="4f2b2-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f2b2-105">Interfaces</span></span>  
  
|<span data-ttu-id="4f2b2-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f2b2-106">Interface</span></span>|<span data-ttu-id="4f2b2-107">설명</span><span class="sxs-lookup"><span data-stu-id="4f2b2-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="4f2b2-108">클라이언트 프로세스에서 프록시를 만들고, 초기화 하 고, 관리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f2b2-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f2b2-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f2b2-109">Requirements</span></span>  
 <span data-ttu-id="4f2b2-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f2b2-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f2b2-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="4f2b2-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="4f2b2-112">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4f2b2-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4f2b2-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f2b2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f2b2-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f2b2-114">See also</span></span>

- [<span data-ttu-id="4f2b2-115">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="4f2b2-115">Hosting Coclasses</span></span>](hosting-coclasses.md)
