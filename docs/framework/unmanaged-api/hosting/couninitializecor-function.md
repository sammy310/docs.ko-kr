---
title: CoUninitializeCor 함수
ms.date: 03/30/2017
api_name:
- CoUninitializeCor
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeCor
helpviewer_keywords:
- CoUninitializeCor function [.NET Framework hosting]
ms.assetid: 50a95b8b-9766-470e-bb29-2c7ecddfd4a1
topic_type:
- apiref
ms.openlocfilehash: 8a8c2764398d737192190f91646d45f4edf3a0e4
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616480"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="69870-102">CoUninitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="69870-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="69870-103">`CoUninitializeCor`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69870-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69870-104">구문</span><span class="sxs-lookup"><span data-stu-id="69870-104">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="69870-105">설명</span><span class="sxs-lookup"><span data-stu-id="69870-105">Remarks</span></span>  
 <span data-ttu-id="69870-106">프로세스에서 공용 언어 런타임을 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69870-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="69870-107">실행 중인 프로세스에서 런타임을 완전히 제거 하려면 해당 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69870-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69870-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69870-108">See also</span></span>

- [<span data-ttu-id="69870-109">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="69870-109">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
