---
description: '자세히 알아보기: CoInitializeCor 함수'
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
ms.openlocfilehash: e1db9914cce8a92cecf78123a2e247d75ec74acf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799852"
---
# <a name="coinitializecor-function"></a><span data-ttu-id="76b3e-103">CoInitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="76b3e-103">CoInitializeCor Function</span></span>

<span data-ttu-id="76b3e-104">`CoInitializeCor`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="76b3e-104">`CoInitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76b3e-105">구문</span><span class="sxs-lookup"><span data-stu-id="76b3e-105">Syntax</span></span>  
  
```cpp  
STDAPI CoInitializeCor (  
    DWORD fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="76b3e-106">설명</span><span class="sxs-lookup"><span data-stu-id="76b3e-106">Remarks</span></span>  

 <span data-ttu-id="76b3e-107">공용 언어 런타임을 초기화 하려면 [CorBindToRuntimeEx](corbindtoruntimeex-function.md) 또는 [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md)중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="76b3e-107">To initialize the common language runtime, use either [CorBindToRuntimeEx](corbindtoruntimeex-function.md) or [CorBindToCurrentRuntime](corbindtocurrentruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76b3e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="76b3e-108">Requirements</span></span>  

 <span data-ttu-id="76b3e-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="76b3e-109">**Header:** Cor.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76b3e-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76b3e-110">See also</span></span>

- [<span data-ttu-id="76b3e-111">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="76b3e-111">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
