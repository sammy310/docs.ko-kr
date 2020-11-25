---
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
ms.openlocfilehash: 4824fcfc53bae6c81760a23f76e83fb8ae7efd79
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715812"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="f38de-102">ICorConfiguration::SetGCHostControl 메서드</span><span class="sxs-lookup"><span data-stu-id="f38de-102">ICorConfiguration::SetGCHostControl Method</span></span>

<span data-ttu-id="f38de-103">가비지 수집기에서 가상 메모리의 한도를 변경 하는 호스트를 요청 하는 데 사용할 콜백 인터페이스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f38de-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f38de-104">구문</span><span class="sxs-lookup"><span data-stu-id="f38de-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f38de-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f38de-105">Parameters</span></span>  

 `pGCHostControl`  
 <span data-ttu-id="f38de-106">진행 가비지 수집기가 가상 메모리의 한도를 변경 하도록 호스트를 요청할 수 있도록 하는 [IGCHostControl](igchostcontrol-interface.md) 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f38de-106">[in] A pointer to an [IGCHostControl](igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f38de-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f38de-107">Requirements</span></span>  

 <span data-ttu-id="f38de-108">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f38de-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f38de-109">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="f38de-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f38de-110">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f38de-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f38de-111">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f38de-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f38de-112">참조</span><span class="sxs-lookup"><span data-stu-id="f38de-112">See also</span></span>

- [<span data-ttu-id="f38de-113">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f38de-113">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)
