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
ms.openlocfilehash: fbf501d906ecc0bf55719fa33d1af2d4db1cc2ef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617098"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="f561c-102">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f561c-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="f561c-103">아파트 내에서 콜백을 만드는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f561c-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="f561c-104">*아파트* 는 동일한 스레드 액세스 요구 사항을 공유 하는 개체에 대 한 프로세스 내의 논리적 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="f561c-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f561c-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f561c-105">Methods</span></span>  
  
|<span data-ttu-id="f561c-106">메서드</span><span class="sxs-lookup"><span data-stu-id="f561c-106">Method</span></span>|<span data-ttu-id="f561c-107">설명</span><span class="sxs-lookup"><span data-stu-id="f561c-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f561c-108">DoCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="f561c-108">DoCallback Method</span></span>](iapartmentcallback-docallback-method.md)|<span data-ttu-id="f561c-109">아파트 내에서 지정 된 함수를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f561c-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f561c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f561c-110">Requirements</span></span>  
 <span data-ttu-id="f561c-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f561c-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f561c-112">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f561c-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f561c-113">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f561c-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f561c-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f561c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f561c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f561c-115">See also</span></span>

- [<span data-ttu-id="f561c-116">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f561c-116">Hosting Interfaces</span></span>](hosting-interfaces.md)
