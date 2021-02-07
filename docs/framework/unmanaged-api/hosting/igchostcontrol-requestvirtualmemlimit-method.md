---
description: '자세히 알아보기: IGCHostControl:: RequestVirtualMemLimit 메서드'
title: IGCHostControl::RequestVirtualMemLimit 메서드
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
ms.openlocfilehash: b0ee22671b63be0ed0d23ebb103a6a5a7ca9f2b9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99709401"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="9e811-103">IGCHostControl::RequestVirtualMemLimit 메서드</span><span class="sxs-lookup"><span data-stu-id="9e811-103">IGCHostControl::RequestVirtualMemLimit Method</span></span>

<span data-ttu-id="9e811-104">가상 메모리의 한도를 변경 하도록 호스트에 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e811-104">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e811-105">구문</span><span class="sxs-lookup"><span data-stu-id="9e811-105">Syntax</span></span>  
  
```cpp  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e811-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e811-106">Parameters</span></span>  

 `sztMaxVirtualMemMB`  
 <span data-ttu-id="9e811-107">진행 할당 될 요청 된 메모리 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9e811-107">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="9e811-108">[in, out] 할당 된 메모리의 실제 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e811-108">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e811-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e811-109">Requirements</span></span>  

 <span data-ttu-id="9e811-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e811-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e811-111">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="9e811-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9e811-112">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9e811-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9e811-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e811-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e811-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9e811-114">See also</span></span>

- [<span data-ttu-id="9e811-115">IGCHostControl 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e811-115">IGCHostControl Interface</span></span>](igchostcontrol-interface.md)
