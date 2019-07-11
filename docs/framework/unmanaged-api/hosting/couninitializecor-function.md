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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e3ce0b9a40d5375f563662d73964d28724209dcd
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758300"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="f7e0e-102">CoUninitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="f7e0e-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="f7e0e-103">`CoUninitializeCor`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e0e-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7e0e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f7e0e-104">Syntax</span></span>  
  
```cpp  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="f7e0e-105">설명</span><span class="sxs-lookup"><span data-stu-id="f7e0e-105">Remarks</span></span>  
 <span data-ttu-id="f7e0e-106">공용 언어 런타임 프로세스에서 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f7e0e-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="f7e0e-107">런타임에 실행 중인 프로세스에서 완전히 제거 하려면 해당 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7e0e-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e0e-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="f7e0e-108">See also</span></span>

- [<span data-ttu-id="f7e0e-109">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="f7e0e-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
