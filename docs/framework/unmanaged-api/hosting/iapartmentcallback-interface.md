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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db933716cc0602ecda5da8a72726408ae4910179
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129807"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="8d2be-102">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d2be-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="8d2be-103">아파트 내의 콜백을 수행 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2be-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="8d2be-104">*아파트* 공유 동일한 스레드 액세스를 요구 하는 개체에 대 한 프로세스 내에서 논리적 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="8d2be-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d2be-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8d2be-105">Methods</span></span>  
  
|<span data-ttu-id="8d2be-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8d2be-106">Method</span></span>|<span data-ttu-id="8d2be-107">설명</span><span class="sxs-lookup"><span data-stu-id="8d2be-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d2be-108">DoCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="8d2be-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="8d2be-109">아파트 내의 지정된 된 함수를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d2be-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d2be-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8d2be-110">Requirements</span></span>  
 <span data-ttu-id="8d2be-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8d2be-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d2be-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d2be-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d2be-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="8d2be-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d2be-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d2be-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d2be-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="8d2be-115">See also</span></span>

- [<span data-ttu-id="8d2be-116">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8d2be-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
