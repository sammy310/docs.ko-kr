---
title: IApartmentCallback 인터페이스
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
ms.openlocfilehash: 4424509c16dd1d9f83db117ae7343fa03995297e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126908"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="cd0c0-102">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd0c0-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="cd0c0-103">아파트 내에서 콜백을 만드는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="cd0c0-104">*아파트* 는 동일한 스레드 액세스 요구 사항을 공유 하는 개체에 대 한 프로세스 내의 논리적 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd0c0-105">메서드</span><span class="sxs-lookup"><span data-stu-id="cd0c0-105">Methods</span></span>  
  
|<span data-ttu-id="cd0c0-106">메서드</span><span class="sxs-lookup"><span data-stu-id="cd0c0-106">Method</span></span>|<span data-ttu-id="cd0c0-107">설명</span><span class="sxs-lookup"><span data-stu-id="cd0c0-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="cd0c0-108">DoCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="cd0c0-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="cd0c0-109">아파트 내에서 지정 된 함수를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd0c0-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd0c0-110">Requirements</span></span>  
 <span data-ttu-id="cd0c0-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd0c0-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="cd0c0-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cd0c0-113">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cd0c0-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd0c0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd0c0-115">참조</span><span class="sxs-lookup"><span data-stu-id="cd0c0-115">See also</span></span>

- [<span data-ttu-id="cd0c0-116">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd0c0-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
