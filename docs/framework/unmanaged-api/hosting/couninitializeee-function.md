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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d05bc472711838236ed18b00ce808d022d9581dc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758211"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="cb15a-102">CoUninitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="cb15a-102">CoUninitializeEE Function</span></span>
<span data-ttu-id="cb15a-103">`CoUninitializeEE` 사용 되지 않습니다 하 고 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb15a-103">`CoUninitializeEE` is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb15a-104">구문</span><span class="sxs-lookup"><span data-stu-id="cb15a-104">Syntax</span></span>  
  
```cpp  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="cb15a-105">설명</span><span class="sxs-lookup"><span data-stu-id="cb15a-105">Remarks</span></span>  
 <span data-ttu-id="cb15a-106">공용 언어 런타임 실행 엔진 프로세스에서 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb15a-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="cb15a-107">실행 엔진 호출을 종료 하려면 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="cb15a-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb15a-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="cb15a-108">See also</span></span>

- [<span data-ttu-id="cb15a-109">CoInitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="cb15a-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="cb15a-110">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="cb15a-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
