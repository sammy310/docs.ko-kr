---
description: '자세히 알아보기: IGCHost:: SetVirtualMemLimit 메서드'
title: IGCHost::SetVirtualMemLimit 메서드
ms.date: 03/30/2017
api_name:
- IGCHost.SetVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetVirtualMemLimit
helpviewer_keywords:
- IGCHost::SetVirtualMemLimit method [.NET Framework hosting]
- SetVirtualMemLimit method [.NET Framework hosting]
ms.assetid: c7e7c2d0-e58c-4650-b40c-47b2be2cda45
topic_type:
- apiref
ms.openlocfilehash: 62cd9e2d84e51f0544e464bdbf49c50af8086546
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709440"
---
# <a name="igchostsetvirtualmemlimit-method"></a><span data-ttu-id="ff160-103">IGCHost::SetVirtualMemLimit 메서드</span><span class="sxs-lookup"><span data-stu-id="ff160-103">IGCHost::SetVirtualMemLimit Method</span></span>

<span data-ttu-id="ff160-104">런타임 가상 메모리의 최대 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff160-104">Sets the maximum size of the runtime's virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff160-105">구문</span><span class="sxs-lookup"><span data-stu-id="ff160-105">Syntax</span></span>  
  
```cpp  
HRESULT SetVirtualMemLimit (  
    [in] SIZE_T sztMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff160-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ff160-106">Parameters</span></span>  

 `sztMaxVirtualMemMB`  
 <span data-ttu-id="ff160-107">진행 런타임 가상 메모리의 최대 크기 (메가바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="ff160-107">[in] The maximum size, in megabytes, of the runtime's virtual memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff160-108">설명</span><span class="sxs-lookup"><span data-stu-id="ff160-108">Remarks</span></span>  

 <span data-ttu-id="ff160-109">런타임의 가상 메모리의 최대 크기를 동적으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff160-109">The maximum size of the runtime's virtual memory can be changed dynamically.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff160-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ff160-110">Requirements</span></span>  

 <span data-ttu-id="ff160-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff160-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff160-112">**헤더:** GCHost, GCHost</span><span class="sxs-lookup"><span data-stu-id="ff160-112">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="ff160-113">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff160-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ff160-114">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff160-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff160-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff160-115">See also</span></span>

- [<span data-ttu-id="ff160-116">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ff160-116">IGCHost Interface</span></span>](igchost-interface.md)
