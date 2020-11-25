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
ms.openlocfilehash: 9d077d5c5a414568b5643cad0171e101d7bb06f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731711"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="5fe6c-102">CoInitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="5fe6c-102">CoInitializeCor Function</span></span>

<span data-ttu-id="5fe6c-103">`CoInitializeCor`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fe6c-103">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fe6c-104">구문</span><span class="sxs-lookup"><span data-stu-id="5fe6c-104">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="5fe6c-105">설명</span><span class="sxs-lookup"><span data-stu-id="5fe6c-105">Remarks</span></span>  

 <span data-ttu-id="5fe6c-106">공용 언어 런타임을 초기화 하려면 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fe6c-106">To initialize the common language runtime, use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fe6c-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5fe6c-107">Requirements</span></span>  

 <span data-ttu-id="5fe6c-108">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="5fe6c-108">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fe6c-109">참조</span><span class="sxs-lookup"><span data-stu-id="5fe6c-109">See also</span></span>

- [<span data-ttu-id="5fe6c-110">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="5fe6c-110">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
