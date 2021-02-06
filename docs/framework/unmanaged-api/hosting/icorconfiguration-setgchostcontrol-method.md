---
description: '자세히 알아보기: ICorConfiguration:: SetGCHostControl 메서드'
title: ICorConfiguration::SetGCHostControl 메서드
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
ms.openlocfilehash: 4d3d6e5e5275adf02f9d693234a5c8e77714fd03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636652"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="815cd-103">ICorConfiguration::SetGCHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="815cd-103">ICorConfiguration::SetGCHostControl Method</span></span>

<span data-ttu-id="815cd-104">가비지 수집기에서 가상 메모리의 한도를 변경 하는 호스트를 요청 하는 데 사용할 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="815cd-104">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="815cd-105">구문</span><span class="sxs-lookup"><span data-stu-id="815cd-105">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="815cd-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="815cd-106">Parameters</span></span>  

 `pGCHostControl`  
 <span data-ttu-id="815cd-107">진행 가비지 수집기가 가상 메모리의 한도를 변경 하도록 호스트를 요청할 수 있도록 하는 [IGCHostControl](igchostcontrol-interface.md) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="815cd-107">[in] A pointer to an [IGCHostControl](igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="815cd-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="815cd-108">Requirements</span></span>  

 <span data-ttu-id="815cd-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="815cd-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="815cd-110">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="815cd-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="815cd-111">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="815cd-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="815cd-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="815cd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="815cd-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="815cd-113">See also</span></span>

- [<span data-ttu-id="815cd-114">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="815cd-114">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
