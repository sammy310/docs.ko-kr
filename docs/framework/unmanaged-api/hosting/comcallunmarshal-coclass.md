---
description: '자세히 알아보기: ComCallUnmarshal Coclass'
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
ms.openlocfilehash: 508c1183e2862a286e9db0390bc0348629a9db8e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799839"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="3d526-103">ComCallUnmarshal Coclass</span><span class="sxs-lookup"><span data-stu-id="3d526-103">ComCallUnmarshal Coclass</span></span>

<span data-ttu-id="3d526-104">인터페이스 포인터의 마샬링을 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d526-104">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d526-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d526-105">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="3d526-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d526-106">Interfaces</span></span>  
  
|<span data-ttu-id="3d526-107">인터페이스</span><span class="sxs-lookup"><span data-stu-id="3d526-107">Interface</span></span>|<span data-ttu-id="3d526-108">설명</span><span class="sxs-lookup"><span data-stu-id="3d526-108">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="3d526-109">클라이언트 프로세스에서 프록시를 만들고, 초기화 하 고, 관리 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d526-109">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d526-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d526-110">Requirements</span></span>  

 <span data-ttu-id="3d526-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d526-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d526-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3d526-112">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="3d526-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d526-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3d526-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d526-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d526-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d526-115">See also</span></span>

- [<span data-ttu-id="3d526-116">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="3d526-116">Hosting Coclasses</span></span>](hosting-coclasses.md)
