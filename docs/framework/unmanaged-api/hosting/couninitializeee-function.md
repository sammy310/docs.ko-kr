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
ms.openlocfilehash: 7b3712b4cb66facc105a03d7bfad235f09339056
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193007"
---
# <a name="couninitializeee-function"></a><span data-ttu-id="bcea5-102">CoUninitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="bcea5-102">CoUninitializeEE Function</span></span>
`CoUninitializeEE` <span data-ttu-id="bcea5-103">사용 되지 않습니다 하 고 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bcea5-103">is obsolete and provides no functionality.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcea5-104">구문</span><span class="sxs-lookup"><span data-stu-id="bcea5-104">Syntax</span></span>  
  
```  
void CoUninitializeEE (  
    BOOL fFlags  
);  
```  
  
## <a name="remarks"></a><span data-ttu-id="bcea5-105">설명</span><span class="sxs-lookup"><span data-stu-id="bcea5-105">Remarks</span></span>  
 <span data-ttu-id="bcea5-106">공용 언어 런타임 실행 엔진 프로세스에서 언로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bcea5-106">The common language runtime execution engine cannot be unloaded from a process.</span></span> <span data-ttu-id="bcea5-107">실행 엔진 호출을 종료 하려면 [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bcea5-107">To shut down the execution engine call [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcea5-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="bcea5-108">See also</span></span>

- [<span data-ttu-id="bcea5-109">CoInitializeEE 함수</span><span class="sxs-lookup"><span data-stu-id="bcea5-109">CoInitializeEE Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md)
- [<span data-ttu-id="bcea5-110">메타데이터 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="bcea5-110">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
