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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b2b7b89c73b59f4f735369659daabb6a8f88300
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779092"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="f6018-102">CoInitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="f6018-102">CoInitializeCor Function</span></span>
<span data-ttu-id="f6018-103">`CoInitializeCor`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f6018-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6018-104">구문</span><span class="sxs-lookup"><span data-stu-id="f6018-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="f6018-105">설명</span><span class="sxs-lookup"><span data-stu-id="f6018-105">Remarks</span></span>  
 <span data-ttu-id="f6018-106">공용 언어 런타임 초기화를 사용 하 여 [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) 하거나 [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f6018-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6018-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f6018-107">Requirements</span></span>  
 <span data-ttu-id="f6018-108">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f6018-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6018-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="f6018-109">See also</span></span>

- [<span data-ttu-id="f6018-110">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="f6018-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
