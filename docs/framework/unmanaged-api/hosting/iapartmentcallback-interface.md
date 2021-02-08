---
description: '자세히 알아보기: IApartmentCallback 인터페이스'
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
ms.openlocfilehash: ddf99b1d926bd2d9765b936143785a975ea378a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785140"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="3112d-103">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3112d-103">IApartmentCallback Interface</span></span>

<span data-ttu-id="3112d-104">아파트 내에서 콜백을 만드는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3112d-104">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="3112d-105">*아파트* 는 동일한 스레드 액세스 요구 사항을 공유 하는 개체에 대 한 프로세스 내의 논리적 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="3112d-105">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3112d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="3112d-106">Methods</span></span>  
  
|<span data-ttu-id="3112d-107">메서드</span><span class="sxs-lookup"><span data-stu-id="3112d-107">Method</span></span>|<span data-ttu-id="3112d-108">설명</span><span class="sxs-lookup"><span data-stu-id="3112d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3112d-109">DoCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="3112d-109">DoCallback Method</span></span>](iapartmentcallback-docallback-method.md)|<span data-ttu-id="3112d-110">아파트 내에서 지정 된 함수를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3112d-110">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3112d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3112d-111">Requirements</span></span>  

 <span data-ttu-id="3112d-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3112d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3112d-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="3112d-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3112d-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3112d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3112d-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3112d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3112d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3112d-116">See also</span></span>

- [<span data-ttu-id="3112d-117">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3112d-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
