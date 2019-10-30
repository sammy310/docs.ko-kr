---
title: CoUninitializeEE 함수
ms.date: 03/30/2017
api_name:
- CoUninitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoUninitializeEE
helpviewer_keywords:
- CoUninitializeEE function [.NET Framework hosting]
ms.assetid: 5f5a311a-839a-465f-89d9-ff1c74da9736
topic_type:
- apiref
ms.openlocfilehash: 3531cfc0815c3f8a9479e35b2df60b2825801b39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136858"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="2fe87-102">CoUninitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="2fe87-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="2fe87-103">`CoUninitializeEE`는 사용 되지 않으며 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe87-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fe87-104">구문</span><span class="sxs-lookup"><span data-stu-id="2fe87-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="2fe87-105">주의</span><span class="sxs-lookup"><span data-stu-id="2fe87-105">Remarks</span></span>  
 <span data-ttu-id="2fe87-106">프로세스에서 공용 언어 런타임 실행 엔진을 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fe87-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="2fe87-107">실행 엔진을 종료 하려면 [Corexitprocess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fe87-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe87-108">참조</span><span class="sxs-lookup"><span data-stu-id="2fe87-108">See also</span></span>

- [<span data-ttu-id="2fe87-109">CoInitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="2fe87-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="2fe87-110">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="2fe87-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
