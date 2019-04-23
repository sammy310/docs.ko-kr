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
ms.openlocfilehash: 0845c4d493cb3c750931a0ae2ad92b628a255c0c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202718"
---
# <a name="couninitializecor-function"></a><span data-ttu-id="31554-102">CoUninitializeCor 함수</span><span class="sxs-lookup"><span data-stu-id="31554-102">CoUninitializeCor Function</span></span>
<span data-ttu-id="31554-103">`CoUninitializeCor`는 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31554-103">`CoUninitializeCor` is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31554-104">구문</span><span class="sxs-lookup"><span data-stu-id="31554-104">Syntax</span></span>  
  
```  
STDAPI_(void) CoUninitializeCor(void);  
```  
  
## <a name="remarks"></a><span data-ttu-id="31554-105">설명</span><span class="sxs-lookup"><span data-stu-id="31554-105">Remarks</span></span>  
 <span data-ttu-id="31554-106">공용 언어 런타임 프로세스에서 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="31554-106">The common language runtime cannot be unloaded from a process.</span></span> <span data-ttu-id="31554-107">런타임에 실행 중인 프로세스에서 완전히 제거 하려면 해당 프로세스를 종료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31554-107">To completely remove the runtime from a running process, you must shut down that process.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31554-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="31554-108">See also</span></span>

- [<span data-ttu-id="31554-109">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="31554-109">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
