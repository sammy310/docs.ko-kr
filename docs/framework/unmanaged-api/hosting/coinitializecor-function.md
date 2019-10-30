---
title: CoInitializeCor 함수
ms.date: 03/30/2017
api_name:
- CoInitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeCor
helpviewer_keywords:
- CoInitializeCor function [.NET Framework hosting]
ms.assetid: 9b9079fb-579e-4141-b3f0-791072dd40dc
topic_type:
- apiref
ms.openlocfilehash: e8d65e739504e01a7d11b37d1b34d7313b13a5e1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138331"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="0cf83-102">CoInitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="0cf83-102">CoInitializeCor Function</span></span>
<span data-ttu-id="0cf83-103">`CoInitializeCor`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0cf83-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cf83-104">구문</span><span class="sxs-lookup"><span data-stu-id="0cf83-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="0cf83-105">주의</span><span class="sxs-lookup"><span data-stu-id="0cf83-105">Remarks</span></span>  
 <span data-ttu-id="0cf83-106">공용 언어 런타임을 초기화 하려면 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cf83-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cf83-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0cf83-107">Requirements</span></span>  
 <span data-ttu-id="0cf83-108">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="0cf83-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cf83-109">참조</span><span class="sxs-lookup"><span data-stu-id="0cf83-109">See also</span></span>

- [<span data-ttu-id="0cf83-110">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="0cf83-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
